# Fees explanation

Network gas for different kind of swaps (for current Uniswap-like DEX-es) takes around:



<table><thead><tr><th width="178">Token pair</th><th width="152.33333333333331">Gas for SaucerSwap V1</th><th>Gas for Pangolin</th><th>Gas for HeliSwap</th><th>Gas for HSuite</th></tr></thead><tbody><tr><td>ERC20 -> ERC20 swap</td><td>910000 Gas</td><td>910000 Gas</td><td>910000 Gas</td><td>N/A</td></tr><tr><td>HBAR -> ERC20 swap</td><td>260000 Gas</td><td>260000 Gas</td><td>255000 Gas</td><td>N/A</td></tr><tr><td>ERC20 -> HBAR swap</td><td>16800000 Gas</td><td>1680000 Gas</td><td>1300000 Gas</td><td>N/A</td></tr></tbody></table>

The third option (ERC20 -> HBAR) consumes more gas than others, because of high cost of burning WHBAR operation (inside exchange). However HeliSwap has different implementation of WHBAR then others, which leads to lower fee on WHBAR burning, so it consumes less amount of gas on ERC20 -> HBAR swaps.\
Additionally 1 and 3 operations require Approval transaction, which costs \~0.05 USD.

HSuite isn't working on smart-contract level, it utilizes Hedera Token Service (HTS) and doesn't need approval transaction as well.

Approx USD cost of swaps on the table below:

<table><thead><tr><th width="178">Token pair</th><th width="152.33333333333331">Fee for SaucerSwap V1</th><th>Fee for Pangolin</th><th>Fee for HeliSwap</th><th>Fee for HSuite</th></tr></thead><tbody><tr><td>ERC20 -> ERC20 swap</td><td>~0.0746 USD</td><td>~0.0746 USD</td><td>~0.0746 USD</td><td>~0.0016 USD</td></tr><tr><td>HBAR -> ERC20 swap</td><td>~0.0213 USD</td><td>~0.0213 USD</td><td>~0.0213 USD</td><td>~0.0016 USD</td></tr><tr><td>ERC20 -> HBAR swap</td><td>~0.1378 USD</td><td>~0.1378 USD</td><td>~0.1066 USD</td><td>~0.0016 USD</td></tr></tbody></table>

Amount of fee charged by EtaSwap can be different for each adapter, it’s possible to change/adjust the fee for a particular adapter. Current fees:

| Exchange   | Fee by EtaSwap |
| ---------- | -------------- |
| SaucerSwap | 0.3%           |
| Pangolin   | 0.3%           |
| HeliSwap   | 0.5%           |
| HSuite     | 0.3%           |

Network fee always charged in HBAR, so make sure you have enough HBAR coins to pay network fee before swap operation.

EtaSwap fee charged in source tokens (note: for HSuite, EtaSwap fee charged in HBAR).

Unused slippage always returns to user.



Example 1:

You have 100 tokenA and you want to exchange it by max possible amount of tokenB. For example lowest rate you found by EtaSwap - it's SaucerSwap with rate 3 (1 tokenA costs 3 tokensB).\
So you initiate swap with default slippage 2.5%.

1. You sign Approval transaction for 100 tokenA (spending 0.05 USD)
2. You sign swap transaction ERC20 -> ERC20 (spending 0.07 USD)
3. EtaSwap charges fee for SaucerSwap operation, 0.3% deducted from your 100 tokenA, so you keep proceed swap with 99.7 tokenA.
4. You expect to receive 99.7 \* 3 = 299.1 tokenB. By slippage rate 2,5% expected minimum income will be 291.6225. If exchange can satisfy this amount - transaction is successful and you receive from 291.6225 up to 306.5775 tokenB.

In total your spendings: 0.12 USD + 100 tokenA, your income 291.6225 - 306.5775 tokenB.



Example 2:

You have some amount of HBAR and you want to buy exacty 200 tokenC. For example lowest rate you found by EtaSwap - it's Pangolin with rate 5 (1HBAR costs 5 tokensC). So you initiate swap with default slippage 2.5%.

1. You don't need to sign Approval transaction, since you are spending root token.
2. You sign swap transaction HBAR -> ERC20 (spending 0.02 USD). Amount of allowed to spend HBARs will be calculated like: reverse rate \* amount to receive + slippage + EtaSwap fee. Reverse rate will be: 1 / 5 = 0.2. So amount, that smart contract allowed to spend: 0.2 \* 200 + 0.2 \* 200 \* 0.025 + 0.2 \* 200 \* 0.003 = 41.12 HBAR.
3. If exchange can satisfy this amount - transaction is successful and you receive exactly 200 tokenC.
4. You receive change (unused HBAR tokens), calculated by: 41.12 HBAR (sent to smart-contract) - 39-41 HBAR (amount spent by exchange to get 200 tokenC) - 0.12 HBAR (EtaSwap fee) = 0 - 2 HBAR.

In total your spendings: 39.12 - 41.12 HBAR, your income 200 tokenC.

{% hint style="info" %}
Note: examples on top calculated with given 0% price impact.
{% endhint %}
