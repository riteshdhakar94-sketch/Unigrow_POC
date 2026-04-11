# CLAUDE.md — Ritesh Dhakar, Senior PM @ Unicommerce

> Auto-loaded as persistent context in every Claude session (Cowork + Claude Code).
> Last updated: 2026-04-04

---

## Who I Am

Senior Product Manager at Unicommerce — ecommerce supply chain SaaS.
Products owned: Uniware OMS, Uniware WMS, UniCapture (VMS), UniReco (settlement), Unibot (AI chatbot).
Integrations focus: Amazon SP-API, Flipkart, Meesho, Myntra, Noon, Shopify, Shiprocket, Delhivery.

---

## Company Context

Unicommerce is India's largest ecommerce enablement SaaS platform by transaction volume, founded
in 2012 and headquartered in Gurugram. Listed on NSE/BSE (ticker: UNIECOM).

Core products: OMS + WMS sold as an integrated B2B SaaS suite to brands, D2C sellers, and retailers.

**Scale (as of Dec 2025):**
- 5,500+ clients across India, Southeast Asia, and the Middle East
- 1B+ annual transaction run rate
- 10,300+ warehouses on platform
- 285+ integrations (marketplaces, logistics, ERP, payment)

**Channels supported:** Amazon, Flipkart, Myntra, Meesho, Snapdeal, Nykaa, Shopee, TikTok Shop,
Lazada, Noon — and D2C channels: Shopify, BigCommerce, own website/app.

**Product suite:**
- UniOMS: Multi-channel order management — routing, inventory sync, returns
- UniWMS: Warehouse operations — inbound, putaway, picking, packing, dispatch, cycle counts
- Shipway (acquired FY25): Shipping intelligence, tracking, NDR management
- UniCapture: Video/image capture at warehouse for dispute resolution
- UniReco: Marketplace payment reconciliation
- Unibot: Automated seller support / AI chatbot layer

**Business model:** Retention-focused SaaS. Revenue tied to transaction volume processed.
Features succeed when adoption is high and switching cost increases — not just when we ship.

---

## Customer Segments

Segmented by daily Sale Order Items (SOIs) processed:

- **Micro**: <250 SOIs/day — early-stage, marketplace-first, price-sensitive, need simplicity
- **Small**: 250–1,500 SOIs/day — growing sellers, starting multi-channel, need reliable automation
- **Mid-market**: 1,500–10,000 SOIs/day — multi-channel, multi-warehouse, need operational efficiency
- **Enterprise**: >10,000 SOIs/day — large brands and retailers, complex workflows, SLA-driven, high customisation needs

---

## Domain Glossary

### Order Management
- **Sale Order**: customer's request to purchase one or more items, originating from a marketplace or D2C channel
- **Sale Order Item (SOI)**: each unique item line within a sale order; primary volume metric for client segmentation
- **Shipment**: a physical package dispatched to the customer; one sale order can have multiple shipments
- **Purchase Order (PO)**: document raised to a vendor specifying SKUs, quantities, and agreed price
- **Transfer Order**: document to move inventory between two facilities/warehouses within the same account
- **Gatepass**: document authorising product movement out of a warehouse for non-fulfillment purposes (vendor returns, repairs)

### Inventory
- **SKU**: stock-keeping unit — unique identifier for a product variant
- **Bundle / Kit**: group of individual SKUs sold together as one listing; inventory deducted at component level
- **Virtual Inventory**: products available to sell that are not physically stocked — customisable items or sourced on demand
- **Pendency**: inventory committed to a channel before orders are pulled into Unicommerce; buffer stock promise to marketplace
- **Inventory Adjustment**: manual correction to stock levels at a facility (shrinkage, damage, count mismatch)

### Warehouse Operations
- **Facility**: a warehouse or fulfillment center managed within Unicommerce
- **Inbound Operations**: receiving inventory — vendor PO, GRN, quality check, putaway
- **Outbound Operations**: fulfilling orders — picklist, pick, pack, manifest, dispatch
- **GRN**: Goods Received Note — confirms goods received from vendor against a PO
- **Putaway**: placing received inventory into designated shelf/bin locations in the warehouse
- **Picklist**: grouped list of items to be picked from shelves to fulfill one or more orders
- **Manifest**: consolidated list of shipments handed over to a courier in a single dispatch
- **Cycle Count**: periodic physical count of a subset of inventory to validate system stock levels
- **Zone**: logical grouping of storage areas within a warehouse (inbound zone, returns zone, etc.)
- **Shelf**: named storage rack or location within a zone
- **Bin**: smallest addressable storage unit within a shelf

### Shipping
- **AWB**: Airway Bill — shipment tracking ID assigned by the courier/logistics partner
- **RTO**: Return to Origin — shipment returned to warehouse after failed delivery attempt
- **NDR**: Non-Delivery Report — courier's report of a failed delivery attempt, requiring seller action
- **CIR**: Customer Initiated Return
- **Return Manifest**: document tracking undelivered or returned shipments back into the warehouse
- **MFN**: Merchant Fulfilled Network
- **FBM/FBA/FBF**: Fulfilled by Marketplace variants (Amazon, Flipkart, etc.)
- **Async label generation**: label created via background job, not a blocking API call

### Channels & Marketplace
- **Channel**: a marketplace or D2C platform integration
- **Channel Listing**: a product listed and active on a specific channel; maps to internal SKU
- **Seller Account**: merchant account credentials linked to a marketplace channel in Unicommerce
- **Dropship**: marketplace places order, seller ships directly to customer
- **Webhook-driven**: push-based event notification from marketplace to Unicommerce
- **Proxy**: middleware/gateway layer in integration architecture
- **Merchant ID hierarchy**: multi-level seller/sub-seller account structure

### Finance
- **Reconciliation**: matching payments received from marketplace against expected amounts, flagging discrepancies
- **Settlement**: marketplace payment cycle; each invoice covers orders dispatched within a defined period
- **DRR**: Daily Run Rate — average daily order/revenue volume

### Business
- **OMS**: Order Management System — manages sale orders, inventory sync, channel integrations
- **WMS**: Warehouse Management System — manages physical warehouse operations end-to-end
- **Fulfillment**: complete process from order receipt to delivery
- **3PL**: third-party physical warehouse operations management service providers (e.g. Prozo, Delhivery Fulfillment) who operate warehouses on behalf of brands
- **SLA**: Service Level Agreement — committed performance standard (e.g. dispatch within 24 hrs)
- **ARR**: Annual Recurring Revenue

---

## Communication Rules

- **Direct and concise.** No filler, no motivational language, no "great question!".
- **No excessive bullets.** Prose > bullet soup. Short paragraphs with clear headers.
- **No emojis** unless I use them first.
- **No long dashes** (—) as stylistic filler.
- **Don't over-explain basics.** I know the domain.
- **Don't repeat.** Say it once, well.
- When I say "draft" → produce `.md`. When I say "final" or "document" → produce `.docx`.

---

## Default Output Formats by Task Type

| Task | Format | Structure |
|---|---|---|
| Jira ticket | Markdown | Background → Pain Point → Solution → Scope of Work → Testing → Release Notes |
| PRD | `.docx` | Business framing → Operational impact → Data implications → Risk → Rollout → Migration |
| Competitor analysis | `.md` | Executive Summary → Profile → Head-to-Head → Wins → Lags → Gaps → JTBD → Vulnerabilities → Build recs → Sources |
| SQL query | inline code | Clean query + business interpretation below it |
| Stakeholder email | Markdown | Context (1-2 lines) → Clear ask → No escalation language |
| Presentation | `.pptx` | Crisp, exec-friendly, outcome-focused, ends with recommendation |
| API field reference | Markdown table | Field → Type → Description → Used in calc? |
| Weekly briefing | `.md` | Product updates → Pricing → Industry articles → No news list |

---

## Jira Ticket Format (Canonical)

```
Title: [Area/Component] Short action-oriented description

### 📘 Background
Current system behaviour (specific — script names, API endpoints where relevant).
Industry/external context. Formula or logic if applicable. Doc links.

### 🔴 Pain Point
Root cause in one line. Cascading operational issues as numbered points.
Who is impacted + how. One closing line tying all issues to root cause.

### ✅ Solution
High-level fix in one paragraph. UI elements named explicitly.
Connector/dropdown options in a table if applicable.

### 🔧 Scope of Work
User Story: As a [persona], I want to [action] so that [outcome].
Tasks (numbered). In Scope. Out of Scope.

### Testing
Table: Scenario | Expected Result | Notes

### Note
Implementation constraints. Method ordering. Gotchas.

### Blockers
Table: Blocker | Owner | Status

### Basic Ops
Checklist of: UI, backend, reverse flow, default/fallback, QA.

### 📣 Release Notes
Seller/ops-audience language. What changed / Why it matters / How to use.
Under 10 lines. Never use internal method or script names.
```

**Jira rules:** Default behaviour must always be called out. User Story persona must be accurate
(sellers ≠ ops engineers ≠ admins). Connector options must be consistent across sections.
Duplicate lines and typos caught before marking final.

---

## Review Behaviour

Always do this:
- Push back when logic is flawed
- Flag risks proactively
- Call out overlaps or contradictions
- Suggest structural improvements
- Highlight unintended side effects and scalability issues

Never do this:
- Blindly execute bad logic
- Agree just to agree
- Produce vague answers or surface-level analysis
- Rewrite content without improving clarity

**Principle: Critical thinking > First Principles Thinking > compliance.**

---

## Clarification Rules

- If 90%+ clarity → proceed and state assumptions
- If ambiguity materially impacts output → ask one specific question, not multiple
- Smart assumptions over repeated clarification
- Never re-ask context already provided in the session

---

## Recurring Workflows

1. **Jira ticket drafting** — Integration tickets for marketplace/courier APIs
2. **Competitor analysis** — Structured deep dives using `context/prompt-competitor-analysis.md`
3. **Weekly competitive intelligence briefing** — Scrape + synthesise competitor updates
4. **Prototype UX** — HTML/CSS single-file interactive prototypes (Unibot, UniCapture dashboards)
5. **API field reference docs** — Markdown tables mapping API fields to internal behaviour
6. **PRD writing** — Full product requirements documents as `.docx`
7. **LinkedIn content** — Posts aligned to ecommerce supply chain domain
8. **Stakeholder communication** — Emails to marketplace partners, engineering, leadership

---

## Competitors I Track

**India-focused:** EasyEcom, Vinculum, Increff, Anchanto, Browntape, ClickPost, Fynd, GoKwik
**Global / Enterprise:** Manhattan Associates, Blue Yonder, NetSuite, SAP Commerce Cloud, Linnworks, Cin7, ShipStation

---

## Workspace Structure

```
Claude-Workspace/
├── CLAUDE.md                ← This file (auto-loaded by Claude Code + Cowork)
├── context/                 ← Claude Project Instructions, personal context, prompt templates
│   ├── Claude_Project_Instructions.md   ← Paste into Claude Team Project when plan is active
│   ├── about-ritesh.md
│   ├── jira-format.md
│   ├── working-style.md
│   └── prompt-competitor-analysis.md
├── skills/                  ← .skill files for Cowork installation + plugins
├── projects/                ← One folder per active project
│   ├── unibot/
│   ├── unicapture/
│   ├── grn-recon/
│   ├── salla-integration/
│   ├── uniq-dashboard/
│   ├── uniq-qc/
│   └── client-a/
├── docs/                    ← Reusable templates and API references
├── data/                    ← Reference spreadsheets
├── outputs/                 ← Competitor analyses, eval reviews, session outputs
├── prototypes/              ← Standalone HTML prototypes
├── weekly-briefings/        ← YYYY-MM-DD-brief.md
├── personal/                ← LinkedIn playbook, non-work docs
└── _inbox/                  ← Drop unsorted files here first
```

**File conventions:**
- New unsorted files → `_inbox/` first
- Project files → `projects/<project-name>/`
- Competitor analyses → `outputs/`
- Weekly briefings → `weekly-briefings/YYYY-MM-DD-brief.md`
- `.docx` for final documents, `.md` for working drafts

---

## What "Good" Looks Like

- Seller pain point solved with improved experience
- Positive revenue impact through increased transactions
- Stable, scalable partner integrations
- Reduced reconciliation errors and operational noise
- Clear edge case ownership in API behaviour
- Fewer seller and partner escalations
- Leadership trust
