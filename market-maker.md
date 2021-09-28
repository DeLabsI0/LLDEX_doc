# Market Maker

Market Maker is quoting a price that is including Market Maker margin. In a separate field market maker can quote a fee related to the gas needed for settlement on a particular blockchain.

A fee of the market maker should be included in the price quoted from the market maker to the market taker. 

### 🤝 Market Maker Front-end

Market Maker typescript example can be found on:

[https://github.com/DeLabsI0/LLDEX/blob/main/LLDEX-App/src/rt\_client.ts](https://github.com/DeLabsI0/LLDEX/blob/main/LLDEX-App/src/rt_client.ts)

Market Maker client can recieve orders from market takers and send transactions to the blockchain for settlement.

![](.gitbook/assets/image%20%281%29.png)

