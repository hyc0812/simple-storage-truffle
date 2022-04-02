# Interact with blockchain and smart contract using truffle
Simple Tutorial explaining how to deploy and interact with smart contract using truffle 


### Run the code:

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
