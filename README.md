# Tezos/Blockchain Education Curriculum

The guide is focusing on developing dapp using Tezos Blockchain. Blockchain generic topics are refered, however not always elaborated further. We suggest to check articles and resources referenced to grasp generic concepts.

## How to Read and Who Should Read The Guide
During the guide we will be marking content depending on the experience level using icons :hatching_chick: and :chicken:.
Guide is focusing on two experience levels of users 
- :hatching_chick: developers with no prior knowledge on blockain
- :chicken: blockchain developers with experience with tezos/other platforms, that would like to work with Tezos ASAP.

Pages in contents bellow are designed to be followed step-by-step. In case you are **advanced user (:chicken:)** you can skip sections addressed to **developers with no prior blockchain experience (:hatching_chick:)**.

Tutorial is using layering when it comes to explanation of concepts. Goal is to make developer build smart contract in shortest possible time. In each section, we will try to focus on minimal set of items, that are required so after completion of each section your profeciency will improve. In case you don't understand some command or concept, we will try to elaborate on in some of later section. Also we believe if you have working set of commands, will less then ideal commentary it's easier to look up the information, rather than other way round.


## Prerequisites
The tutorial focus on Tezos specifics. To successfully follow the course it's recommended to have following prerequisites.
1. You should understand how blockchain works at high level (we suggest to look at [High Level Blockchain Curriculum](generic/recommended_courses.md)])
2. You should be familiar with some programming language. Understanding of functional languages like Lisp, Scheme, Ocaml is a plus. 
3. It's recommended to do some tutorials on Ocaml language - eg. https://try.ocamlpro.com
4. You should be comfortable with command line and shell scripting - eg. https://www.learnshell.org . At the time of writing we've tested the samples on Debian (Raspberry) and Mac OS. 

## Generic Blockchain Intro
* :hatching_chick: [High Level Blockchain Curriculum](generic/recommended_courses.md). Provides references to external material on blockchain.

## Guide Contents 
### Technical Introduction to Tezos
1. :hatching_chick: [Tezos Concepts](tezos/tezos_concepts.md)
2. :hatching_chick: [Technical Architecture / Tezos Components](tezos/technical_architecture.md). Describes tezos programs and how they relate to each other
3. :hatching_chick: [Tezos Networks](tezos/network.md)
4. :hatching_chick: :chicken: [PRACTICE: Installation from source codes](setup/source_install.ipynb)

### Basic Development of Tezos Smart Contract
5. :hatching_chick: :chicken: [PRACTICE: Simple Calculator](code/calculator_dapp.ipynb)

### More Advanced Development of Tezos Smart Contract
6. :chicken: [PRACTICE: Working with Tezos Alphanet](setup/working_with_alphanet.md)
7. :chicken: [PRACTIVE: Voting Smart Contract](code/voting_dapp.ipynb)
8. :chicken: [Tezos Fees and Cost Model](tezos/fees_and_costmodel.md)

### Advanced Tezos Concepts
9. :chicken: [Liquid Proof of Stake](tezos/liquid_proof_of_stake.md)
10. :chicken: [On-chain Governance](tezos/on_chain_governance.md)






