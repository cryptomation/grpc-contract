# GRPC contract for interaction with cryptomation.com

## What is it?
It is grpc contract for getting crypto data from different blockchain network (etherium, near, polygon, tron) in your web3 apps.

## When I find last version?
You could load it here:

```bash
wget https://raw.githubusercontent.com/cryptomation/grpc-contract/main/universal-api.proto
```

## How to use it?
* First you need to create api keys for needed network here: 👉 [CryptoMation/Console](https://console.cryptomation.com)
* Download proto file from this repository: 👉 [CryptoMation/grpc-contract](https://raw.githubusercontent.com/cryptomation/grpc-contract/main/universal-api.proto)
* Compile proto file with grpc compiler: 👉 `protoc --go_out=plugins=grpc:. universal-api.proto`

## What methods are available?
* `getBalance` - get balance of account in the network
* `getTransactions` - get transactions of account in the network

## Simple example how get transactions of account in the tron/near/etherium/polygon network:

⚠ Possible values for network param: `near`, `near-testnet`, `near-mainnet`, `etherium`, `polygon`, `tron`

⚠ You must have grpcurl for running this example

```bash
grpcurl -plaintext -d '{"api_key": "insert_you_api_key", "network":"polygon", "address": "0xdec0de7e6ed3ee7bb3a2c0baae7827d101d1ec20"}' localhost:13000 com.cryptomation.universal.api.v1.grpc.UniversalCryptoApi/getTransactions
```

## Simple example how get balance of account in the tron/near/etherium/polygon network:

⚠ Possible values for network param: `near`, `near-testnet`, `near-mainnet`, `etherium`, `polygon`, `tron`

⚠ You must have grpcurl for running this example

```bash
grpcurl -plaintext -d '{"api_key": "insert_you_api_key", "network":"polygon", "address": "0xdec0de7e6ed3ee7bb3a2c0baae7827d101d1ec20"}' localhost:13000 com.cryptomation.universal.api.v1.grpc.UniversalCryptoApi/getBalance
```
