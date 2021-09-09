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

To achieve low latency execution, Market Taker has a special key stored in the browser. Information about the current key is stored on the blockchain. Each key has validity time. The concept is taken from a regular authorization standard used by companies like Amazon, Google, Facebook.

Execution request is a data structure created off-chain \(ex. in the browser\) and signed according to [EIP-712](https://eips.ethereum.org/EIPS/eip-712) by the session key.

## Why we built Low Latency DEX Protocol

Most of the Crypto volumes are one on specialized Centralized Regulated Exchanges \(CEX\) like Binance, Hobi, Coinbase, FTX and [others](https://coinmarketcap.com/rankings/exchanges/). This is in contradiction with the main idea behind cryptocurrencies: DECENTRALIZATION.

Decentralized Exchanges \(DEX\) are not trying very hard to change it, but still they are a long way behind CEX. To help bring more Crypto volume that settles directly on-chain, we decided to copy the last-look workflow from OTC market.

We hope that our work will be used by single market makers that will be able to offer its liquidity on-chain. The other use of this concept would be by multi-market maker platforms that would aggregate and manage the reputation of market makers.

## Stay Connected

Connect with us on social media to stay up to date with all our 

* Medium
* Discord
* Twitter
* Telegram \(community\) \(announcements\)



