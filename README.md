# Vigilant Eye AI 👁️

**Vigilant Eye** is an advanced **AI-powered law enforcement project** specifically designed for modern policing requirements, such as those of the Prakasam Police Department. It serves as a comprehensive, centralized platform for real-time monitoring, automated number plate recognition (ANPR), and inter-station communication.

The primary goal of the project is to enhance situational awareness, enable rapid response to criminal activities, and streamline the workflow between field officers, checkpoints, and Station House Officers (SHOs).

---

## 🚀 How It Works

Vigilant Eye operates as a cohesive ecosystem connecting edge intelligence with a centralized control room:

1. **AI-Powered Data Capture (ANPR)**:
   - **Live Scanner**: Officers can use connected cameras (via the `/scanner` module) to read license plates in real-time.
   - **Batch Upload**: Video or image evidence can be uploaded (via the `/upload` module).
   - **OCR Engine**: The platform leverages an AI-driven Optical Character Recognition (OCR) engine (`tesseract.js`) to extract text from visual data and isolate license plate numbers.

2. **Automated Verification & Matching**:
   - The extracted plate numbers are instantly queried against a secure MongoDB database containing vehicle registration details, ownership records, and criminal histories (e.g., stolen vehicles, pending challans).
   - The system is optimized to eliminate noise, ensuring only valid, registered hits trigger actionable events.

3. **Real-Time Alerts & Dispatch**:
   - If a flagged vehicle (stolen, suspicious, or involved in a crime) is detected, the system generates an immediate alert.
   - **Socket.io** pushes these alerts in real-time to the respective Station Dashboards and connected field units without requiring a page refresh.

4. **Geospatial Tracking**:
   - Using **Leaflet** maps, the system plots the locations of scans, checkpoints, and active patrols. Dispatchers can visually track the movement of suspect vehicles across different police jurisdictions.

---

## 📋 Core Modules

- **Central Dashboard (`/`)**: A high-level overview of system metrics, active alerts, and recent scans.
- **Station Control Dashboard (`/station-dashboard`)**: Dedicated view for SHOs to manage active patrols, assign tasks, and monitor incidents specifically within their jurisdiction (e.g., Ongole I Town, II Town, etc.).
- **Live Scanner (`/scanner`)**: Real-time ANPR feed interface for instant plate detection.
- **Vehicle Database (`/database` & `/vehicles/:plate`)**: Comprehensive RTO-style database for searching vehicle owner details, insurance validity, PUC, and criminal history.
- **Alerts Management (`/alerts`)**: A system to view, update, and resolve flagged vehicle alerts.
- **Checkpoints (`/checkpoints`)**: Tools to manage static and dynamic police nakabandis (checkpoints) and log vehicles passing through them.
- **Police Stations Directory (`/police-stations`)**: Management and communication hub for all integrated police stations.

---

## 🛠️ Technology Stack

**Frontend:**
- **Framework**: React 19 with TanStack Start (SSR/Routing)
- **Styling**: Tailwind CSS & Radix UI (Accessible, modern components)
- **Animations**: Framer Motion
- **Mapping**: Leaflet & React-Leaflet

**Backend & AI:**
- **Server**: Node.js & Express
- **AI / Vision**: Tesseract.js (Offline capable OCR) and Vercel AI SDK
- **Real-time Communication**: Socket.io

**Database & Storage:**
- **Primary Database**: MongoDB (via Mongoose) for structured vehicle and user data.
- **Auth & Storage**: Supabase for secure authentication and potential blob storage.

---

## 🔑 Default Login Credentials (Testing)

The system comes pre-seeded with test accounts representing different roles within the police department.

**Global Password for all accounts:** `admin123`

### Administrator Account
- **Super Admin**: `admin@gmail.com`

### Station House Officer (SHO) Accounts
- **Ongole I Town SHO**: `onetown@ongole.com`
- **Ongole II Town SHO**: `twotown@ongole.com`
- **Ongole Taluka SHO**: `taluka@ongole.com`
- **Ongole III Town SHO**: `threetown@ongole.com`
- **Chimakurthy SHO**: `chimakurthy@ongole.com`
- **Kandukur SHO**: `kandukur@ongole.com`

---

## 💻 Getting Started (Local Development)

To run the Vigilant Eye project locally on your machine:

1. **Install Dependencies**:
   ```bash
   npm install
   ```

2. **Environment Variables**:
   Ensure your `.env` file is configured with the necessary Supabase and MongoDB connection strings.

3. **Seed the Database** (Optional, to populate mock vehicles and users):
   ```bash
   node backend/seed.cjs
   ```

4. **Start the Development Server**:
   ```bash
   npm run dev
   ```
   This will concurrently start both the Vite frontend and the Express backend/Socket.io server.
