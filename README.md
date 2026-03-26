# 🚀 BlueCarbon

BlueCarbon is a decentralized Web3 application (dApp) designed to register, verify, and trade carbon credits for marine and coastal ecosystem restoration projects (such as mangroves and seagrass). Powered by Ethereum smart contracts, it provides a transparent and immutable registry where environmental organizations can list projects, administrators can verify data to mint carbon credits, and buyers can seamlessly purchase credits through an integrated decentralized marketplace.

## 📖 Description
The voluntary carbon market often suffers from a lack of transparency and double-spending of credits. BlueCarbon solves this by leveraging blockchain technology to track the lifecycle of a carbon credit—from project registration to the final sale. It offers a secure, verifiable, and user-friendly platform that bridges the gap between environmental initiatives and green-conscious investors.

Key Features:

Immutable Registry: Register new environmental projects with initial IPFS data hashes to ensure tamper-proof records.

Role-Based Minting: Secure admin controls to approve vetted projects and mint corresponding ERC-like carbon credits to the project owner's wallet.

Decentralized Marketplace: Project owners can list their earned credits for sale, setting their own prices in Ethereum (ETH).

Secure Transactions: Atomic smart contract functions ensure that funds and credits are swapped safely without intermediaries.

Web3 Integration: Seamless MetaMask wallet connection for authenticated interactions and transparent ledger tracking.

## 🧭 Table of Contents
🛠️ Tech Stack

⚙️ Installation

▶️ Usage

💡 Usage Examples

📂 Project Structure

📜 Smart Contract Documentation

🧪 Testing

🚧 Features

🔮 Future Improvements

🤝 Contributing

👤 Author / Credits

## 🛠️ Tech Stack
Frontend (Client):

React 19 (via Vite)

Ethers.js (v6) - Blockchain interaction & wallet integration

Tailwind CSS - Utility-first styling framework

React Router DOM - Client-side routing

Backend (Smart Contracts):

Solidity (^0.8.9) - Smart contract development

Hardhat - Ethereum development environment

Chai & Ethers - Contract testing framework

## ⚙️ Installation
Prerequisites
Node.js installed

MetaMask browser extension installed

1. Clone the repository

```bash
git clone https://github.com/nishaaddhabale/bluecarbon.git
cd bluecarbon
```

2. Backend (Smart Contract) Setup
Compile and deploy the smart contracts to a local blockchain network.

```bash
cd backend
npm install

# Start a local Hardhat node
npx hardhat node
```

Keep this terminal open. In a new terminal, deploy the contract:

```bash
cd backend
npx hardhat ignition deploy ./ignition/modules/Lock.js --network localhost
```

Note the deployed contract address and update contractAddress in frontend/client/src/App.jsx and Marketplace.jsx.

3. Frontend Setup

```bash
cd ../frontend/client
npm install
```

## ▶️ Usage
Run the Development Server
Navigate to the frontend directory and start the Vite server:

```bash
cd frontend/client
npm run dev
```

The application will open on http://localhost:5173.

Connecting Your Wallet
Open the application in your browser.

Click "Connect Wallet" in the navigation bar.

Authorize the connection via the MetaMask pop-up (ensure you are connected to your local Hardhat network/testnet).

## 💡 Usage Examples

Registering a Project
Navigate to "Register Project".

Enter the Project Name (e.g., Sundarbans Delta Restoration).

Enter the Location (e.g., West Bengal, India).

Provide the IPFS hash linking to your project's environmental data.

Click "Register Project" and sign the transaction in MetaMask.

Buying Credits on the Marketplace
Navigate to the "Marketplace" tab.

Browse active listings of available carbon credits.

Click "View & Buy" on a listing.

Enter the amount of credits you wish to purchase and confirm the transaction. The smart contract will automatically transfer the ETH to the seller and the credits to your wallet.

## 📂 Project Structure

```plaintext
├── backend/
│   ├── contracts/
│   │   └── BlueCarbonRegistry.sol # Core logic for projects, minting, and marketplace
│   ├── ignition/modules/          # Deployment scripts
│   ├── test/                      # Smart contract test files
│   ├── hardhat.config.js          # Hardhat configuration
│   └── package.json
├── frontend/
│   └── client/
│       ├── src/
│       │   ├── components/        # Reusable UI components
│       │   ├── App.jsx            # Routing, wallet connection, and registry logic
│       │   ├── Marketplace.jsx    # Marketplace view and buying logic
│       │   ├── NCCRAdmin.jsx      # Admin panel for approving projects
│       │   ├── ProjectDetails.jsx # Detailed view of a listed project
│       │   ├── index.css          # Global Tailwind styles
│       │   └── main.jsx           # React DOM entry
│       ├── tailwind.config.js
│       ├── vite.config.js
│       └── package.json
└── README.md
```

## 📜 Smart Contract Documentation
(Acting as the API for this Web3 Application)

Core Methods (BlueCarbonRegistry.sol)

registerProject(string _name, string _location, string _dataHash)

Registers a new project under the caller's address. Starts with an unapproved status.

approveAndMint(uint _projectId, uint _creditAmount)

Admin Only. Approves a pending project and mints the specified amount of carbon credits to the project owner.

listCreditsForSale(uint _projectId, uint _amount, uint _pricePerCredit)

Allows a project owner to list their available credits on the marketplace.

buyCredits(uint _listingId, uint _amount)

Payable. Allows any user to purchase credits from an active listing by sending the required ETH amount.

getAllProjects() & getActiveListings()

View functions utilized by the frontend to populate the dashboard and marketplace.

## 🧪 Testing
To run the smart contract test suite using Hardhat and Chai:

```bash
cd backend
npx hardhat test
```

To check test coverage:

```bash
npx hardhat coverage
```

## 🚧 Features

[x] Web3 Wallet connection via MetaMask & Ethers.js.

[x] Project registration and metadata mapping.

[x] Admin-gated functions for verification and minting.

[x] P2P decentralized carbon credit marketplace.

[x] Smart contract event listeners for real-time frontend updates.

[x] Responsive, modern UI built with Tailwind CSS.

## 🔮 Future Improvements

Dynamic IPFS Integration: Upload project reports and ecological data directly to IPFS from the frontend.

ERC-20 / ERC-1155 Standardization: Upgrade internal credit tracking to standard ERC tokens for interoperability with other platforms.

DAO Governance: Transition the admin role from a single wallet to a Decentralized Autonomous Organization (DAO) for community-driven project approvals.

Interactive Maps: Add a geographic map view of all registered restoration projects.

## 🤝 Contributing

Contributions make the open-source community an amazing place to learn, inspire, and create.

Fork the Project.

Create your Feature Branch (git checkout -b feature/AmazingFeature).

Commit your Changes (git commit -m 'Add some AmazingFeature').

Push to the Branch (git push origin feature/AmazingFeature).

Open a Pull Request.

## 👤 Author / Credits

Nishaad Dhabale

GitHub: @nishaaddhabale

Other Projects: [FreeFlow, Mindstash, SwiftPay, Grampanchayat]
