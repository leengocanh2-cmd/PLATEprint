# PLATEPrint

**Every meal leaves a mark. Now you can measure it.**

Food CO₂ tracking and AI-powered swap recommendations for campuses, hospitals, and institutions.

🔗 **Live demo:** [your-project.lovable.app](https://your-project.lovable.app)  
🎥 **2-min video:** [loom.com/share/your-link](https://loom.com/share/your-link)

Built for the KI Sustainability Hackathon · Powered by Google Gemini (DeepMind) · MIT licence

---

## The problem it solves

EU CSRD now requires institutions to report Scope 3 food emissions — but most have no infrastructure to collect this data. PLATEPrint connects existing purchasing records to verified LCA emission factors, generates audit-ready sustainability reports, and suggests AI-powered ingredient swaps grounded in EAT-Lancet and One Health frameworks.

---

## Features

| Feature | What it does |
|---|---|
| Emissions dashboard | Maps every CSV ingredient to Agribalyse LCA factors. Shows CO₂e by category vs. Swedish peer benchmark (280 kg/week). |
| AI swap suggestions | Flags top emitters. "Ask PLATEPrint AI" calls Google Gemini 1.5 Flash for institution-specific recommendations grounded in EAT-Lancet and SDG guidelines. |
| ESG Report | Auto-generates CSRD-aligned Scope 3 Category 1 report with GRI 305 table, SBTi target line, and full methodology appendix. Audit-ready. |
| Nudge Toolkit | Translates CO₂ data into menu decisions — default dishes, sensory renaming, display positioning, social norm messaging — grounded in published behavioural science. |
| Portfolio View | For property managers: all managed sites ranked by CO₂/meal score with 12-month trend lines. Designed for Akademiska Hus multi-site model. |
| Compliance Scoring | Set food sustainability thresholds in lease terms. Auto-monitors concession compliance. Generates renewal alerts when sites fall below targets. |

---

## Quick start
```bash
git clone https://github.com/YOUR_USERNAME/plateprint
cd plateprint
npm install
echo "VITE_GEMINI_KEY=your_key_here" > .env
npm run dev
# Open http://localhost:5173
```

Get a free Gemini API key at **aistudio.google.com** — no credit card required.

---

## CSV format
```
product,quantity_kg
Beef mince 20%,180
Chicken breast,45
Lentils,8
```

Or click **Load sample data** in the app to see a pre-built KI campus canteen dataset.

---

## Architecture

| Layer | Technology | Purpose |
|---|---|---|
| Frontend | React 18 + Vite + TypeScript | Single-page app with sidebar navigation |
| Styling | Tailwind CSS | Minimalist design — one green palette, no gradients |
| Charts | Recharts | Bar charts, line charts, benchmark reference lines |
| CSV parsing | PapaParse | Client-side — no data leaves the browser |
| LCA matching | Custom TypeScript (`src/data/lcaData.ts`) | Alias-based matching to Agribalyse records |
| AI | Google Gemini 1.5 Flash (DeepMind) | Contextual swap recommendations via REST |
| Icons | Lucide React | Sidebar and UI icons |
| Deployment | Lovable (Vercel) | Zero-config live URL + GitHub source push |

---

## LCA matching pipeline
```
1. Exact name match                          → confidence 1.0
2. Alias match ("nötkött" → "Beef mince")   → confidence 0.9
3. Substring match                           → confidence 0.7
4. Unmatched → flagged, 0 kg CO₂e assumed
```

All dashboard figures, ESG reports, and swap suggestions derive from:
`co2_total = co2_per_kg × quantity_kg`

---

## Gemini API integration
```
Endpoint:  https://generativelanguage.googleapis.com/v1beta/
           models/gemini-1.5-flash:generateContent

Auth:      ?key=${VITE_GEMINI_KEY}

Request:   { "contents": [{ "parts": [{ "text": prompt }] }],
             "generationConfig": { "maxOutputTokens": 200,
                                   "temperature": 0.4 } }

Response:  data.candidates[0].content.parts[0].text
```

Temperature 0.4 keeps responses practical. If the call fails, the app falls back to standard swap suggestions — Gemini is an enhancement, not a hard dependency.

---

## Data sources

| Dataset | Provider | Licence |
|---|---|---|
| Agribalyse 3.1 | ADEME (France) | Open Data Commons ODC-By |
| RISE Sweden corrections | RISE Research Institutes of Sweden | CC-BY 4.0 |
| Livsmedelsverket nutritional data | Swedish Food Agency | Open Government Data |

All LCA data is committed to `src/data/lcaData.ts` — core matching works fully offline.

---

## Sustainability frameworks

| Framework | Implementation |
|---|---|
| EAT-Lancet Planetary Health Diet | Swap targets prioritise plant proteins; ruminant meat flagged highest priority |
| One Health | Reducing factory-farmed meat lowers AMR risk |
| SDG 2 — Zero Hunger | Swaps validate protein and caloric equivalence |
| SDG 3 — Good Health | Plant-forward purchasing reduces NCD burden |
| SDG 12 — Responsible Consumption | Weekly emissions quantified and trended |
| SDG 13 — Climate Action | CSRD Scope 3 reporting with SBTi target alignment |
| Doughnut Economics | Compliance scoring respects planetary ceilings and nutrition floors |
| UNESCO ESD | Designed for educational institutions as sustainability living labs |

---

## Environment variables
```
VITE_GEMINI_KEY=AIza...   # Free at aistudio.google.com
```

Never commit your actual key — it is listed in `.gitignore`.

---

## criteria
|---|---|
| Innovation | First platform connecting institutional purchasing CSVs to CSRD Scope 3 reporting with embedded AI swap intelligence |
| Feasibility | Any supplier CSV. No IT integration. Under 2 minutes to first report. |
| Impact & Scalability | Works for any campus, hospital, or property portfolio. Multi-site modules built in. |
| Interdisciplinary | Food science (LCA) + public health + AI (DeepMind) + policy (CSRD/SDGs) + behavioural economics |
| Presentation | Live product above · 2-min Loom above · Full source in this repo |

---

## Licence

MIT — open source, free to use and adapt.
