# Settings

{% hint style="info" %}
Swagger documentation is available by the link: [https://api.etaswap.com/v1/docs](https://api.etaswap.com/v1/docs)
{% endhint %}

`GET` network request returns current application network (`mainnet` or `testnet`).

```bash
curl -X 'GET' \
  'https://api.etaswap.com/v1/settings/network' \
  -H 'accept: application/json'
```

Response example:

```json
{
  "network": "mainnet"
}
```



`GET` tokens request returns list of tokens, supported by EtaSwap (in EVM format).

```bash
curl -X 'GET' \
  'https://api.etaswap.com/v1/settings/tokens' \
  -H 'accept: application/json'
```

Response example:

```json
[
  "0x000000000000000000000000000000000001f385",
  "0x00000000000000000000000000000000000244da",
  "0x00000000000000000000000000000000000331d8",
  "0x000000000000000000000000000000000006f89a",
  "0x0000000000000000000000000000000000083e9e",
  "0x000000000000000000000000000000000008437c",
  "0x0000000000000000000000000000000000098779",
]
```
