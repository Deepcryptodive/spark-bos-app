# Spark Nexus

## Introduction
During the ETHLisbon hackathon in Nov 2023, I embarked on a project to bridge a crucial gap in decentralized finance (DeFi). Tackling the fragmented user interfaces and centralization risks present in current DeFi frontends, specifically lending platforms. The solution: Spark Nexus, a decentralized frontend built on NEAR's Blockchain Operating System (BOS) focused on interacting with Spark Protocol on the Gnosis and Ethereum mainnet. It's a modular design, which also supports other lending markets and blockchains within the same interface.

![image](https://github.com/Deepcryptodive/spark-bos-app/assets/61325205/898b1f71-1bb4-47a5-af2b-c1c565a7b012)


## Problem Statement
DeFi enthusiasts often grapple with two main challenges: the complexity of managing multiple interfaces and the centralization risks inherent in frontends, which can compromise the trustless ethos of their underlying applications. Spark Protocol is an Aave V3 fork active on both Ethereum and Gnosis networks. It provides a web2-style interface (via Cloudflare) but has yet to deliver a fully decentralized frontend.

Just this week,[ Spark's official frontend](https://app.spark.fi/) was unavailable for an extended period, posing significant risks for users needing to adjust their borrow strategies during volatile market conditions. Additionally, the DeFi landscape has recently been subject to by a series of malicious frontend takeovers, with DNS hijacking and other tactics compromising website integrity. Finally, regulatory changes might lead to restricted access to centrally hosted frontends through geoblocking and other techniques.

![Screenshot from 2023-11-02 12-17-36](https://github.com/Deepcryptodive/spark-bos-app/assets/61325205/c3b71c26-02ca-426a-8d6e-5d5ea436869a)

**Spark Nexus addresses these challenges by providing a decentralized, intuitive, and chain-agnostic frontend, ensuring a user experience that remains true to DeFi's foundational principles.**




## Features
Spark Nexus is a full-fledged decentralized application (dApp) that allows users to interact seamlessly with three separate lending protocols: Spark Lend, Aave v3, and Agave. The application supports all essential DeFi lending operations, including:
- Deposits and withdrawals
- Collateral management
- Borrowing and lending
- Real-time data on lending rates, balances, net worth and health factors
- Health factor simulations
- Gas fee estimations
- Wallet management

Additionally, it allows you to effectively view and manage your assets in one UI.
The addition of the Aave v3 lending market on Polygon highlights the modular design, enabling support for other lending markets and other blockchains within the same interface. At the bottom of the page, users can also access the Agave lending market on Gnosis. This can be useful for users to spot lending arbitrage opportunities and quickly act on them, from within the same interface. 

### Forked and Customized Components
The project was originally forked from [this repository](https://near.org/near/widget/ComponentDetailsPage?src=bluebiu.near/widget/ZKEVM.AAVE), and with the exception of the [Agave component](https://near.org/near/widget/ComponentDetailsPage?src=bluebiu.near/widget/Gnosis.Lending), all code has undergone significant customization to make it work seamlessly with Spark Protocol and Gnosis Chain.


### Key Enhancements
During the hackathon, we made several notable changes:
- Developed a dynamic data service (API) for Spark Protocol for real-time fetching and display of on-chain data. [See separate repository](https://github.com/Deepcryptodive/spark-data-service). This provides the frontend with live updates on interest rates, account balances and market conditions. This is live in production, open for anyone to query.
- Integrated privacy-preserving and decentralized RPC providers.
- Configured all necessary Spark Protocol parameters and customized BOS components. All customized components (>6) are available [here](https://near.org/near/widget/ProfilePage?accountId=deepcryptodive.near&tab=apps) and are deployed on NEAR mainnet.



## Deployment
### NEAR Mainnet Access
The final source code for Spark Nexus is deployed on the NEAR mainnet, enabling trustless access. Explore the functionality and features by visiting the following link: [Spark Nexus on NEAR](https://near.org/deepcryptodive.near/widget/SPARK).

### GitHub Repository
For those interested in the development side, the following repositories contains all the code needed. 
* [Frontend](https://github.com/Deepcryptodive/spark-nexus) 
* [Data Service]([url](https://github.com/Deepcryptodive/spark-data-service/))
You can clone, review, and contribute to the code.

### Local Deployment Guide
To run Spark Nexus locally:
1. Ensure that you have `bos-loader` and `bos-cli` installed on your system.
2. Follow the instructions in [this guide](https://docs.near.org/bos/dev/bos-loader) to run `bos-loader`.
3. Set the loader URL to your local server, typically `http://127.0.0.1:3030`.
4. Navigate to `https://near.org/deepcryptodive.near/widget/SPARK` to interact with the locally deployed instance.
5. For the Spark Data Service, you have the option to run it locally, host it on Cloudflare yourself or use the existing deployment. Detailed setup instructions are available in the [Spark Data Service README](https://github.com/Deepcryptodive/spark-data-service/blob/main/README.md).



## Future Development
### Decentralized Data Service
Post-hackathon, we aim to pivot to a fully decentralized data service, enhancing trust and resilience. We're exploring solutions like The Graph for indexing and querying, withouth relying on centralized RPC endpoints or the need for (self-)hosting of the Data Service.

### Proactive Risk Management Tools
One very useful addition in termpos of UX, would be the development of proactive risk management tools. Including customizable alerts for significant token price movements, health factor changes and lending arbitrage. Potential technical solution: WalletConnect's Web3Inbox SDK.

### Speed optimizations
Loading times can be further reduced, through various optimizations that fell outside of the scope of this hackathon submission.

## Conclusion
Spark Nexus is more than a random hackathon project — it's a step towards a more accessible and decentralized DeFi ecosystem. We invite the community to explore and contribute to our vision of a truly decentralized financial future.  We expect to see this frontend integrated on https://alpha.dapdap.net/ in the near future; as a real and performant alternative to the [official Spark Protocol frontend](https://spark.fi/).

It allows you to effectively view and manage your assets in one UI. Think of it like a decentralized portfolio tracker such as [DeBank](https://debank.com/) - but one where you can interact with the underlying protocols!



https://github.com/Deepcryptodive/spark-bos-app/assets/61325205/83e474ad-a725-4317-af34-4e92dd932b15


