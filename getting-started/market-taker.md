# Front-end examples

Each individual market maker is free to create its own front-end that will provide real-time pricing to its customers. We see also a big opportunity for software providers that can create front-ends that would aggregate and measure the performance of multiple market-makers.

The goal of this project was to contribute 

### 👨‍🌾 Market Taker Front-end working example

Market Taker typescript example can be found on:

[https://github.com/DeLabsI0/LLDEX/blob/main/LLDEX-App/src/rt\_client.ts](https://github.com/DeLabsI0/LLDEX/blob/main/LLDEX-App/src/rt_client.ts)

For the signature of Execution requests, we recommend the use of [Utils library for 1inch Limit Orders Protocol](https://github.com/1inch/limit-order-protocol-utils)

![](../.gitbook/assets/image%20%282%29.png)

### 🤝 Market Maker Front-end working example

Market Maker typescript example can be found on:

[https://github.com/DeLabsI0/LLDEX/blob/main/LLDEX-App/src/rt\_client.ts](https://github.com/DeLabsI0/LLDEX/blob/main/LLDEX-App/src/rt_client.ts)

Market Maker is made to quote prices based on quotes coming from Binance, receive orders from market takers and send transactions to the blockchain for settlement.

![](../.gitbook/assets/image%20%281%29.png)





