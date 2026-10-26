# HealthGuard AI

An AI-powered personal healthcare ecosystem with nine collaborating agents and **AI Early Disease Risk Detection**, which spots unhealthy trends before they become problems.

## What's in this folder
| File | Purpose |
|------|---------|
| `index.html` | Working front-end demo (no build step). Open it in a browser. |
| `requirements.md` | Full functional and non-functional requirements |
| `readme.md` | This guide |
| `tasks.md` | Delivery plan and checklist |

## Try the demo
1. Open `index.html`.
2. On **Dashboard**, save a new reading. Charts, the health score and the agent feed update.
3. Open **Risk detection** to see 14-day trend slopes, flags and a 7-day forecast.
4. Try the **Assistant** (type or use the mic). Typing "chest pain" triggers emergency guidance.
5. Use **Emergency** for SOS with live location, **Medicines** for missed-dose alerts, **Records** for search and PDF export (browser print).
6. Toggle dark mode, high contrast and font size at the top.

The demo keeps data in memory with sample values. The assistant is rule-based; production swaps in an LLM API.

## How early risk detection works
For each metric, the last 14 days get a least-squares slope. A slope above a threshold means *Watch*, above twice the threshold means *Needs attention*. The flag goes to the agent bus: Nutrition, Fitness, Mental Wellness and Appointment agents respond with preventive steps. It is preventive guidance only, not a diagnosis.

## Production architecture
```
React + TS + Tailwind (PWA)  →  Express API (JWT, RBAC, rate limit)  →  MongoDB (encrypted fields)
                                        │
                          Agent orchestrator + event bus  →  LLM API
```
- **Auth:** JWT access/refresh tokens, Google OAuth, roles: patient, doctor, admin.
- **Privacy:** AES-256 field encryption, audit log on every record access, HIPAA-inspired controls.
- **Agents:** Monitoring, Symptom, Medication, Nutrition, Fitness, Appointment, Emergency, Records, Mental Wellness.

## Suggested folder layout
```
/client  (components, hooks, pages, charts)
/server  (routes, controllers, agents, middleware, models)
/shared  (types)
```

## Accessibility
Skip link, keyboard-operable controls, ARIA live regions for chat and SOS, high-contrast theme, adjustable font size, voice input and output, reduced-motion support.

## Medical disclaimer
HealthGuard AI provides general information and is not a medical device or a substitute for professional care. In an emergency, call your local emergency number.
