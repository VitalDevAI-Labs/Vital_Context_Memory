# Quick Reference

> Cheat sheet for common commands, environment setup, and key lookups. Agents read this to run the project without asking how.

---

## File Structure

```
project-root/
├── .vital_context/       # Project documentation (this folder)
├── [src/frontend/app]/   # Application source code
│   ├── components/       # UI components
│   ├── services/         # API calls, business logic
│   ├── [store/state]/    # State management
│   ├── types/            # Type definitions
│   └── utils/            # Helpers
├── [backend/server]/     # Backend source (if separate)
│   ├── routes/           # API routes
│   ├── services/         # Business logic
│   ├── db/               # Database helpers
│   └── middleware/        # Auth, validation, etc.
├── .env                  # Environment variables (not committed)
├── package.json
└── README.md
```

Replace brackets with your actual structure.

---

## Common Commands

```bash
# Development
[npm run dev]             # Start dev server
[npm start]               # Start frontend
[cd backend && npm run dev]  # Start backend

# Testing
[npm test]                # Run tests
[npm run lint]            # Lint code

# Build & Deploy
[npm run build]           # Production build
[npm run deploy]          # Deploy (if configured)

# Database
[npx prisma migrate dev]  # Run migrations (if applicable)
```

---

## Environment Variables

| Variable | Where | Purpose | Example |
|----------|-------|---------|---------|
| `[API_KEY]` | `.env` | `[Service authentication]` | `sk-...` |
| `[DATABASE_URL]` | `.env` | `[Database connection]` | `postgres://...` |
| `[GOOGLE_CLIENT_ID]` | `.env` | `[OAuth]` | `123...apps.googleusercontent.com` |

List every required env var. Note which are required vs optional.

---

## Key API Endpoints (Quick Lookup)

| Endpoint | What it does |
|----------|-------------|
| `POST /api/[resource]` | Create |
| `GET /api/[resource]` | List |
| `PATCH /api/[resource]/:id` | Update |
| `DELETE /api/[resource]/:id` | Delete |

Full details + schemas in [architecture.md](architecture.md).

---

## Key Collections / Tables

| Name | Purpose | Primary Key |
|------|---------|-------------|
| `[users]` | User profiles | `userId` |
| `[tasks]` | Core records | `taskId` |
| `[settings]` | User preferences | `userId` |

Full schemas in [architecture.md](architecture.md).
