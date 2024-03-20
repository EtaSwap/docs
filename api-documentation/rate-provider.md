# Rate provider

{% hint style="info" %}
Swagger documentation is available by the link: [https://api.etaswap.com/v1/docs](https://api.etaswap.com/v1/docs)
{% endhint %}

EtaSwap rate provider API section allows to fetch current swap rates for provided token pair from all DEXes in Hedera ecosystem (SaucerSwap, HSuite, HeliSwap, Pangolin).

To get swap rates you need to execute such kind of `GET` request:

```sh
curl -X 'GET' \
  'https://api.etaswap.com/v1/rates?tokenFrom=0x0000000000000000000000000000000000000000&tokenTo=0x000000000000000000000000000000000006f89a&amount=100000000&isReverse=false' \
  -H 'accept: application/json'
```

Query parameters:

* `tokenFrom` - EVM address of token which you want to exchange from. In case if you want to exchange root Hedera token (HBAR) - you need to provide zero address: `0x0000000000000000000000000000000000000000`
* `tokenTo` - EVM address of token which you want to exchange to. In case if you want to exchange root Hedera token (HBAR) - you need to provide zero address: `0x0000000000000000000000000000000000000000`
* `amount` - amount of tokens to send/receive (depending on `isReverse` parameter) in minimum token units
* `isReverse` - boolean flag showing swap type:
  1. false - to exchange specified `amount` of `tokenFrom` to maximum of `tokenTo`
  2. true - to exchange minimum `tokenFrom` to specified `amount` of `tokenTo`

Response - is list of proposed output amount by different liquidity providers. This list is ordered by profitability (max. profitable value comes first).

Response example:

```json
[{
    "transactionType": "SWAP",
    "aggregatorId": "SaucerSwapV2",
    "amountFrom": "100000000",
    "amountTo": "105595",
    "path": "0x0000000000000000000000000000000000163b5a0005dc000000000000000000000000000000000006f89a",
    "route": [
      "0x0000000000000000000000000000000000163b5a",
      "0x000000000000000000000000000000000006f89a"
    ],
    "gasEstimate": 277000
  },
  {
    "transactionType": "INDIRECT_SWAP",
    "aggregatorId": "HSuite",
    "amountFrom": "100000000",
    "amountTo": "103957",
    "gasEstimate": 0,
    "extension": {
      "hSuiteFee": 2
    },
    "route": [
      "0x0000000000000000000000000000000000000000",
      "0x00000000000000000000000000000000000c01f3",
      "0x000000000000000000000000000000000006f89a"
    ]
}]
```

* `transactionType` - indicator of type of the transaction. Options: "SWAP" or "INDIRECT\_SWAP". In future list of options will expand as we implement new algorithms.
* `aggregatorId` - identifier of liquility provider
* `amountFrom` - amount of `tokenFrom` to send in minimum token units
* `amountTo` - amount of `tokenTo` to receive in minimum token units
* `gasEstimate` - amount of gas, that should be attached to[ ](../smart-contracts/smart-contract-addresses.md)[Exchange](../smart-contracts/smart-contract-addresses.md) contract call. Not provided for smart-contract-less exchanges (such as HSuite)
* `path` - internal parameter that should be send to[ ](../smart-contracts/smart-contract-addresses.md)[Exchange](../smart-contracts/smart-contract-addresses.md) contract call to process exchange
* `route` - exchange route (list of array of token addresses in EVM format)
* `extension` - optional property, that store additional exchange information
