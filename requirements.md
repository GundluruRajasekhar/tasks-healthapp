# HealthGuard AI: Requirements

## 1. Goal
A personal healthcare platform that monitors health, manages records, gives AI wellness insights, tracks fitness, books appointments and responds to emergencies. Its standout feature is **AI Early Disease Risk Detection**.

## 2. Functional requirements
| ID | Module | Requirement |
|----|--------|-------------|
| F1 | AI Assistant | Chat, symptom triage, health education, English/Hindi/Telugu, voice in and out, red-flag escalation |
| F2 | Dashboard | Heart rate, BP, glucose, SpO₂, BMI, weight, interactive charts |
| F3 | Medicines | Reminders, dose tracking, missed-dose alerts, refill notices, adherence advice |
| F4 | Records | Encrypted upload of prescriptions, labs, vaccinations; search; PDF export |
| F5 | Nutrition | Meal plans, calories, water, disease-specific diets |
| F6 | Fitness | Steps, exercise, sleep, goals, badges |
| F7 | SOS | One-click alert, contact notification, live location, critical info, history |
| F8 | Appointments | Scheduling, calendar sync, history, follow-ups, telemedicine |
| F9 | Mental health | Mood log, stress check, meditation, daily check-in, support assistant |
| F10 | Predictive analytics | Risk insights, trends, preventive advice, health score, 7-day forecast |
| F11 | **Early Risk Detection** | 14-day trend regression on BP, glucose, HR, SpO₂, sleep and mood; flags drift before thresholds are crossed; always shows a medical disclaimer |
| F12 | Admin | User management, audit log viewer, analytics, agent health |

## 3. Agentic architecture
Nine agents (Monitoring, Symptom, Medication, Nutrition, Fitness, Appointment, Emergency, Records, Mental Wellness) communicate over an event bus (Redis Streams or Mongo change streams). Example: Monitoring flags rising BP → Nutrition proposes a low-salt plan → Appointment suggests a check-up → Mental Wellness checks stress.

## 4. Non-functional requirements
- **Security:** JWT (short-lived access plus refresh), OAuth (Google), RBAC (patient, doctor, admin), AES-256 field encryption, TLS, audit logs, rate limiting, input validation, HIPAA-inspired privacy.
- **Accessibility:** WCAG 2.2 AA, keyboard navigation, ARIA live regions, high contrast, font scaling, voice, reduced motion.
- **Performance:** LCP under 2.5 s on 4G, API p95 under 300 ms.
- **PWA:** installable, offline cache, background sync, push notifications.
- **Quality:** unit, integration and e2e tests; at least 80% coverage on core logic.

## 5. Tech stack
React, TypeScript, Tailwind CSS, Recharts, Node.js, Express, MongoDB, LLM API, Docker, GitHub Actions.

## 6. Safety and compliance
Not a diagnostic device. Every AI health output carries a disclaimer. Red-flag symptoms always route to emergency guidance. Users can export or delete their data.
