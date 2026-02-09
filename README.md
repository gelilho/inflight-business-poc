# Vueling Inflight Experience

> **MWC Barcelona 2026**

An AI-powered digital platform that turns every Vueling flight into a personalized journey — content, entertainment, food ordering, transport recommendation and passenger intelligence — from one booking number and from every single passenger

---

## Documents

| Document | Description |
|---|---|
| **[Vision, Business Case & POC](Vueling%20Inflight%20Experience%20-%20Vision%2C%20Business%20Case%20%26%20POC.md)** | The complete document — problem, vision, 11 pillars, passenger journey, food revenue engine, why now, KPIs, architecture, hyperpersonalization, roadmap, POC scope. **Start here. 8 min read.** |
| **[Presentation Deck](DECK.md)** | 14-slide deck to support the pitch |
| **[Visual Deck (PDF)](export/)** | PDF version with clean Vueling-branded slides |

| **[App Screenshots](SCREENSHOTS.md)** | Full-page screenshots of every screen in the POC — passenger flow sequence |

### Supporting Documents (`appendix/`)

| Document | Description |
|---|---|
| [PITCH_SCRIPT.md](appendix/PITCH_SCRIPT.md) | 7-minute spoken pitch script with timed sections + Q&A |
| [ARCHITECTURE.md](appendix/ARCHITECTURE.md) | Deep-dive on technical architecture, cadence, edge caching |
| [HYPERPERSONALIZATION.md](appendix/HYPERPERSONALIZATION.md) | Full vision — VIP for everyone, predictive catering, loyalty |
| [PASSENGER_JOURNEY.md](appendix/PASSENGER_JOURNEY.md) | Detailed trigger flow from T-24h to landing |
| [KPIs.md](appendix/KPIs.md) | Extended metrics framework |

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
