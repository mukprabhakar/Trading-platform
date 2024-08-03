# Crypto Trading Platform 

## Overview

Welcome to our comprehensive Crypto Trading Platform! This platform leverages advanced technologies and APIs to provide a seamless experience for users to manage their cryptocurrency portfolios, buy and sell crypto, and access real-time market data. Below are the key features and technologies used in the project.

## Features

### AI Chat Bot
- **Functionality:** Handles crypto-related queries like the value of cryptocurrencies and market data.
- **APIs Used:** Gemini API, CoinGecko API

### Buy & Sell Crypto
- **Functionality:** Facilitate smooth crypto transactions with a user-friendly interface.
- **Supported Cryptocurrencies:** Wide array of cryptocurrencies.

### Portfolio Management
- **Functionality:** Robust tools to monitor investments and track performance.

### Advanced Wallet Functionality
- **Wallet to Wallet Transfer:** Securely transfer funds between wallets.
- **Withdrawal to Bank Account:** Directly withdraw funds to bank accounts.
- **Add Balance to Wallet:** Easily top up wallet balances.

### Transaction History
- **Withdrawal History:** View and track past withdrawals.
- **Wallet History:** Access detailed logs of all wallet transactions.
- **Search Coin:** Effortlessly search for any cryptocurrency, providing essential information for informed trading decisions.

### Robust Authentication and Security
- **Login & Register:** Simple and secure user authentication.
- **Two-Factor Authentication:** Extra layer of security for user accounts.
- **Forgot Password:** Easy password recovery process.

## Technology Stack

### Backend
- **Spring Boot:** Framework for building robust backend services.
- **MySQL DB:** Relational database management.
- **Spring Security:** Provides comprehensive security services.
- **Java Mail Sender:** For email notifications and communication.

### Frontend
- **React:** Library for building user interfaces.
- **Tailwind CSS:** Utility-first CSS framework.
- **Redux:** State management for React applications.
- **Axios:** HTTP client for making requests.
- **React-Router-Dom:** Routing library for React applications.
- **Shadcn UI:** UI component library.

### Payment Gateways
- **Razorpay:** Payment gateway for processing transactions.
- **Stripe:** Another payment gateway option for transactions.

### APIs
- **Gemini API:** Provides real-time data for cryptocurrency.
- **CoinGecko API:** Another source for real-time cryptocurrency data.

## Database Schema

```
+---------------------+           +-----------------+
|       Users         |<--------->|    Wallets      |
|---------------------|           +-----------------+
| id                  |               ^            
| fullName            |               |
| email               |               |         
| ...                 |               |
+---------------------+               |
                                      |
+--------------------+            +-----------------+
|      Assets        |<---------->| WalletTransactions |
|--------------------|            +-----------------+
| id                 |
| quantity           |
| buy_price          |<---------->+-----------------+
| coin_id            |            |  Coins         |
| user_id            |            +-----------------+
+--------------------+            | id              |
                                  | symbol          |
+--------------------+            | ...             |
| Withdrawals        |<---------->+-----------------+
|--------------------|
| id                 |
| status             |
| amount             |
| user_id            |
| date               |
+--------------------+

+--------------------+
| Watchlists         |
|--------------------+
| id                 |
| user_id            |
+--------------------+
          |
          |
          v
+--------------------+
| Watchlist_Coins    |
|--------------------|
| watchlist_id       |
| coin_id            |
+--------------------+

+---------------------+           +---------------------+
|   VerificationCodes |<--------->|        Users        |
|---------------------|           +---------------------+
| id                  |
| otp                 |
| user_id             |
| email               |
| mobile              |
| verification_type   |
+---------------------+

+---------------------+           +---------------------+
|  TradingHistories   |<--------->|        Users        |
|---------------------|           +---------------------+
| id                  |
| selling_price       |
| buying_price        |
| coin_id             |
| user_id             |
+---------------------+

+---------------------+           +---------------------+
|    PaymentOrders    |<--------->|        Users        |
|---------------------|           +---------------------+
| id                  |
| amount              |
| status              |
| payment_method      |
| user_id             |
+---------------------+

+---------------------+           +---------------------+
|   PaymentDetails    |<--------->|        Users        |
|---------------------|           +---------------------+
| id                  |
| account_number      |
| account_holder_name |
| ifsc                |
| bank_name           |
| user_id             |
+---------------------+

+---------------------+           +---------------------+
|        Orders       |<--------->|        Users        |
|---------------------|           +---------------------+
| id                  |
| user_id             |
| order_type          |
| price               |
| timestamp           |
| status              |
| order_item_id       |
+---------------------+
          |
          |
          v
+---------------------+           +---------------------+
|      OrderItems     |<--------->|        Coins        |
|---------------------|           +---------------------+
| id                  |
| quantity            |
| coin_id             |
| buy_price           |
| sell_price          |
| order_id            |
+---------------------+

+---------------------+             +---------------------+
|    Notifications    | <---------> |        Users        |
|---------------------|             +---------------------+
| id                  |
| from_user_id        |
| to_user_id          |
| amount              |
| message             |
+---------------------+

+---------------------+           
|   MarketChartData   |
|---------------------|
| id                  |
| timestamp           |
| price               |
+---------------------+

+---------------------+           +---------------------+
| ForgotPasswordTokens|<--------->|        Users        |
|---------------------|           +---------------------+
| id                  |
| user_id             |
| otp                 |
| verification_type   |
| send_to             |
+---------------------+
```

## Getting Started

### Prerequisites
- **Java Development Kit (JDK)**
- **Node.js and npm**
- **MySQL Server**

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/crypto-trading-platform.git
   ```

2. **Backend Setup:**
   - Navigate to the backend directory:
     ```bash
     cd backend
     ```
   - Configure MySQL database in `application.properties`:
     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/crypto_db
     spring.datasource.username=root
     spring.datasource.password=yourpassword
     ```
   - Build and run the backend:
     ```bash
     ./mvnw spring-boot:run
     ```

3. **Frontend Setup:**
   - Navigate to the frontend directory:
     ```bash
     cd frontend
     ```
   - Install dependencies:
     ```bash
     npm install
     ```
   - Start the frontend:
     ```bash
     npm start
     ```

### Usage

- **Access the platform:** Open your browser and navigate to `http://localhost:3000`.
- **Register/Login:** Create a new account or log in with existing credentials.
- **Explore Features:** Use the AI Chat Bot, buy and sell cryptocurrencies, manage your portfolio, and utilize advanced wallet functionalities.

## Contributing

We welcome contributions to enhance the platform. Please follow these steps to contribute:

1. **Fork the repository.**
2. **Create a new branch:**
   ```bash
   git checkout -b feature/your-feature
   ```
3. **Make your changes and commit them:**
   ```bash
   git commit -m "Add your message"
   ```
4. **Push to the branch:**
   ```bash
   git push origin feature/your-feature
   ```
5. **Create a pull request.**

## License

This project is licensed under the MIT License.

## Contact

For any queries or support, please contact:

- **Email:** mukesh.mmp1234@gmail.com
