# 🚀 Crowdfunding Platform

A blockchain-based crowdfunding platform that enables secure, transparent fundraising with smart contract integration and democratic withdrawal approval systems.

## 🌟 Features

### Core Functionality
- **Campaign Creation**: Users can create fundraising campaigns with goals, deadlines, and descriptions
- **Blockchain Integration**: Ethereum smart contracts for secure fund management
- **Multi-Role System**: Support for donors, fundraisers, and administrators
- **File Uploads**: Campaign images and document attachments
- **Real-time Updates**: WebSocket integration for live notifications

### Advanced Features
- **Democratic Withdrawal System**: Contributors vote on fund withdrawal requests
- **Partial Withdrawals**: Flexible fund release with approval mechanisms
- **Google OAuth Integration**: Social login authentication
- **Campaign Management**: Status tracking (pending, approved, active, completed, failed)
- **Comment System**: Engagement and discussion platform
- **Usage Tracking**: Fund usage plan monitoring
- **Notifications**: Real-time alerts for campaign activities

### Security Features
- **JWT Authentication**: Secure token-based authentication
- **Blockchain Security**: Smart contract protection against reentrancy attacks
- **Input Validation**: Comprehensive form validation
- **File Security**: Safe file upload handling

## 🛠 Technology Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **SQLite3** - Database
- **Web3.js** - Ethereum blockchain integration
- **Solidity** - Smart contracts
- **Passport.js** - Authentication middleware
- **Socket.io** - Real-time communication

### Frontend
- **React** - UI framework (client directory)
- **React Bootstrap** - UI components
- **Axios** - HTTP client

### Blockchain
- **Ethereum** - Blockchain platform
- **OpenZeppelin** - Secure smart contract library
- **Truffle/Hardhat** - Development framework

## 📋 Requirements

- Node.js 14+
- npm or yarn
- Ethereum wallet (MetaMask recommended)
- SQLite3

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Murageshadahalli/Crowdfunding_platform.git
   cd Crowdfunding_platform
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```
   Configure the following variables:
   - `DATABASE_URL`: SQLite database path
   - `JWT_SECRET`: JWT secret key
   - `GOOGLE_CLIENT_ID`: Google OAuth client ID
   - `GOOGLE_CLIENT_SECRET`: Google OAuth client secret
   - `SESSION_SECRET`: Session secret
   - `ETHEREUM_RPC_URL`: Ethereum RPC endpoint
   - `PRIVATE_KEY`: Ethereum private key (for development)

4. **Initialize database**
   ```bash
   npm run setup-db
   ```

5. **Deploy smart contracts**
   ```bash
   npm run migrate
   ```

## 🏃‍♂️ Running the Application

### Development Mode
```bash
# Run both backend and frontend
npm run dev

# Or run separately
npm run server  # Backend on port 5004
npm run client  # Frontend on port 3000
```

### Production Mode
```bash
npm start
```

## 📁 Project Structure

```
crowdfunding-platform/
├── server.js                 # Main server file
├── CrowdFunding.sol         # Smart contract
├── package.json             # Dependencies
├── .env                     # Environment variables
├── .gitignore              # Git ignore file
├── config/
│   └── passport.js         # Authentication configuration
├── middleware/
│   └── auth.js             # Authentication middleware
├── models/
│   └── Campaign.js         # Campaign data model
├── routes/
│   └── api/
│       ├── admin.js        # Admin routes
│       ├── auth.js         # Authentication routes
│       ├── campaign.js     # Campaign management
│       ├── campaigns.js    # Campaign CRUD operations
│       ├── comments.js     # Comment system
│       ├── donations.js    # Donation handling
│       ├── files.js        # File uploads
│       ├── fundUsagePlans.js # Fund usage tracking
│       ├── googleAuth.js   # Google OAuth
│       ├── notifications.js # Notification system
│       ├── usageRequests.js # Usage request management
│       ├── withdrawal.js   # Withdrawal operations
│       └── withdrawalRequests.js # Withdrawal requests
├── utils/
│   ├── addIndexes.js       # Database indexing
│   ├── addOAuthColumns.js  # OAuth setup
│   ├── blockchain.js       # Blockchain utilities
│   ├── blockchainSync.js   # Blockchain synchronization
│   ├── cache.js            # Caching utilities
│   ├── envCheck.js         # Environment validation
│   └── websocket.js        # WebSocket setup
├── uploads/                # File uploads directory
├── client/                 # Frontend application
└── crowdfunding.db         # SQLite database
```

## 🔧 Smart Contract Features

The CrowdFunding.sol smart contract includes:

- **Campaign Management**: Create and track crowdfunding campaigns
- **Contribution Tracking**: Record and manage donations
- **Withdrawal System**: Democratic approval for fund withdrawals
- **Partial Withdrawals**: Flexible fund release mechanisms
- **Refund Protection**: Automatic refunds for failed campaigns
- **Security Features**: Reentrancy protection and access controls

### Key Functions
- `createCampaign()`: Create new fundraising campaigns
- `contribute()`: Donate to campaigns
- `requestWithdrawal()`: Request fund withdrawal
- `voteOnWithdrawal()`: Approve/reject withdrawal requests
- `executeWithdrawal()`: Process approved withdrawals
- `getRefund()`: Claim refunds for failed campaigns

## 🔐 Security Considerations

- All fund transfers are handled by smart contracts
- Democratic approval prevents misuse of funds
- Input validation prevents injection attacks
- Secure authentication with JWT tokens
- File upload restrictions prevent malicious uploads

## 📊 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/google` - Google OAuth

### Campaigns
- `GET /api/campaigns` - List all campaigns
- `POST /api/campaigns` - Create new campaign
- `GET /api/campaigns/:id` - Get campaign details
- `PUT /api/campaigns/:id` - Update campaign
- `DELETE /api/campaigns/:id` - Delete campaign

### Donations
- `POST /api/donations` - Make donation
- `GET /api/donations/user/:userId` - Get user donations

### Withdrawals
- `POST /api/withdrawalRequests` - Request withdrawal
- `POST /api/withdrawalRequests/:id/vote` - Vote on withdrawal
- `POST /api/withdrawal/:id/execute` - Execute withdrawal

## 🐛 Troubleshooting

### Common Issues

1. **Database Connection Error**
   - Ensure SQLite3 is installed
   - Check database file permissions

2. **Blockchain Connection Issues**
   - Verify Ethereum RPC URL
   - Check network configuration
   - Ensure wallet is connected

3. **Authentication Problems**
   - Verify JWT secret is configured
   - Check environment variables

4. **File Upload Errors**
   - Ensure uploads directory exists
   - Check file size limits

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📞 Support

For support and questions:
- Create an issue on GitHub
- Contact the development team

## 🗺 Roadmap

- [ ] Mobile application development
- [ ] Advanced analytics dashboard
- [ ] Multi-currency support
- [ ] Escrow services
- [ ] Campaign templates
- [ ] Social sharing features
- [ ] Advanced notification system
- [ ] API rate limiting
- [ ] Multi-language support

## 🌐 Live Demo

[Deploy your application and add the live demo link here]

---

**Built with ❤️ for the crowdfunding community**
