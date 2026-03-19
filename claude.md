# claude.md - Task Manager Project Brain

> This file is your **project memory** and **task tracker**. Update it as you progress through development. It serves as your brain for the entire project.

**Last Updated:** March 19, 2026
**Project:** Smart Task Manager with Google Calendar Integration
**Developer:** VitalDev
**Status:** 🟡 Phase 3 In Progress - Frontend Dashboard

---

## 📊 PROJECT OVERVIEW

### Quick Summary
Building a custom React web application to manage daily tasks, work projects, and interview preparation with:
- Real-time Google Calendar synchronization
- Smart alerts with custom sounds per task type
- Status tracking and daily progress analytics
- Works on phone AND desktop

### Key Info
- **Tech Stack:** React 18 + Node.js + Firebase + Vercel
- **Build Method:** Claude Code CLI (layer-by-layer)
- **Duration:** 3 weeks (Phases 1-5)
- **Internet:** ONLINE required (for power)
- **Access:** Web-based (no download needed)

### Why This Matters
- 🎯 Active job interview preparation (CRITICAL)
- 💼 Multiple ongoing projects needing management
- 📚 Competitive learning phase
- ⏰ All demands competing for attention

---

## 🎯 CORE PROBLEMS TO SOLVE

### Pain Point 1: Task Reminder Failure
- **Problem:** Forget tasks scheduled at specific times
- **Solution:** Smart alerts 30 min, 10 min, and AT task time
- **Implementation:** Browser Notifications + Web Audio API + Service Workers

### Pain Point 2: Status Tracking Gap
- **Problem:** Don't update task completion status
- **Solution:** One-click status updates (□ ◐ ✓ ⏸ ✗)
- **Implementation:** Status dropdown, auto-sync to Calendar

### Pain Point 3: Interview Preparation Anxiety
- **Problem:** No countdown to interview date
- **Solution:** Visual countdown timer with urgency colors
- **Implementation:** Real-time countdown widget on dashboard

### Pain Point 4: Fragmented Task Management
- **Problem:** Tasks scattered across multiple tools
- **Solution:** Central dashboard + Google Calendar sync
- **Implementation:** Bidirectional sync every 5 minutes

### Pain Point 5: No Daily Progress Visibility
- **Problem:** Unclear what was accomplished
- **Solution:** Daily progress analytics with charts
- **Implementation:** Recharts visualization + real-time updates

---

## 📋 FEATURES SPECIFICATION

### Feature 1: Dashboard 📊
**Status:** 🔴 Not Started  
**Phase:** 3  
**Task:** 3.1, 3.2, 3.3, 3.4  

**What it does:**
- Central hub showing all tasks grouped by priority
- Color-coded: 🔴 URGENT, 🟡 HIGH, 🟢 MEDIUM
- Shows time until each task
- Click to expand task details
- Filter by category, status, priority
- Search by title

**Success Criteria:**
- Loads in < 2 seconds
- Displays 10+ tasks without lag
- Real-time sync with Firebase

**Dependencies:**
- Firebase Realtime DB
- React components
- Tailwind CSS styling

---

### Feature 2: Smart Alerts 🔔
**Status:** 🔴 Not Started  
**Phase:** 4  
**Task:** 4.1, 4.2  

**What it does:**
- Progressive alerts: 30 min, 10 min, AT time (for urgent)
- Different sounds per task type
- Browser notifications + Web Audio
- Service Worker for background alerts
- Customizable in settings

**Alert Strategy:**
| Category | Priority | Times | Sound |
|----------|----------|-------|-------|
| Interview Prep | URGENT | 30, 10, 0 min | Loud Alarm |
| Work/Projects | HIGH | 15, 5 min | Chime |
| Daily Tasks | MEDIUM | 10 min | Soft Ping |

**Success Criteria:**
- Alerts trigger within ±30 seconds
- Sounds play correctly on all browsers
- Can customize each alert type
- Works when app closed (Service Worker)

**Dependencies:**
- Browser Notifications API
- Web Audio API
- Service Workers
- Backend scheduler (node-cron)

---

### Feature 3: Interview Countdown ⏱️
**Status:** 🔴 Not Started  
**Phase:** 4  
**Task:** 4.3  

**What it does:**
- Real-time countdown to interview date
- Shows: Days, Hours, Minutes remaining
- Color changes: Green → Yellow → Red as deadline approaches
- Animated when < 24 hours
- Shows interview type (phone, coding, onsite, etc.)
- Milestone tracking

**Display Example:**
```
🎯 INTERVIEW COUNTDOWN
Interview Date: April 2, 2026
Time: 10:00 AM EST

Days: 15
Hours: 6 (Today)
Minutes: 45

Status: ⏳ Approaching
Urgency: HIGH 🔴

Milestones:
✓ Resume submitted
◐ Phone screen done
□ On-site scheduled
```

**Success Criteria:**
- Updates every minute
- Color changes work correctly
- Animation smooth on mobile
- Syncs with Calendar events

**Dependencies:**
- Firebase tasks collection
- Real-time listeners
- Tailwind CSS animations

---

### Feature 4: Status Tracking ✅
**Status:** 🔴 Not Started  
**Phase:** 3  
**Task:** 3.4  

**What it does:**
- Mark task progress: □ ◐ ✓ ⏸ ✗
- One-click status updates
- Auto-updates Google Calendar
- Time spent tracking
- Status history
- Syncs across devices

**Status Meanings:**
- **□ Not Started:** Task waiting to begin
- **◐ In Progress:** Currently working on it
- **✓ Completed:** Task finished
- **⏸ Paused:** Temporarily stopped
- **✗ Cancelled:** No longer needed

**Success Criteria:**
- Status changes sync to Firebase instantly
- Google Calendar updates automatically
- Time tracking accurate
- History shows all changes with timestamps

**Dependencies:**
- Firebase updates
- Google Calendar API
- Real-time listeners

---

### Feature 5: Daily Progress 📈
**Status:** 🔴 Not Started  
**Phase:** 4  
**Task:** 4.4  

**What it does:**
- Real-time completion percentage
- Breakdown by category
- Progress charts (Recharts)
- Time spent today
- On-time vs late tasks
- Productivity streak
- Weekly/monthly trends

**Metrics Tracked:**
- Total completed / remaining
- Completion by category
- Time spent per task
- Tasks on schedule
- Productivity score (0-100)
- Consecutive days on track

**Success Criteria:**
- Updates instantly as tasks complete
- Charts render smoothly
- Data persists daily
- Mobile-friendly visualization

**Dependencies:**
- Recharts library
- Backend metrics service
- Firebase Realtime DB

---

### Feature 6: Settings Panel ⚙️
**Status:** 🔴 Not Started  
**Phase:** 5  
**Task:** 5.0 (custom)  

**What it does:**
- Alert preferences (enable/disable, timing)
- Sound selection per category
- Silent hours configuration
- Google Calendar connection
- Theme (light/dark)
- Timezone, date format
- Data export/backup

**Settings Categories:**
1. Alert Preferences - timing, enable/disable
2. Sound Selection - choose sound per type
3. Time & Scheduling - silent hours, working days
4. Google Calendar - connected status, sync interval
5. Display - theme, timezone, format
6. Data Management - export, backup, clear

**Success Criteria:**
- All settings persist
- Changes apply immediately
- Respected by all features
- Sync with Firebase

**Dependencies:**
- Firebase user document
- React context for settings
- Audio files for sounds

---

## 🏗️ TECHNICAL ARCHITECTURE

### Technology Choices

| Component | Technology | Why |
|-----------|-----------|-----|
| Frontend | React 18+ | Smooth mobile, fast re-renders |
| Styling | Tailwind CSS | Rapid UI, responsive by default |
| Backend | Node.js + Express | JavaScript full-stack, Calendar API easy |
| Database | Firebase Realtime DB | Real-time sync, auto-scaling |
| Hosting | Vercel | Deploy React + Node easily, FREE |
| Calendar | Google Calendar API | Direct integration with existing calendar |
| Notifications | Browser APIs | Cross-browser, mobile support |
| Audio | Web Audio API | Custom sounds, full control |
| Charts | Recharts | Beautiful, responsive React charts |

### Architecture Diagram

```
┌─────────────────────────────────────────┐
│         YOUR DEVICES                    │
│  ┌──────────────┐  ┌──────────────┐   │
│  │ Phone Browser│  │ Desktop      │   │
│  │              │  │ Browser      │   │
│  └──────┬───────┘  └──────┬───────┘   │
│         │                 │            │
└─────────┼─────────────────┼────────────┘
          │                 │ HTTPS
          └────────┬────────┘
                   ↓
        ┌──────────────────────┐
        │ Vercel - Frontend    │
        │ (React App)          │
        └──────────┬───────────┘
                   │ API Calls
                   ↓
        ┌──────────────────────┐
        │ Vercel - Backend     │
        │ (Node.js + Express)  │
        └──────────┬───────────┘
                   │
        ┌──────────┴──────────┐
        ↓                     ↓
    Firebase            Google Calendar
    (Database)          (Events/Sync)
```

### Data Flow Examples

**Creating a Task:**
```
User Input (App)
  ↓
React Component Update
  ↓
API Call to Backend
  ↓
Backend Validation
  ↓
Firebase Save
  ↓
Google Calendar Create Event
  ↓
Real-time Sync to All Devices ✓
```

**Alert Triggered:**
```
Backend Scheduler (Every 1 min)
  ↓
Check Firebase for Due Tasks
  ↓
Find Match (time = now)
  ↓
Send Notification via WebSocket
  ↓
Browser Receives + Plays Sound
  ↓
Display Alert UI + Vibration ✓
```

**Status Updated:**
```
User Clicks "Complete"
  ↓
React UI Updates Instantly
  ↓
API Call to Backend
  ↓
Firebase Task Updated
  ↓
Google Calendar Event Updated
  ↓
Daily Metrics Recalculated
  ↓
Progress Widget Refreshes ✓
```

---

## 📊 DATA MODELS

### Firebase Collections

#### Users Collection
```javascript
/users/{userId}
{
  id: string,                    // Firebase Auth UID
  email: string,
  displayName: string,
  createdAt: timestamp,
  googleCalendarId: string,
  settings: object,              // User settings (see below)
  timezone: string,              // e.g., "US/Eastern"
  preferences: object
}
```

#### Tasks Collection
```javascript
/users/{userId}/tasks/{taskId}
{
  id: string,
  userId: string,
  title: string,
  description: string,
  category: "interview" | "work" | "daily",
  priority: "urgent" | "high" | "medium" | "low",
  status: "not_started" | "in_progress" | "completed" | "paused" | "cancelled",
  
  // Timing
  scheduledTime: timestamp,      // When task should start
  dueTime: timestamp,            // Deadline
  estimatedDuration: number,     // Minutes
  
  // Tracking
  createdAt: timestamp,
  updatedAt: timestamp,
  completedAt: timestamp,
  timeSpent: number,             // Seconds
  
  // Alerts
  alertEnabled: boolean,
  alertTimes: [30, 10, 0],       // Minutes before
  soundProfile: "alarm" | "chime" | "notification",
  
  // Google Calendar
  googleCalendarEventId: string,
  synced: boolean,
  syncedAt: timestamp,
  
  // Interview Specific
  interviewDate: timestamp,
  interviewType: string,
  
  // Metadata
  tags: [string],
  notes: string
}
```

#### Daily Metrics Collection
```javascript
/users/{userId}/metrics/{date}
{
  date: string,                  // YYYY-MM-DD
  userId: string,
  totalTasks: number,
  completedTasks: number,
  inProgressTasks: number,
  pendingTasks: number,
  byCategory: {
    interview: { total: 4, completed: 1 },
    work: { total: 3, completed: 1 },
    daily: { total: 2, completed: 1 }
  },
  totalTimeSpent: number,        // Seconds
  onTimePercentage: number,
  completionPercentage: number,
  productivityScore: number,     // 0-100
  consecutiveDaysOnTrack: number,
  recordedAt: timestamp
}
```

#### Settings Document
```javascript
/users/{userId}/settings
{
  userId: string,
  alerts: {
    interview: { enabled: true, times: [30, 10, 0], sound: "alarm", vibration: true },
    work: { enabled: true, times: [15, 5], sound: "chime", vibration: false },
    daily: { enabled: true, times: [10], sound: "notification", vibration: false }
  },
  silentHours: { start: "21:00", end: "08:00" },
  theme: "dark" | "light",
  timezone: "US/Eastern",
  calendar: {
    connected: boolean,
    accountEmail: string,
    syncInterval: 300            // Seconds
  },
  updatedAt: timestamp
}
```

---

## 📅 DEVELOPMENT TIMELINE & TASKS

### Phase 1: Project Setup (Days 1-2) ✅ COMPLETE
**Goal:** Foundation - folders, configs, credentials

**Tasks:**
- [x] **Task 1.1** - Create project folder structure + package.json
- [x] **Task 1.2** - Setup Firebase config files
- [x] **Task 1.3** - Setup Google OAuth 2.0
- [x] **Task 1.4** - Create .env files with instructions
- [x] **Task 1.5** - Verify all configs work

**Deliverable:** Project structure ready, all configs in place  
**Testing:** `npm install` works, configs verified  
**Success:** Can connect to Firebase and Google APIs

---

### Phase 2: Backend Setup (Days 3-4) ✅ COMPLETE
**Goal:** API - database connection, CRUD endpoints, Google sync

**Tasks:**
- [x] **Task 2.1** - Create Express server scaffold + Socket.IO
- [x] **Task 2.2** - Firebase Realtime DB connection + db helpers
- [x] **Task 2.3** - Task CRUD endpoints (Create, Read, Update, Delete)
- [x] **Task 2.4** - Google Calendar sync route (bidirectional)
- [x] **Task 2.5** - Settings + metrics endpoints, all routes wired

**Deliverable:** Working API with all task operations  
**Testing:** Postman tests for all endpoints  
**Success:** Backend can handle CRUD + Calendar sync

---

### Phase 3: Frontend Dashboard (Days 5-7) ✅ COMPLETE
**Goal:** UI - display tasks, filter, track status

**Tasks:**
- [ ] **Task 3.1** - React app structure + Tailwind setup
- [ ] **Task 3.2** - Dashboard component (main view)
- [ ] **Task 3.3** - Task display + filtering
- [ ] **Task 3.4** - Status tracking UI
- [ ] **Task 3.5** - Connect frontend to backend API

**Deliverable:** Working dashboard displaying tasks  
**Testing:** Manual testing of all UI interactions  
**Success:** Dashboard syncs with backend in real-time

---

### Phase 4: Smart Features (Days 8-10) ✅ UPCOMING
**Goal:** Features - alerts, countdown, analytics, settings

**Tasks:**
- [ ] **Task 4.1** - Alert scheduling system
- [ ] **Task 4.2** - Sound integration + audio files
- [ ] **Task 4.3** - Interview countdown widget
- [ ] **Task 4.4** - Progress analytics + charts
- [ ] **Task 4.5** - Settings panel with all options

**Deliverable:** All smart features working  
**Testing:** Test each feature independently  
**Success:** Alerts trigger, sounds play, countdown updates

---

### Phase 5: Polish & Deploy (Days 11-14) ✅ UPCOMING
**Goal:** Production - responsive, tested, deployed

**Tasks:**
- [ ] **Task 5.1** - Mobile responsive design
- [ ] **Task 5.2** - Dark/light mode support
- [ ] **Task 5.3** - Error handling + edge cases
- [ ] **Task 5.4** - Final QA testing
- [ ] **Task 5.5** - Deploy to Vercel

**Deliverable:** Production-ready app deployed  
**Testing:** Full end-to-end testing  
**Success:** App live on Vercel, all features working

---

## ✅ TASK TRACKER

### Phase 1: Project Setup
```
[✓] Task 1.1 - Create folder structure          Date: Mar 19, 2026
     Commit: "Task 1.1-1.5: Phase 1 - Project Setup Complete"
     Notes: frontend/ + backend/ scaffolding, CRA + Tailwind + Firebase + Express

[✓] Task 1.2 - Firebase config                  Date: Mar 19, 2026
     Commit: "Task 1.1-1.5: Phase 1 - Project Setup Complete"
     Notes: Client SDK (frontend) + Admin SDK dual-strategy (backend)

[✓] Task 1.3 - Google OAuth                     Date: Mar 19, 2026
     Commit: "Task 1.1-1.5: Phase 1 - Project Setup Complete"
     Notes: OAuth2 client with offline access + prompt:consent for refresh tokens

[✓] Task 1.4 - Environment files                Date: Mar 19, 2026
     Commit: "Task 1.1-1.5: Phase 1 - Project Setup Complete"
     Notes: .env.example files with setup instructions for both frontend/backend

[✓] Task 1.5 - Verify configs                   Date: Mar 19, 2026
     Commit: "Task 1.1-1.5: Phase 1 - Project Setup Complete"
     Notes: Health check passes, frontend builds successfully

Phase 1 Complete: 5 / 5 (Date: Mar 19, 2026)
```

### Phase 2: Backend Setup
```
[✓] Task 2.1 - Express server + Socket.IO       Date: Mar 19, 2026
     Commit: "Task 2.1-2.5: Phase 2 - Backend API Complete"
     Notes: app.js (Express) + server.js (HTTP + Socket.IO) separated for testability

[✓] Task 2.2 - Firebase DB service              Date: Mar 19, 2026
     Commit: "Task 2.1-2.5: Phase 2 - Backend API Complete"
     Notes: db/firebaseDb.js - full CRUD helpers + settings + daily metrics

[✓] Task 2.3 - CRUD endpoints                   Date: Mar 19, 2026
     Commit: "Task 2.1-2.5: Phase 2 - Backend API Complete"
     Notes: POST/GET/PATCH/DELETE /api/tasks with filtering + auto metrics recalc

[✓] Task 2.4 - Calendar sync                    Date: Mar 19, 2026
     Commit: "Task 2.1-2.5: Phase 2 - Backend API Complete"
     Notes: Bidirectional - push tasks→Calendar, pull Calendar→tasks

[✓] Task 2.5 - Settings + metrics + wire up     Date: Mar 19, 2026
     Commit: "Task 2.1-2.5: Phase 2 - Backend API Complete"
     Notes: /api/settings, /api/settings/metrics, all routes active in app.js

Phase 2 Complete: 5 / 5 (Date: Mar 19, 2026)
```

### Phase 3: Frontend Dashboard
```
[✓] Task 3.1 - React structure                   Date: Mar 19, 2026
     Commit: "Task 3.1-3.5: Phase 3 - Frontend Dashboard Complete"
     Notes: API service layer (api.js, taskService.js, settingsService.js) + TaskContext

[✓] Task 3.2 - Dashboard component               Date: Mar 19, 2026
     Commit: "Task 3.1-3.5: Phase 3 - Frontend Dashboard Complete"
     Notes: Dashboard.jsx with Sidebar, 3 priority sections (URGENT/HIGH/MEDIUM+LOW)

[✓] Task 3.3 - Task display + filtering          Date: Mar 19, 2026
     Commit: "Task 3.1-3.5: Phase 3 - Frontend Dashboard Complete"
     Notes: TaskCard.jsx, TaskList.jsx, FilterBar.jsx (search + category/status/priority selects)

[✓] Task 3.4 - Status tracking                   Date: Mar 19, 2026
     Commit: "Task 3.1-3.5: Phase 3 - Frontend Dashboard Complete"
     Notes: StatusBadge.jsx - one-click cycling □→◐→✓→⏸→✗, dark-themed color per status

[✓] Task 3.5 - Connect to backend                Date: Mar 19, 2026
     Commit: "Task 3.1-3.5: Phase 3 - Frontend Dashboard Complete"
     Notes: TaskContext auto-fetches on filter changes, AddTaskModal, x-user-id header auth

Phase 3 Complete: 5 / 5 (Date: Mar 19, 2026)
```

### Phase 4: Smart Features
```
[  ] Task 4.1 - Alert system                     Days: __ Time: __
     Commit: "Task 4.1: Alert system"
     Notes:
     
[  ] Task 4.2 - Sound integration                Days: __ Time: __
     Commit: "Task 4.2: Sound integration"
     Notes:
     
[  ] Task 4.3 - Interview countdown              Days: __ Time: __
     Commit: "Task 4.3: Interview countdown"
     Notes:
     
[  ] Task 4.4 - Progress analytics               Days: __ Time: __
     Commit: "Task 4.4: Progress analytics"
     Notes:
     
[  ] Task 4.5 - Settings panel                   Days: __ Time: __
     Commit: "Task 4.5: Settings panel"
     Notes:
     
Phase 4 Complete: __ / __ (Date: _______)
```

### Phase 5: Polish & Deploy
```
[  ] Task 5.1 - Mobile responsive                Days: __ Time: __
     Commit: "Task 5.1: Mobile responsive"
     Notes:
     
[  ] Task 5.2 - Dark/light mode                  Days: __ Time: __
     Commit: "Task 5.2: Theme support"
     Notes:
     
[  ] Task 5.3 - Error handling                   Days: __ Time: __
     Commit: "Task 5.3: Error handling"
     Notes:
     
[  ] Task 5.4 - Final testing                    Days: __ Time: __
     Commit: "Task 5.4: Final testing"
     Notes:
     
[  ] Task 5.5 - Deploy to Vercel                 Days: __ Time: __
     Commit: "Task 5.5: Deploy to Vercel"
     Notes:
     
Phase 5 Complete: __ / __ (Date: _______)
```

---

## 🔧 CURRENT STATUS

### What's Done
- ✅ Phase 1: Full project scaffold (frontend + backend folders, configs, .env templates)
- ✅ Phase 1: Firebase client SDK + Admin SDK configured
- ✅ Phase 1: Google OAuth2 with offline access + refresh token support
- ✅ Phase 2: Express API with Socket.IO (server.js + app.js)
- ✅ Phase 2: Firebase Realtime DB service (CRUD helpers, settings, metrics)
- ✅ Phase 2: Task CRUD endpoints with filtering (category/status/priority/search)
- ✅ Phase 2: Bidirectional Google Calendar sync service
- ✅ Phase 2: Settings + daily metrics endpoints
- ✅ README.md with full setup commands and API docs
- ✅ Deployed to GitHub: https://github.com/VitalDevAI-Labs/Task-manager-web
- ✅ Phase 3: API service layer (api.js, taskService.js, settingsService.js)
- ✅ Phase 3: TaskContext with auto-fetch on filter changes
- ✅ Phase 3: Dashboard with Sidebar, 3 priority sections, AddTaskModal
- ✅ Phase 3: TaskCard, TaskList, FilterBar, StatusBadge components
- ✅ Phase 3: One-click status cycling (□ ◐ ✓ ⏸ ✗)

### What's Next
- 🟡 Task 4.1: Alert scheduling system (node-cron + Socket.IO)
- 🟡 Task 4.2: Sound integration (Web Audio API + audio files)
- 🟡 Task 4.3: Interview countdown widget
- 🟡 Task 4.4: Progress analytics + Recharts charts
- 🟡 Task 4.5: Settings panel

### Blockers
⚠️ Firebase credentials not yet filled in backend/.env and frontend/.env
   → Required before testing live data flow (Phase 3.5)

### Decisions Made
✅ Use Claude Code CLI (layer-by-layer approach)
✅ React 18 + Node.js + Firebase stack
✅ Vercel for hosting (frontend + backend)
✅ Google Calendar API for sync
✅ 3-week build timeline
✅ Online-first (better features)
✅ Web-based (no download)

---

## 📝 DEVELOPMENT NOTES

### Architecture Decisions
- **Why React?** Smooth mobile experience, fast re-renders, easy Google Calendar integration
- **Why Firebase?** Real-time sync across devices, auto-scaling, no complex setup
- **Why Vercel?** One-command deploy for React + Node, automatic CI/CD, FREE tier
- **Why Web-based?** Accessible from phone + desktop, no install needed, always synced

### Performance Targets
- Dashboard load: < 2 seconds
- Task creation: < 500ms
- Alerts trigger: ±30 seconds accuracy
- Sync complete: < 1 minute
- Mobile 3G: No lag
- Battery: Optimized polling

### Quality Standards
- WCAG AA accessibility
- Cross-browser support (Chrome, Safari, Firefox, Edge)
- Mobile-first responsive design
- Graceful error handling
- 99.9% uptime target
- Firebase auto-backup

---

## 🐛 BUGS & ISSUES

### Known Issues
None yet - project is in planning phase

### Resolved Issues
None yet

### To Investigate
None yet

---

## 📚 REFERENCE DOCUMENTS

### Created Documents
- `TASK_MANAGER_PROJECT_SPEC.md` - Complete specification (35KB)
- `CLAUDE_CODE_SETUP_GUIDE.md` - Setup and workflow guide (12KB)
- `CLAUDE_CODE_QUICK_REFERENCE.md` - Task commands reference (22KB)
- `READY_TO_BUILD.md` - Start here guide (6KB)
- `claude.md` - This brain file (this file)

### Key Sections in Spec
- Technical Architecture - see section 🏗️
- Feature Specifications - see section 📋
- Data Models - see section 📊
- Development Timeline - see section 📅
- API Integration - see spec document
- Future Enhancements - see spec document

---

## 💡 QUICK REFERENCE

### File Structure (After Task 1.1)
```
task-manager-app/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── config/
│   │   ├── utils/
│   │   └── App.jsx
│   ├── public/
│   ├── package.json
│   └── .env
├── backend/
│   ├── routes/
│   ├── services/
│   ├── config/
│   ├── db/
│   ├── middleware/
│   ├── server.js
│   ├── app.js
│   ├── package.json
│   └── .env
├── .gitignore
├── README.md
└── claude.md (this file)
```

### Commands You'll Use Often
```bash
# Start backend
cd backend && npm run dev

# Start frontend
cd frontend && npm start

# Commit after task
git add .
git commit -m "Task X.Y: [Description]"

# Claude Code for next task
claude-code run "Task X.Y: [Copy from CLAUDE_CODE_QUICK_REFERENCE.md]"
```

### Key Firebase Collections
- `/users/{userId}` - User profiles
- `/users/{userId}/tasks/{taskId}` - Tasks
- `/users/{userId}/metrics/{date}` - Daily metrics
- `/users/{userId}/alerts/{alertId}` - Alert logs
- `/users/{userId}/settings` - User settings

### Key API Endpoints
- `POST /api/tasks` - Create task
- `GET /api/tasks` - Get all tasks
- `PATCH /api/tasks/:taskId` - Update task
- `DELETE /api/tasks/:taskId` - Delete task
- `GET /api/calendar/sync` - Sync calendar
- `PATCH /api/settings` - Update settings

---

## 🎯 SUCCESS CHECKLIST

### By End of Phase 1
- [ ] Project structure created
- [ ] All configs in place
- [ ] Firebase connected
- [ ] Google OAuth configured
- [ ] `npm install` works
- [ ] No errors in console

### By End of Phase 2
- [ ] All CRUD endpoints working
- [ ] Calendar sync operational
- [ ] All endpoints tested in Postman
- [ ] Backend runs without errors
- [ ] Database reads/writes successful

### By End of Phase 3
- [ ] Dashboard displays tasks
- [ ] Filtering works
- [ ] Status tracking responsive
- [ ] Real-time sync working
- [ ] No lag on mobile

### By End of Phase 4
- [ ] Alerts trigger on time
- [ ] Sounds play correctly
- [ ] Countdown updates live
- [ ] Progress charts render
- [ ] Settings save/load

### By End of Phase 5
- [ ] Mobile responsive
- [ ] Dark mode works
- [ ] All errors handled
- [ ] Full QA passed
- [ ] **APP DEPLOYED! 🚀**

---

## 📞 WHEN STUCK

### If Task Fails
1. Note the exact error
2. Take screenshot or copy error
3. Tell me: "Task X.Y failed. Error: [error]. Files created: [list them]"
4. I'll fix it with full context

### If Unsure About Next Step
1. Check CLAUDE_CODE_QUICK_REFERENCE.md for task command
2. Copy exact command
3. Run: `claude-code run "[COMMAND]"`
4. Tell me when complete

### If Something Breaks Between Tasks
1. Don't panic - this is expected sometimes
2. Tell me which task broke and what error
3. I'll debug with knowledge of all previous tasks
4. We'll fix and continue

---

## 🎉 PROJECT STATUS SUMMARY

```
┌─────────────────────────────────────────┐
│  TASK MANAGER APP - STATUS DASHBOARD    │
├─────────────────────────────────────────┤
│                                         │
│  Planning:       ✅ COMPLETE           │
│  Documentation:  ✅ COMPLETE           │
│  Phase 1:        ✅ COMPLETE (5/5)     │
│  Phase 2:        ✅ COMPLETE (5/5)     │
│  Phase 3:        ✅ COMPLETE (5/5)     │
│  Phase 4:        🔴 PENDING            │
│  Phase 5:        🔴 PENDING            │
│  Deployment:     🔴 PENDING            │
│                                         │
│  Overall:        📊 60% (15/25 tasks)  │
│                                         │
│  Next: Task 4.1 - Alert System         │
│                                         │
└─────────────────────────────────────────┘
```

---

**This is your project brain. Update it as you progress!** 🧠✨
