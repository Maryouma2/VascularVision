# VascularVision 🫀

A daily monitoring web app for dialysis patients — helping them stay safe and informed between dialysis sessions.

## The Problem

Dialysis patients go home between sessions with no structured way to monitor their health. A silent fistula (the access point used during dialysis) can fail without warning. Fluid overload from not tracking weight and intake is the leading cause of emergency hospitalizations. Patients have no easy way to share their daily trends with their doctor.

## The Solution

VascularVision gives patients three core tools:

- **Fistula check** — A daily yes/no check: can you feel the vibration? If not, an immediate alert to contact the doctor.
- **Daily vitals log** — Track weight, blood pressure, and fluid intake every day with trend visualization.
- **Doctor-ready PDF report** — One button generates a clinical summary of the last 7/14/30 days to share at clinic visits.

## Live Demo

> Coming August 2025

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React, Tailwind CSS |
| Backend | Node.js, Express |
| Database | PostgreSQL (Supabase) |
| Auth | JWT |
| PDF | pdfkit |
| Frontend deploy | Vercel |
| Backend deploy | Railway |
| CI/CD | GitHub Actions |

## Features

### MVP (v1.0)
- [x] User registration and login
- [ ] Fistula thrill check with alert escalation
- [ ] Daily vitals logging (weight, blood pressure, fluid intake)
- [ ] Vitals trend chart (14-day history)
- [ ] Home dashboard with daily status summary
- [ ] Doctor-ready PDF report generation
- [ ] Auto-deploy on push via GitHub Actions

### Phase 2 (planned)
- [ ] Medication and session reminders
- [ ] AI chatbot for patient guidance
- [ ] Image-based swelling tracking

## Project Structure

```
vascular-vision/
├── frontend/          # React app
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/  # API calls
│   │   └── App.js
│   └── package.json
├── backend/           # Express API
│   ├── routes/
│   ├── controllers/
│   ├── middleware/
│   ├── db/
│   └── server.js
└── README.md
```

## Getting Started

### Prerequisites
- Node.js v18+
- A Supabase account (free tier)

### Run locally

```bash
# Clone the repo
git clone https://github.com/Maryouma2/vascular-vision.git
cd Vascular-vision

# Start backend
cd backend
npm install
cp .env.example .env   # fill in your Supabase URL and JWT secret
node server.js

# Start frontend (new terminal)
cd frontend
npm install
npm start
```

## Environment Variables

Create a `.env` file in `/backend`:

```
PORT=5000
DATABASE_URL=your_supabase_connection_string
JWT_SECRET=your_secret_key
```

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/auth/register | Register new patient |
| POST | /api/auth/login | Login and receive JWT |
| POST | /api/fistula | Save fistula check |
| GET | /api/fistula/history | Get last 7 checks |
| POST | /api/vitals | Save daily vitals |
| GET | /api/vitals/history | Get last 14 days |
| GET | /api/report/pdf | Generate PDF report |

## Why I Built This

This project was inspired by a conversation with a dialysis care professional about the daily challenges patients face at home between sessions. It is my first fully deployed full-stack healthcare application.

## Author

**Maryam Tahan** — Software Engineer, Lebanese University  
[LinkedIn](https://linkedin.com/in/maryam-tahan-37b1052a5) · [GitHub](https://github.com/Maryouma2)