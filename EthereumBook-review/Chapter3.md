# Ethereum Clients

An Ethereum client is a software application that implements the Ethereum specification and communicates over the peer-to-peer network with other Ethereum clients.

So basically an Ethereum client is a software that implements all the ethereum specification defined in the yellow paper

## Currently, there are six main implementations of the Ethereum protocol, written in six different languages:

* Parity, written in Rust

* Geth, written in Go

* cpp-ethereum, written in C++

* pyethereum, written in Python

* Mantis, written in Scala

* Harmony, written in Java

## Full Node, clents, remote clients, full clients

Running a full node is not neccessary unless if all you want to do is to develop on the ethereum eco system, this is where private local blockchain like Ganache or cloud based ethereum client offered by services provider like infura come into play.

Each full node can help other new nodes obtain the block data to bootstrap their operation, as well as offering the operator an authoritative and independent verification of all transactions and contracts. 

Remote client and "wallet" are used interchangeably, though there are some differences. Usually, a remote client offers an API (such as the web3.js API) in addition to the transaction functionality of a wallet. All mobile wallets are remote clients, because smartphones do not have adequate resources to run a full Ethereum client. eg of remote clients are Jaxx, Status, Trust Wallet Browser Wallets, Cipher Wallets, MetaMask, MyEtherWallet, MyCrypto.

    NB: Mist was the first Ethereum-enabled browser, built by the Ethereum Foundation. It contained a browser-based wallet that was the first implementation of the ERC20 token standard. Mist was also the first wallet to introduce the camelCase checksum (EIP-55). As of March, 2019, Mist was deprecated and should no longer be used.

Full clents run a full node, the Ethereum remote clients do not validate block headers or transactions. They entirely trust a full client to give them access to the blockchain, and hence lose significant security and anonymity guarantees.

## Full Node Advantages:

* Supports the resilience and censorship resistance of Ethereum-based networks

* Authoritatively validates all transactions

* Can interact with any contract on the public blockchain without an intermediary

* Can directly deploy contracts into the public blockchain without an intermediary

* Can query (read-only) the blockchain status (accounts, contracts, etc.) offline

* Can query the blockchain without letting a third party know the information you’re reading

## Disadvantages:

* Requires significant and growing hardware and bandwidth resources

* May require several days to fully sync when first started

* Must be maintained, upgraded, and kept online to remain synced

## Full node vs Archival node

Archival node contains all the blockchain states from the Genesis block while a full node contains the blockchain states too but have been pruned of some very early states.

An archival node disk size can be 1TB + in size while an full node size can be up to 340GB+ in size.

## The JSON-RPC Interface
Ethereum clients offer an application programming interface and a set of Remote Procedure Call (RPC) commands, which are encoded as JavaScript Object Notation (JSON). You will see this referred to as the JSON-RPC API. Essentially, the JSON-RPC API is an interface that allows us to write programs that use an Ethereum client as a gateway to an Ethereum network and blockchain.