# 📦 Subscription Tracker API

A REST API to manage subscriptions, send renewal reminders, and protect endpoints with bot detection and rate limiting.

---

## 🌟 Overview

This API helps users:

-   Manage subscription lifecycles (create, update, cancel)
-   Receive **automated renewal reminders** via email
-   Stay protected with bot detection and rate limiting

Built with ❤️ using **Node.js**, **Express**, and **MongoDB**.

---

## 🚀 Features

-   🔐 JWT-based authentication
-   📧 Email reminders (7, 5, 2, 1 day before renewal)
-   🛡️ Arcjet bot detection and rate limiting
-   🌱 Clean, modular code structure

---

## ⚙️ Tech Stack

-   Node.js & Express.js
-   MongoDB (Mongoose)
-   JSON Web Tokens (JWT)
-   Nodemailer (Gmail SMTP)
-   Arcjet for protection
-   Upstash Workflows for scheduling

---

## ⚡ Getting Started

### 1️⃣ Prerequisites

-   Node.js v18+
-   MongoDB URI
-   Gmail App Password

### 2️⃣ Setup

Clone the repo:

```bash
git clone https://github.com/DaniilBaida/subscription-tracker.git
cd subscription-tracker
npm install
```

Create `.env.development.local` (see example below):

```env
PORT=5500
SERVER_URL=http://localhost:5500
NODE_ENV=development
DB_URI=<your_mongodb_uri>
JWT_SECRET=<your_jwt_secret>
JWT_EXPIRES_IN=1d
ARCJET_KEY=<your_arcjet_key>
QSTASH_URL=http://127.0.0.1:8080
QSTASH_TOKEN=<your_upstash_token>
EMAIL_PASSWORD=<your_gmail_app_password>
```

Run the server:

```bash
npm run dev
```

API is live at `http://localhost:5500`

---

## 📬 Example API Requests

### Register

```http
POST /api/v1/auth/sign-up
{
  "name": "Jane Doe",
  "email": "jane@example.com",
  "password": "123456"
}
```

### Login

```http
POST /api/v1/auth/sign-in
{
  "email": "jane@example.com",
  "password": "123456"
}
```

### Create Subscription

```http
POST /api/v1/subscriptions
Authorization: Bearer <JWT_TOKEN>
Content-Type: application/json

{
  "name": "Pro Plan",
  "price": 19.99,
  "currency": "USD",
  "frequency": "monthly",
  "category": "entertainment",
  "paymentMethod": "Credit Card",
  "startDate": "2025-07-17T00:00:00.000Z",
  "renewalDate": "2025-07-20T00:00:00.000Z"
}
```

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first.

---

## 📜 License

MIT © [Your Name](https://github.com/DaniilBaida)
