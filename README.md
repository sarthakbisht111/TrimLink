# TrimLink — URL Shortener

> A scalable full-stack URL shortening service with custom short links, per-link analytics, and JWT-based authentication.

🔗 **Live:** [trimlink1.onrender.com](https://trimlink1.onrender.com)

---

## Features

- **Custom Short URLs** — generate clean, shareable short links from any long URL
- **JWT Authentication** — secure signup/login with token-based session management
- **Per-link Analytics** — track total clicks per URL with timestamp-based logging
- **User Dashboard** — view and manage all your shortened links in one place
- **Redirect Engine** — fast redirection to original URLs via indexed MongoDB lookups
- **Server-rendered UI** — responsive EJS templates with middleware-driven access control
- **MVC Architecture** — clean separation across `controllers/`, `routes/`, `models/`, `service/`, `views/`

---

## Tech Stack

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?style=flat-square&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![EJS](https://img.shields.io/badge/EJS-B4CA65?style=flat-square&logo=ejs&logoColor=black)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)
![Render](https://img.shields.io/badge/Deployed%20on-Render-46E3B7?style=flat-square)

| Layer       | Technology                        |
|-------------|-----------------------------------|
| Runtime     | Node.js                           |
| Framework   | Express.js                        |
| Database    | MongoDB + Mongoose                |
| Auth        | JWT (JSON Web Tokens)             |
| Templating  | EJS (Embedded JavaScript)         |
| Deployment  | Render                            |

---

## Project Structure

```
TrimLink/
├── controllers/      # Route handler logic (auth, URL, analytics)
├── middleware/       # JWT verification, session guard
├── models/           # Mongoose schemas (User, URL)
├── routes/           # Express route definitions
├── service/          # Business logic layer
├── views/            # EJS templates (dashboard, login, signup)
├── connect.js        # MongoDB connection
└── index.js          # App entry point
```

---

## Getting Started

### Prerequisites
- Node.js v18+
- MongoDB (local or Atlas)

### Installation

```bash
git clone https://github.com/sarthakbisht111/TrimLink.git
cd TrimLink
npm install
```

### Environment Variables

Create a `.env` file in the root:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
PORT=8000
```

### Run Locally

```bash
node index.js
```

Visit `http://localhost:8000`

---

## API Overview

| Method | Endpoint         | Description                    | Auth Required |
|--------|------------------|--------------------------------|---------------|
| POST   | `/user/signup`   | Register a new user            | No            |
| POST   | `/user/login`    | Login and receive JWT token    | No            |
| POST   | `/url`           | Generate a short URL           | Yes           |
| GET    | `/:shortId`      | Redirect to original URL       | No            |
| GET    | `/url/analytics/:shortId` | Get click analytics | Yes           |

---

## Deployment

Deployed on **Render** with MongoDB Atlas integration.

- Auto-deploy on push to `main`
- Optimised Express routing for consistent low-latency responses
- Stateless JWT auth — no server-side session storage

---

## Author

**Sarthak Bisht**
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/sarthakbisht111)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/sarthakbisht111)

---

## License

[MIT](LICENSE)
