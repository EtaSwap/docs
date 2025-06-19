# Bridge

General information about mechanism of work can be found [here](../../bridge/how-it-works.md).

In order to interact with bridge on smart-contract level you need to interact with functions `quote` and `bridgeTokens` of the [adapter smart-contract](../smart-contract-addresses.md) on a source chain.

In order to pay for execution on destination chain, LayerZero and DVN fees you need to attach sufficient value on source chain. Calling `quote` allows you to estimate this value:

```solidity
function quote(
    string calldata symbol,
    uint256 amount,
    address receiver,
    uint32 targetChainId,
    bytes calldata _options
) public view returns (uint256 nativeFee)
```

Quote will return you an estimate in root token of the source chain.

Next step is to call `bridgeTokens` function:

```solidity
function bridgeTokens(
    string calldata symbol, 
    uint256 amount, 
    address receiver,
    uint32 targetChainId,
    bytes calldata _options
)
```

To make call successful you need to make sure of two things:

1. Approved allowance by sender should be ≥ `amount` (sufficient amount allowed)
2. Attached value is equal to `quote` output

`targetChainId` can be found [here](https://docs.layerzero.network/v2/deployments/deployed-contracts) (in column Endpoint Id). `receiver` address can be customised (it isn't mandatory that receiver is the same address as sender).\
`_options` can be constructed by `@layerzerolabs/lz-v2-utilities` library. Destination chain gas amount should be included in the call. We recommend to keep it `140000` gas. Example of options usage:

```typescript
import { Options } from '@layerzerolabs/lz-v2-utilities';

const options = Options.newOptions().addExecutorLzReceiveOption(140000, 0);

const args = [
   'USDC',
   amount,
   receiver,
   targetChainId,
   options.toHex().toString(),
];

// Call quote/bridgeTokens with args
```

After successfull `bridgeTokens` call, event `TokensBridged` will be issued to simplify off-chain tracking of the transactions.

```solidity
event TokensBridged(
   bytes32 indexed guid, 
   address indexed sender, 
   IERC20Metadata token, 
   uint256 amount, 
   address receiver, 
   uint256 fee, 
   uint32 targetChainId
);
```

{% hint style="warning" %}
Fields amount and fee in `TokensBridged` event are normalized to 18 decimals in order to support tokens with different amount of decimals on different chains. Keep in mind that to convert it to original token amount - you need to multiply it to 10^tokenDecimals and divide it by 10^18.
{% endhint %}

After message is processed, event `TokensReleased` event will be issued on destination chain by respective adapter smart-contract.\


```solidity
event TokensReleased(
   bytes32 indexed guid, 
   address indexed receiver, 
   IERC20Metadata token, 
   uint256 amount
);
```
