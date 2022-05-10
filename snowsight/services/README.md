# Services

Snowsight provides two different services:

1. Mempool Stream
   * Provides users with a websocket interface to receive pending (yet to be finalized) transactions
   * Access to the mempool allows for same-block arbitrage, backrunning, and other MEV strategies to be performed
2. Transaction Propagator
   * Provides users with a low-latency transaction relay that propagates transactions to validator nodes much faster than any public RPC
   * Access to the propagator results in users being able to participate in [Priority Gas Auctions](https://www.mev.wiki/terms-and-concepts/priority-gas-auctions) that would otherwise be unwinnable when relying on public RPCs alone
