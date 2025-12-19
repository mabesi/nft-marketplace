# NFT Marketplace - Blockchain Layer

**[🇧🇷 Leia em Português](README-PT.md)** | **[📖 Main Project README](../README.md)**

Smart contracts layer for the NFT Marketplace, built with Hardhat and Solidity.

## Overview

This directory contains the blockchain infrastructure for the NFT Marketplace, including:

- **NFTMarket.sol**: Core marketplace contract for listing and selling NFTs
- **NFTCollection.sol**: ERC721 token contract for minting NFTs (MabesiNFT - MBN)

## Technologies

- Hardhat ^2.18.1
- Solidity 0.8.20
- OpenZeppelin Contracts ^4.8.3
- TypeScript
- Polygon Mumbai Testnet

## Available Scripts

```bash
npm test          # Run tests with coverage report
npm run deploy    # Deploy contracts to Mumbai testnet
npm run verify    # Verify contracts on PolygonScan
```

## Configuration

Create a `.env` file based on `.env.example`:

```bash
SECRET=           # MetaMask mnemonic 12-word phrase
API_KEY=          # PolygonScan API key
RPC_URL=          # RPC server URL (e.g., https://polygon-mumbai-bor.publicnode.com)
CHAIN_ID=         # Chain ID (80001 for Mumbai)
```

## Quick Start

1. Install dependencies:
```bash
npm install
```

2. Configure your `.env` file

3. Deploy contracts:
```bash
npm run deploy
```

4. Copy the deployed contract addresses to the dapp `.env.local` file

## Documentation

For complete documentation, installation instructions, and usage examples, see the [main project README](../README.md).
