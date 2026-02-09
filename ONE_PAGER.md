# Vueling Inflight Experience — One Pager

> **In brief:** An AI-powered digital platform that transforms every Vueling flight into a personalized journey. Pre-order your meal the day before. Discover your destination at 35,000 feet. Listen to curated music. Read the digital evolution of the beloved Ling magazine. Search Vueling's FAQ without leaving the experience. One booking number. One seamless experience. A platform that delights passengers, drives ancillary revenue, and positions Vueling as the most innovative low-cost carrier in Europe.

---

## The Vision

**Transform every Vueling flight into a personalized, immersive digital journey** — from the moment a passenger checks in to the moment they land.

Not just a destination guide. A complete inflight ecosystem: food pre-ordering, curated content, live entertainment, real-time flight tracking, a digital magazine, personalized music, and self-service FAQ — all powered by AI, all from one booking number.

---

## The Problem

- Passengers sit idle for 1-3 hours with zero engagement
- No personalized content or entertainment beyond what they bring
- Food service is reactive — most passengers skip food purchases simply because the current ordering experience isn't convenient enough
- No connection between the airline and the passenger's destination
- When passengers need help, they can't easily find answers to common questions
- Competitors are investing in digital — Vueling risks falling behind

---

## The Solution: Vueling Inflight Experience

A single, unified digital experience delivered via the Vueling app and inflight WiFi portal.

### What the Passenger Gets

| Experience Pillar | What It Delivers |
|---|---|
| **Food & Snacks** | Browse the onboard menu, pre-order before the flight, order during the flight — delivered to your seat. No queues, no waiting. |
| **Your Aircraft** | Aircraft model, name ("Spirit of Barcelona"), registration, age — make flying personal and transparent |
| **Your Crew** | Captain and cabin crew names — humanize the experience, passengers feel they're in good hands |
| **Live Flight Tracker** | Real-time aircraft position on a map, altitude, speed, time to destination — see exactly where you are |
| **Discover Your Destination** | Top 5 highlights, 3 restaurant picks — AI-generated, in their language |
| **Getting to the City** | Airport-to-city transport options (train, bus, taxi) with times, costs, and practical tips — plus the option to book your transfer online |
| **Peace of Mind** | Emergency contacts (police, hospital, taxi) and Vueling helpline always at hand — because feeling safe matters |
| **Weather & News** | 3-day forecast + curated local news (sports, culture, events — inflight-safe) |
| **Music & Audio** | AI-curated playlists personalized per destination — local artists, mix of decades, chill vibes. Discover the soundtrack of Rome before you land |
| **Digital Magazine** | Curated articles about destination, travel tips, Vueling stories — bringing back the spirit of the beloved Ling magazine, now in digital form |
| **FAQ & Help** | Searchable Vueling FAQ — baggage rules, check-in times, loyalty program, rebooking — answers at your fingertips without calling anyone |

---

## The Food & Snacks Revenue Engine

This is the **monetization vertical** that pays for the entire platform.

### Three Moments to Capture a Sale

1. **Day before the flight** — Push notification: "Flying to Rome tomorrow? Pre-order your onboard menu"
2. **After check-in / security** — Second push: "2 hours to go! Want a snack bag ready for boarding?"
3. **Onboard, after takeoff** — Digital menu, tap to order, pay in-app. Crew delivers to your seat.

### Why This Changes Everything

- **No friction**: Order from your phone — no flagging down crew
- **Pre-orders = guaranteed revenue**: Captured before the plane departs
- **Higher basket size**: Digital menus with photos increase avg. order value by 20-40%
- **Crew efficiency**: Pre-orders prepared in advance, less aisle time
- **Smarter catering**: Pre-orders become a demand signal — know what to load, reduce waste

---

## Key Benefits

| For Passengers | For Vueling |
|---|---|
| Pre-order food — it's waiting for them | New ancillary revenue stream (food pre-orders) |
| Rich destination content before landing | Higher NPS and brand loyalty |
| Entertainment (music, magazine, news) | Competitive differentiator vs every LCC |
| Self-service FAQ — answers instantly | Reduced call center volume |
| Real-time flight info — feel in control | Cabin crew operational efficiency |
| Personalized in 6 languages | Scalable to entire route network via AI |
| Emergency contacts always accessible | Data-driven passenger insights |
| Offline-ready — works without connectivity | Reduced paper waste (no physical magazine) |

---

## KPIs We Will Measure

| Category | Metric | Target |
|---|---|---|
| **Engagement** | % passengers using the experience | >25% in 6 months |
| **Engagement** | Avg. time spent in experience | >12 minutes per flight |
| **Engagement** | Content sections explored per session | >3 sections |
| **Revenue** | Food pre-order conversion rate | >8% of passengers |
| **Revenue** | Avg. order value (digital menu) | +30% vs. aisle service |
| **Revenue** | Incremental ancillary revenue per flight | Measured quarterly |
| **Satisfaction** | NPS lift (experience users vs. non-users) | +5 points |
| **Satisfaction** | Inflight satisfaction survey score | >4.2 / 5.0 |
| **Operational** | Cabin crew service time reduction | -15% per flight |
| **Operational** | Food waste reduction (pre-order accuracy) | -20% |
| **Sustainability** | Catering demand forecasting accuracy | >85% accuracy |
| **Sustainability** | Paper magazine elimination | 100% digital by Phase 1 |

---

## Technical Solution — How It Works

The platform is built on an **offline-first, pre-computed architecture**.

### Content Generation (Scheduled, Not On-Demand)

| Content | Refresh Cadence | Source |
|---|---|---|
| Destination highlights, restaurants, transport | Every **2 weeks** | Google Gemini AI |
| Flight details (crew, aircraft) | **Daily** (when crew/aircraft allocated) | Airline ops systems |
| Weather forecast | Every **12 hours** | OpenWeatherMap API |
| Local news | Every **6 hours** (filtered for safety) | NewsAPI.org + AI |
| Music playlists | **Weekly** per destination | AI Curation Engine |
| Digital magazine | **Weekly** | Gemini + Editorial |
| FAQ content | **On change** (from Vueling FAQ database) | Vueling systems |
| Translations (6 languages) | After any content update | Google Gemini AI |

### Offline Delivery — Silent Push & Edge Caching

**With the Vueling app:** T-24h before flight, a silent push downloads everything to the device. At boarding, the experience loads instantly — zero bandwidth.

**Without the app (WiFi portal):** Content is pre-loaded onto an onboard edge cache server via ground WiFi at the gate. Passengers connect and get LAN-speed content — no satellite needed.

**Satellite bandwidth per flight: ~370 KB total.** Only flight tracker, food orders, and payments go over satellite. Less than a single webpage.

---

## System Architecture

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

**Fallback-first design**: UI loads with pre-cached data instantly, then upgrades to live API data. If any API fails, cached data stays — the experience never breaks.

---

## Roadmap

| Phase | What | When |
|---|---|---|
| **POC** (done) | Destination content, flight details, 3 cities, 6 languages, working UI | Feb 2026 |
| **Phase 1** | Food pre-order, flight tracker, digital magazine, FAQ, offline caching | Q2 2026 |
| **Phase 2** | Music playlists, onboard ordering + payments, full route network | Q3 2026 |
| **Phase 3** | Hyperpersonalization engine (preferences, loyalty, VIP treatment) | Q4 2026 |
| **Phase 4** | Commerce (bookable restaurants, transfers, attraction tickets) | 2027 |

---

## Future Vision: Hyperpersonalization

The long-term goal goes beyond content delivery. Every interaction with the Inflight Experience becomes a data point that helps us know and serve the passenger better:

- **Food preferences**: Know that Maria always orders Mediterranean. Suggest it first.
- **Frequent flyer recognition**: A loyal passenger who orders food every flight gets personalized offers and priority service.
- **Treat everyone as VIP**: Whether flying for holidays, leisure, or business — every passenger gets the feeling of premium treatment. Personal greetings, preferred content, remembered choices.
- **Predictive catering**: Aggregate pre-order data to forecast demand and optimize stock per route.

See [HYPERPERSONALIZATION.md](HYPERPERSONALIZATION.md) for the full vision.

---

**Status:** POC Complete — Ready for MWC Demo
**Date:** February 2026
