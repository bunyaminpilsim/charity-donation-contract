# Charity Donation Contract

This repository contains a complete decentralized charity donation platform built using the **Stellar Soroban smart contract platform**. The project is divided into two parts:

---

## 📁 Project Structure

### 1. `charity-donation-token`
This directory contains the **Soroban smart contract** written in Rust. It defines the logic for managing donations through a custom token.

#### Features:
- Creation and configuration of a donation token
- Accepting donations from users
- Emitting events for donations and tracking
- Transparent and secure logic on-chain

> 💡 This contract can be deployed and tested on the Stellar testnet using the Soroban CLI.

---

### 2. `soroban-dapp`
This directory contains the **frontend decentralized application (DApp)** that allows users to interact with the deployed smart contract.

#### Features:
- Connect Stellar wallets (e.g., Freighter)
- Display contract data such as total donations
- Send donation transactions using the donation token
- User-friendly UI for donors

---

## 🚀 Getting Started

### Prerequisites

- [Rust](https://www.rust-lang.org/tools/install)
- [Soroban CLI](https://soroban.stellar.org/docs/install)
- [Node.js](https://nodejs.org/) and npm (for frontend development)

---

## 🛠️ Running the Project

### 1. Compile & Deploy the Contract

```bash
# Navigate to the contract directory
cd charity-donation-token

# Configure identity (replace with your own keys)
soroban config identity add local-user --secret-key <SECRET_KEY>

# Build the contract
soroban contract build

# Deploy to testnet
soroban contract deploy \
  --wasm target/wasm32-unknown-unknown/release/charity_donation_token.wasm \
  --network testnet \
  --source local-user
# Navigate to the frontend directory
cd soroban-dapp

# Install dependencies
npm install

# Start the local development server
npm run dev
