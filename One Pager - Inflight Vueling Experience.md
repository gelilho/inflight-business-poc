# Solution Description Brief — Vueling Inflight Experience

> **One liner:** An AI-powered digital platform that turns every Vueling flight into a personalized journey — content, entertainment, food ordering, transport recommendation and passenger intelligence — from one booking number and from every single passenger.

---

## 1. What Problem Are We Solving?

**34 million passengers spend over 60 million hours a year in our aircraft — with zero digital engagement.**

Today, a Vueling passenger boards, puts on their headphones, and disconnects. The airline owns the most captive, high-intent audience in travel — and does nothing with it.

| Pain Point | Who Feels It |
|---|---|
| No personalized content — passengers bring their own entertainment | **Passengers** |
| Food service depends on a physical cart — low conversion, low convenience | **Passengers / Revenue** |
| Paper magazine nobody reads — cost, waste, no engagement data | **Sustainability / Brand** |
| Passengers google their destination on other platforms before or after landing | **Product / Revenue** |
| When passengers need help, they call a hotline or wait for crew | **Passengers / Operations** |
| No data on what passengers want, read, eat, or prefer | **Data / Strategy** |
| Competitors investing in digital — Vueling risks falling behind | **Leadership** |

**The core insight:** We have the attention. We have the context (destination, language, timing). We have the distribution channel (app + WiFi). We just aren't using any of it.

---

## 2. What Is the Solution?

**The Vueling Inflight Experience** — a single digital platform that delivers personalized content, entertainment, food ordering, and self-service help to every passenger, from one booking number.

### 11 Experience Pillars

```
┌─────────────────────────────────────────────────────────────────────┐
│                                                                     │
│   COMMERCE              CONTENT                UTILITY              │
│   ─────────             ───────                ───────              │
│   Food & Snacks         Discover Destination   Live Flight Tracker  │
│                         Weather & News         Getting to the City  │
│   ENTERTAINMENT         Digital Magazine       Peace of Mind        │
│   ─────────────                                FAQ & Help           │
│   Music & Audio         PERSONALIZATION                             │
│                         ────────────────                            │
│                         Your Aircraft                               │
│                         Your Crew                                   │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

| Pillar | What the Passenger Gets |
|---|---|
| **Food & Snacks** | Pre-order the day before, at the airport, or order onboard. Crew delivers to seat. No cart, no cash, no waiting. |
| **Your Aircraft** | Model, name (e.g. "Air Force Juan"), registration — make flying personal and transparent |
| **Your Crew** | Captain and cabin crew names — passengers feel they're in good hands |
| **Live Flight Tracker** | Real-time map with position, altitude, speed, ETA |
| **Discover Your Destination** | Top 5 highlights, 3 restaurant picks — AI-generated, in their language |
| **Getting to the City** | Transport options (train, bus, taxi) with times and costs + option to book transfers |
| **Peace of Mind** | Emergency contacts (police, hospital) and Vueling helpline — always at hand |
| **Weather & News** | 3-day forecast + curated local news (sports, culture, events — inflight-safe) |
| **Music & Audio** | AI-curated playlists per destination — local artists, mixed decades, chill vibes |
| **Digital Magazine** | The spirit of the beloved Ling magazine, reborn digital — travel stories, tips, Vueling news |
| **FAQ & Help** | Searchable Vueling FAQ — baggage, check-in, loyalty, rebooking — answers without calling |

**It starts as a content platform, evolves into a commerce engine, and matures into the most personal relationship a low-cost carrier has ever had with its passengers.**

---

## 3. How Does It Work?

### Three Principles: Offline-First. Pre-Computed. Minimal Satellite.

Content is **never generated per-request**. Everything is produced on scheduled cadences, cached, and delivered before the passenger boards.

```
┌─────────────────────────────────────────────────────────────────────┐
│           CONTENT GENERATION LAYER (Scheduled)                      │
│                                                                     │
│  Destinations   Flights   News    Music   Magazine   FAQ    Menu    │
│  (2 weeks)      (daily)   (6h)   (weekly) (weekly)  (on Δ) (weekly)│
│       │            │        │       │        │        │       │     │
│       v            v        v       v        v        v       v     │
│  ┌─────────────────────────────────────────────────────────────┐    │
│  │              CONTENT STORE (CDN / Cache)                    │    │
│  └──────────────────────┬──────────────────┬───────────────────┘    │
│                         │                  │                        │
│              ┌──────────┴───┐    ┌─────────┴────────┐              │
│              │ SILENT PUSH  │    │  ONBOARD EDGE    │              │
│              │ (App, T-24h) │    │  CACHE (WiFi)    │              │
│              └──────────┬───┘    └─────────┬────────┘              │
│                         │                  │                        │
│  ┌──────────────────────┴──────────────────┴───────────────────┐    │
│  │           PASSENGER DEVICE (App or Browser)                 │    │
│  └─────────────────────────────┬───────────────────────────────┘    │
│                                │                                    │
│  ┌─────────────────────────────┴───────────────────────────────┐    │
│  │     SATELLITE (Real-time only — ~370 KB per flight)         │    │
│  │     Flight Tracker  │  Food Orders  │  Payments             │    │
│  └─────────────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────────────┘
```

### Two Delivery Channels

**App users (Vueling app installed):**
- T-24h: Silent push downloads full content package (~15-25 MB)
- At boarding: experience loads instantly from device — zero bandwidth

**WiFi portal users (no app):**
- Onboard edge cache server pre-loaded at gate via ground WiFi
- Passengers connect to WiFi → content served at LAN speed — no satellite

**Total satellite budget per flight: ~370 KB.** Only flight tracker (~1KB/30s), food orders (~2KB/order), and payments (~1KB/txn) go over satellite. Less than a single webpage.

### AI Engine: Google Gemini 2.5 Flash

A single AI engine generates ALL content: destination highlights, restaurants, weather, news, transport options, and translations to 6 languages. One model. One prompt layer. One cost structure.

### Architecture (POC)

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

**Cost per passenger: ~0.005 EUR.** Against food revenue, the ROI is 160x–240x.

---

## 4. Why Now?

| Signal | Why It Matters |
|---|---|
| **AI maturity** | Gemini 2.5 Flash can generate production-quality, multilingual content at near-zero cost. This wasn't possible 18 months ago. |
| **Inflight WiFi rollout** | Vueling's fleet is getting connected — we can now deliver real-time experiences (food orders, payments, flight tracker) on top of pre-cached content. |
| **Passenger expectation shift** | Post-pandemic travelers expect digital-first experiences. The gap between "premium airline" and "low-cost carrier" experience is closing — through software, not infrastructure. |
| **Long-haul benchmark** | Passengers experience personalized entertainment, food ordering, and destination content on long-haul flights. They expect the same on short-haul. Vueling can be the first to deliver it. |
| **MWC 2026** | The POC is built, working, and demo-ready. Three cities, six languages, live API. This is the moment to demonstrate capability and vision. |
| **Revenue urgency** | Ancillary revenue is the growth engine for LCCs. Food pre-ordering alone has standalone ROI — 8% conversion × 34M passengers × ~10 EUR = ~27M EUR/year. |

---

## 5. What Does It Enable?

### For Every Stakeholder

```
┌──────────────────────────────────────────────────────────────────────────┐
│                                                                          │
│  PRODUCT            ENGINEERING          DESIGN            DATA          │
│  ───────            ───────────          ──────            ────          │
│  11 pillars of      Offline-first        One unified       Every tap,   │
│  passenger value     architecture         experience        read, order  │
│  from a single       that works at        that feels        becomes a    │
│  booking number      35,000 feet          personal          signal       │
│                                                                          │
│  OPERATIONS          SUSTAINABILITY       REVENUE           LEADERSHIP   │
│  ──────────          ──────────────       ───────           ──────────   │
│  -15% crew           -20% food waste      ~27M EUR/yr       First LCC   │
│  aisle time          Zero paper           food pre-orders   with AI-     │
│                      magazines            alone              powered      │
│                                                             inflight     │
│                                                             experience   │
│                                                                          │
└──────────────────────────────────────────────────────────────────────────┘
```

### The Hyperpersonalization Flywheel

Every interaction creates a preference signal. Over time, the platform learns and adapts:

| What We Learn | What We Do |
|---|---|
| Maria always orders Mediterranean | Menu opens with "Your usual?" — one-tap reorder |
| Carlos reads culture articles | Magazine opens with culture first |
| A family flies to Mallorca | Family content + kids' menu highlighted |
| Frequent flyer orders food every trip | "Welcome back! Your 10th order is on us" |
| Monday BCN→MAD business traveler | Coffee + news-first layout, minimal destination content |

**The objective:** treat every passenger like a VIP/Business customer — whether flying for holidays, leisure, or business. We scale premium treatment through software, not physical infrastructure.

### KPIs

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

### Roadmap

| Phase | Deliverables | Timeline |
|---|---|---|
| **POC** | Destination content, flight details, 3 cities, 6 languages, working UI + API | Feb 2026 |
| **Phase 1** | Food pre-order, flight tracker, digital magazine, FAQ, offline caching | TBD 2026 |
| **Phase 2** | Music, onboard ordering + payments, full route network | TBD 2026 |
| **Phase 3** | Hyperpersonalization (preferences, loyalty, VIP treatment) | End of 2026 |
| **Phase 4** | Commerce (bookable restaurants, transfers, tickets), predictive intelligence | 2027 |

---

## POC Status

- **3 destinations**: Rome, London, Paris
- **6 languages**: es, en, fr, it, ca, gl
- **Single AI engine**: Google Gemini 2.5 Flash (generates ALL content, weather, news, translations)
- **Fallback-first**: UI always works, even if APIs fail
- **All endpoints tested and working**
- **Ready for MWC demo**

---

_Every flight is a canvas. Every passenger is an audience of one._
_Let's build the future of flying together._

**Vueling Inflight Experience — MWC Barcelona 2026**
