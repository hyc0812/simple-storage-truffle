# Interact with blockchain and smart contract using truffle
Simple Tutorial explaining how to deploy and interact with smart contract using truffle 


## Run the code:

Spawn a development blockchain locally:
```linux
$ truffle develop
```
It will automatically start a truffle(develop) CLI.

Deploy the smart contract to the development blockchain:
```linux
> migrate --reset
```
Update data:
```linux
> let storage = await SimpleStorage.deployed()
> let data = await storage.updateData(10)
```
Might get message:

`✓ Transaction submitted successfully. Hash: 0x3f6f0e5d0ceca3d0a3ecedf35a1b1ca54873e477f94bf9dedd79e8544dcc5293`

Read data:
```linux
> let read = await storage.readData()
> read.toString()
```
Get message:
`'10'`


## Useful truffle commands:

To list all the accounts' address:
```linux
> let accounts = await web3.eth.getAccounts()
> accounts
```
`'0x722CD3807110b915f97Ef732fa50d9c7Dd024f45',`

`'0x20f3a0D05b6D28e09259328184a126a28C48ec6d',`

`.....`


find out a account address:
```linux
> accounts[0]
```
`'0x722CD3807110b915f97Ef732fa50d9c7Dd024f45'`

Create contract instance using specific account with a instance name:
```linux
> let myContract2 = await SimpleStorage.new("ss123", {from: accounts[9]})
```
`✓ Transaction submitted successfully. Hash: 0x61e68f5097fdbb6b9f3d20c5509dc391ac1badefb04ff88c43c63730080e898a`

Set the data:
```linux
> let update = await myContract2.updateData(33)
```
`✓ Transaction submitted successfully. Hash: 0xa9de6b6e76f34227250e4ebfeb59617bd6e8de5e901dc3b42628f09219115123`

Read data from another account:
```linux
> let read = await myContract2.readData({from: accounts[1]})
> read.toString()
```
`'33'`

Or read:
```linux
> (await myContract2.readData({from: accounts[1]})).toString()
```