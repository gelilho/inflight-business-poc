# Vueling Inflight Experience

> **MWC Barcelona 2026**

An AI-powered digital platform that turns every Vueling flight into a personalized journey — content, entertainment, food ordering, transport recommendation and passenger intelligence — from one booking number and from every single passenger

---

## Documents

| Document | Description |
|---|---|
| **[Business Case PRD](Business%20Case%20PRD%20-%20Inflight%20Vueling%20Experience.md)** | The complete project document — vision, 11 pillars, passenger journey, food revenue engine, KPIs, architecture, hyperpersonalization, roadmap. **Start here.** |
| **[One Pager](One%20Pager%20-%20Inflight%20Vueling%20Experience.md)** | Solution Description Brief — problem, solution, how it works, why now, what it enables. Aligned for Product, Engineering, Design, Data, and Leadership. |
| **[Presentation Deck](DECK.md)** | Presentation deck — 14 slides to support the pitch |
| **[Visual Deck](Visual%20Deck%20-%20Inflight%20Vueling%20Experience.md)** | Visual presentation deck — 14 slides with rich ASCII art diagrams, box visuals, and data visualizations |

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
