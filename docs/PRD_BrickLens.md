# 📄 BrickLens – PRD (Product Requirements Document)

## 1. Overview
BrickLens is a personal **Lego Photography Journal** that runs on both **web (React)** and **mobile (Flutter/Android)**.  
It allows users to capture, upload, and organize Lego photos from both a DSLR (via web) and a phone (via mobile app). Entries are synced through a shared Firebase backend.  

The app is for **personal creative use only** — no community/social networking features are planned.  

---

## 2. Goals
- Provide a **centralized photo journal** for Lego photography experiments.  
- Support both DSLR workflows (upload via web) and quick mobile shoots (via Android).  
- Record **metadata** for each shoot: story, tags, lighting setup, prompts.  
- Enable **sync between devices** with minimal setup.  
- Keep the design lightweight and extendable (future features: moodboards, stop-motion assistant).  

---

## 3. User Stories
- As a user, I want to **upload DSLR photos via the web app** so I can review and annotate them on a larger screen.  
- As a user, I want to **shoot photos directly from the Android app** so I can quickly capture Lego scenes without using my DSLR.  
- As a user, I want to **add story ideas, tags, and lighting notes** so I can track creative experiments.  
- As a user, I want to **see all my photos in one synced gallery** regardless of source.  
- As a user, I want to **generate random scene prompts** to spark inspiration when I’m stuck.  
- As a user, I want to **work offline on mobile** and sync later, so I can journal anywhere.  

---

## 4. Core Features (MVP)
1. **Gallery (Web + Mobile)**  
   - Grid of entries with thumbnails.  
   - Entry detail view (photo(s) + metadata).  

2. **Photo Capture / Upload**  
   - Web: drag & drop DSLR photos → upload.  
   - Mobile: take photos in-app with phone camera.  

3. **Entry Metadata**  
   - Title, story, tags, lighting setup, optional prompt.  

4. **Sync**  
   - Firebase backend handles real-time sync.  
   - Offline-first support on mobile (Firestore cache).  

5. **Prompt Generator**  
   - Generates random `theme + mood + Lego element`.  
   - Option to save as entry seed.  

---

## 5. Backend (Firebase)
- **Auth:** Google Sign-In or Anonymous (per-user isolation).  
- **Firestore Schema:**  

```
users/{userId}/entries/{entryId}
  title: string
  story: string
  source: "DSLR" | "MOBILE"
  tags: [string]
  lighting: { type: string, notes: string }
  promptUsed: string|null
  photoUrls: [string]
  createdAt: timestamp
  updatedAt: timestamp

users/{userId}/prompts/{promptId}
  theme: string
  mood: string
  element: string
  createdAt: timestamp
```

- **Storage:** `/photos/{userId}/{entryId}/{filename}.jpg`  

---

## 6. Tech Stack
- **Web App:** React + Vite (or Next.js if SSR needed)  
- **Mobile App:** Flutter (Android, later iOS possible)  
- **Backend:** Firebase (Auth, Firestore, Storage)  
- **CI/CD:** GitHub Actions (build + deploy Web, build APKs)  

---

## 7. Roadmap
**Phase 1 (MVP):**
- Firebase setup (Auth, Firestore, Storage).  
- Web: upload DSLR photos + gallery view.  
- Mobile: in-app camera + sync to Firestore.  
- Metadata logging (story, tags, lighting).  

**Phase 2:**
- Prompt generator integration.  
- Inspiration Wall (saved prompts + favorite entries).  
- Offline-first sync improvements.  

**Phase 3 (Future Ideas):**
- Lighting diagram sketches.  
- Stop-motion capture assistant.  
- Export entries as PDF/photo journal.  
