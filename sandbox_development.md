# Using of sandbox environment for development and testing

http://tezos.gitlab.io/mainnet/introduction/various.html#use-sandboxed-mode

```bash
./src/bin_node/tezos-sandboxed-node.sh 1 --connections 1

eval `./src/bin_client/tezos-init-sandboxed-client.sh 1`

tezos-activate-alpha

tezos-autocomplete
```

Get list of wallets
