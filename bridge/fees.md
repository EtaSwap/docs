# Fees

EtaBridge fee is **0.3%**, which is taken in source coin. Which means when user is sending 100 USDC from chain A to chain B - he will receive 99.7 USDC on chain B.

Network fees are including:

1. Estimated gas cost for sending transaction on source chain
2. LayerZero Validators and Executor fees (details: [https://docs.layerzero.network/v2/developers/evm/technical-reference/tx-pricing](https://docs.layerzero.network/v2/developers/evm/technical-reference/tx-pricing)).
3. Estimated gas cost for sending transaction on destination chain

Network fees can vary according to blockchains load at the moment of transaction, but in general they are very low. Network fees are taken in root token of the source chain, e.g. if you are sending USDC from Avalanche to Base - network fees will be taken on the source chain in AVAX token.

