# 🎬 Intermission — Cinema Management & Booking System

[![Node.js](https://img.shields.io/badge/Node.js-v20+-green.svg?logo=nodedotjs)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-5.x-lightgrey.svg?logo=express)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-brightgreen.svg?logo=mongodb)](https://www.mongodb.com/)
[![React Native](https://img.shields.io/badge/React%20Native-0.81-blue.svg?logo=react)](https://reactnative.dev/)
[![Expo](https://img.shields.io/badge/Expo-SDK%2054-black.svg?logo=expo)](https://expo.dev/)
[![Railway](https://img.shields.io/badge/Deployed%20on-Railway-0B0D0E.svg?logo=railway)](https://railway.app/)
[![Netlify](https://img.shields.io/badge/Deployed%20on-Netlify-00C7B7.svg?logo=netlify)](https://www.netlify.com/)

**Intermission** is a modern, cross-platform cinema management and ticketing solution. Built with a robust **Node.js/Express & MongoDB** backend and an intuitive **React Native (Expo)** frontend, it provides an end-to-end cinema experience for both moviegoers and cinema administrators across Mobile and Web.

---

## 🌐 Live Deployments

- 🚀 **Frontend Web Application:** [https://heroic-starburst-5d67de.netlify.app](https://heroic-starburst-5d67de.netlify.app/)
- ⚙️ **Backend REST API:** [https://intermissioncinemaapp-production.up.railway.app](https://intermissioncinemaapp-production.up.railway.app)

---

## ✨ Core Features

### 👤 Customer Features
- **Browse & Search Movies:** Explore currently showing and upcoming movies with genres, synopsis, ratings, and trailers.
- **Showtimes & Schedules:** Select dates and browse available cinema showtimes and screen halls.
- **Interactive Seat Booking:** Select seats, book tickets, and view reservation summaries with instant confirmation.
- **My Bookings & History:** View active tickets, past booking history, and cancel reservations.
- **Ratings & Reviews:** Submit reviews, share feedback, and view movie ratings from other customers.
- **Movie Suggestions & Requests:** Request new movies you want to see screened and view approved community suggestions.

### 🛡️ Administrator Features
- **Movie Catalog Management:** Add, update, or remove movies with metadata and poster links.
- **Showtime Scheduling:** Create and manage showtime slots, assign cinema halls, and set seat capacities.
- **Suggestion Moderation:** Review, approve, or reject user movie suggestions and requests.
- **Feedback & Review Monitoring:** View, moderate, and track customer satisfaction metrics.
- **Booking Management:** Oversee seat reservations and ticket allocations.

---

## 🛠️ Tech Stack

| Layer | Technologies |
|---|---|
| **Frontend** | React Native (Expo SDK 54), React 19, React Navigation, React Native Web, Axios |
| **Backend** | Node.js, Express.js (v5), Mongoose ODM, JWT, bcryptjs, CORS |
| **Database** | MongoDB (Atlas / Local) |
| **Deployment** | Netlify (Frontend Web), Railway (Backend API) |

---

## 📁 Project Structure

```text
Intermission_CinemaApp/
├── backend/
│   ├── config/             # Database connection & initial admin seeding
│   ├── controllers/        # Request handlers (auth, movies, showtimes, bookings, etc.)
│   ├── middleware/         # Auth & authorization middleware
│   ├── models/             # Mongoose schemas (User, Movie, Showtime, Booking, etc.)
│   ├── routes/             # Express API route declarations
│   ├── scripts/            # Database utility scripts
│   ├── utils/              # Helper utilities
│   ├── .env.example        # Backend environment template
│   ├── package.json
│   └── server.js           # Server entry point
│
├── frontend/
│   ├── assets/             # Icons, splash screens, and images
│   ├── src/
│   │   ├── api/            # Axios API client & interceptors
│   │   ├── context/        # React context (Auth state)
│   │   ├── navigation/     # Stack & Tab navigators
│   │   ├── screens/        # Screen components (Auth, Movies, Bookings, Admin, etc.)
│   │   └── utils/          # Frontend helpers
│   ├── .env.example        # Frontend environment template
│   ├── App.js              # Application root
│   ├── app.json            # Expo configuration
│   └── package.json
│
├── .gitignore
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v20 or higher recommended)
- [MongoDB](https://www.mongodb.com/) (Local instance or MongoDB Atlas URI)
- [Expo Go](https://expo.dev/go) app (optional, for running on physical mobile devices)

---

### 1. Backend Setup

1. Open a terminal and enter the `backend` directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file based on [.env.example](file:///c:/Users/Maleesha%20Maddegoda/Desktop/Intermission_CinemaApp-main/Intermission_CinemaApp-main/backend/.env.example):
   ```env
   PORT=5000
   MONGO_URI=mongodb://localhost:27017/intermission_cinema
   JWT_SECRET=your_jwt_secret_key_here
   NODE_ENV=development

   # Optional: Default admin seeded on initial empty database run
   SEED_ADMIN_EMAIL=admin@cinema.local
   SEED_ADMIN_PASSWORD=admin123
   ```

4. Start the backend:
   ```bash
   # Development mode with hot-reload
   npm run dev

   # Production mode
   npm start
   ```
   Backend will run on `http://localhost:5000`.

---

### 2. Frontend Setup

1. Open a new terminal and navigate to `frontend`:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file based on [.env.example](file:///c:/Users/Maleesha%20Maddegoda/Desktop/Intermission_CinemaApp-main/Intermission_CinemaApp-main/frontend/.env.example):
   ```env
   # Local development (Web):
   EXPO_PUBLIC_API_URL=http://localhost:5000/api

   # For physical mobile device testing via Expo Go:
   # Replace with your computer's local IP address (e.g. http://192.168.1.100:5000/api)
   ```

4. Start the app:
   ```bash
   # To launch in Web browser:
   npm run web

   # To launch with Expo CLI (Mobile / Emulator):
   npm start
   ```

---

## 🔑 Default Administrator Credentials

When the database is initialized with no admin accounts, the system automatically creates a default admin:
- **Email:** `admin@cinema.local`
- **Password:** `admin123`

---

## 📡 API Reference Overview

| Endpoint | Method | Description | Access |
|---|---|---|---|
| `/api/auth/register` | POST | Register a new user | Public |
| `/api/auth/login` | POST | Authenticate user & retrieve JWT | Public |
| `/api/movies` | GET / POST | Get all movies / Add a movie | Public / Admin |
| `/api/movies/:id` | GET / PUT / DELETE | Movie details / Update / Delete | Public / Admin |
| `/api/showtimes` | GET / POST | List showtimes / Schedule showtime | Public / Admin |
| `/api/bookings` | GET / POST | User bookings / Create reservation | Authenticated |
| `/api/feedback` | GET / POST | Read reviews / Submit review | Public / Authenticated |
| `/api/suggestions` | GET / POST | Read suggestions / Submit request | Public / Authenticated |

---

## 📄 License
This project is developed for academic purposes under the SLIIT Information Technology curriculum.