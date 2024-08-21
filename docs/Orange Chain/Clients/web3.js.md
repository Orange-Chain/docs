# web3.js

[web3.js](https://web3js.org/) is a JavaScript library that allows developers to interact with EVM-compatible blockchain networks.

You can use web3.js to interact with smart contracts deployed on the Orange network.

---

## Install

To install web3.js run the following command:

```bash
npm install web3
```

## Setup

Before you can start using web3.js, you need to import it into your project.

Add the following line of code to the top of your file to import web3.js:

```javascript
//web3.js v1
const Web3 = require('web3');

//web3.js v4
const { Web3 } = require('web3');
```

## Connecting to Base

You can connect to Base by instantiating a new web3.js `Web3` object with a RPC URL of the Orange network:

```javascript
const { Web3 } = require('web3');

const web3 = new Web3('https://rpc.orangechain.xyz');
```

:::info

To alternatively connect to Orange Testnet, change the above URL from `https://rpc.orangechain.xyz` to `https://testnet-rpc.orangechain.xyz`.

:::

## Accessing data

Once you have created a provider, you can use it to read data from the Orange network.

For example, you can use the `getBlockNumber` method to get the latest block:

```javascript
async function getLatestBlock(address) {
  const latestBlock = await web3.eth.getBlockNumber();
  console.log(latestBlock.toString());
}
```

## Deploying contracts

Before you can deploy a contract to the Orange network using web3.js, you must first create an account.

You can create an account by using `web3.eth.accounts`:

```javascript
const privateKey = “PRIVATE_KEY”;
const account = web3.eth.accounts.privateKeyToAccount(privateKey);
```

:::info

`PRIVATE_KEY` is the private key of the wallet to use when creating the account.

:::

## Interacting with smart contracts

You can use web3.js to interact with a smart contract on Base by instantiating a `Contract` object using the ABI and address of a deployed contract:

```javascript
const abi = [
… // ABI of deployed contract
];

const contractAddress = "CONTRACT_ADDRESS"

const contract = new web3.eth.Contract(abi, contractAddress);
```

Once you have created a `Contract` object, you can use it to call desired methods on the smart contract:

```javascript
async function setValue(value) {
  // write query
  const tx = await contract.methods.set(value).send();
  console.log(tx.transactionHash);
}

async function getValue() {
  // read query
  const value = await contract.methods.get().call();
  console.log(value.toString());
}
```