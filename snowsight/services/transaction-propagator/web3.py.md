# web3.py

```python
import requests
import json
from web3 import Web3
from eth_account.signers.local import LocalAccount

# get web3 provider
web3 = Web3(Web3.IPCProvider())

# get private key from the wallet you paid with
with open(KEY_FILE_PATH) as keyfile:
    private_key = web3.eth.account.decrypt(keyfile.read(), 'key_file_pw')
    
# generate account from private key
BASE_ACCOUNT_FROM: LocalAccount = Account.from_key(private_key)

# sign key string with your signing account wallet
message = "Sign this message to authenticate your wallet with Snowsight."
encoded_message = encode_defunct(text=message)
signed_message = web3.eth.account.sign_message(encoded_message, private_key=private_key)

# create and sign transaction
tx = {
        'from': Web3.toChecksumAddress(BASE_ACCOUNT_FROM.address), 'nonce': web3.eth.getTransactionCount(BASE_ACCOUNT_FROM.address), 'value': 0,
        'to': Web3.toChecksumAddress(BASE_ACCOUNT_FROM.address),
        'gas': int(23000 + 3000),
        'chainId': 43114
    }
signed = web3.eth.account.sign_transaction(tx, private_key)

# send 'signed_key' and 'raw_tx'
packet = {'signed_key': signed_message.signature.hex(), 'raw_tx': signed.rawTransaction.hex()}
r = requests.post('http://tx-propagator.snowsight.chainsight.dev:8081', data=json.dumps(packet))
```
