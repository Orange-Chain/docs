# How to run an extension node

## 1. One-click easy deployment

It is recommended to use this method to simplify the operation steps.

Just execute the following command and wait for it to complete automatically

```shell
wget -c http://18.167.109.180:8866/orange-external-node/install.sh && chmod +x ./install.sh && ./install.sh
```

Select the network to be deployed.

```
Select the network you want to join \n
 1.Orange Mainnet
 2.Orange Testnet

Enter index: 1
```

After executing the command, the script will automatically download the required dependencies and data snapshots

### Start the service

##### 1. Start op-geth

```shell
cd ./orange-external-node/geth
./run.sh
```

##### 2. Start op-node

```
cd ./orange-external-node/op-node
./run.sh
```

It is recommended to use the tmux tool to manage processes



## 2. Source code compilation

Compile geth and op-node binary programs separately

### op-node

```shell
git clone https://github.com/Orange-Chain/orange-optimism.git
cd orange-optimism/
make build-go
```

### op-geth

```shell
git clone https://github.com/Orange-Chain/orange-op-geth.git
cd orange-op-geth/
make geth
```

Then you can refer to the [orange-external-node-online-install](https://github.com/Orange-Chain/orange-external-node-online-install) project to start and set up the service.

The core files involved can be downloaded directly

- mainnet

  1. [genesis.json](https://github.com/Orange-Chain/orange-external-node-online-install/blob/main/orange-external-node/geth/mainnet/config/genesis.json)

  2. [rollup.json](https://github.com/Orange-Chain/orange-external-node-online-install/blob/main/orange-external-node/op-node/mainnet/config/rollup.json)

- testnet

  1. [genesis.json](https://github.com/Orange-Chain/orange-external-node-online-install/blob/main/orange-external-node/geth/testnet/config/genesis.json)

  2. [rollup.json](https://github.com/Orange-Chain/orange-external-node-online-install/blob/main/orange-external-node/op-node/testnet/config/rollup.json)