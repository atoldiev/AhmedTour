<div align="center">

# 🏔️ AhmedTour

**Full-stack tour booking platform for the North Caucasus**

*Платформа бронирования туров по Северному Кавказу: Ингушетия, Чечня, Дагестан, Кабардино-Балкария.*

![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Redux Toolkit](https://img.shields.io/badge/Redux_Toolkit-764ABC?logo=redux&logoColor=white)
![Node.js](https://img.shields.io/badge/Express-000000?logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white)
![Sequelize](https://img.shields.io/badge/Sequelize-52B0E7?logo=sequelize&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-auth-000000?logo=jsonwebtokens&logoColor=white)

</div>

## About

AhmedTour lets travellers browse guided tours by region, check how many seats are left, add tours to a cart and leave reviews. Administrators manage the catalogue and see the booking history.

Built by a team of six developers in Dec 2023 – Feb 2024: **211 commits, 60+ merged pull requests**, feature branches merged into `dev` through PRs.

## Features

**For travellers**
- Region catalogue → tour list → detailed tour page with photos, programme, dates and duration
- Live seat counter (booked / total places) for every tour
- Cart with booking and checkout form
- Reviews and comments on tours
- Registration and login in modal windows

**For administrators**
- Create and edit tours with photo upload
- Booking history page

**Under the hood**
- JWT authentication with **access + refresh tokens** in httpOnly cookies
- Axios interceptors that transparently refresh an expired access token
- Role model (user / admin) and author checks on protected routes
- PostgreSQL schema managed with Sequelize migrations and seeders
- Image uploads via Multer

## Architecture

```
AhmedTour/
├── client/                # React + TypeScript + Vite
│   └── src/
│       ├── components/    # pages, UI, hooks, HOCs
│       ├── redux/         # slices: auth, tour, region, comment, history
│       ├── services/      # API layer (axios)
│       └── types/
└── server/                # Node.js + Express
    ├── db/                # Sequelize models, migrations, seeders
    └── src/
        ├── routes/        # auth, tokens, regions, tours, basket, comments, history
        ├── middlewares/   # access/refresh token checks, uploads
        └── config/
```

**Data model:** `User` · `Role` · `Region` · `Tour` · `PhotoTour` · `Basket` · `Comment` · `History`

## My role

<!-- TODO: проверь и поправь под себя -->
I worked across the stack, focusing on the core user flow:

- App shell and routing, navigation bar, main, region, tour-details and cart pages
- Redux slices and thunks for tours and authentication, axios interceptors
- Cart API on the server, Sequelize models and seed data for tours and photos

## Getting started

```bash
# 1. Server
cd server
cp .env.example .env        # fill in DB credentials and token secrets
npm install
npm run db                  # create DB, run migrations and seeders
npm start                   # http://localhost:3000

# 2. Client
cd ../client
npm install
npm run dev                 # http://localhost:5173
```

`client/.env` → `VITE_SERVER_BASEURL=http://localhost:3000`

## Team

Developed by a team of six.
<!-- TODO: перечисли участников со ссылками на их GitHub, например: [@nickname](https://github.com/nickname) -->
