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
`[
 
  '0x722CD3807110b915f97Ef732fa50d9c7Dd024f45',
  '0x20f3a0D05b6D28e09259328184a126a28C48ec6d',
  '0xcC41177a047e5a29bC8e24E8e2498308569Ea772',
  '0xeB139Afc4E5Dbb69A5465c846667534c2Dc0b9a5',
  '0x83CfEB661bB4e8651D5Cd66924e89EA019F579cd',
  '0x9F58dB8AB1d68df1248818f4B606e1d96D1A26D9',
  '0x483160125F4D6Cf3539C6B0166f6a52CF5D4deA7',
  '0xDc620012294648cC496222d59B23e7cF26396849',
  '0xE2995Ad9A679e4935860b067dF292779A9B19a05',
  '0x6DAA80cf88913F0337C7c7fE85073e214851463e'

]`

find out one account address:
```linux
> accounts[0]
```