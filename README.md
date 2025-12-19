# NFT Marketplace

**[🇧🇷 Leia em Português](README-PT.md)**

![Project Banner](./banner.png)

A decentralized NFT marketplace built on Ethereum-compatible blockchains, enabling users to mint, list, buy, and sell NFTs with a modern web interface.

## :speech_balloon: Description

This project is a complete NFT marketplace implementation consisting of two integrated layers: a blockchain layer with Solidity smart contracts and a dapp layer with a Next.js web interface. The marketplace allows users to create (mint) their own NFTs, list them for sale, browse available NFTs, and purchase items from other users. All transactions are secured by smart contracts deployed on the Polygon Mumbai testnet, with NFT metadata stored on IPFS via Pinata.

## Table of Contents

- [Features](#features)
- [Architecture](#architecture)
  - [Blockchain Layer](#blockchain-layer)
  - [Dapp Layer](#dapp-layer)
- [Built With](#built-with)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Configuration](#configuration)
  - [Usage](#usage)
  - [Building](#building)
- [Project Structure](#project-structure)
- [Back Matter](#back-matter)
  - [Acknowledgements](#acknowledgements)
  - [Contributing](#contributing)
  - [Authors & Contributors](#authors--contributors)
  - [Legal Disclaimer](#legal-disclaimer)
  - [License](#license)

## Features

- **NFT Minting**: Create your own ERC721 NFTs with custom metadata and images
- **Marketplace Listing**: List NFTs for sale with custom pricing
- **Buy/Sell Functionality**: Purchase NFTs directly through smart contracts
- **Wallet Integration**: Connect with MetaMask and other Web3 wallets via Web3Modal
- **IPFS Storage**: Decentralized storage of NFT metadata and images using Pinata
- **User Dashboard**: View your owned NFTs and items you've created
- **Market Browser**: Browse all available NFTs listed on the marketplace
- **Listing Fee System**: 0.025 ETH fee for listing items (configurable)
- **Secure Transactions**: ReentrancyGuard protection and OpenZeppelin security standards
- **Responsive Design**: Modern UI built with TailwindCSS

## Architecture

This project follows a two-layer architecture, combining blockchain smart contracts with a modern web application.

### Blockchain Layer

The blockchain layer contains the smart contracts that power the marketplace functionality.

**📁 Location**: [`/blockchain`](./blockchain)  
**📖 Documentation**: [Blockchain Layer README](./blockchain/README.md)

**Key Components:**

- **NFTMarket Contract**: Core marketplace logic for listing and selling NFTs
- **NFTCollection Contract**: ERC721 token contract for minting NFTs (MabesiNFT - MBN)

**Key Technologies:**
- Hardhat ^2.18.1 (development environment)
- Solidity 0.8.20
- OpenZeppelin Contracts ^4.8.3
- TypeScript
- Polygon Mumbai Testnet

**Available Scripts:**
```bash
npm test          # Run tests with coverage report
npm run deploy    # Deploy contracts to Mumbai testnet
npm run verify    # Verify contracts on PolygonScan
```

**Smart Contract Features:**
- Listing fee mechanism (0.025 ETH)
- Market item creation and sales
- Query functions for market items, user NFTs, and created items
- Automatic approval for marketplace operations
- Protection against marketplace approval removal

---

### Dapp Layer

The dapp layer provides the user interface for interacting with the smart contracts.

**📁 Location**: [`/dapp`](./dapp)  
**📖 Documentation**: [Dapp Layer README](./dapp/README.md)

**Key Components:**

- **Home Page**: Browse all available NFTs on the marketplace
- **Create Page**: Mint new NFTs with image upload to IPFS
- **Account Page**: View your owned NFTs and created items
- **Components**: Reusable UI components (Card, Featured, Header, Footer)

**Key Technologies:**
- Next.js 14.0.3
- React 18
- TypeScript 5
- Ethers.js ^6.8.1 (blockchain interaction)
- TailwindCSS ^3.3.0 (styling)
- Web3Modal ^1.9.12 (wallet connection)
- Axios ^1.6.2 (HTTP requests)

**Available Scripts:**
```bash
npm run dev       # Start development server
npm run build     # Build for production
npm start         # Start production server
npm run lint      # Run ESLint
```

## Built With

**Blockchain:**
- [Hardhat](https://hardhat.org/) - Ethereum development environment
- [Solidity](https://soliditylang.org/) - Smart contract programming language
- [OpenZeppelin](https://www.openzeppelin.com/contracts) - Secure smart contract library
- [Ethers.js](https://docs.ethers.org/) - Ethereum library for JavaScript/TypeScript

**Frontend:**
- [Next.js](https://nextjs.org/) - React framework for production
- [React](https://react.dev/) - JavaScript library for building user interfaces
- [TypeScript](https://www.typescriptlang.org/) - Typed superset of JavaScript
- [TailwindCSS](https://tailwindcss.com/) - Utility-first CSS framework
- [Web3Modal](https://github.com/WalletConnect/web3modal) - Multi-wallet connection library

**Infrastructure:**
- [Polygon](https://polygon.technology/) - Ethereum scaling solution (Mumbai testnet)
- [Pinata](https://www.pinata.cloud/) - IPFS pinning service for NFT metadata

## Getting Started

### Prerequisites

- Node.js (LTS version recommended)
- npm or yarn package manager
- MetaMask or another Web3 wallet
- Polygon Mumbai testnet MATIC tokens (for deployment and testing)
- Pinata account (for IPFS storage)
- PolygonScan API key (for contract verification)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/nft-marketplace.git
cd nft-marketplace
```

2. Install blockchain layer dependencies:
```bash
cd blockchain
npm install
```

3. Install dapp layer dependencies:
```bash
cd ../dapp
npm install
```

### Configuration

#### Blockchain Layer Configuration

Create a `.env` file in the `blockchain` directory:

```bash
# MetaMask mnemonic 12-word phrase
SECRET=your twelve word mnemonic phrase here

# Blockchain API Key (get from PolygonScan)
API_KEY=your_polygonscan_api_key

# RPC Server URL
RPC_URL=https://polygon-mumbai-bor.publicnode.com

# RPC Chain ID (80001 for Mumbai)
CHAIN_ID=80001
```

#### Dapp Layer Configuration

Create a `.env.local` file in the `dapp` directory:

```bash
# BLOCKCHAIN CONFIG -----------------------

# NFT Marketplace contract address (after deployment)
NEXT_PUBLIC_MARKETPLACE_ADDRESS=0x...

# NFT Collection contract address (after deployment)
NEXT_PUBLIC_COLLECTION_ADDRESS=0x...

# Network Chain ID (80001 for Mumbai Polygon)
NEXT_PUBLIC_CHAIN_ID=80001

# PINATA CONFIG --------------------------

# Pinata API Key
NEXT_PUBLIC_PINATA_API_KEY=your_pinata_api_key

# Pinata API Secret
NEXT_PUBLIC_PINATA_API_SECRET=your_pinata_api_secret
```

### Usage

#### 1. Deploy Smart Contracts

First, deploy the smart contracts to the Mumbai testnet:

```bash
cd blockchain
npm run deploy
```

Copy the deployed contract addresses and update the dapp `.env.local` file.

#### 2. Verify Contracts (Optional)

```bash
npm run verify -- <MARKETPLACE_ADDRESS>
npm run verify -- <COLLECTION_ADDRESS> <MARKETPLACE_ADDRESS>
```

#### 3. Run the Dapp

Start the development server:

```bash
cd ../dapp
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

#### 4. Connect Your Wallet

- Click "Connect Wallet" in the application
- Select MetaMask (or your preferred wallet)
- Ensure you're connected to the Polygon Mumbai testnet
- Get test MATIC from a [Mumbai faucet](https://faucet.polygon.technology/)

### Building

To build the dapp for production:

```bash
cd dapp
npm run build
npm start
```

## Project Structure

```
nft-marketplace/
├── blockchain/              # Smart contracts layer
│   ├── contracts/          # Solidity smart contracts
│   │   ├── NFTMarket.sol
│   │   └── NFTCollection.sol
│   ├── scripts/            # Deployment scripts
│   ├── test/               # Contract tests
│   ├── hardhat.config.ts   # Hardhat configuration
│   └── package.json
├── dapp/                   # Web application layer
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── pages/          # Next.js pages
│   │   ├── services/       # API and blockchain services
│   │   └── styles/         # CSS styles
│   ├── public/             # Static assets
│   ├── next.config.js      # Next.js configuration
│   └── package.json
├── banner.png              # Project banner
└── README.md               # This file
```

## Back Matter

### Acknowledgements

- OpenZeppelin for secure smart contract libraries
- Hardhat team for the excellent development environment
- Vercel for Next.js framework
- Pinata for IPFS infrastructure
- Polygon for scalable blockchain infrastructure

### Contributing

Contributions are welcome! Please follow these steps:

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Add your changes: `git add .`
4. Commit your changes: `git commit -am 'Add some feature'`
5. Push to the branch: `git push origin my-new-feature`
6. Submit a pull request :sunglasses:

### Authors & Contributors

| [<img loading="lazy" src="https://github.com/mabesi.png" width=115><br><sub>Mabesi</sub>](https://github.com/mabesi) |
| :---: |

### Legal Disclaimer

<p align="justify">The use of this tool, for any purpose, will occur at your own risk, being your sole responsibility for any legal implications arising from it.</p>
<p align="justify">It is also the end user's responsibility to know and obey all applicable local, state and federal laws. Developers take no responsibility and are not liable for any misuse or damage caused by this program.</p>

### License

This project is licensed under the MIT License.
