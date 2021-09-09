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

Market Maker should take care of the latency between the server that is streaming the price and the end client. Market Maker have full control over reputation 

Market Maker is streaming prices to Market Taker. After getting execution request from Market Taker, Market Maker is able to reject the trade if the price is no longer valid.

They are getting Execution 

Pricing is indicative that Market Makers is able to 

Borrowers are able to borrow crypto assets by supplying ETH and/or Stablecoin as collateral. This gives users flexibility when interacting with other protocols that requires using assets they currently do not have without losing their current positions.

### 👨‍🌾 Market Takers



Market Taker order is a data structure created off-chain and signed according to [EIP-712](https://eips.ethereum.org/EIPS/eip-712).

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



