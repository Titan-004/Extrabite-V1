# 🍽️ ExtraBite – Save Food, Feed Lives

[Live Site](https://extrabite.vercel.app) • [Swagger Docs](https://extrabite-backend-2.onrender.com/swagger-ui) • [Postman API Docs](https://documenter.getpostman.com/view/30078893/2sA35KXuta) • [Frontend GitHub Repo](https://github.com/Titan-004/Extrabite-V1)

**ExtraBite** is a humanitarian web platform that connects food donors (restaurants, households, organizations) with receivers (individuals, NGOs), reducing food wastage and hunger through technology.

Whether you're donating or receiving, ExtraBite ensures a safe, transparent, and fast food-sharing process powered by live updates, geo-location, OTP handovers, and role-based features.

---

## 💡 Mission

To reduce food wastage and alleviate hunger by enabling efficient and safe redistribution of surplus food in real time.

> Even if one meal is saved and reaches one hungry person — it’s worth it.

---

## 🧭 Full-Stack Overview

### 🛠️ Frontend: React + Vite

- **React 19** with **Vite** build tool
- **Tailwind CSS**, **MUI**, and **Framer Motion** for styling and animations
- **Axios** for API interaction with JWT and API key headers
- **Chart.js**, **MUI X-Charts** for analytics
- **React Router**, **React Icons**, and more

### ☕ Backend: Spring Boot

- **Spring Boot 3.5.0**, **Java 17**
- **PostgreSQL** with **Hibernate (JPA)**
- **Spring Security** with **JWT Auth**
- **API Key Authentication** for secure access
- **OpenAPI 3 + Swagger UI**
- **Maven** & **Docker** supported

---

## 🔐 Authentication & Security

- **JWT Authentication**: Role-based access for Donor, Receiver, Admin
- **Custom API Keys**: Secure access from client to backend
- **OTP Verification**: For donation handovers
- **Role-based Dashboards**: Controlled views and permissions

---

## 🔁 App Flow

### 👥 Role Selection
- User selects role: **Donor**, **Receiver**, or **Admin**
- Auto location using geolocation API
- Donors can optionally provide FSSAI license

### 🧑‍🍳 Donor Flow
- Add food: name, quantity, expiry, pickup time, images
- Expiry-based auto deletion (2–4 hours)
- Dashboard: donation history, analytics, active/past requests

### 📥 Receiver Flow
- Browse real-time donations nearby
- Place requests, await OTP from donor
- OTP required for pickup verification

### 🛡️ Admin Flow
- Approve/block users
- View donation stats and platform usage
- Handle user reports and misuse

---

## 📊 Real-Time Analytics

- Donation trends: daily, weekly, monthly
- Sources of food waste (restaurant, household, event, etc.)
- Graphs and comparisons using Chart.js and MUI

---

## 📁 Project Directory Structure

### Frontend (`extrabite-frontend`)
```
📁 src
├── assets/               # Static assets and icons
├── components/           # Shared UI components
├── context/              # React context API
├── pages/                # Page-level components
├── statics_components/   # Charts, reusable blocks
├── util/                 # API helpers, token utils
```

### Backend (`extrabite-backend`)
```
📁 src/main/java/com/extrabite/
├── config/          # Security configs
├── controller/      # REST controllers
├── dto/             # Request & response DTOs
├── entity/          # JPA Entities
├── repository/      # Repositories
├── service/         # Business logic
│   ├── impl/        # Service implementations
│   └── spec/        # Specifications for queries
├── util/            # Utility classes
├── scheduler/       # Scheduled cleanup tasks
```

---

## ⚙️ Setup & Deployment

### 🔧 Prerequisites

- Node.js 18+, Java 17+, Maven 3.6+
- PostgreSQL
- Docker (optional for both frontend/backend)

### 🚀 Run Frontend

```bash
cd extrabite-frontend
npm install
cp .env.example .env    # configure API base URL and API Key
npm run dev             # Start dev server
```

#### Frontend `.env` file:
```env
VITE_API_BASE_URL=https://extrabite-backend-2.onrender.com/api
VITE_API_KEY=your-api-key
```

### ☕ Run Backend (Locally)

```bash
cd extrabite-backend
cp env.example .env     # configure DB and secrets
mvn clean install
mvn spring-boot:run
```

### 🐳 Docker Deployment

```bash
# Backend
docker build -t extrabite-backend .
docker run -d -p 8080:8080 --env-file .env extrabite-backend

# Frontend (optional static deploy via Vercel/Netlify)
npm run build
```

---

## 📚 API Documentation

- **Swagger UI**: [View Interactive Docs](https://extrabite-backend-2.onrender.com/swagger-ui)
- **Postman Collection**: [View on Postman](https://documenter.getpostman.com/view/30078893/2sA35KXuta)
- **OpenAPI Spec**: `/v3/api-docs`

📁 API Modules:
- `/api/auth` – Auth & JWT
- `/api/users` – User profile & roles
- `/api/donations` – Create/manage donations
- `/api/requests` – Request donations
- `/api/rating` – Leave ratings
- `/api/analytics` – Platform stats
- `/api/admin` – Admin-level actions

---

## 🧪 Testing

### Backend
```bash
mvn test
mvn test jacoco:report   # Generate test coverage
```

---

## 💬 Contributing

Contributions welcome!

1. Fork the repo
2. Create a new feature branch
3. Make your changes and add tests
4. Commit & push
5. Create a pull request

---

## 📜 License

This project is open for **educational and humanitarian use**.  
For commercial use or partnerships, please reach out.

---

## 💚 Join ExtraBite — Empower Change, Transform Lives

> Helping even one person makes it worth building.
