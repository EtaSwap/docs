# Overview

EtaBridge is trustless cross-chain liquidity bridge, designed to simplify and streamline token transfers across multiple chains.

With EtaBridge, users can transfer **$USDC** between supported chains in a single transaction—eliminating the need for wrapping or unwrapping tokens. The platform is designed to be **simple**, **fast**, **secure**, and **cost-effective**.

**Key Features:**

* **Open-Source & Trustless**: EtaBridge operates without a centralised authority or a fixed group of validators. All core logic is implemented in publicly verified and accessible smart contracts.
* **Decentralized Validation**: Cross-chain transactions are validated using the [**LayerZero**](https://layerzero.network/) protocol, which allows anyone to become a validator. Currently we use validators from **BCW**, **LayerZero**, and **Horizen Labs**, expanding this list in future as more validators appears.
* **Single transaction.** With classic bridges you have to do several steps, including buying wrapped tokens, which leads to looses on price impact. Unlike classic bridges EtaBridge operates based on native token liquidity stored on both ends, where user put tokens to the treasury on the source chain, we verify transaction and send him tokens from the treasury on destination chain.
