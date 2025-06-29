# BBT Protocol - Bhutan Bitcoin Token on Avalanche

A premium, futuristic dashboard for the Bhutan Bitcoin Token (BBT) protocol built on Avalanche. This project features a complete smart contract system with minting, burning, and pegging mechanisms, along with a beautiful React frontend.

## 🚀 Features

### Smart Contracts
- **BBT Token**: Main token contract with mint/burn functionality
- **BBT Faucet**: Testnet faucet for distributing BBT tokens
- **Collateralization**: 1:1 WAVAX backing with configurable ratios
- **Fee System**: Configurable mint/burn fees (default 0.1%)
- **Emergency Controls**: Pause/unpause and emergency withdrawal functions

### Frontend Dashboard
- **Premium UI**: Glassmorphic cards with Bhutan-themed colors
- **Real-time Data**: Live system metrics and user balances
- **Wallet Integration**: MetaMask connection for Avalanche Fuji testnet
- **Transaction Forms**: Mint and burn BBT tokens
- **System Health**: Real-time collateralization monitoring
- **Responsive Design**: Works on desktop and mobile

## 🛠️ Tech Stack

### Smart Contracts
- **Solidity**: ^0.8.19
- **Hardhat**: Development and deployment framework
- **OpenZeppelin**: Security and standard contracts
- **Avalanche Fuji**: Testnet deployment

### Frontend
- **React**: ^18.3.1 with TypeScript
- **Vite**: Build tool and dev server
- **Tailwind CSS**: Styling with custom Bhutan theme
- **Framer Motion**: Smooth animations
- **Ethers.js**: Web3 integration
- **Lucide React**: Icons

## 📋 Prerequisites

- Node.js 18+ and npm
- MetaMask wallet extension
- Avalanche Fuji testnet AVAX (for gas fees)

## 🚀 Quick Start

### 1. Clone and Install

```bash
git clone <repository-url>
cd E-bhutan
npm install
```

### 2. Environment Setup

Create a `.env` file in the root directory:

```env
# Avalanche Fuji Testnet Configuration
DEPLOYER_PRIVATE_KEY=your_private_key_here
DEPLOYER_ADDRESS=your_wallet_address_here
SNOWTRACE_API_KEY=your_snowtrace_api_key_here
FUJI_RPC_URL=https://api.avax-test.network/ext/bc/C/rpc

# Frontend Configuration
VITE_BBT_TOKEN_ADDRESS=deployed_token_address
VITE_BBT_FAUCET_ADDRESS=deployed_faucet_address
VITE_RESERVE_TOKEN_ADDRESS=0xd00ae08403B9bbb9124bB305C09058E32C39A48c
```

### 3. Deploy Smart Contracts

```bash
# Compile contracts
npm run compile

# Deploy to Fuji testnet
npm run deploy:fuji

# Deploy to local network (for testing)
npm run deploy:local
```

### 4. Update Frontend Configuration

After deployment, update the contract addresses in your `.env` file with the deployed addresses from the deployment output.

### 5. Start Frontend

```bash
npm run dev
```

The dashboard will be available at `http://localhost:5174`

## 🔧 Smart Contract Deployment

### Manual Deployment Steps

1. **Get Fuji Testnet AVAX**:
   - Visit [Avalanche Faucet](https://faucet.avax.network/)
   - Request testnet AVAX

2. **Configure MetaMask**:
   - Add Avalanche Fuji Testnet:
     - Network Name: `Avalanche Fuji Testnet`
     - RPC URL: `https://api.avax-test.network/ext/bc/C/rpc`
     - Chain ID: `43113`
     - Currency Symbol: `AVAX`
     - Block Explorer: `https://testnet.snowtrace.io/`

3. **Deploy Contracts**:
   ```bash
   npm run deploy:fuji
   ```

4. **Verify Contracts** (Optional):
   - Visit [Snowtrace](https://testnet.snowtrace.io/)
   - Verify your deployed contracts

### Contract Addresses

After deployment, you'll get addresses like:
- **BBT Token**: `0x...`
- **BBT Faucet**: `0x...`
- **Reserve Token**: `0xd00ae08403B9bbb9124bB305C09058E32C39A48c` (WAVAX)

## 🎨 Frontend Features

### Design System
- **Bhutan Colors**: Deep navy, gold, saffron, and copper
- **Glassmorphism**: Translucent cards with backdrop blur
- **Animations**: Smooth transitions and hover effects
- **Typography**: Premium fonts with proper hierarchy

### Components
- **Header**: Wallet connection and navigation
- **Metric Cards**: System statistics with animations
- **Balance Card**: Portfolio overview with privacy toggle
- **Transaction Forms**: Mint and burn BBT tokens
- **System Health**: Real-time protocol status

### Wallet Integration
- **MetaMask**: Primary wallet connection
- **Network Detection**: Automatic Fuji testnet switching
- **Transaction Handling**: Mint, burn, and faucet requests
- **Error Handling**: User-friendly error messages

## 🔒 Security Features

### Smart Contracts
- **Reentrancy Protection**: Using OpenZeppelin's ReentrancyGuard
- **Access Control**: Owner and oracle-only functions
- **Emergency Controls**: Pause mechanism for critical situations
- **Fee Limits**: Maximum 10% fees to prevent abuse
- **Collateral Ratios**: Configurable minimum/maximum ratios

### Frontend
- **Input Validation**: Amount and address validation
- **Transaction Confirmation**: User confirmation for all transactions
- **Error Boundaries**: Graceful error handling
- **Mock Data**: Fallback data when contracts aren't deployed

## 📊 Protocol Mechanics

### Minting BBT
1. User approves WAVAX spending
2. User calls `mintBBT(amount)`
3. Contract transfers WAVAX from user
4. Contract mints BBT tokens to user
5. Fee is deducted from minted amount

### Burning BBT
1. User approves BBT spending
2. User calls `burnBBT(amount)`
3. Contract burns BBT tokens from user
4. Contract transfers WAVAX to user
5. Fee is deducted from returned amount

### Collateralization
- **Target Ratio**: 200% (2:1 WAVAX to BBT)
- **Minimum Ratio**: 150% (1.5:1)
- **Maximum Ratio**: 300% (3:1)
- **Automatic Adjustments**: Oracle can adjust ratios

## 🧪 Testing

### Smart Contract Tests
```bash
npm run test
```

### Frontend Testing
```bash
# Run linting
npm run lint

# Build for production
npm run build
```

## 📱 Usage Guide

### Connecting Wallet
1. Click "Connect MetaMask" in the header
2. Approve the connection in MetaMask
3. Switch to Avalanche Fuji Testnet if prompted
4. Your account address will appear in the header

### Getting Test Tokens
1. Use the faucet to get WAVAX from Avalanche
2. Use the BBT faucet to get test BBT tokens
3. Or mint BBT by depositing WAVAX

### Minting BBT
1. Ensure you have WAVAX in your wallet
2. Enter the amount of WAVAX to deposit
3. Click "Mint BBT"
4. Approve the transaction in MetaMask
5. Wait for confirmation

### Burning BBT
1. Ensure you have BBT tokens in your wallet
2. Enter the amount of BBT to burn
3. Click "Burn BBT"
4. Approve the transaction in MetaMask
5. Receive WAVAX in return

## 🔧 Configuration

### Smart Contract Parameters
- **Mint Fee**: 0.1% (10 basis points)
- **Burn Fee**: 0.1% (10 basis points)
- **Decimals**: 8 (like Bitcoin)
- **Max Supply**: 1 billion BBT

### Frontend Configuration
- **Refresh Interval**: 30 seconds
- **Animation Duration**: 0.8 seconds
- **Network**: Avalanche Fuji Testnet (43113)

## 🚨 Troubleshooting

### Common Issues

1. **MetaMask Not Detected**:
   - Install MetaMask browser extension
   - Refresh the page

2. **Wrong Network**:
   - Switch to Avalanche Fuji Testnet
   - Add the network manually if needed

3. **Insufficient Funds**:
   - Get testnet AVAX from the faucet
   - Ensure you have enough for gas fees

4. **Contract Not Deployed**:
   - Deploy contracts first
   - Update contract addresses in `.env`

5. **Transaction Fails**:
   - Check collateralization ratios
   - Ensure sufficient token approval
   - Verify network connection

### Support
- Check the browser console for detailed error messages
- Verify contract addresses are correct
- Ensure you're on the correct network

## 📈 Future Enhancements

### Planned Features
- **Cross-chain Bridge**: Bridge to other networks
- **Governance**: DAO voting system
- **Staking**: Earn rewards by staking BBT
- **Analytics**: Advanced charts and metrics
- **Mobile App**: Native mobile application

### Technical Improvements
- **Oracle Integration**: Real-time price feeds
- **Multi-sig Treasury**: Enhanced security
- **Automated Market Maker**: Liquidity pools
- **Flash Loans**: Advanced DeFi features

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📞 Contact

For questions or support:
- GitHub Issues: [Create an issue](https://github.com/your-repo/issues)
- Email: your-email@example.com

---

**Built with ❤️ for Bhutan's digital economy on Avalanche** 