# Mempool Stream

The Mempool Stream aggregates all pending transactions from Snowsight's validator node network and streamlines them into one source for users. &#x20;

Upon connecting to Snowsight, users must authenticate the connection by sending their `'signed_key'`  to the server.  After this, Snowsight will authenticate the connection and begin streaming pending transactions.

The user has the option whether to receive a notification when pending transactions are finalized into a real block by passing a true or false flag in the `'include_finalized'` field when authenticating the connection .  This allows the user to measure the amount of time a transaction was in the mempool before being finalized into a block.&#x20;

