# Freelance-Market-Escrow---Blockchain-Project

A decentralized freelance marketplace built using Ethereum Smart Contracts and a DApp interface.  
This platform enables clients and freelancers to interact securely without relying on a centralized middleman by using a blockchain-based escrow payment system.

---

# Features

## 1. User Registration & Reputation System

### User Roles
- Client
- Freelancer
- Arbiter (Admin)

### Stored Information
- Name
- Wallet Address
- Role

### Rules
- Freelancers start with a reputation score of `100`
- Prevents duplicate or conflicting registrations using the same wallet address

---

## 2. Job Posting

Only Clients can post jobs.

### Job Information
- Job Title
- Category
- Maximum Budget
- Deadline

### Additional Features
- Each job receives a unique Job ID
- Initial job status is set to `Open`

---

## 3. Bidding System

Freelancers can place bids on open jobs.

### Bid Information
- Bid Amount
- Proposed Completion Time

### Constraints
- Bid amount cannot exceed the client’s maximum budget
- Freelancers with reputation below `50` cannot place bids

---

## 4. Escrow Payment System

Clients hire freelancers by selecting a bid and depositing the exact payment amount into the smart contract.

### Features
- Funds remain locked inside the smart contract until job completion
- Incorrect Ether amount causes the transaction to revert
- Job status changes to `InProgress`

---

## 5. Work Submission & Completion

### Workflow
1. Freelancer submits completed work
2. Client approves the work
3. Smart contract releases payment automatically

### Smart Contract Actions
- Transfers payment to freelancer
- Deducts platform fee
- Updates freelancer reputation

### Reputation Reward
- `+10` reputation points after successful completion

### Final Status
- Job status changes to `Closed`

---

## 6. Dynamic Platform Fee

| Job Value | Platform Fee |
|----------|--------------|
| Less than 1 Ether | 2% |
| Greater than or equal to 1 Ether | 1% |

Platform fees remain inside the contract for the Arbiter/Admin.

---

## 7. Dispute Resolution System

Clients can dispute completed work instead of approving it.

### Arbiter Permissions
Only the Arbiter can resolve disputes.

### Resolution Options
- Refund Client
- Pay Freelancer

### Reputation Penalty
- `-20` reputation points if the client receives a refund

### Final Status
- Job status changes to `Resolved`

---

# Smart Contract Concepts Used

- Solidity Structs
- Enums
- Mappings
- Modifiers
- Payable Functions
- Ether Transfer
- Escrow Logic
- Access Control
- Revert Conditions
- Reputation Management

---

# Technologies Used

- Solidity
- Ethereum Blockchain
- Truffle Framework
- Ganache
- MetaMask
- React.js
- Web3.js

---

# Project Goal

The goal of this project is to demonstrate how decentralized applications and smart contracts can replace centralized freelance marketplaces by introducing:

- Transparency
- Automated Payments
- Trustless Escrow Mechanisms
- Secure Peer-to-Peer Transactions

---
# Installation & Setup

Follow these steps to run the project locally.

---

## 1. Clone the Repository

```bash
git clone <repository-link>
cd Freelance-Market-Escrow---Blockchain-Project
```

---

## 2. Install Dependencies

Install all required Node.js packages.

```bash
npm install
```

---

## 3. Start Ganache

Run Ganache locally to create a personal Ethereum blockchain for testing smart contracts.

### Using Ganache GUI
- Open Ganache
- Create a new workspace
- Start the local blockchain

### Default Local Blockchain
```bash
HTTP://127.0.0.1:7545
```

Make sure MetaMask is connected to the same network.

---

## 4. Configure MetaMask

- Import one of Ganache’s test accounts into MetaMask using its private key
- Add the Ganache local network manually if needed

### Network Configuration
| Field | Value |
|------|------|
| Network Name | Ganache Local |
| RPC URL | http://127.0.0.1:7545 |
| Chain ID | 1337 |
| Currency Symbol | ETH |

---

## 5. Compile Smart Contracts

Compile all Solidity smart contracts.

```bash
truffle compile
```

---

## 6. Deploy Smart Contracts

Deploy the contracts to the local Ganache blockchain.

```bash
truffle migrate
```

If contracts were already deployed previously, use:

```bash
truffle migrate --reset
```

---

## 7. Start the Frontend Application

Run the React frontend locally.

```bash
npm start
```

The application will start on:

```bash
http://localhost:3000
```

---

# Project Structure

```bash
/contracts      -> Solidity Smart Contracts
/migrations     -> Deployment Scripts
/src            -> Frontend Source Code
/test           -> Smart Contract Test Files
/build          -> Compiled Contract Artifacts
```
