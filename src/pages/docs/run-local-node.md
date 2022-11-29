---
title: Run a local node
description: quick start a local node to dev.
---
## Run a local blockchain node

### Start the local node
To start the local Web3Games node:

1. Open a terminal shell.
2. Change to the root directory where you compiled the Web3Games Chain.
3. Start the node in development mode by running the following command:
```shell
error: failed to run custom build command for prost-build v0.10.4
```
The web3games-node command-line options specify how you want the running node to operate. In this case, the --dev option specifies that the node runs in developer mode using the predefined development chain specification. By default, this option also deletes all active data—such as keys, the blockchain database, and networking information when you stop the node by pressing Control-c. Using the --dev option ensures that you have a clean working state any time you stop and restart the node.
4. Verify your node is up and running successfully by reviewing the output displayed in the terminal.
5. The terminal should display output similar to this:
```shell
2022-08-15 12:47:42 Web3Games Node    
2022-08-15 12:47:42 ✌️  version 0.0.1-9ea9897c047    
2022-08-15 12:47:42 ❤️  by Web3Games Developers, 2021-2022    
2022-08-15 12:47:42 📋 Chain specification: Web3Games Development Testnet    
2022-08-15 12:47:42 🏷  Node name: loose-tramp-0752    
2022-08-15 12:47:42 👤 Role: AUTHORITY    
2022-08-15 12:47:42 💾 Database: RocksDb at /var/folders/wz/my4gt5p11jg_35_mmj2g63kc0000gn/T/substrateCfnFIF/chains/web3games_dev/db/full    
2022-08-15 12:47:42 ⛓  Native runtime: web3games-node-2 (web3games-node-1.tx1.au1)    
2022-08-15 12:47:42 🔨 Initializing Genesis block/state (state: 0xbbde…d5eb, header-hash: 0xd50b…6991)    
2022-08-15 12:47:42 👴 Loading GRANDPA authority set from genesis on what appears to be first startup.    
2022-08-15 12:47:43 Using default protocol ID "sup" because none is configured in the chain specs    
2022-08-15 12:47:43 🏷  Local node identity is: 12D3KooWMWefkjFNsmfXBPH8rxo79wEp3eppKCiYokHoYf6iedkk    
2022-08-15 12:47:43 💻 Operating system: macos    
2022-08-15 12:47:43 💻 CPU architecture: aarch64    
2022-08-15 12:47:43 📦 Highest known block at #0    
2022-08-15 12:47:43 〽️ Prometheus exporter started at 127.0.0.1:9615    
2022-08-15 12:47:43 Running JSON-RPC HTTP server: addr=127.0.0.1:9933, allowed origins=None    
2022-08-15 12:47:43 Running JSON-RPC WS server: addr=127.0.0.1:9944, allowed origins=None    
2022-08-15 12:47:47 Accepting new connection, 1/100
2022-08-15 12:47:48 🙌 Starting consensus session on top of parent 0xd50b16401f8204b1fbe6384efbcd5b1d0f6559429046406863ce3f77eb896991    
2022-08-15 12:47:48 🎁 Prepared block for proposing at 1 (5 ms) [hash: 0xbab6379955442946faeb42439bc20f55171fd1ec6a0a28d9429ae919b909d1a2; parent_hash: 0xd50b…6991; extrinsics (1): [0x7cfd…d3fd]]    
2022-08-15 12:47:48 🔖 Pre-sealed block for proposal at 1. Hash now 0x416826dcf0a19c8c5ea9da6926526943a880ff72f0c023719e6d311e4f6e4d6b, previously 0xbab6379955442946faeb42439bc20f55171fd1ec6a0a28d9429ae919b909d1a2.    
2022-08-15 12:47:48 ✨ Imported #1 (0x4168…4d6b)    
2022-08-15 12:47:48 💤 Idle (0 peers), best: #1 (0x4168…4d6b), finalized #0 (0xd50b…6991), ⬇ 0 ⬆ 0    
2022-08-15 12:47:53 💤 Idle (0 peers), best: #1 (0x4168…4d6b), finalized #0 (0xd50b…6991), ⬇ 0 ⬆ 0    
2022-08-15 12:47:54 🙌 Starting consensus session on top of parent 0x416826dcf0a19c8c5ea9da6926526943a880ff72f0c023719e6d311e4f6e4d6b    
2022-08-15 12:47:54 🎁 Prepared block for proposing at 2 (2 ms) [hash: 0xa93100c623c816084389b4947ef9db6f08e9f47428f2e367a8fdee73abfc84c6; parent_hash: 0x4168…4d6b; extrinsics (1): [0xefad…282b]]    
2022-08-15 12:47:54 🔖 Pre-sealed block for proposal at 2. Hash now 0x4ced2fd9fd1b4d48ea8ca11ad3b64d9fae05298bfc8a16b257556a34e9d2e5af, previously 0xa93100c623c816084389b4947ef9db6f08e9f47428f2e367a8fdee73abfc84c6.    
2022-08-15 12:47:54 ✨ Imported #2 (0x4ced…e5af)    
2022-08-15 12:47:58 💤 Idle (0 peers), best: #2 (0x4ced…e5af), finalized #0 (0xd50b…6991), ⬇ 0 ⬆ 0
```
If the number after finalized is increasing, your blockchain is producing new blocks and reaching consensus about the state they describe.
We'll explore the details of the log output in a later tutorial. For now, it's only important to know that your node is running and producing blocks.
6. Keep the terminal that displays the node output open to continue.

### Check Web3Games Chain By Dev Explorer

[Polkadotjs/app](https://polkadot.js.org/apps/?rpc=ws%3A%2F%2F127.0.0.1%3A9944#/js)

### Stop the local node

After a successful transfer, you can continue to explore the front-end template components or stop the local Substrate node the state changes you made. Because you specified the --dev option when you started the node, stopping the local node stops the blockchain and purges all persistent block data so that you can start with a clean state next time you start the node.

To stop the local Substrate node:

1. Return to the terminal shell where the node output is displayed.
2. Press Control-c to terminate the running process.
3. Verify your terminal returns to the terminal prompt in the web3games-node directory.
