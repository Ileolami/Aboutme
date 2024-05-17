---
title: "From Queues to Quickness: zkSync's Role in Enhancing Ethereum's Scalability"
seoTitle: "A deep dive into zkSync."
seoDescription: "zkSync enhances Ethereum's scalability with faster, cheaper transactions using Layer 2 rollups, improving efficiency and reducing congestion"
datePublished: Fri May 17 2024 17:24:02 GMT+0000 (Coordinated Universal Time)
cuid: clway8fk5000i09mmfierak9b
slug: deep-dive-into-zksync-protocol
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715803396274/181a859d-f723-40da-8afc-3b0914b82d2d.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1715966441191/e88b7b24-a158-4932-9106-5a2be76afb09.png
tags: ethereum, layer2, zkevm, zk-snark, zkrollup

---

## The Promising Event

%[https://media.giphy.com/media/0TA0cVV34ECtkaAuOF/giphy.gif?cid=790b7611is4tmymyrto2yntq63st4lg89fnme5hmvkkdlcgo&ep=v1_gifs_search&rid=giphy.gif&ct=g] 

Two months ago, I attended a web3 conference. The event promised to be insightful with plenty of swag and food. People arrived as early as 7 AM to secure a spot. Surprisingly, the hall was almost full by the time I arrived at 7:15 AM, showing the impact of the event's ads. Not only that, the entry was free.

The event started at the scheduled time of 10 AM. The community manager gave a welcome speech and an overview of the event, including their mission, goals, and past meetups they have organized around the country.

There's a saying, "Good things don't last forever." The event began well, with three sessions on insightful topics, without further ado, the host announced, "Breakfast is ready," People were directed to the food section using a "one row after the other" protocol. It took 30 minutes for each row to get their food, so if you were in the fourth row, you could expect to get your food in about 2 hours.

Despite the promise, the distribution process was slow and inefficient. By the time it got to the last row, there was only a little food left. So, the last people had to share what remained among themselves.

Well, people didn't grumble or complain about the arrangement. After all, "you don't judge a book by its cover," as they say. The event continued with games between each session to lift people's spirits.

### The Chaos

There is no beginning without an end, they say. The event came to a close. Swags were already been distributed during the breakout session. It was time for lunch, and the same protocol used for breakfast was applied. However, this time they started with the last row, which was my row. The process was going smoothly until we heard, "The food is finished." This was around 6:15 PM due to the long queue and slow serving method.

Before we knew it, the event turned chaotic. Some men had beaten the caterer, two servers escaped through the fence, a few punches landed on the host's face, and one of the organizers had her wig snatched away. It was hilarious but also unfortunate situation because people's time was wasted due to the poor serving procedure.

### The Wise Solution

In the middle of this chaos, someone said, "This is unfair; the food should have been served inside the hall while people were seated." Everyone agreed, saying "YES" in unison. That was a good solution because it was the same way the swags were distributed, ensuring everyone got their own.

This scenario is like the scalability issue in the Ethereum blockchain. Just as the event organizers struggled to serve breakfast and lunch efficiently, Ethereum faces challenges with many transactions at once.

When too many transactions happen, the network gets congested, causing delays and higher fees. This is similar to attendees waiting in long queues and some not getting served. Rollup Protocols like [zkSync](https://docs.zksync.io/) aim to improve Ethereum's scalability with faster and cheaper transactions.

You may be wondering what Rollups are, but don't worry, this article is going to educate you on what Rollups are, An overview of zkSync, its unique features and why you should use it in your next DApp projects.

## What are Rollups?

%[https://media.giphy.com/media/l4EoUd4mUQbgu7yxi/giphy.gif?cid=790b7611rt8dmhtpka4tkzx1ew9hixkvd7auztjngg8icwcx&ep=v1_gifs_search&rid=giphy.gif&ct=g] 

Picture this: what if a server went to each row to take orders on behalf of everyone? He would go to the food section, sort out the orders himself, get the food, and then share it with the people. That's easier and faster than the long queue protocol.

This is the solution Rollups provided to increase Ethereum's scalability. Rollups are Layer 2 (L2) protocols that sort out calculations off-chain and then bundle multiple transactions together into a single transaction that is then posted on-chain. This reduces congestion and increases the speed and efficiency of the network.

There are currently two types of Rollup, they are

1. **ZK Rollups**: also known as Zero Knowledge Rollups. In this case, the server verifies the orders, processes the orders and submits the orders as a single order to the chef without revealing the details or number of persons involved. Similar to this technique, ZK rollups use Zero-knowledge proof to validate transactions off-chain. Examples of ZK Rollups are Starknet, zkSync etc
    
2. **Optimistic Rollups:** In this case, the server assumes that all orders are correct and processes them quickly, but if the chef disputes an order, it can be checked and corrected. Similarly, Optimistic Rollups assume transactions are valid and only verify them if challenged, which helps in reducing the load on the main Ethereum chain. Examples of Optimistic Rollups are Arbitrum Optimism.
    

> Now that you've understand what Rollups, which type of Rollups will you use and why?
> 
> Leave your answer in the comment section.

## An Overview of zkSync

By now, you must have grasped what zkSync is all about.

Accroing to zkSync doc:

> **zkSync Era** is a [**ZK rollup**](https://docs.zksync.io/build/developer-reference/rollups.html#what-are-zk-rollups), a trustless protocol that uses cryptographic validity proofs to provide scalable and low-cost transactions on Ethereum. In zkSync Era, computation is performed off-chain and most data is stored off-chain as well. As all transactions are proven on the Ethereum mainchain, users enjoy the same security level as in Ethereum.

What distinguishes zkSync is the lower gas fee rate. Not only that, it gives you the same user experience with Ethereum and it is also compatible with other Ethereum wallets.

To better understand how zkSync roll-up transactions:

* **A user creates a transaction:** During the event you order for Jollof rice and chicken(transaction).
    
* **Operator creates a rollup operation and adds it to a block:** The server writes down your order on a piece of paper(rollup operation) and adds it to a stack of other orders for the day (block).
    
* **Block submission:** Once the kitchen gets busy and the stack reaches a certain size (complete block), the server submits it to the manager (zkSync smart contract).
    
* **Partial logic check:** The manager quickly skims the chits (checks part of the logic) to ensure they're all of the same orders and not something else (valid transaction types).
    
* **Block verification and finality:** The server then calculates the total amount from all the orders (proof for the block) and submits it to the manager. If the total matches the cash register (verification succeeds), the manager marks the orders complete (new state is final).
    

## What makes zkSync Unique?

%[https://media.giphy.com/media/ed1z6Wyr4HJvaKFXSx/giphy.gif?cid=790b76110ge5is2qgk0bpkskzz03h2rl1ohr3vla8fpz2jjl&ep=v1_gifs_search&rid=giphy.gif&ct=g] 

Apart from enhancing Ethereum's scalability and performing transactions off-chain to speed up the process, zkSync has some unique features. They are:

1. **Native Account Abstraction(AA)**: zkSync is the first Ethereum Virtual Machine (EVM)-compatible chain to implement native account abstraction.
    
    This feature allows [**contract accounts**](https://ethereum.org/en/developers/docs/accounts/#contract-accounts) to initiate transactions like [**Externally Owned Accounts**](https://ethereum.org/en/developers/docs/accounts/#externally-owned-accounts-and-key-pairs) (EOA) and still contain logic implementation.
    
    Consider EOAs as chefs who only serve food, while Contract Accounts are servers who handle the food. Before AA was implemented, chefs could also dish out and receive food, while servers just sorted the orders. With AA, servers can now dish out food and receive it, even after verifying and processing the orders.
    
    Another interesting thing is that wallets created by this feature enable users’ Social Recovery. (Recovering accounts without the need for their private key). Wallets like [Argent](https://www.argent.xyz/argent-x/) and [Blockwallet](https://blockwallet.io/) use this feature.
    
2. **Bridging Asset:** Bridging asset refers to the process of transferring digital assets between zkSync and other blockchains. Picture it like this, zkSync is a country that only uses the Naira as its only currency. The naira is not accepted in other countries(other blockchains).
    
    To trade with other countries(other blockchains), the citizens build secure banks (bridges) allowing them to exchange Naira for widely accepted currencies like "Dollars" (Ethereum's ETH) or "Arts"(NFTs).
    
    zkSync allows developers to build a free custom bridge for any token provided with a default bridge. [Blockwallet](https://blockwallet.io/) utilize this feature
    
3. **Contract Deployment:** Imagine you want to open multi-chain restaurants across the USA (L1-Main Blockchain). Each restaurant must follow strict health and safety rules (security on the main blockchain). You need to submit detailed plans for each restaurant to a central authority (zkSync operator), which is time-consuming and costly (high cost of deploying each contract on L1).
    
    To simplify, you use a franchise model (contract factories). You create a master plan (code) for your restaurants, covering food prep, hygiene, and staff training. This master plan is submitted and approved once (publishing the code for each contract once on Ethereum).
    
    Franchises then use this approved master plan to set up their restaurants (deploying contracts with the same code). This saves time and money compared to submitting individual plans for each location (significant savings compared to L1). In a simpler term, This means using one contract to deploy several contracts with the help of contract factories.
    
4. **L1 / L2 interoperability:** zkSync enhances communication and easy flow of assets between Layer 1 (Ethereum mainnet) and Layer 2 (zkSync). This allows users to move assets and data between the two layers efficiently, ensuring that decentralized applications (DApps) can leverage the scalability benefits of Layer 2 while maintaining the security and decentralization of Layer 1. This interoperability is crucial for developers looking to build scalable and secure applications on Ethereum.
    
5. **State Differences:** This is another uniqueness zkSync had over other Rollups. Instead of publishing all the transaction data to L1, zkSync only publishes the state difference meaning, it publishes less data to L1 to reduce congestion.
    
    Picture this: Instead of the chef recording every detail of each meal served, like the number of guests, their names, and every ingredient used, zkSync Era only focuses on changes in the kitchen inventory (state diffs). For example, if a table orders 5 plates of jollof rice, the chef might note that 5 kg of rice was used. Additionally, if a specific spice is running low, zkSync Era would record the decrease in that spice's quantity, not every dish it was used in.
    
6. **Gas estimation for transactions:** zkSync uses a more comprehensive approach to estimate transaction fees compared to Ethereum. It considers various factors like account type, transaction length, and signature validation to provide a more accurate fee estimate. [Find out **how to estimate gas for various transaction types**](https://docs.zksync.io/build/tutorials/how-to/estimate-gas.html).
    

## [**Comparing zkSync with Other Rollup Solutions**](https://docs.zksync.io/build/tutorials/how-to/estimate-gas.html)

%[https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExYjgyaXpyeGpnNGYzMW1mZWR1dHdpZTE0ZzY3aHdqZmd1dHVuNDEyYyZlcD12MV9naWZzX3NlYXJjaCZjdD1n/I0zrnUGq5kDoivT9IS/giphy.gif] 

Now that you know some of the unique features zkSync possesses, you might be wondering what advantages zkSync has over other Rollup solutions.

1. **Proof system:** zkSync utilizes zero-knowledge proofs to cryptographically prove the validity of the transaction without revealing all the transaction data. This reduces the amount of data published to Ethereum Blockchain (L1). instead of relying on "assumption" like other Rollups like Arbitrum etc.
    
2. **Gas Fees:** zkSync generally offers lower gas fees compared to other Rollup solutions due to its efficient proof system and off-chain computation, making it more cost-effective for users.
    
3. **EVM Compatibility:** zkSync is fully compatible with the Ethereum Virtual Machine (EVM), enabling developers to deploy and interact with smart contracts written in Solidity or Vyper without needing significant changes. This compatibility ensures that existing Ethereum tools, libraries, and infrastructure can be used seamlessly with zkSync, making it easier for developers to transition their DApps to a more scalable solution. unlike other Rollups like StarkNet that use Novel Virtual Machine(NVM).
    
4. **Security**: zkSync relies heavily on Ethereum security, ensuring that all transactions are verified and recorded on the Ethereum mainnet. This approach provides a high level of security and trustlessness, comparable to the Ethereum network itself. In contrast, Optimistic Rollups like Arbitrum and Optimism assume transactions are valid and only verify them if challenged, which can introduce a delay in finality and potential security concerns during the challenge period. Zero-knowledge rollups like zkSync use cryptographic proofs to validate transactions, offering stronger security guarantees without relying on assumptions.
    

## **Statistics Report on zkSync**

%[https://media.giphy.com/media/BwP6oBTVT5oC4/giphy.gif?cid=790b76118h422mx2nr3jrmzjgu0qvh2bwycixibvu5nj4rll&ep=v1_gifs_search&rid=giphy.gif&ct=g] 

### **General analytic Report**

This is an overview analysis of zkSync by Matterlab on the [Dune Dashboard](https://dune.com/matter_labs/zksync-era-overview) below:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715931362750/f576a242-a161-4932-89cb-a23112dd2164.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715931189785/ca082abe-1b08-41aa-875b-9c5b4159510f.png align="center")

### **Comparison of zkSync Bridgers to other Rollups Bridgers**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715931407332/e10bcddd-f96a-489b-aa36-efc33958f702.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715931450676/9235b83d-f964-4ba7-9aa3-f2fa928bbfc8.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715931501214/e8b21b42-1bfa-4f0c-b7f0-20e448011682.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1715931513671/6ebea412-48d4-4636-97c9-d3301567df54.png align="center")

## **Provided Tool for Developers**

%[https://media.giphy.com/media/kPfcuL4G0Q8xYKpOox/giphy.gif?cid=790b761188zwuk0e0p43ibpgcbf4klmc64w7a4twjukfzl4f&ep=v1_gifs_search&rid=giphy.gif&ct=g] 

zkSync is not just pursuing after increase in scalability but also giving developers the room to build projects that are efficient to humanity and also provide tools for easy development.

These are some of the tools zkSync provides for developers such as:

1. [**SDKs:**](https://docs.zksync.io/build/sdks/js/getting-started.html#examples) These are Software Development Kits (SDKs) that zkSync provides to help developers build and integrate their applications seamlessly. These SDKs include programming languages like **Javascript ether v5 and v6, Python, Swift, Go, Rust and Java** for installation, providers, Accounts, L1-L2 transactions, Paymaster utilities, zkSync Era Features, Smart Account Utilities and also for Frontend Integration.
    
2. [Tooling](https://docs.zksync.io/build/tooling/block-explorer/getting-started.html): such as Block Explorer, zkSync Comand Line Interface(CLI), Hardhat Plugin, Foundry and Ecosystem including NFT Marketplace, Wallets, Integrated Development Environment (IDEs) etc as well as Network Faucets.
    
3. [Testing environment and Debug](https://docs.zksync.io/build/test-and-debug/getting-started.html) procedures.
    
4. [Tutorials](https://docs.zksync.io/build/tutorials/smart-contract-development/account-abstraction/daily-spend-limit.html) on Smart contract development, DApp development, Tooling Guides and How to deposit ETH, Withdraw ETH and a lot more.
    
5. [Application Programming Interface(API) References](https://docs.zksync.io/build/api.html).
    

Aside from these, zkSync is also in support of features such as:

1. Native support of Elliptic Curve Digital Signature Algorithm (ECDSA).
    
2. Solidity version 0.8.x.
    
3. Ethereum cryptographic primitives such as `keccak256`, `sha256`, and `ecrecover`.
    
4. L1 → L2 smart contract messaging.
    

## **Developer Tips for Implementing zkSync in DApps**

If you are interested in implementing zkSync in your project, here are helpful tips :

1. **Understand zkSync's Architecture:** Familiarize yourself with zkSync's architecture and documentation to understand how it integrates with Ethereum and its unique features.
    
2. **Leverage zkSync SDKs:** Utilize zkSync's SDKs and APIs to simplify the integration process and ensure seamless communication between your DApp and zkSync.
    
3. **Optimize Gas Usage:** Take advantage of zkSync's lower gas fees by optimizing your smart contracts for efficient gas usage, reducing overall transaction costs.
    
4. **Test Thoroughly:** Conduct extensive testing on zkSync's testnet before deploying your DApp to the mainnet to ensure it functions correctly and efficiently.
    
5. Make [zkSync Doc](https://docs.zksync.io/) your friend
    
6. Join the zkSync community for [developer update](https://twitter.com/zkSyncDevs)s, [GitHub discussion](https://github.com/zkSync-Community-Hub/zksync-developers/discussions) and [zkSync Discord](https://join.zksync.dev/) to learn, contribute and network.
    

## **Future of Ethereum Scalability with zkSync**

It is the audible to deaf and visible to the blind that the future of Ethereum scalability with zkSync is characterised by improvement and growth.

In addition to its amazing features, zkSync continues to innovate by developing new features like zkPoster.

According to the zkSync doc,

> zkPorter will allow users to choose between a zkRollup account featuring the highest security and a 20x fee reduction compared to Ethereum, or a zkPorter account featuring stable transaction fees of just a few cents in a different security model (much higher than that of a sidechain). Both zkPorter and zkRollup accounts will be able to interact seamlessly together under the hood.

Recently, it was announced that there will be a protocol upgrade to v24 on X before June 2024.

%[https://x.com/zksync/status/1791488199715348727] 

As long as zkSync exists, more features and improvements are coming.

## Conclusion

In conclusion, zkSync's features solve Ethereum congestion and improve its scalability. You can also entrust your projects to zkSync

So event planners and food vendors can learn from zkSync's approach to efficiently manage resources and ensure everyone is served promptly, just as zkSync enhances Ethereum's scalability and transaction speed.

[Check out for more information on zkSync's doc](https://docs.zksync.io/).

If you find this article, Like, Share and Follow for more.

Feedback is welcome too

%[https://media.giphy.com/media/UQaRUOLveyjNC/giphy.gif?cid=790b7611370j831c5w01qzdyuekiozja38k355p1aixwi7pn&ep=v1_gifs_search&rid=giphy.gif&ct=g]