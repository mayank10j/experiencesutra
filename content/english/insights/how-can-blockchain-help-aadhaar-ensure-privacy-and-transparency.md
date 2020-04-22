How Can Blockchain Help Aadhaar Ensure Privacy and Transparency? | EXPERIENCESUTRA                         How Can Blockchain Help Aadhaar Ensure Privacy and Transparency? | EXPERIENCESUTRA                                   

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
*   How Can Blockchain Help Aadhaar Ensure Privacy and Transparency?

Articles
--------

How Can Blockchain Help Aadhaar Ensure Privacy and Transparency?
----------------------------------------------------------------

[INSIGHTS](http://experiencesutra.com/category/insights/)

A much-heated conversation started during the end of last year as the honorable Supreme Court of India delivered its judgment holding the right to privacy as a fundamental right. A substantially big chunk of these conversations revolved around Aadhaar – the world’s largest unique identification system that holds records of over 1.19 billion Indian residents. Aadhaar collects name, date of birth, gender, address, mobile/email (optional) of residents of India and stores these against the corresponding biometric data. With such gargantuan amount of private data stored in a centralized database, the concerns were legit. The SC judgment makes it clear that systems must safeguard matters where there is a “reasonable expectation of privacy”, and it must go beyond personal privacy and also protect individual autonomy.

The primary concern regarding Aadhaar is that a centralized identity database containing demographic and biometric data of over a billion people is an obvious honeypot for hackers. This is not the only concern, though. All the data leaks that were reported in the past had to do with how Aadhaar based authentication works. Your Aadhaar information is connected to a 12 digit Aadhaar number. This Aadhaar number does not hold any meaningful information itself but a service provider, such as your bank or telecom service provider, can use this Aadhaar number and authenticate against information provided by you to verify your identity. Authentication of a person via an Aadhaar User Agency (entities seeking authentication through UIDAI) requires the user to provide their personal data to the AUA. The AUA then authenticates the user by using UIDAI services. An AUA with a mischievous intent may keep an undisclosed record of your demographic and biometric details along with the associated Aadhaar number and commit fraudulent activities.

The UIDAI has acknowledged the aforementioned concern regarding the process of authentication. They have introduced a 16-digit Virtual ID that any Aadhaar user will be able to generate for a temporary period of time by themselves and provide that Virtual ID to the AUA for authentication purposes which will otherwise remain the same. So, you will have an option to not disclose your Aadhaar number to an AUA, but you will still be required to provide your personal information (and in some cases your biometrics, as well). So, bear in mind, when we talk about the security concerns of Aadhaar we are talking about security throughout the different levels of implementation which includes concerns regarding the Aadhaar authentication process as well as the centralized database.

Addressing these concerns there have been a [few](http://www.orfonline.org/expert-speaks/leveraging-technology-for-trust-a-blockchain-based-aadhar/) [proposals](http://www.livemint.com/Opinion/mZuMImncvfpH0POEu3pp6N/How-blockchaining-Aadhaar-can-help.html) for re-implementing the Aadhaar using blockchain technology. Blockchain was initially developed to solve the double spending problem of [Bitcoin](https://bitcoin.org/bitcoin.pdf) – a peer to peer micropayment system. Since then the applications of blockchain has gone beyond its original intended use. The properties of a public blockchain – decentralization, immutability, auditability – incorporated with the Aadhaar should be able to solve the aforementioned grievances with Aadhaar. A blockchain-based Aadhaar would help UIDAI to comply with the data protection and privacy stipulations outlined in the Right to Privacy judgment. It would allow information to be collected, held and utilized transparently with the consent of the individual whose information it is.

In the remaining few paragraphs I shall try to propose answers to the following questions:

1.  How does the blockchain technology help Aadhaar achieving the desired level of trust?
2.  Given the immense cost and scale of the Aadhaar project, would it even be feasible to re-implement it at this late stage?
3.  How do we rectify process of Aadhaar verification so that the user’s privacy is ensured?

I shall start with a brief introduction on how blockchain works. A blockchain, as many of the readers would be aware of, is a distributed ledger consisting of blocks. Each block contains multiple verified transactions. Blocks contain a secured hash which is generated taking into account the index, timestamp, data inside the block, and the hash of the previous block. Such a design makes a blockchain auditable. Any modification to the blocks, after a verified block has been added to the blockchain, would generate a new hash which will be inconsistent with the hashes that precede. The following diagram explains how a blockchain transaction works.

[![how_blockchain_works](http://experiencesutra.com/wp-content/uploads/2018/01/how_blockchain_works.png)](http://experiencesutra.com/wp-content/uploads/2018/01/how_blockchain_works.png)

In our proposed blockchain for Aadhaar, there will be multiple UIDAI trusted nodes (i.e. state governments can opt to become one of the UIDAI trusted nodes). Trusted nodes will be able to validate a transaction and append blocks in the blockchain. Only these trusted nodes will be able to decrypt the data stored in the blocks. Now, because there will be multiple nodes involved in the peer-to-peer network and every node will have a full copy of the blockchain, one or a few nodes getting compromised will not pose a threat to the blockchain. To be able to validate a malicious transaction (i.e. add a new block, or decrypt a data) a hacker must take control of at least 51% of the nodes. Additionally, nodes other than the UIDAI trusted nodes (i.e. NGOs, activists, anybody who wants to) will be able to download the entire blockchain and verify the hashes. This way, anyone will be able to check the integrity of the blockchain without actually looking into the data.

But, there comes a problem. Given the immensity of the data and required bandwidth, is it even possible to implement such a system? A way around for this problem would be to store the actual data in a central server like it is now, and the blocks will hold a pointer to the actual data in the centralized database. The pointer stored will be encrypted and to be able to see the data a node will have to decrypt it. This way, the bandwidth required for the implementation will be much less and the existing infrastructure that stores all the data will be utilized.

In order to ensure privacy in the Aadhaar authentication process carried out by AUAs, we shall write a smart contract. A smart contract is a protocol intended to facilitate, verify, or enforce the negotiation or performance of a contract allowing the performance of credible transactions without third parties. Smart contract transactions are trackable and irreversible. At this moment, as I have already mentioned, Aadhaar users are required to provide their data to the AUA whenever there is a need for identity verification. And this is problematic. We want Aadhaar holders to share their data only with the UIDAI and not the AUA. Our solution is as follows:

1.  The AUA initiates an authentication request to the blockchain specifying the user it wants to authenticate.
2.  The user, upon approving the request, adds their personal data to the blockchain (happens through a government portal). The data, as mentioned earlier, is encrypted and only the UIDAI trusted nodes can decrypt it.
3.  UIDAI authenticates the user and marks the request as approved/rejected.
4.  The AUA initiates another query to check the status of the initial request.

Such a smart contract ensures that no data is shared with the AUA and the entire process can be verified at a later point in time.

In conclusion, it can be said that a more secure and transparent Aadhaar is indeed possible using blockchain. It would protect the Aadhaar holders’ privacy and build trust in the overall system.

[Featured ![How To Stay Relevant In 2030](http://experiencesutra.com/wp-content/uploads/2018/08/34005906806_ae9722f4bf_o-397x310_c.jpg)   INSIGHTS **How To Stay Relevant In 2030**](http://experiencesutra.com/insights/how-to-stay-relevant-in-2030/) 

[Featured ![Everyone needs to be a story teller](http://experiencesutra.com/wp-content/uploads/2016/10/15263928890_5a03ac17e3_k-397x310_c.jpg)   INSIGHTS **Everyone needs to be a story teller**  by Alok Kumar  •](http://experiencesutra.com/insights/everyone-needs-to-be-a-story-teller/) 

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