---
title: "Deep Dive on ZK on Solana vs Ethereum"
seoTitle: "Deep Dive on ZK on Solana vs Ethereum"
seoDescription: "Comparison of zk Rollups on Ethereum and zk Compression on Solana: efficiency and scalability within blockchain technology"
datePublished: Sun Jul 07 2024 04:51:44 GMT+0000 (Coordinated Universal Time)
cuid: clyb2tedo000509iffweh4exk
slug: deep-dive-on-zk-on-solana-vs-ethereum
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1720298948894/cffe6bdc-3e08-4fea-846f-8d72a52fe542.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1720327838364/45d4b79b-c267-461e-8384-5b35403e2489.png
tags: blockchain, ethereum, web3, solana, zkevm, zk-snark, zkrollup, zkcompression

---

## Chaos in Fine Dresses

It was my friend's 25th birthday party. Plans had been made, and friends had travelled from far away to celebrate with her. The large crowd that showed up proved she was popular and friendly. I was part of the organizing team, but we only planned to cater to 100 guests, with invites sent to selected friends and family.

At first, only 30 guests were present at the set time for the party. We were all dressed up for the occasion, including her and her family. In less than two hours, the venue filled up. We had no idea how it happened. At some point, I got worried because the number of guests far exceeded what we had budgeted for.

The worst part came like a young plant sprouting overnight. When it was time to share the food and souvenirs, the first round was given to the guests. However, we couldn't tell if some guests collected twice or not. All we knew was that 100 items couldn't reach all the initial guests.

If only I had known, I would have worn trousers and a shirt. But no, the guests who didn't get souvenirs started ranting soon after, causing chaos in our fine dresses.

Funny but not funny, this is the same scenario occurring in both Ethereum and Solana. In this article, you will learn about zkRollups as a scaling solution in Ethereum and ZK compression as data storage optimization in Solana, how they work, key comparisons, and their use cases.

## Introduction **zk Rollups on Ethereum**

Before we dive deeply into zk Rollups, it is important to understand why they are in existence. In Blockchain technology, there is something called **Blockchain Trilemma**.

![The DBS Guide to the Blockchain Trilemma](https://www.dbs.com.sg/iwov-resources/media/images/articles/nav/what-is-the-blockchain-trilemma/b.jpg align="left")

The **Blockchain Trilemma** is a significant challenge that every blockchain faces in achieving mass adoption. It refers to the difficulty of simultaneously optimizing three core components: decentralization, security, and scalability. Essentially, blockchains often have to make trade-offs between these elements based on their goals and priorities. For instance, Bitcoin and Ethereum prioritize security and decentralization, but this comes at the cost of limited scalability leading to sluggishness in transaction processes.

### What are Rollups?

![Rollups - Layer 2 Scaling | Is it the Next Big Thing? - CoinCodeCap](https://coincodecap.com/wp-content/uploads/2021/09/image-48.png align="left")

This trilemma has led to the development of various layer-2 scaling solutions, such as rollups, to address the scalability issue without compromising security and decentralization. Rollups work by processing transactions off-chain and then submitting a single batch of transactions to the main blockchain.

Picture rollups like this: Imagine a spreadsheet listing the number of students and food choices for each class. Instead of each student submitting their food choices directly to the school principal, the teacher of each class collects the students' food choices based on quantity. Then, the headmaster processes this information and submits it as a single document instead of several documents as seen below.

| Class | Number of Students | Noodles | Rice | Pasta |
| --- | --- | --- | --- | --- |
| Pry one | 10 | 2 | 5 | 3 |
| Pry Two | 20 | 4 | 10 | 6 |
| Pry Three | 13 | 10 | 0 | 3 |

This approach significantly reduces the amount of data that needs to be processed by the principal(on-chain), thereby enhancing scalability while maintaining the security and decentralization of the underlying blockchain.

### Types of Rollup

There are two types of Rollups, categorized based on how they validate transactions off-chain.

1. **Optimistic Rollups**
    
    Optimistic Rollups, as the name suggests, assume that transactions are valid by default and only check for fraud if someone challenges a transaction within a certain period. For example, the servers trust that everyone in the party will give an honest order but have a security measure in place to verify and correct any discrepancies if someone raises a concern.
    
    **Examples of Optimistic Rollups**: Optimism, Arbitrum.
    
2. **zk Rollups**
    
    zk Rollups, on the other hand, use "**zero-knowledge proofs**" to prove each batch of transactions correct by having a **validity proof** submitted on-chain for every batch of transactions. For example, the servers are not just collecting the order from the guests but also verifying each order's accuracy before submitting them to the caterer, ensuring that all orders are correct without needing to rely on trust.
    
    **Examples Of zk Rollups:** zkSync Era, StarkNet, Polygon zkEVM.
    

### zk-Rollups On Ethereum

To understand zk Rollups more deeply, let's elaborate on the birthday party analogy. You are at your best friend's birthday party, which is bustling with guests. Everyone wants to get food from the caterer. Some servers collect all the orders, place a tag on each person to signify they have placed an order, and then go to the caterer to get all the food at once. This way, the caterer only has to process one large order instead of many small ones, making the process much more efficient.

zk Rollups, also known as zero-knowledge Rollups, are like the servers at that party. [They](https://chain.link/education-hub/zero-knowledge-rollup) are layer-2 scaling solutions that move computation and state off-chain into off-chain networks while storing transaction data on-chain on a layer-1 network (like Ethereum).

Think of them as the servers at the birthday party who take orders (multiple transactions) from the guests (users), validate and organize them before going to the caterer (processed off-chain), and then submit the order as a single batch. They work by bundling or "rolling up" multiple transactions into one batch, then processed off-chain. The key feature of zk Rollups is using **zero-knowledge proofs** to ensure the validity of these transactions instead of **assuming** just like the tag on the hands of the guest**.**

### How do they work on the Ethereum network?

zk Rollups interact with the Ethereum network in a structured and efficient manner to enhance scalability while maintaining security and decentralization. Here’s a detailed breakdown of how they work:

1. **Batching Transactions**: Multiple transactions are aggregated into a single batch off-chain. This process involves collecting numerous individual transactions and combining them into one larger transaction. This reduces the number of transactions that need to be processed on the Ethereum mainnet.
    
2. **Generating Proofs**: A zero-knowledge proof (specifically, a zk-SNARK or zk-STARK) is generated to prove the validity of the entire batch of transactions. Zero-knowledge proofs allow one party to prove to another that a statement is true without revealing any information beyond the validity of the statement itself. This ensures that all transactions in the batch are valid without needing to process each transaction individually.
    
3. **Submitting Proofs**: The proof and a minimal amount of data are submitted to the Ethereum mainnet. This submission includes the zero-knowledge proof and some essential data required to verify the proof on-chain.
    
4. **Verification**: The Ethereum network verifies the proof, ensuring that all transactions in the batch are valid. This verification process is efficient and does not require the Ethereum network to process each transaction individually. Instead, it only needs to verify the zero-knowledge proof, which is computationally less intensive.
    
5. **Updating State**: Once the proof is verified, the state of the Ethereum blockchain is updated to reflect the transactions in the batch. This includes updating account balances, smart contract states, and other relevant data.
    
6. **Data Availability**: zk Rollups ensure that the data required to reconstruct the state is available on-chain. This is crucial for maintaining the security and decentralization of the network, as it allows anyone to verify the correctness of the state transitions.
    

![https://medium.com/fcats-blockchain-incubator/how-zk-rollups-work-8ac4d7155b0e](https://miro.medium.com/v2/resize:fit:700/1*Qp1F1a5D5xMTplZsxVcisQ.png align="left")

By following these steps, zk Rollups significantly reduce the amount of data that needs to be processed and stored on-chain, leading to improved scalability and lower transaction costs. This makes Ethereum more efficient and capable of handling a higher volume of transactions without compromising on security or decentralization.

## **Introduction to zk Compression on Solana**

To understand what ZK Compression is, imagine a birthday party with hundreds of guests. Instead of each guest going to the caterer individually, the servers take the guests' orders. This time, instead of showing the number of guests and a list of their food choices to the caterers, the servers verify and encode these details, reducing the amount of data given to the caterer and the data processing needed.

The caterer then decodes these details and verifies them. Once verified, the caterer prepares the food, serves it, and sends it out in batches to the guests. This technique reduces the amount of time the caterer needs to handle the data processing.

For example, The order looks like this

| Row 1 | Row 2 | Row 3 |
| --- | --- | --- |
| 2459 | 4389 | 1023 |

Let's decode the orders:

1. **2459** = 2 plates of Rice, 4 plates of pasta, 5 plates of Chicken Soup, 9 plates of Lobster Sauce.
    
2. **4389** = 4 plates of Rice, 3 plates of Pasta, 8 plates of Chicken Soup, 9 plates of Lobster Sauce.
    
3. **1023 =** 1 plate of Rice, no order for Pasta, 2 plates of Chicken Soup, 3 plates of Lobster Sauce.
    

ZK Compression can be likened to this technique. ZK Compression is a new primitive [built on Solana](https://www.zkcompression.com/) that enables developers to build applications at scale. It is used on the Solana network to optimize data storage and transaction processing. This technology leverages zero-knowledge proofs to compress data, ensuring that only essential information is stored on-chain while maintaining the integrity and security of the transactions.

To elaborate, zero-knowledge proofs allow one party to prove to another that a statement is true without revealing any specific details about the statement itself. In the context of ZK Compression on Solana, the network can verify the validity of transactions without needing to store all the detailed data associated with each transaction. Instead, only the proof and the essential data are stored, significantly reducing the amount of data that needs to be processed and stored.

For instance, consider the caterer analogy. The caterer (Solana) doesn't need to know the exact number of people who ordered each specific dish (individual transactions). Instead, the caterer receives a compressed summary of the orders that have been verified for accuracy. This summary is much smaller in size compared to the full list of orders, making it easier and faster for the caterer to process and serve the food.

By using ZK Compression, Solana can handle a higher volume of transactions more efficiently. This not only speeds up the network but also reduces the storage requirements, making it more cost-effective for developers and users. Furthermore, the use of zero-knowledge proofs ensures that the security and integrity of the transactions are not compromised, even though less data is being stored on-chain.

### Important of ZK Compression to the Solana Network

The importance of ZK Compression to the Solana Network lies in its ability to optimize data storage and transaction processing. By compressing data using zero-knowledge proofs, zk Compression ensures that only essential information is stored on-chain, significantly reducing the amount of data that needs to be processed and stored. This leads to faster transaction times and lower costs, enhancing the network's overall efficiency.

Also, ZK Compression maintains the integrity and security of transactions, ensuring that all data is accurate and verifiable without revealing unnecessary details. This makes it particularly valuable for data-intensive applications, IoT devices, and supply chain management, where efficient data handling and security are crucial. Zk Compression helps Solana scale effectively, supporting a wide range of applications while maintaining high performance and security.

### How does it function on the Solana network?

ZK Compression on Solana functions by optimizing data storage and transaction processing through the use of zero-knowledge proofs.

According to [Zk-compression](https://www.zkcompression.com/learn/in-a-nutshell): this is the breakdown.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720266230559/47c578ab-05ad-4b2c-bfdb-9dc9a108a692.png align="center")

Here’s a detailed breakdown in simple terms:

1. **Data Collection**: Think of this step like a server at a party collecting orders from multiple guests. In zk Compression, data is gathered from various transactions or sources. This step ensures that all necessary information is collected before moving on to the next phase.
    
2. **Data Encoding**: Once the data is collected, it is encoded. This is similar to compressing a large file into a smaller zip file on your computer. The encoding process reduces the size of the data, making it more manageable and easier to handle. This compressed format is what will be submitted on-chain.
    
3. **Zero-Knowledge Proofs**: After encoding, zero-knowledge proofs are generated. These proofs are like a secret handshake that confirms the data is correct without revealing all the details. They allow the network to verify the accuracy and validity of the compressed data without having to go through each transaction.
    
4. **On-Chain Submission**: The next step is submitting the compressed data and the zero-knowledge proofs to the Solana blockchain. This submission is streamlined to include only the essential information needed to verify the data. By doing this, the amount of data stored on-chain is significantly reduced, which helps in maintaining efficiency and speed.
    
5. **Verification and Decoding**: Once the data is on-chain, the Solana network uses zero-knowledge proofs to verify the integrity and accuracy of the data. This step is crucial as it ensures that the data has not been tampered with and is correct. After verification, the data can be decoded back into its original form and used as needed for various applications.
    

## **Key differences between zk Rollups and zk Compression on Ethereum and Solana**

Key differences between zk Rollups and zk Compression on Ethereum and Solana, respectively

1. **Purpose**
    
    * **zk Rollups on Ethereum**: **The primary goal of zk Rollups is to enhance the scalability of the Ethereum network.** They achieve this by bundling multiple transactions into a single batch, which reduces the load on the Ethereum mainnet. This makes it possible to handle a higher volume of transactions without compromising security or decentralization.
        
    * **zk Compression on Solana**: **zk Compression aims to optimize data storage and transaction processing on the Solana network**. Compressing data using zero-knowledge proofs, ensures that only essential information is stored on-chain, leading to faster transaction times and lower costs. This is particularly valuable for data-intensive applications.
        
2. **Implementation**
    
    * **zk Rollups on Ethereum**: use zero-knowledge proofs (zk-SNARKs or zk-STARKs) to validate batches of transactions off-chain. The process involves batching transactions, generating proofs, submitting these proofs along with minimal data to the Ethereum mainnet, and then verifying the proofs on-chain. This ensures that all transactions in the batch are valid without processing each one individually.
        
    * **zk Compression on Solana**: collects data from multiple transactions or sources, encodes it into a compressed format, and generates zero-knowledge proofs to ensure the validity of the compressed data. The compressed data and proofs are then submitted to the Solana blockchain, where they are verified and decoded as needed. This reduces the amount of data stored on-chain.
        
3. **Layer-1 vs. Layer-2**
    
    * **Layer-2 Solution**: zk Rollups are a layer-2 scaling solution. They operate on top of the Ethereum mainnet (layer-1) and offload transaction processing to an off-chain network. The mainnet is only used to store minimal data and verify zero-knowledge proofs. This approach allows Ethereum to scale without altering its underlying layer-1 protocol.
        
    * **Layer-1 Optimization**: zk Compression is a layer-1 optimization technique. It directly enhances the Solana blockchain by optimizing how data is stored and processed on-chain. Unlike layer-2 solutions, which operate on top of an existing blockchain, zk Compression improves the efficiency of the layer-1 network itself.
        
4. **Transaction Costs**
    
    * **zk Rollups on Ethereum**: They reduce transaction costs by bundling multiple transactions into a single batch, which is then processed off-chain. This reduces the gas fees associated with each transaction.
        
    * **zk Compression on Solana**: By compressing data and reducing the amount of information stored on-chain, zk Compression lowers the overall costs associated with data storage and transaction processing.
        
5. **Data Handling**
    
    * **zk Rollups on Ethereum**: Primarily focus on transaction data, ensuring that multiple transactions are validated and processed efficiently.
        
    * **zk Compression on Solana**: Focuses on optimizing both transaction and non-transactional data, making it suitable for a wider range of applications that require efficient data handling.
        
6. **Scalability**
    
    * **zk Rollups on Ethereum**: Enhance scalability by reducing the load on the Ethereum mainnet, allowing it to handle more transactions per second.
        
    * **zk Compression on Solana**: Improves scalability by minimizing the data footprint on the blockchain, which allows for faster processing and higher throughput.
        
7. **Security**
    
    * **zk Rollups on Ethereum**: Maintain security by using zero-knowledge proofs to validate transactions, ensuring that all transactions in a batch are correct.
        
    * **zk Compression on Solana**: Uses zero-knowledge proofs to ensure the integrity and accuracy of compressed data, maintaining security while optimizing storage.
        
8. **Flexibility**
    
    * **zk Rollups on Ethereum**: Primarily designed for financial transactions and applications that require high transaction throughput.
        
    * **zk Compression on Solana**: Offers flexibility for various types of data-intensive applications, including IoT devices and supply chain management, beyond just financial transactions.
        

## Use Cases

### **zk Rollups on Ethereum**

1. **DeFi Applications**: zk Rollups significantly enhance the scalability of decentralized finance platforms. By reducing transaction costs and increasing throughput, they enable more users to participate in DeFi activities such as lending, borrowing, and trading without experiencing network congestion or high fees e.g. [zkSync Paymaster](https://docs.zksync.io/build/zksync-101/paymaster).
    
2. **NFT Marketplaces**: zk Rollups facilitate faster and cheaper transactions for buying, selling, and trading non-fungible tokens. This improvement is crucial for NFT marketplaces where quick and cost-effective transactions can enhance user experience and drive higher volumes of trading activity. e.g [Immutable](https://www.immutable.com/products/trade)
    
3. **Gaming**: In the realm of blockchain-based games, zk Rollups support high-frequency transactions. This capability is essential for games that require rapid in-game transactions, such as buying items, trading assets, or participating in multiplayer events, ensuring a smooth and responsive gaming experience. E.g. [StarkNet Gaming SDKs](https://www.starknet.io/developers/tools-and-resources/#gaming-sdks) and [Immutable X](https://www.immutable.com/games-studio).
    

### **zk Compression on Solana**

1. **Data-Intensive Applications**: zk Compression optimizes storage and processing for applications that handle large amounts of data. This includes decentralized storage solutions where efficient data compression can reduce storage costs and improve retrieval times, making it easier to manage and access vast datasets. e.g
    
2. **IoT Devices**: For Internet of Things devices connected to the Solana network, zk Compression ensures efficient data transmission and storage. This is particularly important for IoT ecosystems where devices generate continuous streams of data that need to be securely and efficiently processed and stored on the blockchain.
    
3. **Supply Chain Management**: In supply chain applications, zk Compression streamlines data management and verification processes. Minimizing the data footprint and ensuring the integrity of compressed data, allows for more efficient tracking, verification, and management of goods as they move through the supply chain, enhancing transparency and reducing the risk of errors or fraud.
    
4. **Token Airdrops**: zk Compression significantly reduces the cost of airdropping tokens to a large number of wallets. For instance, airdropping tokens to a million wallets on Solana would typically cost over $260,000, but with zk Compression, the cost drops to $50, making it 5200 times cheaper.
    
5. **NFT Projects:** On Solana, creating multiple NFTs involves creating multiple accounts, which can be costly due to storage requirements on validator nodes. Zk Compression allows developers to combine many accounts into one, reducing costs significantly by storing the data more efficiently on the ledger and using cryptographic links for integrity.
    

Some projects like [Drip](https://drip.haus/), [Helium](https://docs.helium.com/solana/), and [Hivemapper](https://hivemapper.com/network/coverage) utilize ZK compression in their Applications.

## **Conclusion**

Both zk Rollups on Ethereum and zk Compression on Solana offer significant advancements in blockchain technology. zk Rollups enhance Ethereum's scalability, making it suitable for high-transaction applications like DeFi and gaming. zk Compression on Solana optimizes data storage and processing, crucial for data-intensive applications and NFT projects etc.

## References

[The DSB Guide to Blockchain Trilemma](https://www.dbs.com.sg/personal/articles/nav/investing/what-is-the-blockchain-trilemma#:~:text=The%20Blockchain%20Trilemma%20refers%20to,this%20poses%20challenges%20to%20scalability.)

[What are Blockchain Rollups?](https://www.cyfrin.io/blog/what-are-blockchain-rollups-a-full-guide-to-zk-and-optimistic-rollups#:~:text=A%20blockchain%20rollup%20is%20an,transactions%20in%20the%20transaction%20rollup.)

[Top 5 zk-Rollup Projects](https://blog.thirdweb.com/zk-rollups-projects/)

[Spectacular New Solana Tech: Zk-compression and Blinks](https://thewealthmastery.io/spectacular-new-solana-tech-zk-compression-and-blinks/)

[How zk-Rollups Work](https://medium.com/fcats-blockchain-incubator/how-zk-rollups-work-8ac4d7155b0e)

[ZK Compression](https://www.zkcompression.com/learn/in-a-nutshell)

[**ZK Compression: Solana's Revolutionary Scaling Solution Explained ...**](https://solanacompass.com/learn/Lightspeed/the-next-era-of-solana-scaling-swen-schaferjohann)

[**ZK Compression on Solana Explained: New Era of L1 Scalabili**](https://solanacompass.com/learn/Lightspeed/the-next-era-of-solana-scaling-swen-schaferjohann)[**ty?**](https://www.techopedia.com/zk-compression-on-solana-explained-new-era-of-l1-scalability)

[**Gami**](https://www.techopedia.com/zk-compression-on-solana-explained-new-era-of-l1-scalability)[**ng Committee Launch - Advancing Starknet's Gaming Ecosystem**](https://solanacompass.com/learn/Lightspeed/the-next-era-of-solana-scaling-swen-schaferjohann)

[**R**](https://solanacompass.com/learn/Lightspeed/the-next-era-of-solana-scaling-swen-schaferjohann)[**edefining On-Chain Gaming with Starknet | Starknet**](https://www.techopedia.com/zk-compression-on-solana-explained-new-era-of-l1-scalability)

[**Building C**](https://www.techopedia.com/zk-compression-on-solana-explained-new-era-of-l1-scalability)[**omplex, Fully Onchain Games with Starknet | Starknet**](https://www.starknet.io/blog/building-complex-fully-onchain-games-with-starknet/)

[The Battle against L2s: Solana Introduces ZK Compression](https://hackernoon.com/the-battle-against-l2s-solana-introduces-zk-compression)

[**Solana Compass - The Next Era of Solana Scaling**](https://solanacompass.com/learn/Lightspeed/the-next-era-of-solana-scaling-swen-schaferjohann)

[**Case Study: Hivemapper decentralizes mapping with better real-time data ...**](https://solana.com/news/case-study-hivemapper)