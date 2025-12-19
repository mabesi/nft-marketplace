# NFT Marketplace

**[🇺🇸 Read in English](README.md)**

![Banner do Projeto](./banner.png)

Um marketplace NFT descentralizado construído em blockchains compatíveis com Ethereum, permitindo que usuários criem, listem, comprem e vendam NFTs com uma interface web moderna.

## :speech_balloon: Descrição

Este projeto é uma implementação completa de um marketplace NFT composto por duas camadas integradas: uma camada blockchain com smart contracts em Solidity e uma camada dapp com interface web em Next.js. O marketplace permite que usuários criem (mint) seus próprios NFTs, os listem para venda, naveguem pelos NFTs disponíveis e comprem itens de outros usuários. Todas as transações são protegidas por smart contracts implantados na testnet Polygon Mumbai, com metadados dos NFTs armazenados no IPFS via Pinata.

## Índice

- [Funcionalidades](#funcionalidades)
- [Arquitetura](#arquitetura)
  - [Camada Blockchain](#camada-blockchain)
  - [Camada Dapp](#camada-dapp)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Começando](#começando)
  - [Pré-requisitos](#pré-requisitos)
  - [Instalação](#instalação)
  - [Configuração](#configuração)
  - [Uso](#uso)
  - [Build](#build)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Informações Adicionais](#informações-adicionais)
  - [Agradecimentos](#agradecimentos)
  - [Contribuindo](#contribuindo)
  - [Autores e Contribuidores](#autores-e-contribuidores)
  - [Aviso Legal](#aviso-legal)
  - [Licença](#licença)

## Funcionalidades

- **Criação de NFTs**: Crie seus próprios NFTs ERC721 com metadados e imagens personalizadas
- **Listagem no Marketplace**: Liste NFTs para venda com preços personalizados
- **Compra/Venda**: Compre NFTs diretamente através de smart contracts
- **Integração com Carteiras**: Conecte-se com MetaMask e outras carteiras Web3 via Web3Modal
- **Armazenamento IPFS**: Armazenamento descentralizado de metadados e imagens NFT usando Pinata
- **Painel do Usuário**: Visualize seus NFTs e itens que você criou
- **Navegador de Mercado**: Navegue por todos os NFTs disponíveis listados no marketplace
- **Sistema de Taxa de Listagem**: Taxa de 0.025 ETH para listar itens (configurável)
- **Transações Seguras**: Proteção ReentrancyGuard e padrões de segurança OpenZeppelin
- **Design Responsivo**: Interface moderna construída com TailwindCSS

## Arquitetura

Este projeto segue uma arquitetura de duas camadas, combinando smart contracts blockchain com uma aplicação web moderna.

### Camada Blockchain

A camada blockchain contém os smart contracts que alimentam a funcionalidade do marketplace.

**📁 Localização**: [`/blockchain`](./blockchain)  
**📖 Documentação**: [README da Camada Blockchain](./blockchain/README-PT.md)

**Componentes Principais:**

- **Contrato NFTMarket**: Lógica central do marketplace para listar e vender NFTs
- **Contrato NFTCollection**: Contrato de token ERC721 para criar NFTs (MabesiNFT - MBN)

**Tecnologias Principais:**
- Hardhat ^2.18.1 (ambiente de desenvolvimento)
- Solidity 0.8.20
- OpenZeppelin Contracts ^4.8.3
- TypeScript
- Polygon Mumbai Testnet

**Scripts Disponíveis:**
```bash
npm test          # Executar testes com relatório de cobertura
npm run deploy    # Implantar contratos na testnet Mumbai
npm run verify    # Verificar contratos no PolygonScan
```

**Funcionalidades dos Smart Contracts:**
- Mecanismo de taxa de listagem (0.025 ETH)
- Criação e vendas de itens do mercado
- Funções de consulta para itens do mercado, NFTs do usuário e itens criados
- Aprovação automática para operações do marketplace
- Proteção contra remoção de aprovação do marketplace

---

### Camada Dapp

A camada dapp fornece a interface do usuário para interagir com os smart contracts.

**📁 Localização**: [`/dapp`](./dapp)  
**📖 Documentação**: [README da Camada Dapp](./dapp/README-PT.md)

**Componentes Principais:**

- **Página Inicial**: Navegue por todos os NFTs disponíveis no marketplace
- **Página Criar**: Crie novos NFTs com upload de imagem para IPFS
- **Página Conta**: Visualize seus NFTs e itens criados
- **Componentes**: Componentes de UI reutilizáveis (Card, Featured, Header, Footer)

**Tecnologias Principais:**
- Next.js 14.0.3
- React 18
- TypeScript 5
- Ethers.js ^6.8.1 (interação com blockchain)
- TailwindCSS ^3.3.0 (estilização)
- Web3Modal ^1.9.12 (conexão com carteira)
- Axios ^1.6.2 (requisições HTTP)

**Scripts Disponíveis:**
```bash
npm run dev       # Iniciar servidor de desenvolvimento
npm run build     # Build para produção
npm start         # Iniciar servidor de produção
npm run lint      # Executar ESLint
```

## Tecnologias Utilizadas

**Blockchain:**
- [Hardhat](https://hardhat.org/) - Ambiente de desenvolvimento Ethereum
- [Solidity](https://soliditylang.org/) - Linguagem de programação para smart contracts
- [OpenZeppelin](https://www.openzeppelin.com/contracts) - Biblioteca de smart contracts seguros
- [Ethers.js](https://docs.ethers.org/) - Biblioteca Ethereum para JavaScript/TypeScript

**Frontend:**
- [Next.js](https://nextjs.org/) - Framework React para produção
- [React](https://react.dev/) - Biblioteca JavaScript para construção de interfaces
- [TypeScript](https://www.typescriptlang.org/) - Superset tipado de JavaScript
- [TailwindCSS](https://tailwindcss.com/) - Framework CSS utility-first
- [Web3Modal](https://github.com/WalletConnect/web3modal) - Biblioteca de conexão multi-carteira

**Infraestrutura:**
- [Polygon](https://polygon.technology/) - Solução de escalonamento Ethereum (testnet Mumbai)
- [Pinata](https://www.pinata.cloud/) - Serviço de pinning IPFS para metadados NFT

## Começando

### Pré-requisitos

- Node.js (versão LTS recomendada)
- npm ou yarn como gerenciador de pacotes
- MetaMask ou outra carteira Web3
- Tokens MATIC da testnet Polygon Mumbai (para deploy e testes)
- Conta Pinata (para armazenamento IPFS)
- Chave API do PolygonScan (para verificação de contratos)

### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/seuusuario/nft-marketplace.git
cd nft-marketplace
```

2. Instale as dependências da camada blockchain:
```bash
cd blockchain
npm install
```

3. Instale as dependências da camada dapp:
```bash
cd ../dapp
npm install
```

### Configuração

#### Configuração da Camada Blockchain

Crie um arquivo `.env` no diretório `blockchain`:

```bash
# Frase mnemônica de 12 palavras do MetaMask
SECRET=sua frase mnemônica de doze palavras aqui

# Chave API Blockchain (obtenha no PolygonScan)
API_KEY=sua_chave_api_polygonscan

# URL do Servidor RPC
RPC_URL=https://polygon-mumbai-bor.publicnode.com

# Chain ID RPC (80001 para Mumbai)
CHAIN_ID=80001
```

#### Configuração da Camada Dapp

Crie um arquivo `.env.local` no diretório `dapp`:

```bash
# CONFIGURAÇÃO BLOCKCHAIN -----------------------

# Endereço do contrato NFT Marketplace (após deploy)
NEXT_PUBLIC_MARKETPLACE_ADDRESS=0x...

# Endereço do contrato NFT Collection (após deploy)
NEXT_PUBLIC_COLLECTION_ADDRESS=0x...

# Chain ID da Rede (80001 para Mumbai Polygon)
NEXT_PUBLIC_CHAIN_ID=80001

# CONFIGURAÇÃO PINATA --------------------------

# Chave API Pinata
NEXT_PUBLIC_PINATA_API_KEY=sua_chave_api_pinata

# Secret API Pinata
NEXT_PUBLIC_PINATA_API_SECRET=seu_secret_api_pinata
```

### Uso

#### 1. Implantar Smart Contracts

Primeiro, implante os smart contracts na testnet Mumbai:

```bash
cd blockchain
npm run deploy
```

Copie os endereços dos contratos implantados e atualize o arquivo `.env.local` do dapp.

#### 2. Verificar Contratos (Opcional)

```bash
npm run verify -- <MARKETPLACE_ADDRESS>
npm run verify -- <COLLECTION_ADDRESS> <MARKETPLACE_ADDRESS>
```

#### 3. Executar o Dapp

Inicie o servidor de desenvolvimento:

```bash
cd ../dapp
npm run dev
```

Abra [http://localhost:3000](http://localhost:3000) no seu navegador.

#### 4. Conectar sua Carteira

- Clique em "Connect Wallet" na aplicação
- Selecione MetaMask (ou sua carteira preferida)
- Certifique-se de estar conectado à testnet Polygon Mumbai
- Obtenha MATIC de teste de uma [faucet Mumbai](https://faucet.polygon.technology/)

### Build

Para fazer o build do dapp para produção:

```bash
cd dapp
npm run build
npm start
```

## Estrutura do Projeto

```
nft-marketplace/
├── blockchain/              # Camada de smart contracts
│   ├── contracts/          # Smart contracts Solidity
│   │   ├── NFTMarket.sol
│   │   └── NFTCollection.sol
│   ├── scripts/            # Scripts de deploy
│   ├── test/               # Testes de contratos
│   ├── hardhat.config.ts   # Configuração Hardhat
│   └── package.json
├── dapp/                   # Camada de aplicação web
│   ├── src/
│   │   ├── components/     # Componentes React
│   │   ├── pages/          # Páginas Next.js
│   │   ├── services/       # Serviços de API e blockchain
│   │   └── styles/         # Estilos CSS
│   ├── public/             # Assets estáticos
│   ├── next.config.js      # Configuração Next.js
│   └── package.json
├── banner.png              # Banner do projeto
└── README.md               # Este arquivo
```

## Informações Adicionais

### Agradecimentos

- OpenZeppelin pelas bibliotecas de smart contracts seguros
- Equipe Hardhat pelo excelente ambiente de desenvolvimento
- Vercel pelo framework Next.js
- Pinata pela infraestrutura IPFS
- Polygon pela infraestrutura blockchain escalável

### Contribuindo

Contribuições são bem-vindas! Por favor, siga estes passos:

1. Faça um fork do projeto!
2. Crie sua branch de feature: `git checkout -b minha-nova-feature`
3. Adicione suas mudanças: `git add .`
4. Faça commit das suas mudanças: `git commit -am 'Adiciona nova feature'`
5. Faça push para a branch: `git push origin minha-nova-feature`
6. Submeta um pull request :sunglasses:

### Autores e Contribuidores

| [<img loading="lazy" src="https://github.com/plinio.png" width=115><br><sub>Plinio</sub>](https://github.com/plinio) |
| :---: |

### Aviso Legal

<p align="justify">O uso desta ferramenta, para qualquer finalidade, ocorrerá por sua conta e risco, sendo de sua exclusiva responsabilidade quaisquer implicações legais decorrentes.</p>
<p align="justify">É também responsabilidade do usuário final conhecer e obedecer todas as leis locais, estaduais e federais aplicáveis. Os desenvolvedores não assumem qualquer responsabilidade e não são responsáveis por qualquer uso indevido ou dano causado por este programa.</p>

### Licença

Este projeto está licenciado sob a Licença MIT.
