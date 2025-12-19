# NFT Marketplace - Camada Blockchain

**[🇺🇸 Read in English](README.md)** | **[📖 README Principal do Projeto](../README-PT.md)**

Camada de smart contracts para o NFT Marketplace, construída com Hardhat e Solidity.

## Visão Geral

Este diretório contém a infraestrutura blockchain para o NFT Marketplace, incluindo:

- **NFTMarket.sol**: Contrato principal do marketplace para listar e vender NFTs
- **NFTCollection.sol**: Contrato de token ERC721 para criar NFTs (MabesiNFT - MBN)

## Tecnologias

- Hardhat ^2.18.1
- Solidity 0.8.20
- OpenZeppelin Contracts ^4.8.3
- TypeScript
- Polygon Mumbai Testnet

## Scripts Disponíveis

```bash
npm test          # Executar testes com relatório de cobertura
npm run deploy    # Implantar contratos na testnet Mumbai
npm run verify    # Verificar contratos no PolygonScan
```

## Configuração

Crie um arquivo `.env` baseado no `.env.example`:

```bash
SECRET=           # Frase mnemônica de 12 palavras do MetaMask
API_KEY=          # Chave API do PolygonScan
RPC_URL=          # URL do servidor RPC (ex: https://polygon-mumbai-bor.publicnode.com)
CHAIN_ID=         # Chain ID (80001 para Mumbai)
```

## Início Rápido

1. Instale as dependências:
```bash
npm install
```

2. Configure seu arquivo `.env`

3. Implante os contratos:
```bash
npm run deploy
```

4. Copie os endereços dos contratos implantados para o arquivo `.env.local` do dapp

## Documentação

Para documentação completa, instruções de instalação e exemplos de uso, veja o [README principal do projeto](../README-PT.md).
