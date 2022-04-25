ANUJ SINHA

20BCE2166

                                                                           **CSE1007 – JAVA PROGRAMMING**

**THEORY ASSIGNMENT 1**

**MERKLE TREE**

**INTRODUCTION:**

- A Merkle tree is a hash-based data structure that is a generalization of the hash list. It is a tree structure in which each leaf node is a hash of a block of data, and each non-leaf node is a hash of its children. Typically, Merkle trees have a branching factor of 2, meaning that each node has up to 2 children.
- Merkle trees are used in distributed systems for efficient data verification. They are efficient because they use hashes instead of full files. Hashes are ways of encoding files that are much smaller than the actual file itself. Currently, their main uses are in peer-to-peer networks such as Tor, Bitcoin and Git.
- Hash trees can be used to verify any kind of data stored, handled and transferred in and between computers. Currently the main use of hash trees is to make sure that data blocks received from other peers in a peer-to-peer network are received undamaged and unaltered, and even to check that the other peers do not lie and send fake blocks. Suggestions have been made to use hash trees in trusted computing systems.

![Picture 1](RackMultipart20220425-1-230lvr_html_202fb2fb57c85752.gif)

**Why is Merkle tree better than binary tree?**

- It provides both integrity and validity of data.
- The memory needed to store the data is significantly reduced.
- It only needs small amounts of information to be transmitted across networks.
- It provides a way of verifying transactions in a block without downloading an entire block.

**Why Merkle tree is used in blockchain?**

- A blockchain is comprised of various blocks that are linked with one another, hence the name blockchain. Merkle tree stores the blockchain data in an efficient and secure way.
- It can verify blockchain data very quickly. It also provides quick movement of large amounts of data from one computer node to the other blockchain network.
- Every transaction that occurs on the blockchain network has a hash associated with it. These hashes are stored in the form of a tree-like structure such that each hash is linked to its parent.
- Since numerous transactions are stored on a particular block, all the transaction hashes that are present in the block are also hashed, which results in a Merkle root.

![](RackMultipart20220425-1-230lvr_html_944b7a0206a18733.jpg)

![](RackMultipart20220425-1-230lvr_html_de30a1e45ac7798e.png)

**ARCHITECTURE OF MERKLE TREE:**

- A Merkle tree stores all the transactions in a block by producing a digital fingerprint of the entire set of transactions. It allows the user to verify whether a transaction can be included in a block or not.
- Merkle trees are created by repeatedly calculating hashing pairs of nodes until there is only one hash left. This hash is called the Merkle Root, or the Root Hash. The Merkle Trees are constructed in a bottom-up approach.
- A **hash function** maps any type of arbitrary data of any length to a fixed-size output. It is commonly used in cryptography since it is a cryptographic function. They are efficient and are well-known for one property: they are irreversible. It&#39;s a one-way function that&#39;s only meant to work in one direction.
- Every leaf node is a hash of transactional data, and the non-leaf node is a hash of its previous hashes. Merkle trees are in a binary tree, so it requires an even number of leaf nodes. If there is an odd number of transactions, the last hash will be duplicated once to create an even number of leaf nodes.

![Picture 7](RackMultipart20220425-1-230lvr_html_75ad57477b48e1a7.gif)

- The above example is the most common and simple form of a Merkle tree, i.e **., Binary Merkle Tree**. There are four transactions in a block: **TX1, TX2** , **TX3** , and **TX4**. Here you can see, there is a top hash which is the hash of the entire tree, known as the **Root Hash** , or the **Merkle Root**.
- Each of these is repeatedly hashed, and stored in each leaf node, resulting in Hash 0, 1, 2, and 3. Consecutive pairs of leaf nodes are then summarized in a parent node by hashing **Hash0** and **Hash1** , resulting in **Hash01** , and separately hashing **Hash2** and **Hash3** , resulting in **Hash23**. The two hashes (Hash01 and Hash23) are then hashed again to produce the Root Hash or the Merkle Root.
- Merkle Root is stored in the **block header**. The block header is the part of the bitcoin block which gets hash in the process of mining. It contains the hash of the last block, a Nonce, and the Root Hash of all the transactions in the current block in a Merkle Tree. So having the Merkle root in block header makes the transaction **tamper-proof**. As this Root Hash includes the hashes of all the transactions within the block, these transactions may result in saving the disk space.

![](RackMultipart20220425-1-230lvr_html_95bed0d4c8eaf513.png)

- The Merkle Tree maintains the **integrity** of the data. If any single detail of transactions or order of the transaction&#39;s changes, then these changes reflected in the hash of that transaction. This change would cascade up the Merkle Tree to the Merkle Root, changing the value of the Merkle root and thus invalidating the block. So everyone can see that Merkle tree allows for a quick and simple test of whether a specific transaction is included in the set or not.

**ALGORITHM OF MERKLE TREE:**

**REFERENCES:**

[https://www.geeksforgeeks.org/introduction-to-merkle-tree/](https://www.geeksforgeeks.org/introduction-to-merkle-tree/)

[https://www.simplilearn.com/tutorials/blockchain-tutorial/merkle-tree-in-blockchain](https://www.simplilearn.com/tutorials/blockchain-tutorial/merkle-tree-in-blockchain)

[https://www.investopedia.com/terms/m/merkle-tree.asp](https://www.investopedia.com/terms/m/merkle-tree.asp)

[https://brilliant.org/wiki/merkle-tree/#:~:text=A%20Merkle%20tree%20is%20a,has%20up%20to%202%20children](https://brilliant.org/wiki/merkle-tree/#:~:text=A%20Merkle%20tree%20is%20a,has%20up%20to%202%20children).

[https://iq.opengenus.org/merkle-tree/](https://iq.opengenus.org/merkle-tree/)

[https://brilliant.org/wiki/merkle-tree/](https://brilliant.org/wiki/merkle-tree/)

[https://www.javatpoint.com/blockchain-merkle-tree](https://www.javatpoint.com/blockchain-merkle-tree)
