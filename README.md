 # Sui NFT Uploader — Slush Wallet Integration

A complete implementation of an NFT smart contract on Sui Blockchain, combined with a simple DApp flow for:

🔗 Connecting to Slush Wallet

🖼️ Uploading NFT metadata & image

🧱 Deploying & minting NFTs using Move

🚀 Display Standard integration for wallet/explorer compatibility

### 📖 Overview

This project demonstrates how to build and mint NFTs on the Sui blockchain using Move.
It includes:

NFT struct with metadata

Creator field tracking

Mint / Burn functions

Display Standard for NFT previews

Optional frontend integration for uploading NFTs via Slush Wallet

### 🎯 Features

✔ Upload NFT image & metadata

✔ Mint NFT using connected Sui wallet (Slush)

✔ Burn & transfer functionality

✔ Display Standard-ready metadata

✔ Clean and readable Move module

### 📦 Tech Stack

Sui Move – Smart contract

Sui CLI – Deployment

Slush Wallet / Sui Wallet – User interaction

Testnet SUI – Gas fees

(Optional) TypeScript frontend

## 🧱 Smart Contract — NFT Module
Module Path:
sources/nft.move

Core Capabilities:

Unique NFT struct with:

name

description

image_url

creator

Minting NFT and sending it to the caller

Burning NFT

Display Standard for Explorer & Wallet previews

View functions

## 🗂 Project Structure
root/
 ├── Move.toml
 ├── sources/
 │    └── nft.move
 ├── README.md
 └── frontend/      (optional)

## 🚀 Deployment Guide
1. Initialize Move Package
sui move new nft_contract
cd nft_contract

2. Configure Move.toml
[package]
name = "nft"
edition = "2024.beta"

[addresses]
nft_package = "0x0"

[dependencies]
Sui = { 
  git = "https://github.com/MystenLabs/sui.git", 
  subdir = "crates/sui-framework/packages/sui-framework", 
  rev = "framework/testnet" 
}

3. Deploy to Sui Testnet
sui client publish --gas-budget 100000000

## 🔍 Code Explanation
### NFT Struct
public struct NFT has key, store {
    id: UID,
    name: String,
    description: String,
    image_url: Url,
    creator: address
}

Fields Explained:

id — unique identifier

name — NFT title

description — metadata text

image_url — link to hosted image

creator — address of the minter

### Mint Function

Creates an NFT and assigns it to the transaction sender.

### Burn Function

Destroys the NFT and deletes its id.

## 💻 Optional: Frontend Integration (DApp)

If you create a UI for this project, it may include:

Connect / Disconnect Slush Wallet

Upload image → get URL

Fill metadata

Mint NFT button

Preview minted NFT

A lightweight frontend can be added inside the frontend/ folder.

## 🧪 Testing

Use:

sui move test


Includes:

Test-only initializer

Validation for metadata

Mint/Burn logic

## 🤝 Contributing

Pull requests are welcome!
If you find bugs or improvements, feel free to open an issue.

## 📜 License

This project is released under the MIT License.

## ⭐ Support This Project

If you find this useful, consider giving the repo a ⭐ on GitHub!
It helps others discover Sui-related examples and workshops.
