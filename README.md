# TrustChain Final 🔗

A complete Stellar blockchain dApp with smart contract, tests and demo video.

## 🌐 Live Demo
👉 https://trustchain-final.vercel.app

## 🎥 Demo Video
👉 https://youtu.be/q-A2phdjtME

## 📌 Project Description
TrustChain Final is a complete end-to-end Stellar dApp featuring multi-wallet support, smart contract integration, 4 passing tests, real-time activity feed and full documentation.

## 🛠️ Tech Stack
- React + Vite
- Stellar SDK
- Freighter Wallet API
- Stellar Testnet (Horizon)
- Soroban RPC (Smart Contract)
- Rust + Soroban SDK (Smart Contract)
- Vitest (Testing)

## ✨ Features
- Multi-wallet support (Freighter, xBull, Albedo)
- 3 error types handled
- Custom smart contract deployed and called from frontend
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

### About the Contract
This is a **custom, self-made Soroban smart contract** written from scratch in **Rust**. It was built specifically for TrustChain Final and deployed directly to Stellar Testnet using the Stellar CLI.

The contract has 3 functions:
- `send_payment` — records and validates XLM payment amount
- `validate` — validates payment amount is positive and within limits
- `version` — returns the contract version

### Contract Details
- **Contract ID:** CA7S27CDLIGZMZT3FMBROSGCJRP4BNPWDXUN5MKTKOVX3RGAGLSVT4EA
- **Network:** Stellar Testnet
- **Type:** WASM Contract (Soroban)
- **Language:** Rust
- **Contract Folder:** `contract/src/lib.rs`

### Contract Links
- 🔗 Direct URL: https://stellar.expert/explorer/testnet/contract/CA7S27CDLIGZMZT3FMBROSGCJRP4BNPWDXUN5MKTKOVX3RGAGLSVT4EA
- 🔗 [View Deployed Contract on Stellar Expert](https://stellar.expert/explorer/testnet/contract/CA7S27CDLIGZMZT3FMBROSGCJRP4BNPWDXUN5MKTKOVX3RGAGLSVT4EA)

### How the Contract Was Written
The contract is located in `contract/src/lib.rs`:

```rust
#![no_std]
use soroban_sdk::{contract, contractimpl, Env, Symbol, symbol_short, Address, log};

#[contract]
pub struct TrustChainContract;

#[contractimpl]
impl TrustChainContract {
    pub fn send_payment(env: Env, from: Address, amount: u64) -> u64 {
        from.require_auth();
        log!(&env, "Payment sent: {}", amount);
        amount
    }
    pub fn version(_env: Env) -> Symbol {
        symbol_short!("TC_v1")
    }
    pub fn validate(_env: Env, amount: u64) -> bool {
        amount > 0 && amount <= 1_000_000
    }
}
```

### How the Contract Was Built & Deployed
```bash
# Step 1: Add WASM target
rustup target add wasm32v1-none

# Step 2: Build the contract
stellar contract build

# Step 3: Generate deployer key
stellar keys generate pritty --network testnet

# Step 4: Fund the account on testnet
stellar keys fund pritty --network testnet

# Step 5: Deploy the contract
stellar contract deploy \
  --wasm target/wasm32v1-none/release/hello_world.wasm \
  --source pritty \
  --network testnet
```

## 🧪 Tests
4 tests passing using Vitest:
- ✅ Validate Stellar wallet address format
- ✅ Validate XLM amount is positive
- ✅ Validate smart contract ID length
- ✅ Reject empty recipient address

## 📸 Test Output
![Test Results](level%203%20screenshots/Test%20Results.jpg)

## 🚀 Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/Pritty05/trustchain-final.git
```

2. Install dependencies:
```bash
cd trustchain-final
npm install
```

3. Run the app:
```bash
npm run dev
```

4. Run tests:
```bash
npx vitest run
```

5. Open browser at http://localhost:5173

## 📋 Requirements
- Freighter Wallet browser extension installed
- Freighter set to Testnet network

## 📸 Screenshots

## 📸 Screenshots

### 1. Wallet Options
![Wallet Options](level%203%20screenshots/Wallet%20Options.jpg)

### 2. Wallet Connected
![Wallet Connected](level%203%20screenshots/Wallet%20Connected.jpg)

### 3. Call Contract
![Call Contract](level%203%20screenshots/Call%20Contract.jpg)

### 4. Transaction Success
![Transaction Success](level%203%20screenshots/Transaction%20Success.jpg)

### 5. Test Results
![Test Results](level%203%20screenshots/Test%20Results.jpg)

### 6. Live Activity Feed
![Live Activity Feed](level%203%20screenshots/Live%20Activity%20Feed.jpg)

### 7. Stellar Expert
![Stellar Expert](level%203%20screenshots/Steller%20Expert.jpg)

---
Made with ❤️ for the Stellar Community 🚀