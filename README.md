# MarCat

**The connecting layer for Indian FMCG retail.**

MarCat is one platform spanning four stakeholder portals — Brand, Supplier, Retailer, Consumer — built to coordinate the four nodes of Indian retail that today operate as disconnected silos.

Live in production at **Banjara**, a supermarket built from scratch in Ahmedabad pin-code 380015 (India's densest retail corridor), since **27 April 2026**.

Pitch: **[pitch.marcat.in](https://pitch.marcat.in)** · PDF: **[marcat-pitch.pdf](https://pitch.marcat.in/marcat-pitch.pdf)**

---

## The chip board

```
        Brand ───────────────────── Consumer
          │                            │
          │                            │
          └────────── MarCat ──────────┘
          │                            │
          │                            │
       Supplier ───────────────────── Retailer
```

Four nodes. One connecting layer. The chip board is the literal architecture metaphor — each node has a portal, MarCat is the wire between them.

| Node | Portal status |
|---|---|
| Retailer | LIVE — at Banjara since 27 April 2026 |
| Consumer | LIVE — at Banjara since 27 April 2026 |
| Brand | BUILT — awaiting first brand customer |
| Supplier | BUILT — awaiting first distributor customer |

---

## Production scale

| Metric | Count |
|---|---|
| Stakeholder portals | 4 |
| Production routes | 311 |
| Database tables | 203 |
| Postgres RPCs | 91 |
| Indexes | 307 |
| RLS policies | 291 |
| AI endpoints | 7 |
| Build duration | 3 months (Feb 2026 → 27 April 2026 launch) |
| Production rollbacks since launch | 0 |

---

## Tech stack

- **Framework:** Next.js 14 (App Router)
- **Language:** TypeScript 5
- **Styling:** Tailwind CSS
- **Database:** Supabase (Postgres + Auth + Edge Functions + Realtime + Storage)
- **Security:** Row-Level Security across all tables
- **Animation:** Framer Motion
- **AI:** Anthropic Claude API (Sonnet 4.6 + Haiku 4.5 + Haiku vision)
- **Deployment:** Vercel
- **Mobile:** Capacitor (Android APK) + PWA fallback

---

## AI endpoints in production

| Endpoint | Model | Purpose |
|---|---|---|
| `morning-brief` | Sonnet 4.6 | Daily store observations with prompt caching + hard cost cap |
| `copilot` | Haiku 4.5 | Stateful retailer chat companion |
| `photo-verify` | Haiku 4.5 (vision) | Store photo verification for onboarding |
| `help-ask` | Haiku 4.5 | In-app help with Claude synthesis + static fallback |
| `plan-chat` | Sonnet 4.6 | Follow-up scheme planning conversation |
| `csv-map` | Haiku 4.5 | Migration CSV column mapping with structured output |
| `migration-detect` | Haiku 4.5 | Tally / Marg / Busy / Vyapar source-system detection |

All endpoints implement: prompt caching where applicable, per-call cost tracking, hard daily cost caps, structured-output validation, rule-based fallback when API unavailable.

---

## Retailer portal — feature surface (live at Banjara)

The largest portal, ~177 routes:

- **POS / Billing** — 6,000+ SKUs, multi-slot pricing, scheme engine
- **Inventory / Products** — batch expiry tracking, velocity RPC
- **Purchase / Ordering** — cost-basis modes, scheme builder, e-way ready
- **Reports / Analytics** — 52 views across Sales / Inventory / Brand / Customers / Credit / Tax / Returns
- **Promotions / Schemes / Campaigns** — 11 mechanic types
- **Marketing / WhatsApp** — Meta Business API, segment targeting, conversion attribution
- **AI Copilot + Morning Brief + Help** — production-cost-capped
- **Onboarding** — AI photo verification, CSV column mapping
- **Customers / Segmentation** — RFM segments, lifecycle stages
- **Vendors / Suppliers** — outstanding tracking
- **Dashboard** — 12 KPIs, keyboard navigation
- **Network / Multi-store** — DB-ready for chain rollouts
- **Settings** — 8 sub-routes

---

## Layered roadmap

| Layer | Status | Year |
|---|---|---|
| **L1 Tech** — software platform across 4 portals | Live | Now |
| **L2 Fulfillment** — orchestrated logistics brand → distributor → retailer | Built, awaiting first customer | Y5 |
| **L3 Credit-across-nodes** — transaction-history-based small-cap loans | Designed | Y8 |
| **L4 AI-guided complete infra** — predictive stocking, brand placement, financial aid | Vision | Y10+ |

---

## Operator context

MarCat is dogfooded at **Banjara** — a real supermarket in Ahmedabad pin-code 380015, built from scratch by the founder and operating since 27 April 2026.

The corridor is India's densest retail competition zone:

- 3 DMart stores within 5 km
- Reliance SMART, Star Bazaar nearby
- Blinkit, Zepto, Instamart all serving the same pin-code

If software survives here, it survives anywhere. Banjara runs every MarCat module daily as captive validation.

---

## Repos

| Repo | Purpose |
|---|---|
| **[marcat-pitch-site](https://github.com/swarbhanugupta/marcat-pitch-site)** | Source code for [pitch.marcat.in](https://pitch.marcat.in) — Next.js 14 + Framer Motion deck |
| **marcat-architecture** (this repo) | Architecture overview |
| **marcat-v2** (private) | Operational platform — Banjara production deployment |

---

## Team

- **Swarbhanu Gupta** — Founder, sole engineer. 8+ years FMCG distribution software (Bizom, Happay, Qoruz, ex-VP Sales CultureX). 55+ B2B enterprise accounts closed prior. Built MarCat solo in 3 months while simultaneously building and operating Banjara.
- **Divya Pandya** — Co-founder, Operations. 7+ years HR & People Ops (Intugine, ex-Country Lead Outsourced). Runs daily store operations + cashier training at Banjara since launch. B.Tech + MBA.

---

## Contact

- **Email:** swarbhanu@marcat.in
- **Pitch deck:** [pitch.marcat.in](https://pitch.marcat.in)
- **PDF download:** [marcat-pitch.pdf](https://pitch.marcat.in/marcat-pitch.pdf)
- **Visit the supermarket lab:** Banjara, Ahmedabad pin-code 380015

---

*MarCat is pronounced "Market" — the cat is for memorability.*
