# Presentation Deck — Vueling Inflight Experience
### From dead air time to digital magic — at 35,000 feet

---

## SLIDE 1 — COVER

**Vueling Inflight Experience**

_The first AI-powered, end-to-end digital journey for low-cost aviation_

Personalized content. Immersive entertainment. Onboard food ordering.
All from one booking number.

MWC Barcelona 2026

---

## SLIDE 2 — THE PROBLEM

### 34 million passengers. 60 million hours. Zero engagement.

- No personalized content — passengers bring their own entertainment
- Food service depends on a cart pushed down the aisle — low conversion
- The paper magazine nobody reads costs money and trees
- When they land, they google everything on someone else's platform
- When they need help, they call a hotline or wait for crew

**We have the attention. We just aren't using it.**

---

## SLIDE 3 — THE OPPORTUNITY

### What if every flight felt like a first-class experience?

Imagine a passenger boards and immediately gets:

- Pre-ordered snacks already waiting
- A personal destination guide — in their language
- A curated music playlist with local artists
- A digital magazine (the spirit of Ling, reborn digital)
- Real-time flight tracking on a live map
- A digital menu — tap, order, pay, delivered to seat
- Answers to any question about Vueling — instantly

**That's not a flight. That's an experience.**

---

## SLIDE 4 — THE SOLUTION: 11 PILLARS

| Pillar | What the Passenger Gets |
|---|---|
| **Food & Snacks** | Pre-order before. Order onboard. Delivered to seat. |
| **Your Aircraft** | Name, model, registration — make flying personal |
| **Your Crew** | Captain and cabin crew names — feel in good hands |
| **Live Flight Tracker** | Real-time map, altitude, speed, ETA |
| **Discover Destination** | Top 5 highlights, 3 restaurants — AI-generated |
| **Getting to the City** | Transport options + bookable transfers |
| **Peace of Mind** | Emergency contacts + Vueling helpline |
| **Weather & News** | 3-day forecast + curated safe local news |
| **Music & Audio** | Destination playlists — local artists, mixed decades |
| **Digital Magazine** | The new Ling — travel stories, tips, Vueling news |
| **FAQ & Help** | Searchable Vueling FAQ — answers without calling |

One app. One booking number. A complete journey.

---

## SLIDE 5 — THE FOOD REVENUE ENGINE

### Three moments to capture a sale

```
DAY BEFORE               AT THE AIRPORT              ONBOARD
  |                         |                           |
  | Push: "Pre-order        | After security:           | After takeoff:
  |  your onboard menu"     | "Add a snack bag?"        | Digital menu
  |                         |                           | Tap → Order → Pay
  v                         v                           v
  PRE-ORDER                 PRE-ORDER                   LIVE ORDER
  (guaranteed revenue)      (pickup or onboard)         (crew delivers)
```

- Pre-orders = revenue captured before departure
- Digital menu with photos = +30% avg. order value
- Pre-orders as demand signal = smarter catering, less food waste

---

## SLIDE 6 — MUSIC & FAQ (Future Pillars)

### Music — Discover the Soundtrack of Your Destination

- AI-curated playlists personalized per destination
- Local artists mixed with global hits across decades
- Moods: chill, upbeat, focus, local vibes
- Refreshed weekly — always fresh
- Inflight-safe: no explicit content

### FAQ — Answers at Your Fingertips

- Searchable Vueling FAQ built into the experience
- Baggage rules, check-in times, loyalty program, rebooking policies
- Powered by Vueling's existing FAQ database
- Reduces call center volume — passengers help themselves
- Future: AI-powered conversational FAQ (ask a question, get an answer)

---

## SLIDE 7 — HOW IT'S TRIGGERED

```
T-24h    Silent push: content pre-cached on device
         Push notification: "Pre-order your menu"

T-3h     After check-in / security: "Add a snack bag?"

T-0      Boarding → WiFi / App → Full experience loads instantly

T+15min  Cruising → Food ordering live → Browse, order, pay

T+90min  Descent → "30 min to Rome! Weather & transport info"

LANDING  "Rate your experience?" → NPS survey
```

---

## SLIDE 8 — ARCHITECTURE

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

**Offline-first**: Content pre-cached via silent push (app) or edge cache (WiFi portal). Only food orders + payments use satellite. Total bandwidth per flight: **~370 KB**.

---

## SLIDE 9 — KPIs

| Category | Metric | Target |
|---|---|---|
| **Engagement** | Activation rate | >25% in 6 months |
| **Engagement** | Session duration | >12 minutes |
| **Revenue** | Food pre-order conversion | >8% of passengers |
| **Revenue** | AOV uplift (digital vs. aisle) | +30% |
| **Satisfaction** | NPS lift (users vs. non-users) | +5 points |
| **Operational** | Crew aisle time reduction | -15% |
| **Sustainability** | Food waste reduction | -20% |
| **Sustainability** | Catering demand forecast accuracy | >85% |

---

## SLIDE 10 — BUSINESS IMPACT

**Revenue**: 8% pre-order conversion x 34M passengers x ~10 EUR = significant incremental F&B revenue. Every content card is a future commerce touchpoint.

**Brand**: First LCC with a true digital inflight experience. Not Ryanair. Not EasyJet. Not Wizz Air. Vueling first.

**Cost**: AI content: ~0.005 EUR/passenger. Eliminates paper magazine. Reduces food waste. Crew efficiency gains.

**Data**: Every interaction builds a passenger profile. See [Hyperpersonalization Vision](#).

---

## SLIDE 11 — ROADMAP

| Phase | Deliverables | Timeline |
|---|---|---|
| **POC** (done) | Content + flight details, 3 cities, 6 languages, working UI | Feb 2026 |
| **Phase 1** | Food pre-order, flight tracker, magazine, FAQ, offline caching | Q2 2026 |
| **Phase 2** | Music, onboard ordering + payments, full route network | Q3 2026 |
| **Phase 3** | Hyperpersonalization (preferences, loyalty, VIP treatment) | Q4 2026 |
| **Phase 4** | Commerce (bookable restaurants, transfers, tickets) | 2027 |

---

## SLIDE 12 — HYPERPERSONALIZATION VISION

### The future: treat every passenger like a VIP

- Know that Maria always orders Mediterranean — suggest it first
- Recognize frequent flyers who use the food service — offer loyalty perks
- Remember content preferences — highlight what they care about
- Whether flying for holidays, leisure, or business — make it personal
- Aggregate data to predict demand, optimize routes, reduce waste

**The Inflight Experience isn't just a product. It's a data flywheel.**

---

## SLIDE 13 — LIVE DEMO

**Scenario:** Maria Garcia, seat 14D, VY71299 Barcelona → Rome, Spanish

_[Live API call + UI demo]_

"This is the POC. Live. Working. Now imagine: add a pre-order button, a music tab, a FAQ search. That's Phase 1."

---

## SLIDE 14 — CLOSING

### Every flight is a canvas. Every passenger is an audience of one.

Vueling can be the **first low-cost carrier** to deliver a truly personalized, AI-powered inflight experience at scale.

Content. Entertainment. Commerce. Personalization.
All from one booking number.

**The POC is proven. The architecture is designed. The business case is clear.**

**Let's build the future of flying. And let's do it first.**

---

_Vueling Inflight Experience — MWC Barcelona 2026_
