# NFT Marketplace - Camada Dapp

**[🇺🇸 Read in English](README.md)** | **[📖 README Principal do Projeto](../README-PT.md)**

Camada de aplicação web para o NFT Marketplace, construída com Next.js e React.

## Visão Geral

Este diretório contém a aplicação frontend para o NFT Marketplace, incluindo:

- **Página Inicial**: Navegue por todos os NFTs disponíveis no marketplace
- **Página Criar**: Crie novos NFTs com upload de imagem para IPFS
- **Página Conta**: Visualize seus NFTs e itens criados
- **Componentes**: Componentes de UI reutilizáveis (Card, Featured, Header, Footer)

## Tecnologias

- Next.js 14.0.3
- React 18
- TypeScript 5
- Ethers.js ^6.8.1
- TailwindCSS ^3.3.0
- Web3Modal ^1.9.12
- Axios ^1.6.2

## Scripts Disponíveis

```bash
npm run dev       # Iniciar servidor de desenvolvimento
npm run build     # Build para produção
npm start         # Iniciar servidor de produção
npm run lint      # Executar ESLint
```

## Configuração

Crie um arquivo `.env.local` baseado no `.env.example`:

```bash
NEXT_PUBLIC_MARKETPLACE_ADDRESS=    # Endereço do contrato NFT Marketplace
NEXT_PUBLIC_COLLECTION_ADDRESS=     # Endereço do contrato NFT Collection
NEXT_PUBLIC_CHAIN_ID=               # Chain ID da Rede (80001 para Mumbai)
NEXT_PUBLIC_PINATA_API_KEY=         # Chave API Pinata
NEXT_PUBLIC_PINATA_API_SECRET=      # Secret API Pinata
```

## Início Rápido

1. Instale as dependências:
```bash
npm install
```

2. Configure seu arquivo `.env.local` com os endereços dos contratos implantados

3. Inicie o servidor de desenvolvimento:
```bash
npm run dev
```

4. Abra [http://localhost:3000](http://localhost:3000) no seu navegador

## Documentação

Para documentação completa, instruções de instalação e exemplos de uso, veja o [README principal do projeto](../README-PT.md).
