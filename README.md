Owner Contract – Hardhat Deployment (Lisk Sepolia)
A clean, production‑ready Hardhat project demonstrating how to compile, configure, and deploy a Solidity smart contract using Hardhat Ignition.
This repository includes:
- A minimal Owner.sol contract
- A matching Ignition deployment module
- Environment‑based network configuration
- Deployment to Lisk Sepolia
- A clear, visual explanation of the workflow

🧭 Architecture Overview
flowchart TD
    A[Owner.sol Contract] --> B[Hardhat Compiler]
    B --> C[Ignition Deployment Module]
    C --> D[Lisk Sepolia RPC]
    D --> E[Blockscout Explorer]



📁 Project Structure
graph TD
    A[hardhatproject/] --> B[contracts/Owner.sol]
    A --> C[ignition/modules/Owner.ts]
    A --> D[hardhat.config.ts]
    A --> E[test/]
    A --> F[.env]
    A --> G[package.json]



🚀 Quick Start
1. Install dependencies
npm install


2. Create your .env file
# Owner Contract — Hardhat deployment guide

This repository demonstrates compiling and deploying the `Owner.sol` contract using Hardhat and Hardhat Ignition. It includes an Ignition deployment module and example artifacts.

Summary
- Contracts: `contracts/Owner.sol`
- Ignition module: `ignition/modules/Owner.ts`
- Networks configured in `hardhat.config.ts`: `sepolia`, `arcTestnet`, `liskSepolia`

Prerequisites
- Node.js v16+ and npm
- A funded testnet account (for test deployments)

1) Prepare your environment

- Create a `.env` file at the project root (do NOT commit it). Example template:

```
# Sepolia RPC
RPC_URL1="https://your-sepolia-rpc.example"

# Arc Testnet RPC
RPC_URL2="https://your-arc-rpc.example"

# Lisk Sepolia RPC
RPC_URL3="https://rpc.sepolia-api.lisk.com"

# Your wallet private key WITHOUT the 0x prefix
PRIVATE_KEY="your_private_key_without_0x"

# Etherscan or explorer API key (used for contract verification)
ETHERSCAN_API_KEY="your_api_key_here"
```

- The repo already expects these variables in `hardhat.config.ts`.

2) Install and build

```bash
npm install
npx hardhat compile
```

3) Run tests

```bash
npx hardhat test
```

4) Local node (optional)

```bash
npx hardhat node
```

5) Deployment (Ignition)

- Deploy the `Owner` module to Lisk Sepolia (example):

```bash
npx hardhat ignition deploy ./ignition/modules/Owner.ts --network liskSepolia
```

- Deploy to Sepolia or Arc Testnet by changing `--network`:

```bash
npx hardhat ignition deploy ./ignition/modules/Owner.ts --network sepolia
npx hardhat ignition deploy ./ignition/modules/Owner.ts --network arcTestnet
```

6) Deploy via script (alternative)

```bash
npx hardhat run --network liskSepolia scripts/deploy.ts
```

7) Verify contracts

- If the target explorer supports verification and you have an API key set in `ETHERSCAN_API_KEY`:

```bash
npx hardhat verify --network sepolia <DEPLOYED_CONTRACT_ADDRESS>
```

Notes & safety
- Never commit private keys. Add `.env` to `.gitignore`.
- Use small test funds on testnets before moving to mainnet.
- Ignition deployment history and journals are in `ignition/deployments/`.

Helpful commands
- Compile: `npx hardhat compile`
- Test: `npx hardhat test`
- Typechain: `npx hardhat typechain`
- Start node: `npx hardhat node`

Files referenced
- Hardhat config: [hardhat.config.ts](hardhat.config.ts)
- Example env: [.env](.env)
- Deployment module: [ignition/modules/Owner.ts](ignition/modules/Owner.ts)

If you want, I can also:
- add a `.env.example` file, or
- run the test suite now, or
- commit this README update for you.

---

MIT
