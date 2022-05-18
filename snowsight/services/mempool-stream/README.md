# Mempool Stream

Mempool data on Avalanche C-Chain is only shared amongst validator nodes.  When any node receives a pending transaction, it is randomly gossiped to ten other validator nodes in its peer list regardless of stake.\
\
The Mempool Stream solves three problems for users:

1. Technical expense barrier: Running a validator is technically difficult and time consuming
2. Capital expense barrier: Each validator node requires 2000 AVAX to be staked
3. Infrastructure expense barrier: A single validator node does not provide an accurate view of the mempool due to the present pending transaction gossiping algorithm

The Mempool Stream solves these problems by aggregating all pending transactions from Snowsight's validator node network and streamlines them into one source for users. &#x20;

Upon connecting to Snowsight, users must authenticate the connection by sending their `'signed_key'`  to the server.  After this, Snowsight will authenticate the connection and begin streaming pending transactions.

The user has the option whether to receive a notification when pending transactions are finalized into a real block by passing a true or false flag in the `'include_finalized'` field when authenticating the connection .  This allows the user to measure the amount of time a transaction was in the mempool before being finalized into a block.&#x20;

