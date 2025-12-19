# NFT Marketplace - Dapp Layer

**[🇧🇷 Leia em Português](README-PT.md)** | **[📖 Main Project README](../README.md)**

Web application layer for the NFT Marketplace, built with Next.js and React.

## Overview

This directory contains the frontend application for the NFT Marketplace, including:

- **Home Page**: Browse all available NFTs on the marketplace
- **Create Page**: Mint new NFTs with image upload to IPFS
- **Account Page**: View your owned NFTs and created items
- **Components**: Reusable UI components (Card, Featured, Header, Footer)

## Technologies

- Next.js 14.0.3
- React 18
- TypeScript 5
- Ethers.js ^6.8.1
- TailwindCSS ^3.3.0
- Web3Modal ^1.9.12
- Axios ^1.6.2

## Available Scripts

```bash
npm run dev       # Start development server
npm run build     # Build for production
npm start         # Start production server
npm run lint      # Run ESLint
```

## Configuration

Create a `.env.local` file based on `.env.example`:

```bash
NEXT_PUBLIC_MARKETPLACE_ADDRESS=    # NFT Marketplace contract address
NEXT_PUBLIC_COLLECTION_ADDRESS=     # NFT Collection contract address
NEXT_PUBLIC_CHAIN_ID=               # Network Chain ID (80001 for Mumbai)
NEXT_PUBLIC_PINATA_API_KEY=         # Pinata API Key
NEXT_PUBLIC_PINATA_API_SECRET=      # Pinata API Secret
```

## Quick Start

1. Install dependencies:
```bash
npm install
```

2. Configure your `.env.local` file with deployed contract addresses

3. Start development server:
```bash
npm run dev
```

4. Open [http://localhost:3000](http://localhost:3000) in your browser

## Documentation

For complete documentation, installation instructions, and usage examples, see the [main project README](../README.md).
