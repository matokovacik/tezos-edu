# Tezos Technical Architecture

This section describes main components used in tezos blockchain. 


## Tezos Node
This is the key component of the Tezos. It is a daemon responsible for communication with peers, sends/receives blocks and updates its state. To interact with blockchain it is required to have node fully synced with the rest of network.

Tezos node is exposing RPC API, that can be used to interact with blockchain.

**WORKING COMMENT**: At the time of writing, it takes up to week to synchronise with Alphanet.

## Tezos Client 
Tezos client is command line utility used to communicate with the node using the RPC. In addition to that tezos-client has a wallet component build in.


## Tezos Admin
Admin client provides additional command to interact with peer-to-peer layer. We will not use this component through this guide.

## Delegate
Delegate is term used to describe 3 additional components. These components are related to baking and are not essential for development of smart contracts.

### Baker
The baker is a daemon that once connected to an account, computes the baking rights for that account, collects transactions from the mempool and bakes a block. Note that the baker is the only program that needs direct access to the node data directory for performance reasons.

### Endorser
The endorser is a daemon that once connected to an account, computes the endorsing rights for that account and, upon reception of a new block, verifies the validity of the block and emits an endorsement operation. It can endorse for a specific account or if omitted it endorses for all accounts.

### Accuser
The accuser is a daemon that monitors all blocks received on all chains and looks for bakers who signed two blocks at the same level, endorsers who injected more than one endorsement operation for the same baking slot.

Upon finding such irregularity, it will emit respectively a double-baking or double-endorsing denunciation operation, which will cause the offender to loose its security deposit.