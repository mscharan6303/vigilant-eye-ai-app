# Vigilant Eye AI 👁️

Vigilant Eye is an advanced **AI Project** tailored for modern law enforcement and police operations. It serves as a comprehensive dashboard and monitoring system built to enhance situational awareness, rapid response, and inter-station communication.

## Features
- **AI-Powered Analysis**: Utilizes `tesseract.js` for OCR and AI to extract actionable intelligence from various sources, such as automated number plate recognition (ANPR).
- **Real-Time Dashboards**: Powered by `Socket.io` and `React`, offering live updates for field officers and dispatchers.
- **Geospatial Mapping**: Integrated with `Leaflet` to track units, incidents, and resources dynamically.
- **Secure Architecture**: Built with modern web standards (Tanstack Start, React 19, Tailwind CSS) and secured by robust backends including Supabase and MongoDB.

## Screenshots

![Prakasam Police Badge](public/prakasam_police_badge.png)
*Prakasam Police Integration*

![Officer Dashboard](public/officer_1.png)
*Field Officer View 1*

![Officer App](public/officer_2.png)
*Field Officer View 2*

## Tech Stack
- **Frontend**: React 19, Tanstack Start/Router, Tailwind CSS, Radix UI, Framer Motion
- **Backend/AI**: Express, Mongoose, Socket.io, Tesseract.js (OCR), AI SDK
- **Database**: MongoDB (via Mongoose), Supabase
- **Mapping**: Leaflet, React-Leaflet

## Default Login Credentials (Testing)

For local development and testing, you can use the following seeded accounts. 
**Global Password for all accounts:** `admin123`

### Administrator Account
- `admin@gmail.com` (Super Admin)

### Station House Officer (SHO) Accounts
- `onetown@ongole.com` (Ongole I Town SHO)
- `twotown@ongole.com` (Ongole II Town SHO)
- `taluka@ongole.com` (Ongole Taluka SHO)
- `threetown@ongole.com` (Ongole III Town SHO)
- `chimakurthy@ongole.com` (Chimakurthy SHO)
- `kandukur@ongole.com` (Kandukur SHO)

## Getting Started

1. Install dependencies:
   ```bash
   npm install
   ```

2. Run the development server:
   ```bash
   npm run dev
   ```
