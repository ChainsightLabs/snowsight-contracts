# Transaction Propagator

The Transaction Propagator is an HTTP endpoint that users may leverage to propagate their transactions faster through Avalanche C-Chain.  Any transactions recevied by the Transaction Propagator are immediately relayed throughout Snowsight's validator node network, resulting in  much better performance than a public RPC.

Similar to the Mempool Stream, users must authenticate by sending their `'signed_key'` in the same payload that contains their transaction.&#x20;

