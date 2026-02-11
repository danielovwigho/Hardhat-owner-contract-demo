# Sample Hardhat Project

This project demonstrates a basic Hardhat use case. It comes with a sample contract, a test for that contract, and a Hardhat Ignition module that deploys that contract.

Lightweight Hardhat project with example contracts and Ignition deployments.

**Project highlights**

- Example contracts: `Owner.sol` (owner management).
- Ignition deployment artifacts are stored under the `ignition/` folder.

**Prerequisites**

- Node.js v16 or newer
- npm

**Install**

```bash
npm install
```

**Common commands**

- Show Hardhat help:

```bash
npx hardhat help
```

- Compile contracts:

```bash
npx hardhat compile
```

- Run tests:

```bash
npx hardhat test
```

- Run tests with gas reporting (if configured):

```bash
REPORT_GAS=true npx hardhat test
```

- Start local node:

```bash
npx hardhat node
```

- Run Ignition deployment for a module (example):

```bash
npx hardhat ignition deploy ./ignition/modules/Owner.ts
```

**Typechain**

Generate TypeScript contract typings:

```bash
npx hardhat typechain
```

**Environment / Deployment**

- Create a `.env` file for RPC URLs and private keys when targeting testnets or mainnet.
- This repo uses `@nomicfoundation/hardhat-ignition` for scripted deployments; see the `ignition/` folder for examples.

**Notes**

- See `package.json` for dev dependencies used by this project.
- Artifacts and build-info are stored under `artifacts/` and `cache/`.
