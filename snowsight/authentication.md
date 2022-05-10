# Authentication

Upon connection to the service, Snowsight expects a message to be sent in JSON format with a key-value pair named 'signed\_key' containing a signed message in [EIP-191 compatible format](https://eips.ethereum.org/EIPS/eip-191) from the wallet that paid for access to Snowsight.

Example signed key:

```json
"signed_key": "0x65233a17f581aa0404f1867560d3a2ee1a654596fc71c6c4f3706d1bd9b7da6873a3f0b153f7da5d55e04af9c8e67003d178134fb28c2aa8695f9c0227fe13a21b"
```

This allows Snowsight to confirm that your external address has paid the appropriate amount of AVAX to accept the connection.

The Services section contains code snippets of how to generate the signed key for your desired service.
