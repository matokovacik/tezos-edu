SHA-256
5 requirements for hashing algorithm
1. One way 
2. Deterministic
3. Fast Computation
4. The Avalanche Effect
5. Must withstand collisions



Parts of blockchain

- Hash Cryptography
- Immutable Ledger
- Distributed P2P Network
- Mining
- Consensus Protocol


To Read:
- ref. On the secure hash algorithm family
- ref. The Blockchain Economy: A beginner's guide to institutional cryptoeconomics (https://medium.com/@cryptoeconomics)
- ref. The Meaning of Decentralization (https://medium.com/@VitalikButerin/the-meaning-of-decentralization-a0c92b76a274)
- ref. A beginners guide to Tezos (https://medium.com/@linda.xie/a-beginners-guide-to-tezos-c9618240183f)
- ref. soft fork vs hard fork blockchain (https://www.investopedia.com/terms/h/hard-fork.asp)
- ref. https://medium.com/loom-network/understanding-blockchain-fundamentals-part-1-byzantine-fault-tolerance-245f46fe8419
- ref. https://www.zastrin.com/courses/simple-tezos-dapp/lessons/3-3
- 


### Sample Voting Contract
As a sample we will implement voting contract. 
Voting contract will enable to initially specify candidates. Afterwards voters can give a vote to specific candidate. Each voter can vote only once.

#### Smart Contract Structure in Liquidity
Each liquidity file consist of three parts
- version declaration (of liquidity)
- storage definition
- entry functions 
  - at least method main is required. This method is called when contract is executed.


**Voting.liq**

```ocaml
[%%version 0.4
  
type storage = {
  candidates : (string, int) map;
  voters : (address, bool) map;
}

let%init init_candidates (candidate_names : string list) =
  let candidates = List.fold (fun (elt, map) -> Map.add elt 0 map) candidate_names
    (Map[] : (string, int) map) in
  { candidates = candidates; voters = (Map : (address, bool) map) }

let%entry main (candidate_name : string) (storage : storage) =
  let addr = Current.source() in
  let storage =
    storage.voters <- match Map.find addr storage.voters with
    | None -> Map.add addr true storage.voters
    | Some x -> failwith ("Voter has already voted", addr)
  in

  let storage =
    storage.candidates <- match Map.find candidate_name storage.candidates with
    | None -> failwith("Candidate is not valid", candidate_name)
    | Some x -> Map.add candidate_name (x + 1) storage.candidates ;
  in
  (([] : operation list), storage)
```