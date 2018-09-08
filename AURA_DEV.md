Initialize genesis block with the 2 test addresses / sealers
```
./build/bin/geth   --datadir node1/ init goerli.json 
./build/bin/geth   --datadir node2/ init goerli.json 
```

Command to start boot-node:

```
./build/bin/bootnode -nodekey boot.key -verbosity 9 -addr :30303
```

Commands to start validator nodes (on localhost):

```
geth --datadir node2/ --syncmode 'full' --port 30312 --rpc --rpcaddr 'localhost' --rpcport 8550 --rpcapi 'personal,db,eth,net,web3,txpool,miner' --bootnodes 'enode://bb9b7408f9f18a7a731acd1afc4085758a7de599ab3a04cdb532953c06d37ad8647a662e055e1b138f0dae3b35c17a3d3d096b368037867512bca76962d54752@127.0.0.1:30303' --networkid 6283 --gasprice '1' -unlock 'd1d8fbd2fc163a4ee4304695f5d868461ad251ba' --password node2/password.txt --mine

geth --datadir node1/ --syncmode 'full' --port 30311 --rpc --rpcaddr 'localhost' --rpcport 8545 --rpcapi 'personal,db,eth,net,web3,txpool,miner' --bootnodes 'enode://bb9b7408f9f18a7a731acd1afc4085758a7de599ab3a04cdb532953c06d37ad8647a662e055e1b138f0dae3b35c17a3d3d096b368037867512bca76962d54752@127.0.0.1:30303' --networkid 6283 --gasprice '1' -unlock 'fcdca607e8d3aaad6147d5c7cd821679c04c86aa' --password node1/password.txt --mine
```
