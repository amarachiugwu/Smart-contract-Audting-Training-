# Chapter 1

## What is Ethereum
Ethereum is often described as "the world computer.” this simply means that it is a globally accessible computer/machine with a single state and a virtual machine that applies changes to that state.

Ethereum executes programs known as "Smart contracts"

Ethereum uses ether to meter and constrain execution resource costs.

## Motivation
Ethereum is the mother of decentralization, this has brought about data availability, auditability, transparency and neutrality. Ethereum reduces or eliminates censorship and reduces certain counterparty risks.

## Etherum Compared to Bitcoin
The purpose and construction of Ethereum are strikingly different from those of the open blockchains that preceded it, including Bitcoin.

Ethereum’s purpose is not primarily to be a digital currency payment network. While the digital currency ether is both integral to and necessary for the operation of Ethereum, ether is intended as a utility currency to pay for use of the Ethereum platform as the world computer.

 Ethereum’s language is Turing complete, meaning that Ethereum can straightforwardly function as a general-purpose computer. Unlike Bitcoin, which has a very limited scripting language which is  intentionally, constrained to simple true/false evaluation of spending conditions..

## Components of a Blockchain

A peer-to-peer (P2P) network, Transactions, A set of consensus rules, A state machine, A chain of cryptographically secured blocks, A consensus algorithm that decentralizes control over the blockchain, A game-theoretically sound incentivization scheme. One or more open source software implementations of the above ("clients").

## The Birth of Ethereum
After the power of the Bitcoin model was recognized, developers faced a conundrum: they either needed to build on top of Bitcoin which has intentional constraints or start a new blockchain.

Toward the end of 2013, Vitalik Buterin, a young programmer and Bitcoin enthusiast, started thinking about further extending the capabilities of Bitcoin and Mastercoin.

Dr. Gavin Wood, however, was one of the first people to reach out to Vitalik and offer to help with his C++ programming skills. Gavin became Ethereum’s cofounder, codesigner, and CTO.

The founders worked for years, building and refining the vision. And on July 30, 2015, the first Ethereum block was mined. The world’s computer started serving the world.

### Ethereum answers the question:
    "What if we could track any arbitrary state and program the state machine to create a world-wide computer operating under consensus?"

### NB:
    Ethereum runs on the Ethereum main network, which is addressable on TCP port 30303, and runs a protocol called ÐΞVp2p.

### Ethereum's Ability (Turing-complete)

    Ethereum’s ability to execute a stored program, in a state machine called the Ethereum Virtual Machine, while reading and writing data to memory makes it a Turing-complete system and therefore a UTM. Ethereum can compute any algorithm that can be computed by any Turing machine, given the limitations of finite memory.

### Ethereum's Innovation

    Ethereum’s groundbreaking innovation is to combine the general-purpose computing architecture of a stored-program computer with a decentralized blockchain, thereby creating a distributed single-state (singleton) world computer. Ethereum programs run "everywhere," yet produce a common state that is secured by the rules of consensus.

### Haulting Problem
    this problem states whether it is possible, given an arbitrary program and its input, to determine whether the program will eventually stop running

### Implications of Turing Completeness

Turing-complete systems can run in "infinite loops," a term used (in oversimplification) to describe a program that does not terminate. Ethereum can’t predict if a smart contract will terminate, or how long it will run, without actually running, This is effectively a DoS attack. A program that abuses resources gets to abuse the world’s resources.

To solve this challenge, Ethereum introduces a metering mechanism called gas. As the EVM executes a smart contract, it carefully accounts for every instruction (computation, data access, etc.). Each instruction has a predetermined cost in units of gas. When a transaction triggers the execution of a smart contract, it must include an amount of gas that sets the upper limit of what can be consumed running the smart contract. The EVM will terminate execution if the amount of gas consumed by computation exceeds the gas available in the transaction. Gas is the mechanism Ethereum uses to allow Turing-complete computation while limiting the resources that any program can consume.

