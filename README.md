# USDT Exchange - OTC Trading Platform

A legitimate OTC USDT trading platform that allows users to sell USDT for INR at premium rates. Built with Node.js, Express, and SQLite.

## Features

- **User Authentication**: Secure registration and login system with JWT tokens
- **Dashboard**: Real-time balance tracking and transaction history
- **USDT Deposits**: TRC-20 USDT deposit tracking with on-chain verification
- **Sell Orders**: Convert USDT to INR at locked rates
- **Security Features**: PIN-protected withdrawals and secure transactions
- **Modern UI**: Beautiful, responsive interface with gradient design

## Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: SQLite3
- **Authentication**: JWT + Express Sessions
- **Frontend**: HTML, CSS, JavaScript (Vanilla)
- **Security**: bcryptjs for password hashing

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd usdtdrainer-main
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
```bash
cp .env.example .env
```

Edit `.env` with your configuration:
```
PORT=3000
JWT_SECRET=your_jwt_secret_here
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_email_password
```

4. Start the server:
```bash
npm start
```

For development with auto-reload:
```bash
npm run dev
```

## Project Structure

```
usdtdrainer-main/
├── public/                 # Frontend files
│   ├── index.html         # Landing page
│   ├── register.html      # Registration page
│   ├── login.html         # Login page
│   ├── dashboard.html     # User dashboard
│   ├── styles.css         # Global styles
│   └── script.js          # Frontend scripts
├── routes/                # API routes
│   ├── auth.js           # Authentication endpoints
│   ├── users.js          # User management
│   ├── deposits.js       # Deposit handling
│   └── orders.js         # Order management
├── models/                # Database models
│   ├── database.js       # Database initialization
│   ├── User.js           # User model
│   ├── Deposit.js        # Deposit model
│   └── Order.js          # Order model
├── middleware/            # Custom middleware
│   └── auth.js           # Authentication middleware
├── server.js             # Main server file
├── package.json          # Dependencies
└── .env.example          # Environment variables template
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user

### Users
- `GET /api/users/profile` - Get user profile
- `POST /api/users/set-pin` - Set transaction PIN

### Deposits
- `GET /api/deposits/address` - Get deposit address
- `POST /api/deposits/submit` - Submit deposit
- `GET /api/deposits/history` - Get deposit history

### Orders
- `GET /api/orders/rate` - Get current exchange rate
- `POST /api/orders/create` - Create sell order
- `GET /api/orders/history` - Get order history

## Security Features

1. **Password Hashing**: All passwords are hashed using bcryptjs
2. **JWT Authentication**: Secure token-based authentication
3. **PIN Protection**: 6-digit PIN for secure withdrawals
4. **Session Management**: Secure session handling
5. **Input Validation**: Server-side validation for all inputs

## Usage

1. **Register**: Create an account at `/register`
2. **Login**: Sign in at `/login`
3. **Deposit USDT**: Get your TRC-20 address and deposit USDT
4. **Sell USDT**: Convert your USDT to INR at current rates
5. **Withdraw**: Receive INR directly to your bank account

## Configuration

### TRC-20 Address
Update the deposit address in `routes/deposits.js`:
```javascript
const depositAddress = 'TYourTronAddressHere';
```

### Exchange Rate
The current rate is set in `routes/orders.js`. For production, integrate with a real-time rate API.

## Development Notes

- This is a demonstration platform for educational purposes
- For production use, implement proper KYC/AML compliance
- Add email verification for user registration
- Implement proper blockchain monitoring for deposits
- Add proper error handling and logging
- Consider using PostgreSQL or MongoDB for production
- Implement proper rate limiting and DDoS protection

## License

This project is for educational purposes only.

## Disclaimer

This software is provided as-is for educational purposes. Ensure compliance with local regulations before deploying for commercial use.
