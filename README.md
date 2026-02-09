# Vueling Inflight Experience

> **MWC Barcelona 2026**

An AI-powered digital platform that turns every Vueling flight into a personalized journey — content, entertainment, food ordering, and passenger intelligence — from one booking number.

---

## Documents

| Document | Description |
|---|---|
| **[PRD.md](PRD.md)** | The complete project document — vision, 11 pillars, passenger journey, food revenue engine, KPIs, architecture, hyperpersonalization, roadmap. **Start here.** |
| **[DECK.md](DECK.md)** | Presentation deck — 14 slides to support the pitch |

### Supporting Documents (`appendix/`)

| Document | Description |
|---|---|
| [PITCH_SCRIPT.md](appendix/PITCH_SCRIPT.md) | 7-minute spoken pitch script with timed sections + Q&A |
| [ARCHITECTURE.md](appendix/ARCHITECTURE.md) | Deep-dive on technical architecture, cadence, edge caching |
| [HYPERPERSONALIZATION.md](appendix/HYPERPERSONALIZATION.md) | Full vision — VIP for everyone, predictive catering, loyalty |
| [PASSENGER_JOURNEY.md](appendix/PASSENGER_JOURNEY.md) | Detailed trigger flow from T-24h to landing |
| [KPIs.md](appendix/KPIs.md) | Extended metrics framework |
| [ONE_PAGER.md](appendix/ONE_PAGER.md) | Earlier one-pager (superseded by PRD) |

---

## Architecture

```
┌──────────────────────┐         ┌──────────────────────────┐
│   inflight-ui-poc    │  HTTP   │     inflight-poc          │
│   React + Vite       │ ──────→ │     FastAPI + Gemini      │
│   :3000              │         │     :8000                  │
└──────────────────────┘         └──────────────────────────┘
        │                                   │
        │ fallback-data.ts                  └── Gemini 2.5 Flash
        │ (demo never breaks)                   (single AI engine: highlights,
        └───────────────────                     restaurants, weather, news,
                                                 transport, translations)
```

---

## Related Repositories

| Repo | What |
|---|---|
| [inflight-poc](../inflight-poc) | Backend API — Python / FastAPI / Gemini AI |
| [inflight-ui-poc](../inflight-ui-poc) | Frontend UI — React / Vite / TypeScript |

---

**Status:** POC Complete — Ready for Demo
