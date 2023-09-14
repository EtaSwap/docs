# ABI and interaction

All smart contracts code are open source and can be found on official [github](https://github.com/EtaSwap).

Full smart contracts ABI can be found by next links:

1. [BaseOracle](https://github.com/EtaSwap/etaswap-smart-contracts/blob/master/artifacts/contracts/oracles/OracleBase.sol/OracleBase.json)
2. [Exchange](https://github.com/EtaSwap/etaswap-smart-contracts/blob/master/artifacts/contracts/Exchange.sol/Exchange.json)
3. [SaucerSwapAdapter](https://github.com/EtaSwap/etaswap-smart-contracts/blob/master/artifacts/contracts/adapters/SaucerSwapAdapter.sol/SaucerSwapAdapter.json)
4. [PangolinAdapter](https://github.com/EtaSwap/etaswap-smart-contracts/blob/master/artifacts/contracts/adapters/PangolinAdapter.sol/PangolinAdapter.json)
5. [HeliSwapAdapter](https://github.com/EtaSwap/etaswap-smart-contracts/blob/master/artifacts/contracts/adapters/HeliSwapAdapter.sol/HeliSwapAdapter.json)

{% hint style="info" %}
The integrity and authenticity of source code can be verified by comparing contract bytecode on hashscan with ABI.bytecode parameter in repository. Also you can build project by yourself with the same hardhat settings and result bytecode should be the same as on hashscan.
{% endhint %}

In next section we will describe main interaction ways to EtaSwap smart contracts.
