# How it works

Basically EtaBridge has adapters, deployed on each supported chain. Those adapters contain liquidity. Bridging happens by next scenario:

1. User sign approval transaction for X amount of tokens to bridge.
2. User call `bridgeTokens` method on source chain. Smart-contract takes X amount of tokens and initiate LayerZero message.
3. After validation by DVNs, LayerZero executor delivers message to the destination chain adapter, which allocates (X - fee) amount of tokens and send them to the user.

In order to execute transaction on destination chain, adapter on that chain should have enough liquidity on the balance. In case if at moment of time adapter doesn't have enough liquidity - transaction issued by LayerZero executor will fail. In case if message failed by lack of liquidity reason - user need to wait until liquidity will be rebalanced and execute message manually (or reach the team for help). On [https://app.etabridge.com](https://app.etabridge.com/) UI we put a warning and prevent user from bridging in case if destination adapter has not enough liquidity. However if you are going to call smart-contract directly or build your own UI - you should take care of checking if there sufficient amount of liquidity on destination chain, before initiating transaction.

{% hint style="warning" %}
If message delivery was failed by any reason on destination chain - it can be executed later manually.
{% endhint %}
