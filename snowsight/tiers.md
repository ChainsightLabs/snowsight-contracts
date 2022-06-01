# Tiers

Snowsight provides three tiers available to users:

1. Premium Tier\*
   * Lowest latency connection to mempool, with up to 3 concurrent websocket connections
   * Highest priority access for institutional users
   * **𝛿** (pending -> finalized): \~2.1 s
   * Per-block pending transaction coverage: >95%
2. Standard Tier
   * Generic connection to mempool, lower priority than Premium Tier
   * **𝛿** (pending -> finalized): \~900 ms
   * Per-block pending transaction coverage: \~75%
3. Trial Tier
   * No cost connection to mempool
   * Lowest priority access, mempool access can be delayed and no pending transaction coverage guarantees

\*only Premium Tier is eligible to use the Transaction Propagator&#x20;
