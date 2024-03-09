# Exchange

Exchange contract is factory that processing user swap with particular exchange adapter. In general exchange call looks like:

<img src="../../.gitbook/assets/file.excalidraw.svg" alt="" class="gitbook-drawing">

Each adapters has it's own realization of swap (depends on DEX interfaces) but all of them implement the same interface for factory.

To swap tokens through factory we should call method `swap()` of Exchange contract:

```solidity
function swap(
    string calldata aggregatorId,
    bytes calldata path,
    uint256 amountFrom,
    uint256 amountTo,
    uint256 deadline,
    bool isTokenFromHBAR,
    bool feeOnTransfer
) external payable whenNotPaused nonReentrant
```

Parameters:

*   `aggregatorId` - for now it's 4 possible options for this field:

    1. `SaucerSwapV1`
    2. `SaucerSwapV2`
    3. `Pangolin`
    4. `HeliSwap`

    Choose the one which DEX you want to use for swap.
* `path`special way encoded swap route. Could be different depending on particular provider. Value can be retrieved from API.
* `amountFrom` and `amountTo`. Amounts of tokens to swap in coins. Each token has different amount of decimals, for example if you want to swap 1 GRELF to your account, which has 8 decimals - you need to provide `amountFrom=100000000`.
* `deadline` - this is "rudiment" of porting DEXes from ethereum network, because on ethereum transactions can wait large amount of time before execution (with different gas strategy). On Hedera most of all transactions processed in 4 seconds. Value of this field should be 10 digits timestamp. Just make sure this timestamp > current date. For example on Javascript you can use this snippet to calculate `deadline`:

```javascript
const deadline = Math.floor(Date.now() / 1000) + 1000;
```

* `isTokenFromHBAR`. True if you swapping HBAR to something, otherwise false.
* `feeOnTransfer`. This parameter regulate which token to apply slippage. If you want to apply slippage to tokenTo (it means you swap exact amount of `tokenFrom` to variable amount of `tokenTo`) - you need to pass `false`, otherwise (it means you want to receive exact amount of `tokenTo` using variable amount of `tokenFrom` - pass `true`. If you want more explanation about AMM basics and slippage - proceed by this link: [https://academy.binance.com/en/articles/what-is-an-automated-market-maker-amm](https://academy.binance.com/en/articles/what-is-an-automated-market-maker-amm)



Also there is one more useful readonly function on Exchange smart-contract:

```solidity
function adapterFee(string calldata aggregatorId) external view returns (uint8 fee);
```

This function returns current EtaSwap fee for particular aggregator. Returned value dimension - is promille. For example if function return 1 - it means EtaSwap fee is 0.1%.
