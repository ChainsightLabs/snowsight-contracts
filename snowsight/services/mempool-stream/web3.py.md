---
description: python
---

# web3.py

```python
import websocket
from web3 import Web3
from eth_account.signers.local import LocalAccount
from eth_account.account import Account
from eth_account.messages import encode_defunct
import json

# get private key from the wallet you paid with
with open(KEY_FILE_PATH) as keyfile:
    priv_key = web3.eth.account.decrypt(keyfile.read(), 'key_file_pw')

# sign key string with your signing account wallet
msg = "Sign this message to authenticate your wallet with Snowsight."
encoded_msg = encode_defunct(text=message)
signed_msg = web3.eth.account.sign_message(encoded_msg, priv_key)

# make websocket connection and send 'signed_key'
ws = websocket.create_connection("ws://mempool-stream.snowsight.chainsight.dev:8589")
packet = {'signed_key': signed_message.signature.hex(), 'include_finalized': True}
ws.send(json.dumps(packet))

# on success, first message will contain {'status': 'authenticated'}
resp = json.loads(ws.recv())
if resp['status'] == 'authenticated': {
    # < do shadowy super coder stuff here >
}
```
