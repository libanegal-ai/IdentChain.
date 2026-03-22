import React, { useState } from 'react';
import { Shield, Send, CreditCard, User, Bell, ChevronRight, Fingerprint } from 'lucide-react';

const IdentChainDashboard = () => {
  const [balance, setBalance] = useState("2,450.50");
  const [isAuthenticated, setIsAuthenticated] = useState(false);

  return (
    <div className="min-h-screen bg-slate-950 text-white font-sans p-4">
      {/* Header Section */}
      <header className="flex justify-between items-center mb-8 p-4">
        <div className="flex items-center gap-2">
          <div className="bg-blue-600 p-2 rounded-lg">
            <Shield size={24} />
          </div>
          <h1 className="text-xl font-bold tracking-tight">IdentChain</h1>
        </div>
        <div className="flex gap-4">
          <Bell className="text-slate-400" />
          <div className="w-8 h-8 bg-slate-800 rounded-full border border-slate-700"></div>
        </div>
      </header>

      {/* Wallet Balance Card */}
      <div className="bg-gradient-to-br from-blue-700 to-indigo-900 rounded-3xl p-6 mb-8 shadow-2xl relative overflow-hidden">
        <div className="relative z-10">
          <p className="text-blue-100 text-sm mb-1">Total USDT Balance</p>
          <h2 className="text-4xl font-bold mb-6">${balance}</h2>
          <div className="flex gap-4">
            <button className="flex-1 bg-white/10 backdrop-blur-md border border-white/20 py-3 rounded-xl flex items-center justify-center gap-2 hover:bg-white/20 transition">
              <Send size={18} /> Send
            </button>
            <button className="flex-1 bg-white/10 backdrop-blur-md border border-white/20 py-3 rounded-xl flex items-center justify-center gap-2 hover:bg-white/20 transition">
              <CreditCard size={18} /> Buy
            </button>
          </div>
        </div>
        {/* Decorative circle */}
        <div className="absolute -right-10 -top-10 w-40 h-40 bg-white/10 rounded-full blur-3xl"></div>
      </div>

      {/* Biometric Security Status */}
      <div className="bg-slate-900 border border-slate-800 rounded-2xl p-4 mb-8 flex items-center justify-between">
        <div className="flex items-center gap-3">
          <div className="bg-green-500/10 p-3 rounded-full text-green-500">
            <Fingerprint size={24} />
          </div>
          <div>
            <p className="text-sm font-semibold">Biometric Link Active</p>
            <p className="text-xs text-slate-400">FaceID secured via Passkey</p>
          </div>
        </div>
        <div className="h-2 w-2 bg-green-500 rounded-full animate-pulse"></div>
      </div>

      {/* Recent Transactions */}
      <div className="px-2">
        <div className="flex justify-between items-center mb-4">
          <h3 className="font-bold text-lg">Recent Activity</h3>
          <button className="text-blue-500 text-sm">See All</button>
        </div>

        <div className="space-y-4">
          {[
            { name: "Ahmed Ali", amount: "-50.00", status: "Sent", time: "2m ago" },
            { name: "Merchant Pay", amount: "-120.00", status: "Paid", time: "1h ago" },
            { name: "Deposit", amount: "+500.00", status: "Received", time: "3h ago" },
          ].map((tx, i) => (
            <div key={i} className="flex justify-between items-center p-3 bg-slate-900/50 rounded-xl hover:bg-slate-900 transition cursor-pointer">
              <div className="flex gap-3 items-center">
                <div className="w-10 h-10 bg-slate-800 rounded-full flex items-center justify-center font-bold text-slate-400">
                  {tx.name[0]}
                </div>
                <div>
                  <p className="font-medium text-sm">{tx.name}</p>
                  <p className="text-xs text-slate-500">{tx.time} • Gasless</p>
                </div>
              </div>
              <div className="text-right">
                <p className={`font-bold text-sm ${tx.amount.startsWith('+') ? 'text-green-500' : 'text-white'}`}>
                  {tx.amount} USDT
                </p>
                <p className="text-[10px] text-slate-600 uppercase tracking-widest">{tx.status}</p>
              </div>
            </div>
          ))}
        </div>
      </div>

      {/* Bottom Navigation */}
      <nav className="fixed bottom-0 left-0 right-0 bg-slate-950/80 backdrop-blur-lg border-t border-slate-900 p-4 flex justify-around">
        <div className="text-blue-500 flex flex-col items-center gap-1">
          <Shield size={20} />
          <span className="text-[10px]">Home</span>
        </div>
        <div className="text-slate-500 flex flex-col items-center gap-1">
          <CreditCard size={20} />
          <span className="text-[10px]">Cards</span>
        </div>
        <div className="text-slate-500 flex flex-col items-center gap-1">
          <User size={20} />
          <span className="text-[10px]">Profile</span>
        </div>
      </nav>
    </div>
  );
};

export default IdentChainDashboard;






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
