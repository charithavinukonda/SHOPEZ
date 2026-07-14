# 🛒 ShopEZ — Full-Stack MERN E-Commerce Platform

A complete e-commerce platform built with **MongoDB, Express.js, React.js, and Node.js**.

---

## 🗂️ Project Structure

```
shopez/
├── backend/                  # Express.js API server
│   ├── models/               # Mongoose models (User, Product, Order, Review, Cart)
│   ├── routes/               # REST API routes
│   ├── middleware/           # Auth & error middleware
│   ├── utils/                # Helper utilities
│   ├── server.js             # App entry point
│   └── .env.example          # Environment variables template
│
├── frontend/                 # React.js SPA
│   ├── src/
│   │   ├── context/          # Auth & Cart context providers
│   │   ├── components/
│   │   │   ├── layout/       # Navbar, Footer
│   │   │   └── common/       # ProductCard, PrivateRoute, SellerRoute
│   │   └── pages/
│   │       ├── HomePage.js
│   │       ├── ProductsPage.js
│   │       ├── ProductDetailPage.js
│   │       ├── CartPage.js
│   │       ├── CheckoutPage.js
│   │       ├── OrdersPage.js
│   │       ├── LoginPage.js
│   │       ├── RegisterPage.js
│   │       ├── ProfilePage.js
│   │       └── seller/       # Seller dashboard, products, orders
│   └── public/
└── package.json              # Workspace scripts
```

---

## 🚀 Quick Start

### 1. Clone & Install
```bash
git clone https://github.com/yourname/shopez.git
cd shopez
npm run install:all
```

### 2. Configure Backend
```bash
cd backend
cp .env.example .env
# Edit .env with your MongoDB URI and JWT secret
```

### 3. Run Development Servers

**Terminal 1 — Backend:**
```bash
npm run dev:backend
# Runs on http://localhost:5000
```

**Terminal 2 — Frontend:**
```bash
npm run dev:frontend
# Runs on http://localhost:3000
```

---

## 🔑 API Endpoints

| Method | Endpoint | Auth | Description |
|--------|----------|------|-------------|
| POST | `/api/auth/register` | — | Register new user |
| POST | `/api/auth/login` | — | Login |
| GET | `/api/auth/me` | 🔒 | Get current user |
| GET | `/api/products` | — | List products (filter, sort, paginate) |
| GET | `/api/products/featured` | — | Featured products |
| GET | `/api/products/:id` | — | Product detail |
| POST | `/api/products` | 🔒 Seller | Create product |
| PUT | `/api/products/:id` | 🔒 Seller | Update product |
| DELETE | `/api/products/:id` | 🔒 Seller | Delete product |
| GET | `/api/cart` | 🔒 | Get cart |
| POST | `/api/cart` | 🔒 | Add to cart |
| DELETE | `/api/cart/:productId` | 🔒 | Remove from cart |
| POST | `/api/orders` | 🔒 | Place order |
| GET | `/api/orders/my` | 🔒 | My orders |
| GET | `/api/reviews/:productId` | — | Product reviews |
| POST | `/api/reviews/:productId` | 🔒 | Post review |
| GET | `/api/seller/dashboard` | 🔒 Seller | Analytics |
| GET | `/api/seller/orders` | 🔒 Seller | Manage orders |
| PUT | `/api/orders/:id/status` | 🔒 Seller | Update order status |
| POST | `/api/payment/create-intent` | 🔒 | Stripe payment intent |

---

## 🎨 UI Features

| Page | Features |
|------|----------|
| **Home** | Hero banner, category grid, featured products, CTA |
| **Products** | Search, category/price filters, sort, pagination |
| **Product Detail** | Image gallery, qty selector, star ratings, reviews |
| **Cart** | Qty controls, free shipping indicator, order summary |
| **Checkout** | Address form, COD/Stripe payment selection |
| **Orders** | Status badges, order history |
| **Seller Dashboard** | Revenue chart (Recharts), stats cards, low-stock alerts |
| **Seller Products** | Full product table, stock indicators |
| **Seller Orders** | Status filter, real-time status update |

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18, React Router v6, CSS Modules |
| State | Context API (Auth + Cart) |
| HTTP | Axios |
| Charts | Recharts |
| Icons | React Icons (Feather) |
| Backend | Node.js, Express.js |
| Database | MongoDB + Mongoose |
| Auth | JWT + bcryptjs |
| Payments | Stripe |
| Security | Helmet, express-rate-limit, CORS |

---

## 📋 Environment Variables

```env
PORT=5000
NODE_ENV=development
MONGO_URI=mongodb://localhost:27017/shopez
JWT_SECRET=your_super_secret_key
JWT_EXPIRE=7d
CLIENT_URL=http://localhost:3000
STRIPE_SECRET_KEY=sk_test_...
STRIPE_WEBHOOK_SECRET=whsec_...
```
