# Theoretical Background

## Abstract 

We introduce LLDEX Protocol: a new pattern for crypto trading. LLDEX Protocol is a definition of a new pattern that is combining low latency OTC trading with Last Look known mainly from multi-bank FX market with on-chain trade settlement where the smart contract is playing the role of Central Clearing Counterparty \(CCP\). LLDEX Protocol enables users to buy or sell crypto assets at a specific price and settle the trade directly between wallets \(Wallet2Wallet trading\). LLDEX Protocol workflow is set to be a true alternative for trading on centralized low latency order books run by crypto exchanges. Until now users had to compromise between the safety of funds and the cost of trading. With LLDEX Protocol it is possible to keep all funds in the on-chain wallet and still be able to trade using real-time constantly changing prices updated hundreds of times a second. To prevent low latency arbitrage LLDEX is supporting Last Look to give necessary protection to slower market makers. As of today, we have not found any other platform that is using this model. 

## LLDEX Mission 

We believe in a free and open society that works together to create a better world. We believe that blockchain technology can work as a general consensus mechanism. Blockchain is particularly useful for building trust and coordination in the case of financial products. We are committed to bringing all our experience from Traditional Finance into Decentralized Finance to at least make finance more free and open to its participants. Having decades of experience in Traditional Finance, on the operational level we believe that Core Banking Systems, international payment systems, financial messaging systems, settlement centers, central counterparty clearing, credit card processors, payment processors should be replaced with a set of smart contracts to gain interoperability, cost efficiency, security of funds and transparency. We are committed to making it happen.

## Overview of popular trading workflows:

There is a couple of popular trading workflow and credit risk patterns that are worth mentioning to get a broader overview of the current state of available financial infrastructure and enable the reader to quickly understand the innovation that LLDEX Protocol is bringing to the financial community. We simplified a lot of concepts and one can argue that the below definitions are not precise, do not cover all cases, or are even incorrect. For that reason, readers that want to get a precise understanding of trading workflow and credit risk patterns should conduct their own research.

#### Market and settlement risk models:

* Settlement directly on accounts of a broker/bank/crypto exchange

The client is holding the money in the account of the broker. In the case of simple FX/crypto exchange, trade settlement is usually happening instantly on the accounts of the client. The first and second instrument is still held by the broker in the name of the client. The client is taking market and settlement risk of broker/bank/crypto exchange. In this case, most of the trading would happen on The Single Dealer Portal of a given broker/bank/crypto exchange. 

* The settlement with broker/bank/crypto exchange in Delivery Versus Payment settlement model

The client is trading with a counterparty that is not in direct control of the customer funds before and after the trade. Trade settlement is happening on an agreed date. To settle the trade, the client is sending the money to the broker account. The broker after getting the money from the client is sending the opposite currency/cryptocurrency/security to the client \(the transfer of the opposite amount happens after client payment is finalized\). Both parties are taking a market risk before the trade settlement \(the price of the instrument would change and the opposite counterparty would not be willing to settle\). The client is also taking settlement risk because there is no guaranty that the broker after will send back the opposite currency/cryptocurrency/security after recipience of customer funds.

* Use of Central counterparty \(CCP\) clearing as a middleman

To reduce the market and settlement risk of trading there are established financial institutions that mitigated counterparty risk of the trade. CCP can be used to address market risk and settlement risk. In case of market risk, both parties would hold collateral with CCP. CCP would perform mark-to-market of open positions between counterparties and initiate margin calls to assure that collateral will cover potential costs related to the liquidation of the trade. If CCP is connected with CLOB, market risk could be mitigated almost fully. 

To mitigate settlement risk, executed trades are submitted to a clearinghouse, which then steps between the two original traders and takes over the counterparty risk for the trade. For example, trade between member firm A and firm B becomes two trades: A-CCP and CCP-B. 

[https://en.wikipedia.org/wiki/Central\_counterparty\_clearing](https://en.wikipedia.org/wiki/Central_counterparty_clearing)

* On-chain settlement

Smart contracts executed on-chain can take over the entire settlement procedure and act as a CCP for the trade. Risk related to trade settlement is mitigated by the security of the blockchain and the code of the smart contract that is being used. The use of smart contracts for trade settlement is transforming the risk of a particular counterparty into the risk related to the structure of a given blockchain and the code of the smart contract.

Smart contracts are also often used for market risk mitigation \(ex. MakerDAO\). In most cases, mark-to-market of an open position is done with the use of so-called Price Oracles like Chainlink. The code of the smart contract is defining under what conditions and how positions can be liquidated.

#### Trading models:

* Central Limit Order Book \(CLOB\)

There is one central place that is matching orders. CLOB is offering so-called firm liquidity, where active orders on the CLOB server are matched/executed without optionality. Due to the possibility of latency arbitrage between CLOB platforms, pricing engines of market makers are usually based in the same data center as CLOB servers and there is a constant fight between market participants to find the fastest route between different CLOB platforms with an active market of the same/linked instrument. In the case of cryptocurrencies, almost all popular centralized exchanges like Binance, Coinbase, Huobi are using this execution model.

* OTC trading with Last Look

In OTC trading market maker/ liquidity provider provides a quote rather than a firm price via single dealer platform, phone, chat, or third-party execution venue. After getting a quote client is sending an execution request to the liquidity provider. When a request to trade against the quoted price is received, the LP may hold the request for some time \(LAST LOOK\) and then execute or reject the trade. During the last look window market maker can check if the pricing is still valid and auto-hedge the trade before giving final confirmation to the end client. Last look's quote-driven behavior is commonly argued to be necessary to protect the liquidity providers in a fragmented and unregulated marketplace where there is no central exchange for a given instrument. [https://en.wikipedia.org/wiki/Last\_look\_\(foreign\_exchange](https://en.wikipedia.org/wiki/Last_look_%28foreign_exchange)\)

* On-chain Automated Market Maker model

Automated market makers \(AMMs\) allow digital assets to be traded without permission and automatically by using on-chain liquidity pools instead of a traditional market of buyers and sellers. Price is influenced not by market makers, but by trades that are executed against the pool. For AMMs, arbitrage traders are financially incentivized to find assets that are trading at discounts in liquidity pools and buy them up until the asset???s price returns in line with its market price. Liquidity Providers that are contributing funds to the pool will incur losses when the price ratio of the pooled asset deviates from the price at which LP deposited funds. The higher the shift in price, the higher the loss incurred. In the case of AMM, Liquidity Provision is only profitable, when losses related to change in price ratio are smaller than fees earned from trades executed against the pool.

* Aggregators 

There is a common pattern of aggregators that are putting all prices from different sources on one screen or allow trading via one API. Aggregators can combine off-chain and on-chain liquidity in CLOB and OTC models.

#### Combination of settlement risk models with trading models

* Centralized Crypto exchanges are in most cases combining CLOB with settlement directly on accounts of a broker. Market risk and liquidations are managed by a Centralized Crypto exchange.
* Stock exchanges are in most cases combining CLOB with Central counterparty \(CCP\) clearing.
* Decentralized exchanges are in most cases combining on-chain price discovery \(ex. Automated Market Maker or on-chain/side-chain order book\) with on-chain settlement.
* OTC brokers are combining OTC trading with Last Look with Delivery Versus Payment settlement. This model is forcing the end client to evaluate the credit risk of individual brokers.
* LLDEX model is a unique combination of on-chain settlement that is mitigating settlement risk with low latency OTC off-chain price discovery based on quotes. In the latter stages, we plan to use the same model for on-chain settled derivatives. We would like to combine OTC off-chain price discovery based on quotes for derivative products with on-chain mark-to-market/margin calls and final trade settlement.

## Factors driving LLDEX design 

To design a new workflow for decentralized exchange that will make a difference, we came back to the first principle thinking about the economics of price discovery and trade settlement. We decided to question current solutions available in the crypto market and focus on a totally new design that will inspire a new wave of innovation in Decentralized Finance. We believe that Centralized Crypto Exchanges decided to run the Central Limit Order Book model as a way to simplify liquidity management on their platforms and make it as transparent as possible. CLOB is particularly demanding for market makers due to the latency war that is happing between exchanges where the same instrument is available for trading. If the price would change on one exchange to allow arbitrage on the other exchange, the fastest player would execute an arbitrage order on the other exchange. In most cases, the fastest player would be quicker than a bit slower market maker that had the intention to make markets on CLOB exchange. This creates a situation, where market making is just limited to the biggest and fastest payers that are able to arbitrage between CLOB exchanges and withdraw their quotes fast enough to prevent somebody else from arbitraging them. All slower payers that are willing to make markets using directional or neutral strategies are ending up losing money with their orders being executed mainly by low latency arbitraging bots and not by real market takers.

On the other hand profitability of Automated Market Maker strategies popular in Decentralized Finance is also questionable. The market volatility that is driving arbitrage volumes on AMM DEX???es is generating losses for market makers that often are greater than market maker fees generated from trading. It seems to be a very similar structure to market-making on CLOB exchanges where only highly capital and technically prepared participants are able to make a profit mainly thanks to different arbitrage strategies \(check [https://docs.flashbots.net/](https://docs.flashbots.net/) to get the overview of the market\). We believe that a cost of losses that are experienced by market makers are passed to market takers that need to pay much bigger fees \(currently 0.3% for most pairs\) to at least partially reword market makers for the risk that they are taking. We believe this is not sustainable and this waste of money should be fixed in the long run. We are currently preparing more in-depth research on this topic to statistically prove this statement. Questioning the most popular solutions we come back to very basic characteristics of Crypto Currencies. We believe that cryptocurrencies in their foundation are much more similar to FX than to Equity. Following similarities can be found:

* Crypto Currencies are traded all around the world and are not related to a particular region or exchange \(much more similar to FX than to an Equity market that is linked to a particular location/exchange/time zone\)
* Crypto Currencies are not controlled by any particular entity \(similarity to FX\)
* Crypto Currencies are not regulated \(similarity to FX\)

In traditional finance, Central Order Book Model is popular in the case of equity trading and not so popular in the case of FX or other OTC markets \([https://www.risk.net/definition/central-limit-order-book-clob](https://www.risk.net/definition/central-limit-order-book-clob)\). Most of FX volumes is done between market-makers and market taker via Streaming or RFQ workflows that support with Last Look. Taking the above similarities between FX and Crypto, LLDEX design is taking much more from FX trading than to Equity trading.

In OTC FX market microsecond latency is not that important as in the case of Equity and Futures trading on centralized exchanges. It is perfectly normal to expect 250-700 ms response times when trading on Multi Dealer Platforms like FXAll, 360t, or Bloomberg. Last Look protection of market maker and credit check workflow make OTC FX market much slower than Equity CLOB???s but on the other side, OTC FX is offering constant access to deep liquidity unseen Equity or Crypto markets with volume trades being almost 20 times bigger on a global scale \(FX volume is estimated at around $5 Trillion per day and equity at roughly $200 billion per day\).

90% of trades on the interbank market are done between market makers and market takers that have some sort of relationship with each other. Order Book-style trading is relatively limited because there are very few market participants that know where the real market is in a particular millisecond. Market Makers aggregate feeds from multiple sources and offer prices to the end customers. Thanks to Last Look Market Makers are able to check if the market price that they quoted has not changed to much. During the last look Market Makers can auto-hedge flow before giving final confirmation to the end customer. Thanks to this structure bid-ask spread on the most traded FX pairs is &lt; 0.001% for $1 million, 0.0025% \(0.3 pip on EURUSD\) and &lt; 0.003% for 10 million of liquidity . To buy $5 million worth of ETH on Binance, one needs to pay a premium of around 0.23% from the mid-market price. FX liquidity offered by an average bank \(that is just passing liquidity and not making markets\) is 100 times more liquid than the biggest crypto exchange in the world. 

To even get a wider perspective we decided to compare volumes and generated fees. On 22 of September 2021, the volume of the biggest Decentralized Exchange \(DEX\) Uniswap v3 was 1.9b USD with 3.2m fees paid to Liquidity Providers. This gives an average fee of 0.16%. Professional FX market maker: XTX was doing on average 200 billion USD a day in 2019 with revenue of 1.78m USD per day \([https://fxnewsgroup.com/forex-news/institutional/market-maker-xtx-markets-2019-revenue-up-339m/](https://fxnewsgroup.com/forex-news/institutional/market-maker-xtx-markets-2019-revenue-up-339m/)\). The average fee of XTX was 0.001%. Market Maker fees on FX market are almost 190 times less than the fee earned by Uniswap liquidity providers.

It was a bit of research that is explaining why we decided to make LLDEX design more similar to OTC than to CLOB or AMM. 

With LLDEX design we decided to:

* compromise sub-millisecond latency achievable on top Crypto exchanges running CLOB model
* give last look protection for market makers to allow risk-free liquidity brokerage \(pass liquidity from one place to the other and make immediate risk fee profit with every trade\)
* democratize access to deep OTC liquidity thanks to a blockchain settlement process

## Summary of LLDEX design

LLDEXProtocol implements a settlement layer for quotes send from market maker to market taker. Market makers are responsible for executing pre-signed execution requests send to market takers.

On-chain LLDEXProtocol does guarantee that each execution request signed by market taker is only executed once and transfers are successfully executed for both sides of the trade: maker to taker, and taker to maker. 

The smart contract is responsible for transfers that are executed for both sides of the trade: maker to taker, and taker to maker. Validations of execution requests send from market takers to market makers are expected to be performed off-chain.



