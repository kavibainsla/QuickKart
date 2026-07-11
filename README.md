# QuickKart 🛒

A full-stack e-commerce web application inspired by quick-commerce platforms like Blinkit & Zepto. Built with **React**, **Node.js**, **Express**, and **MongoDB**.

---

## 🏗️ Project Structure

```
QuickKart/
├── client/        # Customer-facing React frontend (Vite + Tailwind CSS v4)
├── admin/         # Admin panel React frontend (Vite + Tailwind CSS v4)
└── server/        # Express.js backend (Node.js + MongoDB)
```

---

## ✨ Features

### Customer App (`/client`)
- 🔐 Email/Password & Google OAuth authentication
- 🛍️ Browse products by category
- 🛒 Cart management with real-time updates
- 💳 Checkout with multiple payment options (card, wallet, COD)
- 📦 Order tracking with status simulation
- 🔄 Subscription management (weekly/monthly deliveries)
- 💰 Wallet with transaction history
- 🏠 Multiple delivery address management
- 🎫 Support ticket system
- 📝 Blog & About pages

### Admin Panel (`/admin`)
- 📊 Dashboard with key metrics
- 📦 Product & Category CRUD management
- 👥 User management
- 🚚 Order management & status updates
- 🎫 Customer support ticket handling

### Backend (`/server`)
- RESTful API with Express.js
- Session-based authentication
- Google OAuth 2.0 integration
- Automated cron jobs (subscription processing, order simulation)
- MongoDB with Mongoose ODM

---

## 🚀 Getting Started

### Prerequisites
- Node.js v18+
- MongoDB (local or MongoDB Atlas)
- Google OAuth credentials (optional, for Google Sign-In)

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/QuickKart.git
cd QuickKart
```

### 2. Set Up the Backend
```bash
cd server
npm install
cp .env.example .env
# Edit .env with your MongoDB URI, session secret, and Google OAuth credentials
```

### 3. Set Up the Client
```bash
cd ../client
npm install
cp .env.example .env
# Edit .env with your backend URL and Google Client ID
```

### 4. Set Up the Admin Panel
```bash
cd ../admin
npm install
cp .env.example .env
# Edit .env with your backend URL and client URL
```

### 5. Seed the Database (Optional)
```bash
cd server
node seed.js
```

### 6. Run the Application

**Terminal 1 — Backend:**
```bash
cd server
npm run dev     # http://localhost:5000
```

**Terminal 2 — Client:**
```bash
cd client
npm run dev     # http://localhost:5173
```

**Terminal 3 — Admin:**
```bash
cd admin
npm run dev     # http://localhost:5174
```

---

## ⚙️ Environment Variables

### Server (`server/.env`)
| Variable | Description |
|---|---|
| `PORT` | Server port (default: 5000) |
| `NODE_ENV` | Environment (development/production) |
| `MONGODB_URI` | MongoDB connection string |
| `SESSION_SECRET` | Secret key for session encryption |
| `CLIENT_URL` | Frontend URL for CORS |
| `ADMIN_URL` | Admin URL for CORS |
| `GOOGLE_CLIENT_ID` | Google OAuth 2.0 Client ID |
| `GOOGLE_CLIENT_SECRET` | Google OAuth 2.0 Client Secret |

### Client (`client/.env`)
| Variable | Description |
|---|---|
| `VITE_API_URL` | Backend API URL |
| `VITE_GOOGLE_CLIENT_ID` | Google OAuth Client ID (must match server) |

### Admin (`admin/.env`)
| Variable | Description |
|---|---|
| `VITE_API_URL` | Backend API URL |
| `VITE_CLIENT_URL` | Client store URL for navigation links |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React 19, Vite, Tailwind CSS v4, Redux Toolkit, Framer Motion |
| **Backend** | Node.js, Express.js v5 |
| **Database** | MongoDB, Mongoose |
| **Auth** | Express Session, bcryptjs, Google OAuth 2.0 |
| **Cron Jobs** | node-cron |
| **Deployment** | Vercel (frontend), Render (backend) |

---

## 📁 API Routes

| Route | Description |
|---|---|
| `POST /api/auth/register` | Register a new user |
| `POST /api/auth/login` | Login with email/password |
| `POST /api/auth/google` | Login with Google |
| `POST /api/auth/logout` | Logout user |
| `GET /api/auth/me` | Get current user |
| `GET /api/products` | Get all products |
| `GET /api/categories` | Get all categories |
| `GET /api/cart` | Get user cart |
| `POST /api/orders` | Place an order |
| `GET /api/orders` | Get user orders |
| `GET /api/subscriptions` | Get user subscriptions |
| `GET /api/wallet` | Get wallet balance & transactions |
| `GET /api/admin/...` | Admin-only routes |

---

## 🔑 Creating an Admin Account

```bash
cd server
node scripts/create_specific_admin.js
```

Or promote an existing user:
```bash
node scripts/make_admin.js
```

---

## 📜 License

MIT License — feel free to use this project for learning and personal use.
