# Milestone 1

## Parallel Processing of Large Text Files and Distributed Data Storage on Blockchain

### Introduction

Blockchain is a distributed decentralized ledger that is not managed by any third-parties. It's specifically utilized for secure and instant transactions. Main advantages of the system are:

- **Security of the data:** Data cannot be erased or modified by any individuals, which implies immutability.
- **Usage of cryptographic tools to protect the data:** Hash functions are utilized to encrypt information and usually, SHA-256 hashing algorithm is preferred.
- **Usage of Consensus algorithm:** The algorithm validates and confirms the transactions without any third-party involvement.
- **Chronological order of transactions:** This ensures that the transactions indeed happened at a specific point of time, which prevents possible frauds and duplicate entries.

### Importance of the Topic

Despite the advantages, one of the main gaps of the system is the ***sequential block-by-block processing of transactions***. For example, to process a transaction, a minor node adds a block to the chain where each block is a set of transactions to execute. Once the consensus has been reached on a block, validators replay the transactions of that block to compare the generated hash with the original hash to confirm the transactions. However, all of these happen one block at a time. Therefore, there is a need of parallel processing to increase throughput.

### Goals of the Project

Henceforth, our first contribution will be the implementation of the parallel processing of the large text files on the blockchain system, like Ethereum. 

While building this application, one of the suggested solutions will be taken into account:

- Implementation of ***leader-follower architecture*** (see example illustration below), whereby a blockchain node analyzes the transactions to determine the interdependencies, constructs a directed acyclic graph (DAG) of those dependencies and allocates (shards) the work amongst off chain followers. This ensures parallelism through grouping the transactions based on the degree of dependency. Independent transactions get assigned to separate follower nodes. Even though sequential processing is observed within the groups, the entire process happens to be parallel, which increases the throughput and speed.

The second supplementary goal of the project is to implement ***distributed data storage on a blockchain system***. This is particularly advantageous to ensure the security of the stored data and its high availability with no single point of failure.

### Challenges of Proposed Applications

1. ***Consistency:*** Ensuring the end result of the parallel processing is equivalent to the execution of sequential processing.
2. ***Failure handling:*** Tackling cases when one node is seemingly stuck and cannot continue the execution, which creates a bottleneck for the whole process due to the unavailability of the block.
3. ***Concurrency:*** This is a concurrency issue since the data is being processed in parallel rather than sequentially.
4. ***Security:*** Distributed data storage implies that the owners of the data lose control over it and therefore, better techniques must be in place to protect the data

### Sample Research Papers
1. [How Blockchain Works](https://link.springer.com/chapter/10.1007/978-1-4842-3444-0_2)
2. [On the Exploitation of Blockchain for Distributed File Storage](https://www.hindawi.com/journals/js/2020/8861688/)
3. [DiPETrans: A Framework for Distributed Parallel Execution of Transactions of Blocks in Blockchain](https://arxiv.org/pdf/1906.11721.pdf)
4. [SlimChain: Scaling Blockchain Transactions through Off-Chain Storage and Parallel Processing](http://vldb.org/pvldb/vol14/p2314-xu.pdf)


### Illustration of the Leader-Follower Architecture

![DiPETrans Explained](https://github.com/gwDistSys20/project-lutfi-lutfizad/blob/main/milestone-1/leader-follower.png)


