# UPSC Study Tracker

A full-featured study tracking dashboard built with React, Chart.js, and Firebase.

## Features
- 📊 Study time tracking (Today / Week / Month / Total)
- 🔥 Daily streak calendar
- 🎯 Goal setting (daily hours, target date, study day target)
- 📖 Course-wise breakdown with donut chart
- 📈 Weekly study hours line chart
- ⏱ Built-in study timer (auto-logs on save)
- 📋 Activity log with delete
- 📅 Exam countdown (Prelims, Mains, Interview)
- 📉 Pace analysis (required vs current)
- ☁️ Firebase Firestore sync (optional)

---

## Quick Start (Local)

Just open `index.html` in any browser. Data is stored in localStorage.

---

## Firebase Setup (Cloud Sync)

1. Go to https://console.firebase.google.com
2. Create a new project (e.g. `upsc-tracker`)
3. Enable **Firestore Database** (start in test mode)
4. Go to **Project Settings → Your Apps → Web App** and copy the config
5. Open `index.html` and replace the `FIREBASE_CONFIG` block:

```js
const FIREBASE_CONFIG = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

---

## Deploy to Firebase Hosting

```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login
firebase login

# Initialize (select Hosting, use current directory)
firebase init hosting

# Deploy
firebase deploy
```

Your app will be live at `https://YOUR_PROJECT.web.app`

---

## Firestore Data Structure

```
/activities/{id}
  - date: "2026-05-07"
  - type: "Study"
  - course: "Polity"
  - subject: "Indian Constitution"
  - topic: "Fundamental Rights"
  - startTime: "10:00"
  - duration: 120   (minutes)

/goals/main
  - dailyHrs: 7
  - targetDate: "2026-07-05"
  - studyDayTarget: 383
```

---

## Customising Exam Dates

Edit the `exams` array inside `App` in `index.html`:

```js
const exams = [
  { name: 'UPSC Prelims 2026', date: '2026-05-24' },
  { name: 'UPSC Mains 2026',   date: '2026-09-21' },
  { name: 'Interview',          date: '2027-02-01' },
];
```
