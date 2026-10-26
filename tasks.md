# HealthGuard AI: Tasks

## Phase 0: Demo (done in `index.html`)
- [x] Glassmorphism UI, dark/light, high contrast, font size controls
- [x] Dashboard with vitals logging, charts, BMI, health score
- [x] AI Early Disease Risk Detection with 7-day forecast and disclaimer
- [x] Assistant with triage, 3 languages, voice in/out
- [x] Medicines, records (search, PDF via print), nutrition, fitness, SOS, appointments, mental health
- [x] Agent activity feed

## Phase 1: Foundation
- [ ] Vite + React + TypeScript + Tailwind project
- [ ] Express API, MongoDB models (User, Vital, Medicine, Record, Appointment, Alert, AuditLog)
- [ ] Docker Compose, ESLint, Prettier, CI pipeline

## Phase 2: Security
- [ ] JWT access/refresh, Google OAuth
- [ ] RBAC middleware (patient, doctor, admin)
- [ ] AES-256 encryption for records and uploads
- [ ] Audit logging, rate limiting, validation (zod), Helmet

## Phase 3: Core features
- [ ] Vitals CRUD and Recharts dashboard
- [ ] Medicine reminders (cron plus push)
- [ ] Records upload, search, PDF export
- [ ] Nutrition, fitness, mental health modules
- [ ] Appointments with calendar sync, telemedicine room

## Phase 4: AI and agents
- [ ] Event bus and agent orchestrator
- [ ] Nine agents with shared memory
- [ ] LLM assistant with safety guardrails and red-flag routing
- [ ] Early Risk Detection service (trend regression, later ML model)
- [ ] Multi-language voice (Web Speech API)

## Phase 5: Emergency
- [ ] SOS with SMS/push to contacts, live location link
- [ ] Emergency history and critical info card

## Phase 6: PWA, admin, quality
- [ ] Service worker, offline cache, background sync, push notifications
- [ ] Admin panel (users, audit logs, analytics)
- [ ] Accessibility audit (axe, screen reader pass)
- [ ] Unit, integration and e2e tests (80%+ core coverage)

## Phase 7: Launch
- [ ] Deploy (Vercel client, Render/Railway API, MongoDB Atlas)
- [ ] Demo video, pitch deck, final README polish
