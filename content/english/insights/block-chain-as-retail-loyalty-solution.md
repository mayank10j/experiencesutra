Block-chain as Retail loyalty Solution | EXPERIENCESUTRA                         Block-chain as Retail loyalty Solution | EXPERIENCESUTRA                                   

*   [![EXPERIENCESUTRA](/wp-content/themes/tresor-theme/images/logo.png)](http://experiencesutra.com/)

*   [PURPOSE](http://experiencesutra.com/purpose/)
*   [PEOPLE](http://experiencesutra.com/people/)
*   [SPACE](http://experiencesutra.com/gallery/space/)
*   [ABOUT US](http://experiencesutra.com/about-us/)

 [Show menu](#dat-menu)

*   [HOME](http://experiencesutra.com/)
*   [PROJECTS](http://experiencesutra.com/category/projects/)
*   [INSIGHTS](http://experiencesutra.com/category/insights/)
*   [EXPERIMENTS](http://experiencesutra.com/category/experiments/)
*   [SCRIBBLES](http://experiencesutra.com/category/scribbles/)
*   [CONTACT US](http://experiencesutra.com/contact-us/)

*   [Home](http://experiencesutra.com)
*   [INSIGHTS](http://experiencesutra.com/category/insights/)
*   Block-chain as Retail loyalty Solution

Articles
--------

Block-chain as Retail loyalty Solution
--------------------------------------

[INSIGHTS](http://experiencesutra.com/category/insights/)

Loyalty programs are Marketing strategy used by the brand to make customer stick to their platform/product. This blog proposes a novel loyalty platform built on top of blockchain technology to be used by brands. We will start with an introduction to blockchain technology and in various sections try to answer following questions.

What is benefit of using Blockchain for loyalty solution?  
How Block-chain help in interoperability and transferability of loyalty perks?  
How this ensures blocking ensure scarcity of loyalty coins and limit liability for brands?  
How Block-chain improves better customer experience or improves convenience to customers?  
How this solution ensures better operations cost?  
How this solution improves the overall security of Loyalty programs?  
How to prevent customer data leak?

**Introduction to Block-chain**
-------------------------------

Block-chain, as we know today, was first introduced to the world by a Satoshi Nakamoto in 2008 through his landmark paper \[5\]. He followed it by the implementation of the first peer to peer decentralized currency called Bitcoin. Bitcoin introduced a couple of very important concepts, First among these were the use of Merkel trees for generating a combined hash of set of transactions. Individual leaf of Merkel tree is used as transaction storage in form of Data Blocks, These hashes are stored as Transaction ID, Merkel tree is constructed from these hashes with Root of each Merkel Tree containing combined hashes of all leaf transactions ( See Figure 1). In practice, it means that if there is a slight modification in any of these transactions or even order of transactions, Merkel root will also change.

[![Hash Tree](http://experiencesutra.com/wp-content/uploads/2018/02/hashTree-1024x652.png)](http://experiencesutra.com/wp-content/uploads/2018/02/hashTree.png)

Hash Tree

Block-chain is a read-only linked list of continually growing records or Blocks of data. As a part of single block Header, Merkel root acts as a cryptography proof of transactions in the block as well as their order. Apart from Merkel root each block header also stores timestamp and pointer to the previous block with its hash ( See figure 2). By storing the hash of the previous block one can always come back and calculate and re-verify all previous transactions and check the authenticity of block-chain.

[![Block Data](http://experiencesutra.com/wp-content/uploads/2018/02/blockData.png)](http://experiencesutra.com/wp-content/uploads/2018/02/blockData.png)

Block Data

Block-chain technology is divided into two major categories, Permission-less and Permissioned. In permission-less block-chains (e.g. bitcoin and Ethereum ) participation in a network is open to everybody very few restrictions. Original Nakamoto paper and Bitcoin implementation provided system of economic incentives for its governance and working. First among them was which transactions to choose for inclusion in main Block-chain ? If number of transactions submitted for storage on main Block-chain are very large due to spam / popularity of network or large transactions size ,inclusion of every transaction in Main-chain becomes very prohibitive. To prevent this In Bitcoin ,number of blocks per hour are capped at around 6/hour with block data size of around 1 MB. These restrictions enables a person with average computer hardware to store participate in network with full transaction history and help in overall network health. With few blocks generated per hour it becomes very difficult to decide which transactions to choose and which ones to discard, as there is no central authority for governance. This is solved by a novel incentive system called _Proof of work_ in bitcoin world. Each node who wants to acquire write access on block-chain for one block period needs to participate in a competition to solve a complex computer puzzle that needs huge computing power to solve. After successfully solving this puzzle node is awarded a mining award as well transactions fees that is included by each network participants. If a miner misuses this append rights by submitting fraudulent transactions network can verify it by checking block-chain history and reject miners award and all money/effort spent by miner on proof of work is lost forever. This creates a strong economic incentive to become honest miner. In Permissioned block-chain ( e.g. Hyperledger Fabric , Ripple etc.) on the other hand all network participants need to be approved from a trusted authority before becoming network participants. As only restricted set of peers are validators Permissioned block-chain avoids expensive Proof of work algorithm for its working. For making Permissioned block-chain immune to few corrupt nodes Distributed consensus algorithm (e.g. Practical Byzantine fault tolerance) are applied. This provides some of the benet public block-chain into Permissioned block-chain.

### Block-chain technology for Customer Loyalty solution

Traditionally customer loyalty solutions are built on top of centralized database technology where a single centralized database instance is used to record issuance, transfer and redemption of loyalty awards.  
In our Blockchain based solution, every authenticated user is issued with digital wallet through which he can access  
his loyalty benefit. After every loyalty event ( Issuance,redemption,transfer,expiration of loyalty points) a new  
transaction is generated and signed with user key and sent to blockchain network. these transactions are collected and committed by validators in form of blocks, eventually updating all network nodes into a single ledger using its inbuilt consensus algorithm. A single wallet can handle loyalty token transactions from multiple brands.

In Following subsections, we will try to emphasize unique benefits of our blockchain based solution compared to a traditional database solution.

#### 1) Centralized vs Peer to Peer Distributed Solution

Compared to centralized database solution, Block-chain technology does not store transactions at one store/place instead all full participating nodes have a copy of full ledger history. This solves the issue of database downtime as well as increase security of the overall system. As once set up Block-chain based solution does not rely on a central server instead all stores themselves act as server as well client using Peer to peer network communication. Doing this helps in reducing Server setup and maintenance and thus reduces overall operations cost and downtime and improves resiliency.

#### 2) Transactions immutability

As illustrated in introduction section due to use of strong cryptography proof. Transactions committed on block-chain are tamper proof and immutable. Even if few nodes in network are hacked/tempered system can always detect and correct fraudulent transactions. This drastically improves overall security of system compared to current system which is very prone to tempering.

#### 3) Customer Privacy

Taking inspiration from projects like Block-certs \[1\] and Hyperledger Indy \[3\] In our proposed solution customer KYC is handled by separate authorization service which collects customer data (e.g. identity proof, Phone Number etc.) ochain and after successful verification issues a digital certificate which is linked with a public key in main block-chain. If at any time customer wants to delete his account, only his/her certificate and linking needs to be revoked as no customer PII data is stored in block-chain itself. With increasing data privacy regulatory requirements e.g. Upcoming European Union GDPR requirements \[4\]. Businesses needs to provide strong audit trail of customer data collection of and provide full control to customer of his/her private data. Our approach solves this issue with minimal exposure of customer data with strong audit trail provided by blockchain technology. This also removes concerns regarding incompatiblity of GDPR and Block-chain because of immutability of stored data and GDPR regulation related to data deletion. \[2\].

#### 4) Interoperability and transferability of loyalty perks

As mentioned earlier a single customer wallet can support multiple loyalty rewards of different brands, with very simple smart contracts executed between brands ,different loyalty rewards can be made inter-portable. Also it is very easy to allow transferability of loyalty between different user account.

### Conclusion and Outlook

Blockchain technology is turning out to be disruptive force that is replacing traditional database solutions. Due to its low cost of operation,  
improved security ,network resiliency and decentralized architecture. Blockchain technology is  
an strong fit for application in customer loyalty solution.

### References

1. BLOCKCERTS , the open initiative for blockchain certicates. [https://www.hyperledger.org/projects/hyperledger-indy](https://www.hyperledger.org/projects/hyperledger-indy), accessed: 2017-12-30

2. The blockchain-gdpr paradox. [https://medium.com/wearetheledger/the-blockchain-gdpr-paradox-fc51e663d047](https://medium.com/wearetheledger/the-blockchain-gdpr-paradox-fc51e663d047), accessed: 2010-09-30

3. Hyperledger Indy , distributed ledger , purpose-built for decentralized identity. [http://www.blockcerts.org/](http://www.blockcerts.org/), accessed: 2017-12-30

4. GDPR for software developers. [https://www.infoq.com/articles/gdpr-for-software-devs](https://www.infoq.com/articles/gdpr-for-software-devs), accessed: 2017-12-30

5. Nakamoto, S.: Bitcoin: A peer-to-peer electronic cash system (2008)

[Featured ![Affordable experiences](http://experiencesutra.com/wp-content/uploads/2015/04/IMG_0866-397x310_c.jpg)   INSIGHTS **Affordable experiences**](http://experiencesutra.com/insights/creating-affordable-experiences/) 

[Featured ![The Nano-book](http://experiencesutra.com/wp-content/uploads/2015/05/1-397x310_c.png)   INSIGHTS **The Nano-book**  by Meenakshi Jauhari Chawla  •](http://experiencesutra.com/insights/the-nano-book-notes-from-the-future/) 

[Tweets by @keplervaani](https://twitter.com/twitterdev)

Socialize
---------

[**0**_Shares_](http://www.facebook.com/sharer/sharer.php?u=http://experiencesutra.com) [**0**_Tweets_](#) [**0**_+1's_](https://plus.google.com/share?url=http://experiencesutra.com) [**0**_Shares_](http://www.linkedin.com/shareArticle?mini=true&url=http://experiencesutra.com&title=EXPERIENCESUTRA+-+Humanizing+Technology)

EXPERIENCESUTRA
---------------

Humanizing technology  
© 2016 - Kepler186f

[Close Window](#)

### Loading, Please Wait!

This may take a second or two. ![Loading, Please Wait!](http://experiencesutra.com/wp-content/themes/tresor-theme/images/loading.gif "Loading, Please Wait!")