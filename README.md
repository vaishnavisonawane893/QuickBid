# QuickBid – Real-Time Online Auction & Bidding Platform

QuickBid is a full-stack, enterprise-grade online auction and bidding marketplace that enables real-time bidding, seamless auction management for sellers, and administrative oversight. Built with **React**, **Node.js/Express**, **MongoDB**, and **Tailwind CSS**.

---

## ?? Key Features

### ?? User / Buyer Portal
- **Browse & Filter:** Explore active, upcoming, and featured auctions by category, price, and ending time.
- **Real-Time Bidding:** Place bids with instant updates, outbid alerts, and minimum bid validation.
- **My Bids & Orders:** Track active bids, winning history, and complete checkouts.
- **Wishlist & Notifications:** Save auctions for later and get notified on price updates.

### ?? Seller Portal
- **Become a Seller:** Onboard with identity verification and seller credentials.
- **Auction Management:** Create listings with image gallery (Cloudinary), starting price, reserve price, and custom duration.
- **Bidding History:** Monitor incoming bids and finalize auction winners upon expiry.

### ??? Admin Dashboard
- **Platform Analytics:** Total revenue, active auctions, customer conversion, and dispute metrics.
- **User Management:** Oversee buyers and sellers, approve pending accounts, and manage roles.
- **Auction Moderation:** Approve, reject, or flag pending auctions.
- **Dispute Center:** Resolve conflicts between buyers and sellers.

---

## ??? Tech Stack

- **Frontend (Client):**
  - React 18 / 19, Vite
  - Tailwind CSS, PostCSS, Autoprefixer
  - React Router v6 / v7
  - Lucide React & Heroicons
  - Axios (configured with auth interceptors)
  - Context API (`AuthContext`, `UserContext`)

- **Backend (Server):**
  - Node.js & Express.js
  - MongoDB & Mongoose ODM
  - JSON Web Tokens (JWT) & bcryptjs
  - Cloudinary & Multer for media uploads
  - Node-Cron for automated auction lifecycle management

---

## ?? Repository Structure

```
QuickBid/
+-- client/                     # Frontend React application
¦   +-- public/                 # Static assets
¦   +-- src/
¦   ¦   +-- api/                # Axios instance & API endpoints
¦   ¦   +-- components/         # Dashboard, layout, product, navigation, profile components
¦   ¦   +-- context/            # AuthContext & UserContext state providers
¦   ¦   +-- pages/              # Admin, seller, buyer, and authentication views
¦   ¦   +-- routes/             # Public, protected, seller, and admin routes
¦   ¦   +-- App.jsx             # Main router shell
¦   ¦   +-- main.jsx            # React root mount
¦   +-- .env.example            # Client environment template
¦   +-- tailwind.config.js      # Tailwind CSS styling tokens
¦   +-- vite.config.js          # Vite build tool configuration
¦
+-- server/                     # Backend Express REST API
¦   +-- config/                 # Cloudinary & database connection setup
¦   +-- controllers/            # Request handlers (Auth, Auctions, Bids, Users)
¦   +-- middleware/             # Auth JWT verification, admin check, file uploads
¦   +-- models/                 # Mongoose schemas (User, Bid, BidItem, Order, Slide)
¦   +-- routes/                 # Express API routes
¦   +-- cronJobs.js             # Automated auction expiration cron jobs
¦   +-- index.js                # Express app entry point
¦   +-- .env.example            # Server environment template
¦
+-- README.md                   # Platform documentation
```

---

## ?? Getting Started Locally

### Prerequisites
- **Node.js** (v18.x or higher)
- **npm** (v9+)
- **MongoDB** (Local instance or MongoDB Atlas URI)

---

### 1. Clone Repository
```bash
git clone https://github.com/vaishnavisonawane893/QuickBid.git
cd QuickBid
```

---

### 2. Backend Setup
```bash
cd server
npm install

# Configure environment variables
cp .env.example .env
```

Edit `server/.env` with your values:
```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/quickbid
JWT_SECRET=your_jwt_secret_key
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

Start the backend server:
```bash
npm start
# Server will run on http://localhost:5000
```

---

### 3. Frontend Setup
In a new terminal window:
```bash
cd client
npm install

# Configure environment variables
cp .env.example .env
```

Start the frontend development server:
```bash
npm run dev
# App will run on http://localhost:5173
```

---

## ????? Author

**Vaishnavi Sonawane**  
GitHub: [@vaishnavisonawane893](https://github.com/vaishnavisonawane893)

---

## ?? License

This project is licensed under the MIT License.
