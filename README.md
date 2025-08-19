# 📸 BrickLens

BrickLens is a personal **Lego Photography Journal** that syncs across **Web (React)** and **Android (Flutter)**.  
It helps you capture, upload, and annotate Lego photo shoots — whether taken with a DSLR or your phone.  
Think of it as a creative diary for Lego storytelling.

---

## ✨ Features
- **Web App (React)**
  - Upload DSLR photos.
  - Annotate with story, tags, lighting notes.
  - Browse a synced gallery on desktop.

- **Mobile App (Flutter/Android)**
  - Shoot Lego photos directly in-app.
  - Add quick notes and prompts on the go.
  - Sync with web gallery when online.

- **Backend (Firebase)**
  - Firestore for metadata.
  - Cloud Storage for high-resolution photos.
  - Offline-first sync on mobile.

---

## 🗂️ Project Structure
```
bricklens/
├── backend/            # Firebase config / rules
├── web-app/            # React app for DSLR workflow
├── mobile-app/         # Flutter Android app
└── shared/             # Shared models and utils
```

---

## 🛠️ Tech Stack
- **Frontend (Web):** React + Vite
- **Frontend (Mobile):** Flutter (Android, iOS optional)
- **Backend:** Firebase (Auth, Firestore, Storage)

---

## 🚀 Getting Started

### 1. Clone the Repo
```bash
git clone https://github.com/<your-username>/bricklens.git
cd bricklens
```

### 2. Setup Firebase
- Create a Firebase project at [Firebase Console](https://console.firebase.google.com/).
- Enable **Auth (Google or Anonymous)**, **Firestore**, and **Cloud Storage**.
- Copy config into both `web-app` and `mobile-app`.

### 3. Run Web App
```bash
cd web-app
npm install
npm run dev
```

### 4. Run Mobile App
```bash
cd mobile-app
flutter pub get
flutter run
```

---

## 📌 Roadmap
- [x] Define PRD and architecture.
- [ ] Initialize Firebase project.
- [ ] Implement web upload & gallery view.
- [ ] Build mobile capture & sync.
- [ ] Add prompt generator.
- [ ] Release MVP.
