# Foundry

Foundry is a smart contract development toolchain.

With Foundry you can manage your dependencies, compile your project, run tests, deploy smart contracts, and interact with the chain from the command-line and via Solidity scripts.

Check out the [Foundry Book](https://book.getfoundry.sh/) to get started with using Foundry with Orange.

---

# Using Foundry with Orange

Foundry supports Orange out-of-the-box.

Just provide the Orange RPC URL and Chain ID when deploying and verifying your contracts.

## Mainnet

### Deploying a smart contract

```bash
forge create ... --rpc-url=https://rpc.orangechain.xyz
```

### Verifying a smart contract

```bash
forge verify-contract ... --chain-id 61022
```

## Testnet

### Deploying a smart contract

```bash
forge create ... --rpc-url=https://testnet-rpc.orangechain.xyz
```

### Verifying a smart contract

```bash
forge verify-contract ... --chain-id 240515
```