# Oracles

The oracles contracts for all liquidity providers in EtaSwap inherited from `BaseOracle.sol` and all of them implement next interface:

```solidity
function getRate(IERC20 srcToken, IERC20 dstToken) external view returns (uint256 rate, uint256 weight);
```

To retrieve the rate of the particular DEX - you should call getRate function of corresponding Oracle smart contract. List of oracle addresses can be found [here](../smart-contract-addresses.md).

Return values is `srcToken` to `dstToken` rate and weight, calculated as square root of multiplication `srcToken` and `dstToken` balances.&#x20;
