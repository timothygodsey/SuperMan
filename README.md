# ERC20 Token Bridge

## Team Members

- @timothygodsey - Developer


## Introduction

This project is using Polymer Infrastructure to bridge between OP Sepolia and Base Sepolia testnet. It provides a delicated UI to help users to know the balance of ERC20 tokens on both chains. Users can bridge ERC20 token between chain via one-click.The core logic is managed through a custom IBC (Inter-Blockchain Communication) channel of Polymer, enabling secure and verifiable transactions across different blockchains.


## Steps to reproduce


1. Contract install, compile, deploy
```
just install
npx hardhat compile
just deploy optimism base
```
2. Copy the result of contract deployed(port address) or go to /config/config.json copy sendUniversalPacket.optimism.portAddr and sendUniversalPacket.base.portAddr
3. Go to /ibc-token-bridge/src/App.vue replace `OP_PORT_ADDRESS` and `BASE_PORT_ADDRESS` with port address from step 2
4. Go to /artifacts/contracts/IBCToken.sol/IBCToken.json file to copy ABI
5. Go to /ibc-token-bridge/src/abi.js replace `CONTRACT_ABI` with ABI from setp 4
6. Frontend install, start
```
cd ibc-token-bridge
npm i
npm run serve
```

## Proof of testnet interaction

After following the steps above you should have interacted with the testnet. You can check this at the [IBC Explorer](https://explorer.ethdenver.testnet.polymer.zone/).

Here's the data of our application:

- Contract (OP Sepolia) : 0xc958C5Ed8f1deAc4B1763889a45a6a24d9EF3871
- Contract (Base Sepolia): 0xc958C5Ed8f1deAc4B1763889a45a6a24d9EF3871
- Channel (OP Sepolia): 0xc958C5Ed8f1deAc4B1763889a45a6a24d9EF3871
- Channel (Base Sepolia): 0xc958C5Ed8f1deAc4B1763889a45a6a24d9EF3871

- Proof of Testnet interaction:
    - [SendTx](https://optimism-sepolia.blockscout.com/tx/0x27a859bc3038ee5bbe90c71c39007005732ca33a355181cd3bef3ac779e3f736)
    - [RecvTx](https://base-sepolia.blockscout.com/tx/0xe206968e327389e3c1cf18e6dcf1b6503b97f72fee31a6ab15f7b41ce5881d5c)
    - [Ack](https://base-sepolia.blockscout.com/tx/0xe206968e327389e3c1cf18e6dcf1b6503b97f72fee31a6ab15f7b41ce5881d5c)

## What we learned

How to make a dApp using Polymer.

## Future Improvements

The cross-chain bridge can be extended to other standard tokens, such as ERC404 token

## License
Apache 2.0