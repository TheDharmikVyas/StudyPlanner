# StudyOptima 📅

**StudyOptima** is a personalized daily self-study timetable generator and tracker. Designed for students, it optimizes your daily timeline (incorporating college hours, commute times, and dinner breaks) and schedules study blocks for your subjects while avoiding fatigue, matching quiet locations, and suggesting evidence-based learning techniques.

---

## ✨ Features

- **College Routine Integration**: Define your college start/end times and commute hours. The system locks these blocks on your schedule and schedules study slots during your actual free hours.
- **Priority-Weighted Allocator**: High-focus subjects get allocated more time slots.
- **Fatigue Avoidance**: Automatically alternates subjects to prevent studying the same topic for too many consecutive hours.
- **Evidence-Based Study Methods**: Automatically recommends:
  - **Feynman Technique / Active Recall** for High-priority analytical subjects (e.g., Math, Coding) at your **Hostel Desk**.
  - **Cornell Note-Taking** for Medium-priority conceptual subjects (e.g., Software Engineering) at the **Library**.
  - **Spaced Repetition / Flashcards** for Low-priority memorization subjects (e.g., History) in the **Silent Study Zone**.
- **Interactive Focus Clock**: A functional Pomodoro Timer (25 min study / 5 min break) featuring an animated progress ring and chime alarms.
- **Adherence & Progress Cockpit**: Real-time progress trackers showing total study targets, completed blocks, and your daily adherence rate (with confetti reward!).
- **Light & Dark Mode**: Persistent theme settings with accessible, high-contrast alert boxes.

---

## 🛠️ Tech Stack

- **Frontend**: React (18), Vite, TypeScript, Vanilla CSS (Premium Glassmorphic Styles), Lucide Icons, Canvas Confetti.
- **Backend**: Node.js, Express, CORS.
- **Database**: File-based persistence (`study-data.json` mock DB).

---

## 🚀 Getting Started

### Prerequisites

Make sure you have [Node.js](https://nodejs.org/) installed (v16+ recommended).

### Installation

1. Open your terminal in the project root folder.
2. Install all dependencies for the root coordinator, backend, and frontend with a single command:
   ```bash
   npm run install:all
   ```

### Running the Application

1. Start both backend (port 5001) and frontend (port 3001/3000) servers concurrently by running:
   ```bash
   npm run dev
   ```
2. Open your browser and navigate to **[http://localhost:3001](http://localhost:3001)** (or check the terminal logs for the exact port Vite assigned).

---

## 📂 Project Structure

```text
├── backend/
│   ├── package.json        # Express dependencies
│   ├── server.js           # API Endpoints & DB synchronization
│   ├── solver.js           # Daily study allocation logic
│   └── sample-data.js      # Default subjects, time windows, and locations
├── frontend/
│   ├── package.json        # React & Vite dev dependencies
│   ├── vite.config.ts      # Proxy server configuration (localhost:5001)
│   ├── index.html          # Web shell (Inter/Outfit Google Fonts)
│   ├── src/
│   │   ├── main.tsx        # React entrypoint
│   │   ├── App.tsx         # Dashboard cockpit, states, and toggle triggers
│   │   ├── index.css       # Custom design tokens, timeline, and light/dark theme override
│   │   └── components/
│   │       ├── DailyInputPanel.tsx    # Forms for Routine, Subjects, Blocks & Places
│   │       ├── DailyStudyTimeline.tsx # Vertical schedule checklist and Focus trigger
│   │       └── StudyGuideConsole.tsx  # Active Pomodoro Timer & study methodology guide
└── package.json            # Root script orchestrator (concurrently)
```

