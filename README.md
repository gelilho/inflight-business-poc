# Vueling Inflight Experience — Business Documentation

> **MWC Barcelona 2026**

This repository contains all business documentation, pitch materials, and strategic vision for the Vueling Inflight Experience — an AI-powered digital platform that transforms every flight into a personalized journey.

---

## Documents

| Document | What It Covers |
|---|---|
| [ONE_PAGER.md](ONE_PAGER.md) | Executive summary — vision, pillars, benefits, KPIs, technical overview |
| [PITCH_DECK.md](PITCH_DECK.md) | Presentation deck — 14 slides ready for Keynote/PowerPoint |
| [PITCH_SCRIPT.md](PITCH_SCRIPT.md) | 7-minute spoken pitch with timed sections + Q&A prep |
| [ARCHITECTURE.md](ARCHITECTURE.md) | System architecture — how both projects connect, content cadence, offline strategy |
| [PASSENGER_JOURNEY.md](PASSENGER_JOURNEY.md) | Complete trigger flow from T-24h to landing |
| [HYPERPERSONALIZATION.md](HYPERPERSONALIZATION.md) | Future vision — how we learn from passengers and treat everyone like a VIP |
| [KPIs.md](KPIs.md) | Metrics framework — engagement, revenue, satisfaction, operations |

---

## Related Repositories

| Repo | What It Is |
|---|---|
| [inflight-poc](../inflight-poc) | Backend API — Python / FastAPI / Gemini AI |
| [inflight-ui-poc](../inflight-ui-poc) | Frontend UI — React / Vite / TypeScript |

---

## Architecture at a Glance

```
┌──────────────────────┐         ┌──────────────────────────┐
│   inflight-ui-poc    │  HTTP   │     inflight-poc          │
│   React + Vite       │ ──────→ │     FastAPI + Gemini      │
│   :3000              │         │     :8000                  │
└──────────────────────┘         └──────────────────────────┘
        │                                   │
        │ fallback-data.ts                  ├── Gemini 2.5 Flash (AI content)
        │ (pre-cached data)                 ├── OpenWeatherMap (weather)
        └── demo never breaks               └── NewsAPI (news)
```

---

**Status:** POC Complete — Ready for MWC Demo
**Date:** February 2026
