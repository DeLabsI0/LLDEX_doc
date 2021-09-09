# What is LLDEX?

## Low Latency DEX Protocol

Low Latency DEX is Wallet2Wallet permissionless protocol to settle crypto trades between 2 counterparties. It allows users to agree on the price off-chain in a low latency environment and settle the trade on-chain.

The protocol can be used by two counterparties that would like to trade with each other and settle trades on-chain. 

### 🤝 General workflow

1. Market Maker is streaming prices to Market Taker
2. Market Taker is sending execution request to Market Maker
3. Maker Maker is approving the trade request and sending trade to the blockchain for trade settlement

To allow **low latency** execution workflow between 2 parties without compromising security, we implemented an additional key set on the market taker and on the market maker side. Information about keys used for low latency workflows is saved on the blockchain.

### 🤝 Market Maker

Rates streamed by Market Maker do not commit the Market Maker to confirm particular execution. It is up to the Market Maker to decide if the transaction can be sent to the blockchain. 

Designed workflow is allowing for risk-free position auto-hedging. If the hedge trade would not be possible at the given price, Market Maker can reject the execution request.

Market Maker should take care of the latency between the server that is streaming the price and the end client. Market Maker has full control over its reputation. Constant trade rejections will cause reputation damage.

### 👨‍🌾 Market Takers

Market Taker is getting current prices from Market Maker. Market Taker is sending execution request to the Market Maker. 

To achieve low latency execution, Market Taker has a special key set stored in the browser. 

Execution request is a data structure created off-chain \(ex. in the browser\) and signed according to [EIP-712](https://eips.ethereum.org/EIPS/eip-712). 



Lenders are able to now earn risk-free yield \(as high as 1000+%\) on not only popular assets, but also the long tail of crypto assets, including yield farmed tokens, that exist today! Easily deposit your tokens on Beta into the token's money market, or create it yourself if it's not there yet.

### 

### 📈 Traders

Traders are able to short sell any crypto asset by using their ETH and/or Stablecoin as collateral. Beta provides an integrated "1-Click" Short that makes initiating and managing short positions simple.

### 🧨 Liquidators

Liquidators are able to earn a premium bounty reward for monitoring and liquidating under-collateralized positions.









## Stay Connected

Connect with us on social media to stay up to date with all our 

* Medium
* Discord
* Twitter
* Telegram \(community\) \(announcements\)



