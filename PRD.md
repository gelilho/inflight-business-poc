# Vueling Inflight Experience — PRD

> **One line:** An AI-powered digital platform that turns every Vueling flight into a personalized journey — content, entertainment, food ordering, and passenger intelligence — from one booking number.

---

## 1. Vision

Transform every Vueling flight into the best two hours of a passenger's day.

Today, 34 million passengers spend 60 million hours a year in our aircraft with zero engagement. They bring their own entertainment, skip food because the ordering process isn't convenient, and land googling everything about their destination on someone else's platform. We own the attention but we're not using it.

**The Vueling Inflight Experience** changes this. A single digital platform — delivered through the Vueling app and inflight WiFi — that combines personalized destination content, immersive entertainment, real-time flight information, food pre-ordering, and self-service help. All AI-powered. All in the passenger's language. All from one booking number.

It starts as a content platform, evolves into a commerce engine, and matures into the most personal relationship a low-cost carrier has ever had with its passengers.

---

## 2. What the Passenger Gets — 11 Pillars

| # | Pillar | What It Delivers |
|---|---|---|
| 1 | **Food & Snacks** | Pre-order the day before, order onboard from your phone, crew delivers to your seat. No cart, no cash, no waiting. |
| 2 | **Your Aircraft** | Model, name ("Spirit of Barcelona"), registration — make flying personal and transparent |
| 3 | **Your Crew** | Captain and cabin crew names — passengers feel they're in good hands |
| 4 | **Live Flight Tracker** | Real-time map with position, altitude, speed, ETA — see exactly where you are |
| 5 | **Discover Your Destination** | Top 5 highlights, 3 restaurant picks — AI-generated, in their language |
| 6 | **Getting to the City** | Transport options (train, bus, taxi) with times and costs + option to book transfer online |
| 7 | **Peace of Mind** | Emergency contacts (police, hospital) and Vueling helpline — always at hand |
| 8 | **Weather & News** | 3-day forecast + curated local news (sports, culture, events — inflight-safe) |
| 9 | **Music & Audio** | AI-curated playlists per destination — local artists, mixed decades, chill vibes |
| 10 | **Digital Magazine** | The spirit of the beloved Ling magazine, reborn digital — travel stories, tips, Vueling news |
| 11 | **FAQ & Help** | Searchable Vueling FAQ — baggage, check-in, loyalty, rebooking — answers without calling |

---

## 3. The Passenger Journey — When It Triggers

The experience doesn't start at boarding. It starts **24 hours before the flight** and continues **after landing**.

```
T-24h ─── BEFORE THE FLIGHT ──────────────────────────────────────────────
  │
  ├─ Silent push: all content pre-cached on device (~15-25 MB)
  ├─ Push notification: "Flying to Rome tomorrow? Pre-order your menu"
  └─ Passenger opens app → browses menu → orders → pays → "Lunch booked!"

T-3h ─── AT THE AIRPORT ──────────────────────────────────────────────────
  │
  ├─ After check-in: "Checked in! Explore Rome while you wait"
  ├─ After luggage drop: "Luggage done! Add a snack bag?"
  ├─ After security: "You're through! Want a picnic bag for your flight?"
  └─ At the gate: full experience already loaded — music, magazine, destination

T-0 ─── BOARDING ──────────────────────────────────────────────────────────
  │
  ├─ Vueling App: detects WiFi → loads pre-cached experience instantly
  ├─ WiFi Portal: enter PNR → content served from onboard edge cache
  └─ Welcome screen: crew names, aircraft, destination, food, music, FAQ

T+15min ─── CRUISING ─────────────────────────────────────────────────────
  │
  ├─ Browse all content (offline): highlights, restaurants, magazine, music
  ├─ Food ordering goes live: digital menu → cart → pay → crew delivers
  ├─ Live flight tracker: real-time map
  └─ Pre-orders delivered first, then live orders by seat number

T-30min ─── APPROACHING DESTINATION ──────────────────────────────────────
  │
  ├─ "30 minutes to Rome!"
  ├─ Weather on arrival + transport summary + baggage carousel
  └─ Emergency contacts surfaced

LANDING ─── POST-FLIGHT ──────────────────────────────────────────────────
  │
  ├─ "Welcome to Rome! Rate your experience?"
  ├─ NPS survey + optional feedback
  └─ Destination guide stays accessible for the whole trip
```

---

## 4. The Food Revenue Engine

The pillar that **pays for the entire platform**.

**Three moments to capture a sale:**
- **T-24h** — Pre-order via push notification → guaranteed revenue before departure
- **T-3h** — Airport push after security → snack bag upsell
- **T+15min** — Onboard digital menu → tap, order, pay, crew delivers

**Why this is transformational:**
- Pre-orders = **revenue locked in before the plane departs**
- Digital menus with photos = **+30% average order value** vs. aisle cart
- Pre-orders as demand signal = **smarter catering, -20% food waste**
- Crew efficiency = pre-orders prepared in advance, **-15% aisle service time**

---

## 5. KPIs & Business Impact

| Category | Metric | Target |
|---|---|---|
| **Engagement** | Activation rate | >25% in 6 months |
| **Engagement** | Avg. session duration | >12 minutes |
| **Revenue** | Food pre-order conversion | >8% of passengers |
| **Revenue** | AOV uplift (digital vs. aisle) | +30% |
| **Satisfaction** | NPS lift (users vs. non-users) | +5 points |
| **Operational** | Crew aisle service time reduction | -15% |
| **Sustainability** | Food waste reduction | -20% |
| **Sustainability** | Catering demand forecast accuracy | >85% |

**Revenue projection (Year 1, conservative):** 8% of 34M passengers x 10 EUR avg. = ~27M EUR in pre-order revenue alone. Plus onboard digital ordering. Plus reduced waste. The food vertical alone has standalone ROI.

**North Star Metric:** Passenger Lifetime Value (PLV) delta — do experience users fly more, spend more, and recommend Vueling more?

---

## 6. Technical Solution

### Architecture

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

### Three Principles: Offline-first. Pre-computed. Minimal satellite.

**Content is never generated per-request.** Everything is produced on scheduled cadences and cached:

| Content | Cadence | Source |
|---|---|---|
| Destination content | Every 2 weeks | Google Gemini AI |
| Flight details (crew, aircraft) | Daily | Airline ops systems |
| Weather | Every 12 hours | Google Gemini AI |
| News | Every 6 hours | Google Gemini AI (safety rules in prompt) |
| Music playlists | Weekly | AI Curation Engine |
| Magazine | Weekly | Gemini + Editorial |
| FAQ | On change | Vueling systems |

### Delivery: Silent Push + Edge Caching

**App users:** T-24h, a silent push downloads the full content package. At boarding → loads instantly. Zero bandwidth.

**WiFi portal users:** Onboard edge cache server pre-loaded at the gate via ground WiFi. Content served at LAN speed — no satellite needed.

**Satellite budget per flight: ~370 KB.** Only flight tracker (~1KB/30s), food orders (~2KB/order), and payments (~1KB/txn) go over satellite. Less than a single webpage.

### Full Platform Vision

```
+======================================================================+
|                 CONTENT GENERATION LAYER (Scheduled)                  |
|  Destination │ Flight Ops │ News │ Music │ Magazine │ FAQ │ Menu     |
|  (2 weeks)   │ (daily)    │ (6h) │(weekly)│(weekly) │(on Δ)│(weekly)|
+======+===============+=========+========+==========+=======+=========+
       |               |         |        |          |       |
       v               v         v        v          v       v
+======================================================================+
|                 CONTENT STORE (CDN / Cache)                          |
+==============+=======================+================================+
               |                       |
        +------+------+        +------+-------+
        | SILENT PUSH |        | ONBOARD EDGE |
        | (App, T-24h)|        | CACHE (WiFi) |
        +------+------+        +------+-------+
               |                       |
+==============+=======================+================================+
|                 PASSENGER DEVICE (App or Browser)                    |
+=================================+=====+===============================+
                                  |     |
+==============+==================+=====+===============================+
|              SATELLITE (Real-time only — ~370 KB/flight)             |
|  Flight Tracker │ Food Orders │ Payments                            |
+======================================================================+
```

**Cost per passenger: ~0.005 EUR.** Against food revenue, the ROI is 160x-240x.

---

## 7. Future Vision: Hyperpersonalization

The Inflight Experience is not just a product — it's a **data flywheel**. Every pre-order, every article read, every playlist played, every FAQ searched is a preference signal.

**The objective:** treat every passenger like a VIP — whether flying for holidays, leisure, or business.

| What We Learn | What We Do |
|---|---|
| Maria always orders Mediterranean | Menu opens with "Your usual?" — one-tap reorder |
| Carlos reads culture articles on every flight | Magazine opens with culture first |
| A family flies to Mallorca | Family content + kids' menu highlighted |
| Frequent flyer orders food on every trip | "Welcome back! Your 10th order is on us" |
| Monday BCN→MAD business traveler | Coffee + news-first layout, minimal destination content |

**The VIP promise:** We scale the feeling of premium treatment through software, not physical infrastructure. Personal greetings. Remembered preferences. Curated offers. No extra cost per passenger — just smarter data.

**Frequent Flyer + Food = Loyalty Gold:** The passenger who flies often and orders food regularly is among the most engaged and monetizable. They get recognized, rewarded, and made to feel that Vueling knows them.

**Predictive catering:** Aggregate pre-orders become a demand signal. We know what to load per route, per day, per season. Less waste. Lower cost. Fresher food.

---

## 8. Roadmap

| Phase | Deliverables | Timeline |
|---|---|---|
| **POC** ✅ | Destination content, flight details, 3 cities, 6 languages, working UI + API | Feb 2026 |
| **Phase 1** | Food pre-order, flight tracker, digital magazine, FAQ, offline caching | Q2 2026 |
| **Phase 2** | Music, onboard ordering + payments, full route network | Q3 2026 |
| **Phase 3** | Hyperpersonalization (preferences, loyalty, VIP treatment) | Q4 2026 |
| **Phase 4** | Commerce (bookable restaurants, transfers, tickets), predictive intelligence | 2027 |

---

## 9. POC Status

- **3 destinations**: Rome, London, Paris
- **6 languages**: es, en, fr, it, ca, gl
- **2 repos**: Backend API (Python/FastAPI) + Frontend UI (React/Vite)
- **AI engine**: Google Gemini 2.5 Flash
- **Single AI engine**: Google Gemini 2.5 Flash (generates ALL content, weather, news, translations)
- **Fallback-first**: UI always works, even if APIs fail
- **All endpoints tested and working**
- **Ready for MWC demo**

---

_Every flight is a canvas. Every passenger is an audience of one._
_Let's build the future of flying._

**Vueling Inflight Experience — MWC Barcelona 2026**
