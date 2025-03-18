# Release notes



* v 1.4.4 (13.01.2025)\
  Fixed:\
  &#x20; \- Delays in connecting wallet and showing tokens balances\
  Improved:\
  &#x20; \- Set WalletConnect as connection method for HashPack (removed hashconnect)\

* v 1.4.3 (26.12.2024)\
  Fixed:\
  &#x20; \- Issue with fetching tokens from HeliSwap (was blocked by some firewalls)\
  &#x20; \- "UniswapV2: K" transaction error.\
  Improved:\
  &#x20; \- Enabled gzip on server (amount of data, transmitted during initial loading reduced from 7.1MB to 2.0MB)\

* v 1.4.2 (21.12.2024)\
  Added:\
  &#x20; \- tokenFrom and tokenTo setup as query parameters\
  Fixed:\
  &#x20; \- New tokens will appear instantly on EtaSwap after appearing on any DEX\
  &#x20; \- Not asking to associate tokens for users which have configured unlimited associations\
  &#x20; \- Black screen on decimals overflow\
  &#x20; \- Clipboard access request on copying transaction ID\

* v 1.4.1 (04.12.2024)\
  Added:\
  &#x20; \- Selectable routes\
  Improved:\
  &#x20; \- Initial token list loading time\

* v 1.4.0 (01.07.2024)\
  Added:\
  &#x20; \- Advanced statistics (total volume, volume by DEX, volume by source, volume by wallet, swaps by wallet)\
  &#x20; \- 50 new tokens\
  Fixed:\
  &#x20; \- Appearing spinner on Tokens page\
  &#x20; \- Slightly increased debounce for fetching rates (from 500ms to 650ms)\

* v 1.3.0 (01.06.2024)\
  Added:\
  &#x20; \- WalletConnect support\

* v 1.2.0 (03.06.2024)\
  Added:\
  &#x20; \- Split-swaps\
  Fixed:\
  &#x20; \- Backend response time optimize (2-3 times faster now)\

* v 1.1.0 (22.05.2024)\
  Redesign\

* v 1.0.5 (25.04.2024)\
  Fixed:\
  &#x20; \- Disable input fields when loader is active (switching output amount)\

* v 1.0.4 (15.04.2024)\
  Added:\
  &#x20; \- Token balance displaying in corner of input field\
  &#x20; \- Token balances displaying in tokens selection modal \
  Fixed:\
  &#x20; \- Preserve token amount in input field on switching token\
  &#x20; \- Preserve token amount in input field after associating token\
  &#x20; \- Preserve token amount in input field after executing swap\
  &#x20; \- Interval with requesting new rate now works more precise, also fixed double-requesting same rate\
  &#x20; \-  Add 5% to slippage options (to be able to process tokens with high custom fees)\

* v 1.0.3 (02.04.2024)\
  Added:\
  &#x20; \- 186 new tokens (711 in total)\
  &#x20; \- Warning on exchange tokens with custom fees (like BSL)\
  &#x20; \- Advanced smart-routing algorithm (output amount should become even better)\
  Fixed:\
  &#x20; \- Spinner on fetching rate\

* v 1.0.2 (23.03.2024)\
  Fixed:\
  &#x20; \- SaucerSwapV2 execution error when smart-route using pools with different fees\
  &#x20; \- WHBAR address in route output param replaced by AddressZero\

* v 1.0.1 (18.03.2024)\
  Added:\
  &#x20; \- Smart routing (indirect swaps)\

* v 1.0.0 (07.03.2024)\
  Added:\
  &#x20; \- SaucerSwapV2 integration\
  &#x20; \- Introduce of API\
  Updated:\
  &#x20; \- Set HeliSwap fee as 0.3%. Now all providers has 0.3% fee on our side\

* v 0.3.4 (10.02.2024)\
  Added:\
  &#x20; \- Token association buttons\
  &#x20; \- HSuite fee display\
  Fixed: \
  &#x20; \- Skip provider if failed to download it token list\

* v 0.3.3 (15.01.2024)\
  Added:\
  &#x20; \- 92 new tokens for SaucerSwap\
  &#x20; \- Supported token lists for mainnet and testnet ([https://app.etaswap.com/tokenListMainnet.json](https://app.etaswap.com/tokenListMainnet.json), [https://app.etaswap.com/tokenListTestnet.json](https://app.etaswap.com/tokenListTestnet.json))\

* v 0.3.2 (13.12.2023)\
  Fixed:\
  &#x20; \- Nullify field values on switching tokens\

* v 0.3.1 (12.12.2023)\
  Added:\
  &#x20; \- HSuite indirect swaps ("Smart routing")\
  Updated:\
  &#x20; \- HSuite rate source (API instead of tokenPair)\

* v 0.3.0 (30.11.2023)\
  Added:\
  &#x20; \- HSuite\
  &#x20; \- Approx. network fee\
  &#x20; \- Notifications (success/error transactions)\
  &#x20; \- Loader (spinner)\
  Updated:\
  &#x20; \- Code refactoring (introduce Typescript)\

* v 0.2.2 (22.10.2023)\
  Added:\
  &#x20; \- Search in tokens modal (by name, symbol and address)\
  Fixed:\
  &#x20; \- Precision of rate (consider 0.3% of each DEX fee)\
  &#x20; \- Leading zero in fields\
  &#x20; \- Testnet factory address\
  &#x20; \- Field values after exchange\

* v 0.2.1 (14.10.2023)\
  Added:\
  &#x20; \- Version of application in right bottom corner\
  Fixed:\
  &#x20; \- Overlapping social icons\
  &#x20; \- Styles on mobile page\
  &#x20; \- Website (main page) updates\
  &#x20; \- SPA routing (opening /tokens page)\

* v 0.2.0 (09.10.2023)\
  Added:\
  &#x20; \- Blade wallet\
  Updated:\
  &#x20; \- Slightly reduced gas amount for HeliSwap (cheaper WHBAR burning)\
  &#x20; \- Code refactoring\
  Fixed:\
  &#x20; \- Bug on switching network to testnet\

* v 0.1.2 (29.09.2023)\
  Added:\
  &#x20; \- Price impact calculation\
  &#x20; \- Min receive / Max spend values\
  Updated:\
  &#x20; \- Slippage rate set to 1.0% by default\
  &#x20; \- UI improvements (hint with too hight price impact, input fields validation)\

* v 0.1.1 (18.09.2023)\
  Added:\
  &#x20; \- All tokens from SaucerSwap, Pangolin and HeliSwap\
  &#x20; \- Rate refresh on idle (+progressbar)\
  &#x20; \- Documentation (gitbook)\
  &#x20; \- 404 page\
  Fixed:\
  &#x20; \- SPA routes 404\

* v 0.1.0 (12.09.2023)\
  Beta version release
