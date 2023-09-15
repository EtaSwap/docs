# How to swap tokens

To swap your tokens at the best rate - need to follow next steps:

1. Open [https://app.etaswap.com](https://app.etaswap.com) &#x20;
2. Choose the tokens you want to swap. The first row is token you want to sell, and second (lower) token you want to buy.\
   ![](<.gitbook/assets/image (2).png>)\

3. In the appeared modal window you can find token address, name and symbol. Make sure the token address matches the token you need, because token name and symbol could be not unique.\
   ![](<.gitbook/assets/Screenshot 2023-09-14 at 19.09.57.png>)\
   The icons on the right side - is list of exchanges that have this token available.\
   There is HBAR token among others. It doesn't have an address, because it's root Hedera token.
4. When you selected necessary tokens - EtaSwap will check prices on the exchanges and show you best rate to swap.\
   ![](<.gitbook/assets/image (3).png>)
5. If you see "Low volume" mark near the DEX rate it means that DEX token pair is drained (exchange has not enough coins on balance to complete your transaction).\
   ![](.gitbook/assets/image.png)\

6. Before the swap action - make sure tokens you selected - is associated to your account. In case at least one of the tokens is not associated to account - the transaction will fail.\
   Quick note: you don't need to associate WHBAR to your account in order to swap HBAR to another token (only associate it if you want to swap exactly WHBAR). All operations with wrapping/unwrapping already implemented in Adapter smart contract.
7. After click "Swap" - your wallet will ask you to sign two operations one by one:
   * Approve allowance (will be ommited in case you are selling HBAR)
   * Swap
8. In case of any transaction fail - please copy transaction id and reach the team by [telegram](https://t.me/etaswap) or [discord](https://discord.com/channels/1149085148223111228).
