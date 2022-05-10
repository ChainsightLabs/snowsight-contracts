---
description: javascript
---

# ethers.js

```javascript
const provider = new ethers.providers.StaticJsonRpcProvider(AVAX_RPC_URL);
const wallet = new ethers.Wallet(PRIVATE_KEY, provider);

// Sign in
const key = "Sign this message to authenticate your wallet with Snowsight.";
const signed_key = await wallet.signMessage(key);

// Open websocket
const ws = new WebSocket("ws://mempool-stream.snowsight.chainsight.dev:8589");

ws.on("open", () => {
  console.log("Ws::open");
  ws.send(JSON.stringify({ signed_key: signed_key, include_finalized: true }));
});

ws.on("message", async (data: any) => {
  if (data.status === "authenticated") {
    console.log("Ws::authenticated");
  }
  console.log("received: %s", data);
});
```
