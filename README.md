# QuickBid – Real-Time Online Auction & Bidding Platform

QuickBid is a full-stack, enterprise-grade online auction and bidding marketplace that enables real-time bidding, seamless auction management for sellers, and administrative oversight. Built with **React**, **Node.js/Express**, **MongoDB**, and **Tailwind CSS**.

---

## ✨ Key Features

### 👤 User / Buyer Portal
- **Browse & Filter:** Explore active, upcoming, and featured auctions by category, price, and ending time.
- **Real-Time Bidding:** Place bids with instant updates, outbid alerts, and minimum bid validation.
- **My Bids & Orders:** Track active bids, winning history, and complete checkouts.
- **Wishlist & Notifications:** Save auctions for later and get notified on price updates.

### 🏪 Seller Portal
- **Become a Seller:** Onboard with identity verification and seller credentials.
- **Auction Management:** Create listings with image gallery (Cloudinary), starting price, reserve price, and custom duration.
- **Bidding History:** Monitor incoming bids and finalize auction winners upon expiry.

### 🛡️ Admin Dashboard
- **Platform Analytics:** Total revenue, active auctions, customer conversion, and dispute metrics.
- **User Management:** Oversee buyers and sellers, approve pending accounts, and manage roles.
- **Auction Moderation:** Approve, reject, or flag pending auctions.
- **Dispute Center:** Resolve conflicts between buyers and sellers.

---

## 🚀 Tech Stack

### Frontend (Client)
- **Framework:** React 18 / 19, Vite
- **Styling:** Tailwind CSS, PostCSS, Autoprefixer
- **Navigation:** React Router v6 / v7
- **Icons:** Lucide React & Heroicons
- **API Client:** Axios (configured with auth interceptors)
- **State Management:** Context API (AuthContext, UserContext)

### Backend (Server)
- **Runtime:** Node.js & Express.js
- **Database:** MongoDB with Mongoose ODM
- **Authentication:** JSON Web Tokens (JWT) & bcryptjs
- **File Storage:** Cloudinary & Multer for image processing
- **Background Tasks:** Node-Cron for automated auction lifecycle management

---

## 📁 Repository Structure

\\nQuickBid/
├── client/                     # Frontend React application
│   ├── public/                 # Static assets, logos, and illustrations
│   ├── src/
│   │   ├── api/                # Axios instance & API endpoints
│   │   ├── components/         # Dashboard, layout, product, navigation, profile components
│   │   ├── context/            # AuthContext & UserContext state providers
│   │   ├── pages/              # Admin, seller, buyer, and authentication views
│   │   ├── routes/             # Public, protected, seller, and admin routes
│   │   ├── App.jsx             # Main router shell
│   │   └── main.jsx            # React root mount
│   ├── .env.example            # Client environment template
│   ├── tailwind.config.js      # Tailwind CSS styling tokens
│   └── vite.config.js          # Vite build tool configuration
│
├── server/                     # Backend Express REST API
│   ├── config/                 # Cloudinary & database connection setup
│   ├── controllers/            # Request handlers (Auth, Auctions, Bids, Users)
│   ├── middleware/             # Auth JWT verification, admin check, file uploads
│   ├── models/                 # Mongoose schemas (User, Bid, BidItem, Order, Slide)
│   ├── routes/                 # Express API routes
│   ├── cronJobs.js             # Automated auction expiration cron jobs
│   ├── index.js                # Express app entry point
│   └── .env.example            # Server environment template
│
└── README.md                   # Platform documentation
\\n
---

## 📡 API Reference

| Module | Method | Endpoint | Access | Description |
|---|---|---|---|---|
| **Auth** | POST | /api/auth/register | Public | Register new buyer or seller account |
| **Auth** | POST | /api/auth/login | Public | Authenticate user & return JWT token |
| **Auctions** | GET | /api/bids | Public | List all active public auctions with filters |
| **Auctions** | GET | /api/auction/:id | Public | Retrieve auction details and current bid |
| **Auctions** | POST | /api/auction/bid/:id | Buyer | Place a new bid on an active auction item |
| **Seller** | GET | /api/seller/bids | Seller | Fetch all listings created by current seller |
| **Seller** | POST | /api/seller/bids | Seller | Create a new auction listing with Cloudinary images |
| **Admin** | GET | /api/admin/users | Admin | List all registered users (buyers and sellers) |
| **Admin** | PUT | /api/admin/users/:id/role | Admin | Update user roles or account status |
| **Admin** | GET | /api/admin/auctions/pending | Admin | View pending auctions requiring approval |
| **Admin** | PUT | /api/admin/auctions/:id/approve | Admin | Approve or reject pending auction |
| **Users** | GET | /api/users/profile | User | Retrieve current user profile details |
| **Users** | PUT | /api/users/profile | User | Update profile, address, and preferences |

---

## ⚙️ Environment Variables

### Server (server/.env)
\env
# Server Port
PORT=5000

# MongoDB Connection URL (Local or Atlas)
MONGO_URI=mongodb://localhost:27017/quickbid

# JWT Authentication Secret
JWT_SECRET=your_jwt_secret_key_minimum_256_bits_long_example

# Cloudinary Cloud Storage
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
\\n
### Client (client/.env)
\env
# Backend API Base URL
VITE_API_URL=http://localhost:5000/api
\\n
---

## 🏃 Getting Started Locally

### Prerequisites
- **Node.js** (v18.x or higher)
- **npm** (v9+)
- **MongoDB** (Local instance or MongoDB Atlas URI)

---

### 1. Clone Repository
\ash
git clone https://github.com/vaishnavisonawane893/QuickBid.git
cd QuickBid
\\n
---

### 2. Backend Setup
\ash
cd server
npm install

# Configure environment variables
cp .env.example .env
\\n
Update server/.env with your MongoDB URI and Cloudinary credentials, then start the server:
\ash
npm start
# Server will run on http://localhost:5000
\\n
---

### 3. Frontend Setup
In a new terminal window:
\ash
cd client
npm install

# Configure environment variables
cp .env.example .env
\\n
Start the frontend development server:
\ash
npm run dev
# App will run on http://localhost:5173
\\n
---

## 👩‍💻 Author

**Vaishnavi Sonawane**  
GitHub: [@vaishnavisonawane893](https://github.com/vaishnavisonawane893)

---

## 📄 License

This project is licensed under the MIT License.
