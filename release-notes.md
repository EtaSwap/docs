# Release notes



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
