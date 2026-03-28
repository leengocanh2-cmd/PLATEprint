# PLATEprint
# PLATEPrint — Food Sustainability Intelligence

**Food CO₂ tracking and AI-powered swap recommendations for campuses, hospitals, and institutions.**

Built for the KI Sustainability Hackathon · Powered by Google Gemini (DeepMind) · Open source

🔗 **Live demo:** [your-project.lovable.app](https://your-project.lovable.app)
🎥 **2-min video:** [loom.com/share/your-link](https://loom.com/share/your-link)

---

## What is Plateprint?

Plateprint is a food sustainability platform for institutional catering — designed for Karolinska Institutet, Swedish hospitals, university campuses, and property managers like Akademiska Hus.

It solves a specific, urgent problem: institutions must now report Scope 3 food emissions under EU CSRD, but have no infrastructure to collect this data. Plateprint connects to existing food purchasing data (CSV upload from any supplier system), maps every ingredient to verified European LCA emission factors, and produces audit-ready sustainability reports — while suggesting lower-footprint alternatives grounded in EAT-Lancet and One Health frameworks.

---

## Key features

- **Instant emissions baseline** — Upload any supplier CSV, get CO₂e/week by food category in seconds
- **Agribalyse LCA matching** — 29 ingredients matched to Agribalyse 3.1 + RISE Sweden verified data
- **AI-powered swap suggestions** — Google Gemini (DeepMind) generates contextual, institution-specific recommendations grounded in EAT-Lancet and SDG guidelines
- **CSRD Scope 3 report** — Auto-generated, audit-ready, GRI 305 aligned
- **Peer benchmarking** — Compare against Swedish institutional catering average (280 kg CO₂e/week)

---

## Sustainability frameworks integrated

| Framework | How Plateprint implements it |
|---|---|
| EAT-Lancet Planetary Health Diet | Swap targets prioritise plant proteins and reduce ruminant meat |
| One Health | Reduces AMR risk by deprioritising factory-farmed meat |
| SDG 2 (Zero Hunger) | Ensures swaps maintain protein and caloric equivalence |
| SDG 3 (Good Health) | Reduces diet-related disease burden in institutional settings |
| SDG 12 (Responsible Consumption) | Tracks and minimises food purchasing waste and footprint |
| SDG 13 (Climate Action) | Quantifies food-system GHG reduction with auditable methodology |
| UNESCO ESD | Designed for educational institutions as living labs for sustainability |
| Doughnut Economics | Respects planetary boundaries while maintaining social food equity |

---

## Technology stack

| Layer | Tool | Why |
|---|---|---|
| Frontend + build | Lovable (React + Vite + TypeScript) | Rapid development, live deployment |
| AI recommendations | Google Gemini 1.5 Flash (DeepMind) | Context-aware sustainability advice |
| LCA data | Agribalyse 3.1 (ADEME) | Open-licence, EU-standard emission factors |
| Regional corrections | RISE Research Institutes of Sweden | Swedish-specific transport + production factors |
| Nutritional data | Livsmedelsverket | Protein equivalence for swap validation |
| Styling | Tailwind CSS | Minimal, responsive design |
| Deployment | Lovable cloud (Vercel infrastructure) | Zero-config, instant live URL |

---

## Running locally

```bash
git clone https://github.com/YOUR_USERNAME/Plateprint
cd Plateprint
npm install
echo "VITE_GEMINI_KEY=your_key_here" > .env
npm run dev
# Open http://localhost:5173
```

Get a free Gemini API key at: aistudio.google.com

---

## Using the app

1. Open the live URL or run locally
2. Click **"Load sample data"** (pre-loaded KI campus order) or upload your own CSV
3. CSV format: two columns — `product` (ingredient name) and `quantity_kg`
4. View the emissions dashboard and bar chart by category
5. Click **"Ask Plateprint AI"** on any swap card for Gemini-powered recommendations
6. Scroll to the CSRD report section for the compliance export

---

## Data sources and licensing

- **Agribalyse 3.1** — ADEME (Agence de la transition écologique), Open Data Commons ODC-By licence
- **RISE Sweden** — CC-BY 4.0, Swedish regional corrections
- **Livsmedelsverket** — Swedish open government data
- All LCA data is committed directly to this repository — no external API dependency for core functionality


## Licence

MIT — open source, free to use and adapt.
