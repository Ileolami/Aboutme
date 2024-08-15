---
title: "Eight Things you need to know Before Building on Stellar Blockchain"
seoTitle: "Overview of Stellar Blockchain"
seoDescription: "Learn to build scalable projects on Stellar Blockchain with insights on network structure, consensus protocol, smart contracts, and more"
datePublished: Thu Aug 15 2024 20:10:21 GMT+0000 (Coordinated Universal Time)
cuid: clzvpsywz00010al95hem7yky
slug: eight-things-you-need-to-know-before-building-on-stellar-blockchain
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1723484150136/a19456ad-ec09-4516-9253-f6db351032ab.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1723752556540/98726d30-e75b-4667-920d-4e7f0fc64465.png
tags: blockchain, stellar, stellar-blockchain-development

---

"*Why do I have to transfer my crypto to a CEX account before I can get fiat and pay for something?*" This was my thought three years ago. Even though this process doesn't take much time, I still find it inconvenient.

As an entry-level blockchain frontend engineer, this problem occupied my mind like a lioness guarding her territory. I spoke to my friend about it, and he said, "Ileolami, I have thought about this problem too." We discussed how we could provide a solution, but we had limited resources and capacity.

Then I attended a Stellar Developer meetup in Lagos in July. "Yes, this is it. This is what I need for my projects," I thought. I immediately called my friend, "Chuks, I found the solution to the problem we talked about three years ago." My excitement was palpable to the person sitting next to me at the meetup.

Are you surprised and curious? You should be. You are reading this article because I am excited to share what [Stellar Blockchain](https://stellar.org/) is and how it solves this challenge. In this article, I will share the **NINE THINGS YOU NEED TO KNOW BEFORE BUILDING ON STELLAR BLOCKCHAIN**, along with practical examples and projects that can be built on it.

## Overview Of Stellar Blockchain

What if I told you there is a blockchain that allows interaction with traditional financial applications and seamless cross-border payments? Imagine a network where you can send or deposit cryptocurrency and receive its equivalent in fiat currencies, like US dollars or Nigerian Naira, and vice versa.

Yes, there is one, and it is **STELLAR.** Stellar is a layer-one, decentralized, open-source, public, and peer-to-peer blockchain. It allows developers to build applications, issue assets, and connect to existing traditional (web2) financial institutions. It is designed to enable creators, innovators, and developers to build projects on the network that can interoperate with each other.

In simple terms, Stellar is a bridge that connects the real world and blockchain technology without any noticeable differences.

![Stellar Bridge illustration](https://cdn.hashnode.com/res/hashnode/image/upload/v1723454551298/21e983fe-eabd-4683-90b1-fb95ee78fe57.png align="center")

The Stellar network offers fast, efficient, scalable, and affordable transactions. It is designed to handle thousands of transactions within 5 seconds, ensuring users experience minimal delays. Its efficiency is further highlighted by low transaction fees, making it an attractive option for both individuals and businesses.

The scalability of Stellar is one of its standout features, allowing it to process up to 1,000 operations per ledger. This means that the network can handle a significant number of transactions simultaneously, ensuring that users experience smooth and uninterrupted service.

Also, the affordability of transactions on the Stellar network makes it accessible to users from various economic backgrounds, promoting financial inclusion and enabling seamless cross-border payments.

## Eight Things to Know About Stellar Blockchain

Having explained what the Stellar blockchain is. In this section, you will learn about nine important aspects of Stellar: Network, Stellar Consensus Protocol, Stellar Core, Smart Contracts, RPC and Horizon, Stellar SDK, Anchors, Stellar Decentralized Exchange (DeX), and Transaction Process and Fees.

Let's dive right in.

### Stellar Networks

Stellar blockchain has three networks, they are **Mainnet(public network), Testnet(test network)** and **Futurenet(dev network).** These three networks are created to help developers in various stages of development and testing.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1723552568948/a3958c30-a6d4-45ba-8b48-ee10d747d229.png align="center")

#### Mainnet(Public Network or Pubnet)

This is the main Stellar network where real transactions take place, involving actual money and assets. It’s used when your application is live and interacting with real-world financial systems and requires Lumens (XLM) for transactions, covering fees, balances, and rent.

> For example, If you were to launch a wallet app on Stellar that people use to send and receive money, Mainnet is where these transactions would happen.

* It is operated by the public, meaning it's decentralized.
    
* It requires Lumens (XLM, Stellar's cryptocurrency) for various actions like covering transaction fees or maintaining account balances.
    
* It supports up to 1,000 operations per ledger and will have specific limits for smart contract transactions(100).
    

#### Testnet(Test Network)

This is a playground for developers to test their applications in an environment that closely mimics the Mainnet but without real money involved. It’s a safe space to experiment without financial risk.

> For example, before you launch the wallet app on Mainnet, you test it first on Testnet to make sure everything works perfectly before deploying it to Mainnet.

* The Stellar Development Foundation (SDF) runs three core validator nodes.
    
* A bot called **Friendbot** gives you free fake XLM to use for testing.
    
* Testnet is limited to 100 operations per ledger and one smart contract transaction per ledger.
    
* Testnet data resets every four months to clear out old data and keep the network clean.
    

#### Futurenet

This network can be called "**Laboratory(experimental)**" where developers can try out cutting-edge features that haven’t yet been rolled out to Mainnet or Testnet. It’s less stable but offers a sneak peek at future updates.

> For example, If Stellar is working on a new feature that your app might use, you could test it on Futurenet before it’s officially released.

The Futurenet also works similarly to Testnet, handling the same number of operations and smart contract transactions per ledger. It is reset periodically and run by the SDF.

It is important to note that when this reset is carried out, all the test accounts and transactions you created will be wiped out. To avoid this when testing, it's recommended to carry out [**Test data automation**](https://developers.stellar.org/docs/learn/fundamentals/networks#test-data-automation) that can automatically refill these networks with the necessary data after they are reset.

### Stellar Consensus Protocol(SCP)

Stellar Consensus Protocol(SCP) is based on an infrastructure called the **FEDERATED BYZANTINE AGREEMENT(FBA)** using the **Proof of Agreement(PoH)** consensus mechanism is different from the common ones like Proof Of Work(PoW) by Bitcoin, Proof of Stake (PoS) or Proof of History(PoH).

Instead of using computational power or staked coins, SCP relies on the agreement of trusted nodes that is nodes trusting specific other nodes (called a **quorum set**) to agree on transactions.

#### How Stellar Consensus Protocol(SCP) works

To have a better understanding of how SCP works, let's use this analogy below:

> Imagine participating in a quiz where the host asks each row to choose a representative to answer questions on their behalf. Your row chooses you to represent them. Every question you answer isn’t just for you; it’s for everyone in your row. With each correct answer, you feel the collective excitement build. And finally, when the quiz ends, you’ve won. But it’s not just your victory—it’s a win for your entire row.

##### **SCP Components Explanation Using the Quiz Analogy**

![SCP component](https://cdn.hashnode.com/res/hashnode/image/upload/v1723554183970/df486cf4-91c2-455e-a0c7-2d7e5968ea9e.png align="center")

* **Quorum Set**
    
    In that quiz, each row had to choose a representative to answer questions. These chosen reps represent the "quorum set" in SCP. Just like your row trusted you to answer on their behalf, in SCP, each node in the network selects a group of other nodes (its quorum set) that it trusts to help decide which transactions should be added to the ledger.
    
* **Thresholds and Quorum Slices**
    
    Let’s say in the quiz, your row decided that they needed the agreement of at least two reps to finalize your answers or theirs. This is like the "threshold" in SCP, where a node requires a certain number of trusted nodes (quorum slice) e.g. two or five nodes to agree before it accepts a transaction. If two or more reps (trusted nodes) agree with you, your answer (decision) is accepted.
    
* **Federated Voting**
    
    When you answered a question in the quiz, your partners also gave their answers. If enough of them agree with you, your answer is accepted. This process mirrors "federated voting" in SCP, where nodes vote on whether to accept a transaction based on the agreement within their quorum set.
    
* **Node Blocking Sets**
    
    Imagine if two reps from different rows consistently disagreed with your answers. They could block your answers from being accepted if they were influential enough. This is similar to "node blocking sets" in SCP, where certain nodes can prevent consensus if they disagree.
    
* **Final Consensus (Winning the Quiz)**
    
    In the quiz, because you answered most questions correctly and other reps agreed with your answers, your row won. This is like reaching the final consensus in SCP. When enough nodes (like the reps) agree on the same transaction, it’s confirmed and added to the ledger, similar to how your correct answers led to your row winning the quiz.
    

### Stellar Core

Stellar Core is the software that powers individual nodes in the Stellar network. These nodes maintain the distributed ledger and participate in the Stellar Consensus Protocol to validate and process transactions, typically reaching consensus and updating the ledger every 5-7 seconds.

For a better understanding, see Stellar Core as the **"Class Captain"** who coordinates the class. Each Student in the class represents a node. The Class Captains (Stellar Core nodes) ensure that all students (nodes) follow the same rules and agree on answers (transactions) every few seconds. After a quick discussion (reaching a consensus), the captains update the class board (ledger) with the latest correct answers.

### Smart Contract Development

Applications on the Stellar Blockchain are created using smart contracts. These are self-executing programmable codes designed to automatically enforce agreements and are trustless. These smart contracts are written in the [Rust programming language](https://www.rust-lang.org/) and compiled into **WebAssembly (Wasm)** for deployment.

Aside from writing smart contracts in Rust, Stellar has a smart contract platform called Soroban. This means that Soroban is a designated system that provides the tools and environment on Stellar for developers to write smart contracts. This makes it possible to create decentralized applications (dApps) and complex financial services directly on the Stellar blockchain.

> Note: Stellar smart contracts use few subsets of full Rust language and must adhere to the specialized libraries.

#### How Smart Contract Works

You will understand this process using an example.

> Imagine you are building an Escrow feature for your E-commerce DApp. Here is the process you will follow:

##### Development process

* [**Soroban Rust SDK**](https://developers.stellar.org/docs/build/smart-contracts/overview#soroban-rust-sdk)
    
    First, you'll use the Soroban Rust SDK to write the smart contract for your escrow feature. The SDK provides you with tools and functions specifically designed for Stellar smart contracts, making it easier to handle tasks like cryptographic hashing, signature verification, and managing on-chain data.
    
    *Example:* You code the escrow logic in Rust, ensuring that funds from a buyer are held securely until the seller fulfils their part of the transaction. This smart contract will only release the funds to the seller once the buyer confirms receiving the goods.
    
* [**Host Environment**](https://developers.stellar.org/docs/build/smart-contracts/overview#host-environment)
    
    The host environment, part of the SDK, allows you to test and debug the smart contract on your local machine before deploying it. It simulates the real blockchain environment, ensuring that your contract behaves as expected.
    
    *Example:* You can run the escrow smart contract on your computer, simulate different scenarios (like the seller failing to deliver), and ensure the contract handles each situation correctly before it goes live.
    

##### Storage and Deployment Process

* [**WASM**](https://developers.stellar.org/docs/learn/fundamentals/stellar-data-structures/contracts#wasm)
    
    After writing the contract, you'll compile it into a [**WebAssembly (WASM)**](https://webassembly.org/) file. This file contains the executable code for your escrow feature and is what will be deployed to the Stellar network.
    
    *Example:* The WASM file is like the final, packaged version of your escrow contract, ready to be installed on the blockchain.
    
* [**Contract Instance**](https://developers.stellar.org/docs/learn/fundamentals/stellar-data-structures/contracts#contract-instances)
    
    Once the WASM file is deployed, you can create multiple instances of the escrow contract. Each instance operates independently but uses the same underlying code. For example, each buyer-seller pair in your E-commerce DApp might use a separate instance of the escrow contract.
    
    *Example:* If five different buyers use your platform to buy from five different sellers, the same escrow contract can be instantiated five times—each handling a separate transaction.
    
* [**Contract Storage**](https://developers.stellar.org/docs/learn/fundamentals/stellar-data-structures/contracts#contract-storage)
    
    The contract storage is where all the data related to your escrow contract is kept on the blockchain. This includes details like the amount of funds held in escrow, the identities of the buyer and seller, and the status of the transaction using either **temporary storage** for short-term data or **persistent storage** for important data that must be retained over time or **Instance storage.**
    
    *Example:* When a buyer initiates an escrow transaction, the contract storage will keep a record of the deposited funds, waiting for the contract’s conditions to be met before releasing the funds to the seller.
    

### Data Querying On Stellar Network

Stellar also keep data querying in mind when building this blockchain. It provides four tools for developers to query network data, submit transactions, and interact with smart contracts without needing to understand the low-level details of Stellar Core, facilitating seamless communications between end-users, apps and Stellar Core.

These four tools are:

#### Remote Procedure Call(RPC)

The **RPC (Remote Procedure Call)** service on the Stellar network provides real-time access to the **current state** of the blockchain within a seven-day retention window. It includes data like account balances and smart contract states.

**Key features:**

* **Current State Information:** Access real-time data, such as account balances and smart contract states, essential for wallets or DApps.
    
* **Transaction Submission:** Send transactions to the network and check their status. Data is retained for seven days.
    
* **Scalability and Simplicity:** Lightweight and easy to scale, ideal for real-time applications needing current data without historical data.
    

##### Soroban-RPC

Soroban-RPC is a specialized version of RPC tailored for Soroban. It provides similar features but is optimized for developers working with Soroban smart contracts. Like the standard RPC, Soroban-RPC focuses on providing current state data, which is ideal for dApps that require the latest information.

Soroban-RPC is designed to be easy to deploy and maintain. Developers can quickly set up an instance using a Docker image, making it accessible without needing extensive infrastructure management.

**Some of the RPC application examples are:**

* **Real-Time Wallet Balances:** A wallet application could use RPC to fetch and display the most recent account balances, ensuring users always see the latest information.
    
* **Smart Contract Interaction:** A dApp built on Soroban might use Soroban-RPC to interact with smart contracts, such as querying the current state of a contract or submitting a transaction to execute a contract function.
    
* **Transaction Monitoring:** A service that tracks transactions could use RPC to provide real-time updates on the status of transactions, such as confirming whether a payment has been processed or is still pending.
    

#### Data Indexer

Data indexers are specialized tools designed to process and organize blockchain data, making it more accessible and easier to query for end users. They transform raw blockchain data into a readable structured format, enabling advanced analysis and more user-friendly interactions with the data.

It offers features such as

1. **Advanced Querying:** Data indexers allow developers to perform complex queries and retrieve specific information from the blockchain, such as filtering transactions based on certain criteria or tracking particular assets.
    
2. **Enhanced Analytics:** They provide features like statistical analysis, visualization of transaction flows, and tracking metrics related to decentralized finance (DeFi).
    
3. **User-Friendly Interface:** By making data more accessible and easier to interpret, data indexers are a more user-friendly and cost-effective choice for users who need to interact with blockchain data beyond basic transaction lookups.
    

> This tool is suitable for apps like Crypto Wallet where your users can have better insights into their transaction history. Instead of just showing a list of transactions, using this data indexer to provide detailed analytics with Charts like [Recharts Package](https://www.npmjs.com/package/recharts), such as spending trends, visualization of how their assets are distributed across different accounts, or even predictive analytics to help them manage their portfolio more effectively.

#### Horizon

Horizon is an HTTP API that acts as a bridge between applications and the Stellar network, making it easier for projects like wallets, decentralized exchanges, and asset issuers to interact with Stellar. It allows users to submit transactions, query account balances, and stream events related to accounts. This API simplifies the process by translating the complex, performance-oriented data of Stellar Core into a more user-friendly format.

Horizon can be accessed via cURL, a browser, or Stellar SDKs. Using SDKs is recommended to reduce complexity when integrating with Stellar. While you can run your own Horizon instance for full operational control, you can also use the publicly available instances provided by the SDF for the testnet and futurenet.

Horizon manages three types of data—**current state, historical state,** and **derived state**—in a single database. This setup allows for real-time transactional use but makes Horizon resource-intensive to operate.

> It's important to note that Horizon does not store smart contract data but does interact with Stellar Asset Contracts (SAC) and smart contract operations like `invokeHostFunction`.

Horizon is suitable for applications like:

* **Decentralized Exchange (DEX):** If you're building a DEX on Stellar, Horizon allows you to access current and historical data about asset trades, manage order books, and process transactions securely.
    
* **Asset Issuance:** For entities looking to issue new assets on the Stellar network, Horizon facilitates the creation, management, and distribution of these assets, while also tracking their movement across accounts.
    

#### Hubble

Hubble is an open-source, publicly accessible dataset that provides a comprehensive historical record of the Stellar network. Unlike Horizon, which is geared towards real-time transaction processing, Hubble is optimized for handling large-scale, analytic workloads. In a simple term, See Hubble as a "**Lable"** that can be used to shove all the records from the Stellar pot(network) onto a plate.

This tool is used when you want to handle complex queries that might cause performance issues or timeouts in Horizon. For example, if you need to analyze transaction patterns over several years or perform cross-chain analytics, Hubble is the right tool.

Also If your project requires access to the entire history of the Stellar network, such as tracking asset movement or analyzing network growth over time, Hubble provides the necessary data without the limitations of Horizon’s storage and real-time processing.

Use case includes:

1. **Financial Analytics:** A financial analyst might use Hubble to track the historical performance of a specific asset on the Stellar network, analyzing transaction volumes, price changes, and market trends over several years.
    
2. **Research and Development:** A blockchain researcher could use Hubble to study the adoption rates of Stellar’s features by analyzing how often certain types of transactions have been used over time.
    
3. **Cross-Chain Analytics:** By using BigQuery’s capabilities, a developer can compare Stellar network data with data from other blockchains to identify trends, correlations, or opportunities for interoperability.
    

### [Stellar SDK](https://developers.stellar.org/docs/tools/sdks/library)

Stellar’s Software Development Kits (SDKs) provide devs with the tools, libraries, and documentation to interact with and develop on the blockchain.

The SDK Library allows developers to interact with the Stellar network using various programming languages.

Here are the following programming language SDKs available:

* **JavaScript SDK:** Used for building Stellar apps on Node.js or in the browser. It interacts with Soroban RPC and Horizon APIs for transaction management.
    
* **Python SDK:** Ideal for Python developers to build Stellar apps, offering tools for transaction management and Horizon API communication.
    
* **iOS SDK:** Supports iOS and Mac development, allowing for transaction management and interaction with Soroban smart contracts.
    
* **Flutter SDK:** Tailored for Flutter developers, enabling transaction handling and Soroban smart contract deployment.
    
* **PHP SDK:** A PHP tool for building Stellar apps, managing transactions, and working with Soroban smart contracts.
    
* **Go SDK:** Split into packages for transaction construction and Horizon API interaction.
    
* **Rust SDK:** A Rust crate for Soroban, essential for developers working with the Soroban smart contract platform.
    

### Anchors and Anchor Platform

Anchors are important components of the Stellar network, acting as on and off-ramps connecting traditional financial systems and blockchain technology. Anchors allow users to transfer fiat currencies such as the US dollars or Nigerian naira, and receive an equivalent digital token on the Stellar network. Anchors also provide digital token redemption for real-world assets.

Stellar hosts a global network of anchors, and businesses can use the Anchor Platform to create their anchor services. The Anchor platform consists of tools and APIs to easily create on-off-ramp services, using standard interfaces and stellar ecosystem offerings (SEPs) with stellar wallets and exchanges The easy-to-integrate platform supports asset management, connection services, and user account management, and offers flexible deployment options such as Docker and Kubernetes.

Remember when I told you earlier that I was seeking a solution for cross-border exchange like sending BTC and receiving it in USDT? This is a perfect use case for this.

You can build an entire Fintech company solely on this component alone e.g. **EasySend(a fintech company)** wants to offer a cross-border remittance service between the United States and Nigeria, allowing users to send money from the U.S. to recipients in Nigeria quickly and at a low cost.

**How It Works:**

1. **On-Ramp (U.S. Anchor):**
    
    * EasySend partners with a U.S.-based anchor that integrates with the Stellar network.
        
    * A customer in the U.S. deposits U.S. dollars into the anchor’s bank account through a traditional payment method, such as a bank transfer or credit card.
        
    * The U.S. anchor issues equivalent digital tokens (e.g., USDT or USDC) on the Stellar network, which are credited to the customer's Stellar wallet.
        
2. **Cross-Border Transfer:**
    
    * The customer uses their Stellar wallet to send the USD tokens to a recipient in Nigeria. The transaction occurs almost instantly on the Stellar network, with minimal fees.
        
3. **Off-Ramp (Nigerian Anchor):**
    
    * The Nigerian recipient partners with a local anchor that can convert digital tokens into Nigerian naira.
        
    * The recipient receives the USD tokens in their Stellar wallet and redeems them through the Nigerian anchor.
        
    * The Nigerian anchor exchanges the USD tokens for Nigerian naira and deposits the naira into the recipient's bank account or provides it as cash at a physical location.
        

### Operation, Transaction Process and Fee

The final thing that developers need to understand is how actions affect stellar networks.

#### Operation

Operations are the individual actions that modify the Stellar ledger from their account. For example, sending payments, invoking smart contracts, or changing account settings. Each operation has a threshold level (low, medium, or high) that determines the required signature weight for authorization. For example, if an account’s medium threshold is set to 5, the combined signature weight for operations needing a medium threshold must meet or exceed 5. Operations in smart contract transactions are limited to one per transaction.

#### Transaction

Having understood that an Operation is a singular action that modifies the Stellar ledger then how are these several operations processed on the Stellar network?

Remember when you are learning about Stellar Networks, you learn that Mainnet supports up to 1,000 operations and 100 smart contract transactions per ledger while Testnet and Futurenet can only take up 100 operations and 1 smart contract transaction per ledger. This is what a Transaction does, it bundles up these several operations and smart contract transactions and processes them.

Transactions must be signed and authorized by the source account's public key, and if multiple signatures are needed (e.g., when the transaction affects more than one account), they must meet the required threshold weight.

> Note: Transactions are atomic in the sense that if one operation or a smart contract transaction fails, the entire transaction fails.

Another thing to note is before submission, transactions undergo several validity checks, grouped into three categories: preconditions, operation validity, and transaction validity.

* Preconditions are optional, like time bounds or minimum sequence numbers, and help define when a transaction is valid.
    
* Operation validity checks ensure the operations meet signature, format, and protocol version requirements.
    
* Transaction validity checks include verifying the source account’s existence, fee payment, and correct sequence number.
    

![Operations and transaction illustration](https://cdn.hashnode.com/res/hashnode/image/upload/v1723719284379/a5a1ae06-811d-421c-970a-3f47630d71f2.png align="center")

#### Fees

As you know every blockchain requires gas fees to process transactions using the blockchain token. As for stellar, Fees are paid in XLM and include a *Resource Fee* for smart contract transactions, based on resource consumption, and an *Inclusion Fee*, the maximum amount willing to be paid for ledger inclusion.

* **Resource Fees**: Applied to smart contract transactions, calculated based on resource consumption (CPU, memory, etc.). They are non-refundable except for specific components like rent or events.
    
* **Inclusion Fees**: The maximum amount a user is willing to pay for a transaction to be included in the ledger. These vary depending on network conditions and surge pricing.
    

Smart contract transactions undergo metering to account for resource costs. Strategies for managing fees include setting a high maximum fee or using fee-bump transactions to ensure inclusion during surge pricing.

## Conclusion

You must have experienced some "wow" when you read this article, Yes that's the whole essence of this article. This article has exposed you to core concepts and components of Stellar Blockchain such as Stellar Network, Stellar Core, Anchor, SCP, Stellar SDK, Operation and Transaction processing and fees, Data querying and Smart contract development.

### References

[Stellar Site](https://stellar.org/)

[Stellar Developers' Doc](https://developers.stellar.org/)

[Stellar Discord channel](https://discord.gg/st7Mxd58BV)

[Developers' Blog](https://www.stellar.org/developers-blog)

[Stellar Community Fund](https://communityfund.stellar.org/)

[GitHub page](https://github.com/stellar)

[Community Fund](https://communityfund.stellar.org/)