# Vueling Inflight Experience
## Vision, Business Case & POC

**By Angel Garcia** | Read time: 7 minutes

---

34 million passengers fly Vueling every year. They spend over 60 million hours in our aircraft. We capture zero digital engagement from any of it.

This document explains why that changes now, how we do it, and what we've already built.

---

## 1. The Problem

A Vueling passenger boards, puts on headphones, and disconnects. They brought their own entertainment because we offer none. They skip the food because ordering means flagging down a crew member pushing a cart. When they land, they google their destination on someone else's platform. When they have a question — baggage rules, connecting gates, rebooking — they raise their hand and wait.

And here's what nobody thinks about: passengers switch to airplane mode. No internet. No content. Nothing. That dead air time is the most captive moment in their entire travel journey — and we waste it.

Meanwhile, cabin crew spends a huge part of every flight answering the same five questions: "What's my baggage allowance?" "Where's my connecting gate?" "What time do we land?" "Can I change my seat?" "Do you have vegetarian options?" That's time they could spend on service, safety, and selling.

**We own the audience. We have the context. We have the app. We just aren't using any of it.**

---

## 2. The Vision

One platform. One booking number. A complete journey.

The **Vueling Inflight Experience** is a digital platform — delivered through the Vueling app and inflight WiFi — that gives every passenger personalized destination content, entertainment, food ordering, real-time flight info, and self-service help. AI-powered. In their language. Automatically.

It works in airplane mode. Content is pre-cached 24h before the flight. Only food orders, payments, and the live tracker need WiFi (~370 KB per flight).

It starts as a content platform. It evolves into a commerce engine. It matures into the most personal relationship a low-cost carrier has ever had with its passengers.

---

## 3. What the Passenger Gets

### The 11 Pillars

| # | Pillar | What It Delivers |
|---|---|---|
| 1 | **Food & Snacks** | Pre-order the day before or order during the flight. Tap, pay, crew delivers to your seat. |
| 2 | **Your Aircraft** | Name, model, registration. "You're flying on Air Force Juan." |
| 3 | **Your Crew** | Captain and cabin crew names. You know who's flying you. |
| 4 | **Live Flight Tracker** | Real-time map, altitude, speed, ETA. |
| 5 | **Discover Destination** | Top 5 highlights, 3 restaurant picks. AI-generated, in your language. |
| 6 | **Getting to the City** | Train, bus, taxi — times, costs, bookable transfers. |
| 7 | **Peace of Mind** | Emergency contacts + Vueling helpline. Always at hand. |
| 8 | **Weather & News** | 3-day forecast + curated local news. Inflight-safe. |
| 9 | **Music & Audio** | Destination playlists — local artists, mixed decades, chill vibes. |
| 10 | **Digital Magazine** | Ling magazine, reborn digital. Travel stories, tips, Vueling news. |
| 11 | **FAQ & Help** | Searchable Vueling FAQ — answers without calling, without asking crew. |

### Plus: Connecting Flights

Gate, terminal, departure time — shown before landing. Pre-loaded from booking data.

---

## 4. The Passenger Journey

The experience starts **24 hours before the flight** and continues **after landing**.

| When | What Happens |
|---|---|
| **T-24h** | Silent push: all content pre-cached on device. Push: "Flying to Rome? Pre-order your menu." |
| **T-3h** | Airport triggers: "Add a snack bag?" after security. Full experience already loaded at the gate. |
| **Boarding** | App opens in airplane mode → everything loads instantly. WiFi portal → PNR login → same experience. |
| **Cruising** | Browse all content offline. Food ordering goes live via WiFi. FAQ available. Flight tracker live. |
| **T-30min** | "30 minutes to Rome!" Weather, transport, connecting flight info, emergency contacts. |
| **Landing** | "Welcome to Rome! Rate your experience?" Destination guide stays accessible for the trip. |

---

## 5. The Food Revenue Engine

This is the pillar that **pays for the entire platform**.

Three moments to capture a sale:

1. **T-24h** — Push notification: "Pre-order your menu." Revenue locked in before departure.
2. **T-3h** — Airport push after security: "Add a snack bag?" Impulse upsell.
3. **Onboard** — Digital menu with photos. Tap, order, pay, crew delivers. No cart needed.

The numbers:
- Digital menus with photos → **+30% average order value** vs. aisle cart
- Pre-orders as demand signal → **-20% food waste**, smarter catering
- Pre-orders prepared in advance → **-15% crew aisle time**
- **Year 1 projection (conservative):** 8% of 34M passengers × €10 avg = **~€27M** in pre-order revenue alone

The food vertical has standalone ROI. Everything else on the platform is upside.

---

## 6. Cabin Crew Impact

This platform doesn't replace crew. It frees them.

| Before | After |
|---|---|
| Crew answers "What's the baggage allowance?" 30 times per flight | Passenger checks FAQ on their screen |
| Crew announces connecting gate info over PA | Passenger sees gate, terminal, transfer time on their phone |
| Crew pushes cart, recites menu options, handles cash | Passenger browses digital menu, orders, pays — crew just delivers |
| Crew handles complaints about lack of info | Passenger has everything — weather, transport, contacts, news |

Estimated impact: **-15% aisle service time.** **-40% repetitive questions.** Crew focuses on hospitality, safety, and high-value interactions.

---

## 7. Why Now?

| Signal | Why It Matters |
|---|---|
| **AI maturity** | Gemini 2.5 Flash generates multilingual content at ~€0.005/passenger. Not possible 18 months ago. |
| **WiFi rollout** | Vueling's fleet is getting connected. Real-time features become possible. |
| **Passenger expectations** | People get personalized content on long-haul flights. They expect it on short-haul too. |
| **Airplane mode solved** | Pre-caching makes airplane mode an opportunity, not a barrier. |
| **Revenue urgency** | Ancillary revenue is the LCC growth engine. Food alone = ~€27M/year potential. |
| **MWC 2026** | The POC is live. Three cities, six languages. This is the moment. |

---

## 8. KPIs & Business Impact

| Category | Metric | Target |
|---|---|---|
| Engagement | Activation rate | >25% in 6 months |
| Engagement | Avg. session duration | >12 minutes |
| Revenue | Food pre-order conversion | >8% of passengers |
| Revenue | AOV uplift (digital vs. aisle) | +30% |
| Satisfaction | NPS lift (users vs. non-users) | +5 points |
| Operations | Crew aisle time reduction | -15% |
| Operations | Crew repetitive questions reduction | -40% |
| Sustainability | Food waste reduction | -20% |
| Sustainability | Catering forecast accuracy | >85% |

**Cost per passenger: €0.005.** ROI on food revenue alone: **160x–240x.**

**North Star:** Do experience users fly more, spend more, and recommend Vueling more?

---

## 9. Architecture

### Three principles: Offline-first. Pre-computed. Minimal satellite.

Nothing is generated on the fly. Content is produced on schedules, cached, and pushed to devices before boarding. That's why airplane mode works.

| Content | Cadence | Source |
|---|---|---|
| Destinations + translations (6 languages) | Every 2 weeks | Gemini AI |
| Flight details (crew, aircraft) | Daily | Airline ops |
| Connecting flights (gate, terminal) | Real-time | Airline ops |
| Flight advisories (airplane mode, etc.) | Static | Vueling ops |
| Weather | Every 12 hours | Gemini AI |
| News | Every 6 hours | Gemini AI |
| Music playlists | Weekly | AI curation |
| Magazine | Weekly | Gemini + editorial |
| FAQ | On change | Vueling systems |

### Delivery

**App users:** Silent push at T-24h. Content loads in airplane mode. Zero bandwidth at cruise.

**WiFi users:** Onboard edge server pre-loaded at the gate via ground WiFi. Content at LAN speed.

**Satellite budget: ~370 KB per flight.** Only live tracker, food orders, and payments go over satellite.

### AI Engine

One model: **Google Gemini 2.5 Flash.** It generates everything — highlights, restaurants, weather, news, transport, translations. One prompt layer. One cost structure.

### POC Architecture

```
┌──────────────────────┐         ┌──────────────────────────┐
│   inflight-ui-poc    │  HTTP   │     inflight-poc          │
│   React + Vite       │ ──────→ │     FastAPI + Gemini      │
│   :3000              │         │     :8000                  │
└──────────────────────┘         └──────────────────────────┘
        │                                   │
        │ fallback-data.ts                  └── Gemini 2.5 Flash
        │ (demo never breaks)                   (all content types,
        └───────────────────                     6 languages)
```

---

## 10. Hyperpersonalization (Future)

Every interaction is a preference signal. Every pre-order, every article read, every FAQ searched, every playlist played.

| What We Learn | What We Do |
|---|---|
| Maria always orders Mediterranean | "Your usual?" — one-tap reorder |
| Carlos reads culture articles | Magazine opens with culture first |
| Family flies to Mallorca | Kids' menu + family content highlighted |
| Monday BCN→MAD business traveler | Coffee + news layout, skip tourist content |
| Passenger always checks connecting gate | Connection info shown first on welcome screen |

This is how you scale premium treatment without premium cost. Personal greetings. Remembered preferences. Curated offers. Zero marginal cost — just smarter data.

**Predictive catering:** Aggregate pre-orders tell us what to load per route, per day, per season. Less waste. Fresher food.

---

## 11. Roadmap

| Phase | What | When |
|---|---|---|
| **POC** ✅ | Content + flight details, 3 cities, 6 languages, working UI + API | Feb 2026 |
| **Phase 1** | Food pre-order, flight tracker, magazine, FAQ, offline caching, connecting flights | 2026 |
| **Phase 2** | Music, onboard ordering + payments, full route network | 2026 |
| **Phase 3** | Hyperpersonalization — preferences, loyalty, VIP treatment | Late 2026 |
| **Phase 4** | Commerce — bookable restaurants, transfers, tickets, predictive intelligence | 2027 |

---

## 12. POC: What's Built

The POC proves the core idea works: **one API call with a booking number returns a complete, personalized inflight experience.**

**What it does:**
- Takes a PNR + language → returns destination highlights, restaurants, weather, news, transport, flight details, crew, aircraft
- All content generated by Gemini 2.5 Flash
- Mobile-first React UI
- Fallback-first: if the API fails, pre-computed data loads — the demo never breaks

**What it proves:**
- One AI engine handles all content types across 6 languages
- One API call, one booking number, one complete experience
- Content quality is production-ready out of the box
- Cost: ~€0.005 per passenger

**POC scope:**
- 3 destinations: Rome, London, Paris
- 6 languages: Spanish, English, French, Italian, Catalan, Galician
- 2 repos: Python/FastAPI backend + React/Vite frontend
- All endpoints tested and working
- Ready for live demo at MWC

**Not in the POC (Phase 1+):** food ordering, payments, flight tracker, music, magazine, offline caching, personalization.

The POC is the foundation. Everything else builds on the same architecture.

---

_Every flight is a canvas. Every passenger is an audience of one._

**Let's build the future of flying.**

**Vueling Inflight Experience — MWC Barcelona 2026**
