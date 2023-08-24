# Running M7 Coin on Ubuntu 20.04

## Server Requirements:

- Operating System: Ubuntu 20.04
- Type: Secured VPS 
- RAM: 8 Gigs RAM
- Cores: 4 Processing Core
- Disk: 100 GB SSD

## 1. Downloading and installing geth:

```sh
wget https://github.com/enterwayne/m7coin/releases/download/v1.0/geth-alltools-linux-amd64.tar.xz && tar -xvf geth-alltools-linux-amd64.tar.xz && cd geth-alltools-linux-amd64 && cp * /usr/local/bin && cd ../ && rm -rf geth-alltools-linux-amd64 && rm geth-alltools-linux-amd64.tar.xz
```



## 2.1 Download MainNet Genesis File:
```sh
wget https://github.com/enterwayne/m7coin/releases/download/v1.0/msevencoin.json
```


or (if running testnet)


## 2.2 Download TestNet Genesis File:
```sh
wget https://github.com/enterwayne/m7coin/releases/download/v1.0/msevencointestnet.json
```



## 3.1 Initialising Data Directory for MainNet:
```sh
geth --datadir "/root/.msevencoin" init msevencoin.json
```


or (if running testnet)


## 3.2 Initialising Data Directory for TestNet:
```sh
geth --datadir "/root/.msevencointestnet" init msevencointestnet.json
```



## 4.1 Running M7 Coin MainNet:
```sh
screen geth --datadir "/root/.msevencoin" --networkid 99785  --port 5280 --syncmode 'full' --bootnodes enode://bfc45c38063475a6ee2cff45b3c72d296173b264bc48ae7007399dc60b893dae2df5dcb5a6ee6efe5541569da85dd47262534d23543f00a0975aa6076979b08f@172.105.49.176:5280 2>>/root/.msevencoin/chain.log &
```

or (if running testnet)


## 4.2 Running M7 Coin TestNet:
```sh
screen geth --datadir "/root/.msevencointestnet" --networkid 83205 --port 15280 --syncmode 'full' --bootnodes enode://3444ed6295e89c34997b24656df3fd1246eb006cda0e6cbe8206a143d28f382b867ebe57836d91343bdfb3591555ee266ca12220336b7b749445f1b5f62d6e06@172.104.206.6:15280 --gcmode=archive --http --http.port 19672 -http.vhosts="localhost" --http.api "eth,net,web3,txpool" 2>>/root/.msevencointestnet/chain.log &

```




### Web3 Documentation:

https://web3js.readthedocs.io/en/v1.2.2/getting-started.html#adding-web3-js


### RPC Documentation:

https://ethereum.github.io/execution-apis/api-documentation
