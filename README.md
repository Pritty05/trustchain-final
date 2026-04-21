# TrustChain Final 🔗

A complete Stellar blockchain dApp with smart contract, tests and demo video.

## 🌐 Live Demo
👉 https://trustchain-final.vercel.app

## 🎥 Demo Video
👉 https://youtu.be/IL-mGt_CK34

## 📌 Project Description
TrustChain Final is a complete end-to-end Stellar dApp featuring multi-wallet support, smart contract integration, 4 passing tests, real-time activity feed and full documentation.

## 🛠️ Tech Stack
- React + Vite
- Stellar SDK
- Freighter Wallet API
- Stellar Testnet (Horizon)
- Soroban RPC (Smart Contract)
- Vitest (Testing)

## ✨ Features
- Multi-wallet support (Freighter, xBull, Albedo)
- 3 error types handled
- Smart contract integration
- Real-time XLM balance
- Send XLM transactions
- Transaction status (⏳ Pending → ✅ Success → ❌ Failed)
- Transaction hash + Stellar Explorer link
- Live Activity Feed
- Loading states and progress indicators
- Disconnect wallet

## ⚠️ Error Handling
- Error Type 1: Account not found on testnet
- Error Type 2: Wallet extension not installed
- Error Type 3: User rejected wallet connection

## 📜 Smart Contract
- Contract ID: CDLZFC3SYJYDZT7K67VZ75HPJVIEUVNIXF47ZG2FB2RMQQVU2HHGCN4
- Network: Stellar Testnet
- Called from frontend via Soroban RPC

## 🧪 Tests
4 tests passing using Vitest:
- ✅ Validate Stellar wallet address format
- ✅ Validate XLM amount is positive
- ✅ Validate smart contract ID length
- ✅ Reject empty recipient address

## 🚀 Setup Instructions

1. Clone the repository:
   git clone https://github.com/Pritty05/trustchain-final.git

2. Install dependencies:
   cd trustchain-final
   npm install

3. Run the app:
   npm run dev

4. Run tests:
   npx vitest run

5. Open browser at http://localhost:5173

## 📋 Requirements
- Freighter Wallet browser extension installed
- Freighter set to Testnet network

## 📸 Screenshots

### 1. App Running
![App Running](Level-3%20Screenshots/app-running.png)

### 2. Wallet Selection
![Wallet Selection](Level-3%20Screenshots/wallet%20selection.png)

### 3. Call Contract
![Contract Called](Level-3%20Screenshots/call%20connect.png)

### 4. Transaction Success
![Transaction Success](Level-3%20Screenshots/successful%20tracsaction.png)

### 5. Test Results
![Test Results](Level-3%20Screenshots/test-results.png)

### 6. Live Activity Feed
![Live Activity Feed](Level-3%20Screenshots/live%20activity%20feed.png)