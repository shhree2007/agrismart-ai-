# AgriSmart AI — Intelligent Agricultural Stewardship & Telemetry Platform

An engineering project providing an end-to-end precision agronomy platform with crop pathology detection, automated smart irrigation telemetry, microclimate risk advisory, APMC mandi market price intelligence, and persistent Google Cloud Firestore integration.

---

## 🌟 Key Features

1. **Executive Agro-Station Dashboard**:
   - Real-time weather banner (Temperature, Humidity, Wind speed, Precipitation, UV index) from station `MH-SOL-092`.
   - Crop Health Index (NDVI) monitoring across crop parcels (Sugarcane, Soybean, Cotton).
   - Live telemetry status for soil moisture and automated fertigation cycles.
   - Microclimate-driven Agri Alerts with prioritized action triggers.

2. **Leaf Pathology & Crop Disease Diagnostics**:
   - Deep leaf pathology detection engine with bounding-box lesion visualization.
   - Diagnostic confidence metrics, pathogen identification, and curative action plans (Chemical + Bio-fungicide protocols).
   - Downloadable agronomic prescriptions.

3. **Smart Irrigation & Autonomous Solenoid Valve Control**:
   - Submersible pump telemetry (3.8 BAR pressure, flow rate, emergency cutoff).
   - Real-time sector valve toggling with automated rain-delay intelligence.
   - 24-hour depth-sensor soil moisture tracking.

4. **APMC Mandi Real-Time Price Intelligence**:
   - Commodity price tracker with MSP (Minimum Support Price) baseline comparisons.
   - 6-month historical trend analysis and regional mandi comparison (Solapur, Barshi, Latur, Akola).
   - Distance-adjusted net realization calculations.

5. **Multilingual Support (Engineering Accessibility)**:
   - Complete localized UI across **English**, **मराठी (Marathi)**, and **हिंदी (Hindi)**.
   - Seamless language toggle from login and top navigation.

6. **Cloud Database & Security Architecture**:
   - Persistent **Google Cloud Firestore** integration.
   - Attribute-Based Access Control (ABAC) in `firestore.rules`.
   - Data models defined in `firebase-blueprint.json`.

---

## 🛠️ Technology Stack

| Layer | Technologies |
|---|---|
| **Frontend UI** | React 19, TypeScript, Tailwind CSS v4, Lucide Icons, Material Symbols |
| **Build & Tooling** | Vite, ESBuild, Bun / Node.js |
| **Database** | Google Cloud Firestore (Enterprise Edition) |
| **Security & RBAC** | Firebase Security Rules (ABAC with strict schema guards) |
| **Localization** | Custom React Context I18n Engine (English, Marathi, Hindi) |

---

## 📂 Project Structure

```text
├── firebase-applet-config.json  # Cloud project and database credentials
├── firebase-blueprint.json      # Schema blueprint & data contracts
├── firestore.rules              # Hardened Zero-Trust Firestore security rules
├── index.html                   # HTML entry point with metadata
├── package.json                 # Dependencies and build scripts
├── src/
│   ├── App.tsx                  # Root layout, routing & state
│   ├── firebase.ts              # Firebase SDK initialization & error handler
│   ├── components/
│   │   ├── Header.tsx           # Navigation header, search & language switcher
│   │   ├── Sidebar.tsx          # Collapsible sliding navigation sidebar
│   │   ├── MobileNav.tsx        # Mobile dock navigation
│   │   ├── SettingsModal.tsx    # Database status & sensor configurations
│   │   └── HelpCenterModal.tsx  # Support & FAQs
│   ├── context/
│   │   └── LanguageContext.tsx  # Multi-language provider
│   ├── i18n/
│   │   └── translations.ts      # Translation dictionary (en, mr, hi)
│   ├── services/
│   │   └── dbService.ts         # Firestore CRUD and persistence methods
│   ├── views/
│   │   ├── DashboardView.tsx
│   │   ├── DiseaseDetectionView.tsx
│   │   ├── CropRecommendationView.tsx
│   │   ├── WeatherRiskView.tsx
│   │   ├── SmartIrrigationView.tsx
│   │   ├── MarketPricesView.tsx
│   │   ├── AIAssistantView.tsx
│   │   ├── ProfileView.tsx
│   │   └── LoginView.tsx
│   ├── data/
│   │   └── mockData.ts
│   └── types.ts
└── tsconfig.json
```

---

## 🚀 Getting Started

### 1. Prerequisites
- Node.js (v18 or higher)
- npm or bun

### 2. Installation
```bash
# Clone the repository
git clone https://github.com/<your-username>/<your-repo-name>.git

# Navigate to project directory
cd <your-repo-name>

# Install dependencies
npm install
```

### 3. Run Development Server
```bash
npm run dev
```
Open your browser and navigate to `http://localhost:3000`.

### 4. Build for Production
```bash
npm run build
```

---

## 🔒 Security & Database Rules
The Cloud Firestore database enforces zero-trust security:
- Default-deny global catchall.
- Identity integrity checking (`request.auth.uid == userId`).
- Strict schema validation helpers (`isValidUserProfile`, `isValidIrrigationZone`).
- Protection against ID-poisoning and oversized data payloads.

---

## 👥 Authors & Academic Attribution
Developed as an Engineering Project for Precision Agronomy & Agricultural IoT Stewardship.
