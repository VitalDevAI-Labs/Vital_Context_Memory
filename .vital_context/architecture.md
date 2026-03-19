# Technical Architecture

> The technical brain of the project. Agents read this to understand how the system is built, what schemas exist, and why key decisions were made.

---

## Stack

| Layer | Technology | Version | Why |
|-------|-----------|---------|-----|
| Frontend | `[e.g., React 18]` | `[version]` | `[rationale]` |
| Styling | `[e.g., Tailwind CSS]` | | `[rationale]` |
| Backend | `[e.g., Node.js + Express]` | | `[rationale]` |
| Database | `[e.g., Firebase Realtime DB]` | | `[rationale]` |
| Auth | `[e.g., Firebase Auth]` | | `[rationale]` |
| Hosting | `[e.g., Vercel]` | | `[rationale]` |
| APIs | `[e.g., Google Calendar API]` | | `[rationale]` |

---

## Architecture Diagram

```
┌─────────────────────────────┐
│        Client Devices       │
│  (Browser / Mobile / PWA)   │
└─────────────┬───────────────┘
              │ HTTPS
              ▼
┌─────────────────────────────┐
│     Frontend (Hosting)      │
│     [Framework + UI]        │
└─────────────┬───────────────┘
              │ API Calls
              ▼
┌─────────────────────────────┐
│     Backend (API Server)    │
│     [Runtime + Framework]   │
└──────┬──────────────┬───────┘
       │              │
       ▼              ▼
  ┌──────────┐  ┌──────────────┐
  │ Database │  │ External APIs│
  │          │  │ (Calendar,   │
  │          │  │  Auth, etc.) │
  └──────────┘  └──────────────┘
```

Replace with your actual architecture. Keep it ASCII for portability.

---

## Data Models

Define every collection/table the system uses. Agents use this to write correct queries and avoid schema mismatches.

### `[Collection/Table 1]` — `[purpose]`
```
{
  id: string,               // primary key
  field1: string,           // description
  field2: number,           // description
  field3: timestamp,        // description
  nested: {
    subfield: string        // description
  },
  createdAt: timestamp,
  updatedAt: timestamp
}
```

### `[Collection/Table 2]` — `[purpose]`
```
{
  id: string,
  field1: string,
  field2: boolean
}
```

Add one block per collection/table. Include field types and brief descriptions.

---

## Data Flows

Document key user actions as step sequences so agents understand the full pipeline.

### Flow: `[e.g., Create a Record]`
```
User Input → Frontend Validation → API Call → Backend Validation
→ Database Write → External API Sync → Real-time Update to Client
```

### Flow: `[e.g., Alert Triggered]`
```
Scheduler Check → Query Due Items → Match Found
→ Send Notification → Play Sound → Display UI Alert
```

Add flows for every critical path in your app.

---

## API Endpoints

| Method | Route | Purpose | Auth |
|--------|-------|---------|------|
| POST | `/api/[resource]` | Create | Yes |
| GET | `/api/[resource]` | List (with filters) | Yes |
| GET | `/api/[resource]/:id` | Get one | Yes |
| PATCH | `/api/[resource]/:id` | Update | Yes |
| DELETE | `/api/[resource]/:id` | Delete | Yes |

Add query params, request/response shapes if complex.

---

## Key Decisions

Document architectural choices so agents don't re-debate them or make conflicting choices.

| # | Decision | Chose | Over | Why |
|---|----------|-------|------|-----|
| 1 | `[e.g., State management]` | `[Zustand]` | `[Redux, Context]` | `[Less boilerplate, fits project scale]` |
| 2 | `[e.g., Database]` | `[Firebase]` | `[Postgres, Supabase]` | `[Real-time sync, no server needed]` |
| 3 | `[e.g., Hosting]` | `[Vercel]` | `[Netlify, AWS]` | `[Free tier, easy deploy]` |

Add decisions as they're made. This is the living decisions log.

---

## Constraints & Limitations

- `[e.g., Firebase free tier: 100 concurrent connections]`
- `[e.g., Google Calendar API: 1M queries/day]`
- `[e.g., Browser notifications require HTTPS]`
- `[e.g., Service workers don't work in Safari private browsing]`

Document anything that constrains implementation choices.
