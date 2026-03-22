# 🛡️ IdentChain: The Biometric Gateway to USDT

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![ERC-4337](https://img.shields.io/badge/Standard-ERC--4337-blue)](https://eips.ethereum.org/EIPS/eip-4337)
[![Platform-Ethereum](https://img.shields.io/badge/Platform-Ethereum/L2-green)](#)

**"Your Identity is Your Key – No More Seed Phrases."**

IdentChain is a revolutionary **Smart Wallet** built on **Account Abstraction (ERC-4337)**. It eliminates the complexities of Web3 by replacing traditional seed phrases with **Biometric Authentication (FaceID/Passkeys)** and enabling **Gasless Transactions** using **Tether (USDT)**.

---

## 🌟 Why IdentChain? Innovation)

Current crypto wallets are hard to use. Losing 12 words means losing your money. **IdentChain changes that.**

* **🚫 Zero Seed Phrases:** We use **WebAuthn** to turn your phone's Secure Enclave into a hardware wallet.
* **⛽ Native USDT Gas:** Pay transaction fees directly in **USDT**. No need to buy ETH or MATIC first.
* **🔐 Biometric Recovery:** Recover your account using your face or fingerprint on any authorized device.
* **⚡ One-Click UX:** Experience a banking app feel with the security of a non-custodial blockchain wallet.

---

## 🛠️ Technical Stack

IdentChain is powered by the latest advancements in the Ethereum ecosystem:

| Layer | Technology |
| :--- | :--- |
| **Protocol** | **ERC-4337** (Account Abstraction) |
| **Cryptography** | **Secp256r1** (WebAuthn / Passkeys) |
| **Stablecoin Logic** | **Tether WDK** (Wallet Development Kit) |
| **Execution** | **EntryPoint & Bundler** Architecture |
| **Smart Contracts** | **Solidity ^0.8.19** |

---

## 🏗️ How It Works

### 1. Account Validation (`validateUserOp`)
When a user initiates a transfer, the Smart Contract verifies the **biometric signature** against the registered public key on-chain. If the signature is valid, the transaction proceeds.

### 2. The Paymaster (Gasless Logic)
IdentChain uses a custom **Paymaster** contract. The Paymaster pays the network fee (Gas) in ETH/MATIC and simultaneously deducts the equivalent value in **USDT** from the user's wallet. This creates a seamless "Gasless" experience.

---

## 📂 Repository Layout

```text
├── contracts/          # Smart Contracts (Solidity)
│   ├── IdentAccount.sol  # Core Smart Wallet Logic
│   └── Paymaster.sol     # USDT Gas-fee abstraction
├── docs/               # Technical Whitepaper & Specs
├── scripts/            # Deployment & Testing scripts
└── README.md           # Project Documentation
