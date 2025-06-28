# Expense Management System (MERN Stack)

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Installation & Setup](#installation--setup)
  - [1. Clone the Repository](#1-clone-the-repository)
  - [2. Server Setup](#2-server-setup)
  - [3. Client Setup](#3-client-setup)
- [Environment Variables](#environment-variables)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Folder Structure](#folder-structure)
- [Usage](#usage)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

This Expense Management System is a full-stack web application built with the MERN stack (MongoDB, Express, React, Node.js). It allows users to sign up, log in, and track their incomes and expenses. Data visualizations—pie charts and bar charts—provide an intuitive overview of spending and earning patterns. Authentication is handled securely using JSON Web Tokens (JWT).

## Features

- User registration and login with JWT authentication
- Add, edit, and delete income or expense transactions
- View transaction list in tabular form
- Dynamic pie chart to visualize category-wise distribution
- Dynamic bar chart to visualize month-wise totals
- Protected routes: only authenticated users can manage data

## Tech Stack

- **Frontend:** React, React Router, Chart.js (or Recharts)
- **Backend:** Node.js, Express.js
- **Database:** MongoDB (Mongoose ODM)
- **Authentication:** JSON Web Tokens (JWT)
- **Styling:** CSS / Bootstrap / Tailwind (choose your preference)

## Prerequisites

- Node.js (v14+)
- npm or yarn
- MongoDB database (local or cloud - e.g. MongoDB Atlas)

## Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/expense-management-app.git
cd expense-management-app
```

### 2. Server Setup

```bash
cd server
npm install
```

Create a `.env` file in the `server` folder (see [Environment Variables](#environment-variables)).

### 3. Client Setup

```bash
cd ../client
npm install
```

## Environment Variables

In the `server` directory, create a `.env` file containing:

```env
PORT=5000
MONGO_URI=<your-mongodb-connection-string>
JWT_SECRET=<your-jwt-secret>
JWT_EXPIRES_IN=1d
```

Replace `<your-mongodb-connection-string>` with your MongoDB URI and `<your-jwt-secret>` with a secure random string.

## Running the Application

### Start the Server

```bash
cd server
npm run dev
```

The server will run on `http://localhost:5000` by default.

### Start the Client

```bash
cd client
npm start
```

The frontend will run on `http://localhost:3000` and proxy API requests to the server.

## API Endpoints

*All endpoints prefixed with* `/api/v1`

### Auth

| Method | Endpoint         | Description                |
| ------ | ---------------- | -------------------------- |
| POST   | `/auth/register` | Register a new user        |
| POST   | `/auth/login`    | Authenticate and get a JWT |

### Transactions

| Method | Endpoint            | Description                       |
| ------ | ------------------- | --------------------------------- |
| GET    | `/transactions`     | Get all transactions for the user |
| POST   | `/transactions`     | Add a new transaction             |
| PUT    | `/transactions/:id` | Update a transaction by ID        |
| DELETE | `/transactions/:id` | Delete a transaction by ID        |

All transaction routes require a valid `Authorization: Bearer <token>` header.

## Folder Structure

```
expense-management-app/
├── client/               # React frontend
│   ├── public/
│   └── src/
│       ├── components/   # Reusable components (Navbar, Chart, TransactionForm)
│       ├── pages/        # Pages (Login, Dashboard)
│       ├── services/     # API service functions
│       └── App.js
├── server/               # Express backend
│   ├── config/
│   │   └── connectDb.js  # MongoDB connection
│   ├── controllers/      # Request handlers (transactionCtrl.js, userController.js)
│   ├── models/           # Mongoose models (userModel.js, transactionModel.js)
│   ├── routes/           # Express routes (userRoute.js, transactionRoutes.js)
│   ├── middleware/       # Auth middleware (auth.js)
│   ├── server.js         # Entry point
│   └── .env              # Environment variables
├── .gitignore
├── package.json (root)
└── README.md
```

## Usage

1. **Register** a new account or **Log in**.
2. **Add** income or expense transactions by specifying title, amount, type (income/expense), and date.
3. View all transactions in a table and summary charts below.
4. **Edit** or **Delete** transactions as needed.

## Screenshots

&#x20;

## Contributing

Contributions are welcome! Please fork the repository and open a pull request with your changes.

## License

Distributed under the MIT License. See `LICENSE` for more information.

