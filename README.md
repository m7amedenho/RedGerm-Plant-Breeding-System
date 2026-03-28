<div align="center">

<br/>
<div align="center">
```
██████╗ ███████╗██████╗  ██████╗ ███████╗██████╗ ███╗   ███╗
██╔══██╗██╔════╝██╔══██╗██╔════╝ ██╔════╝██╔══██╗████╗ ████║
██████╔╝█████╗  ██║  ██║██║  ███╗█████╗  ██████╔╝██╔████╔██║
██╔══██╗██╔══╝  ██║  ██║██║   ██║██╔══╝  ██╔══██╗██║╚██╔╝██║
██║  ██║███████╗██████╔╝╚██████╔╝███████╗██║  ██║██║ ╚═╝ ██║
╚═╝  ╚═╝╚══════╝╚═════╝  ╚═════╝ ╚══════╝╚═╝  ╚═╝╚═╝     ╚═╝
```
</div>
**Enterprise Plant Breeding & Trial Management System**

*From genetic material to variety release — one unified platform.*

<br/>

![Laravel](https://img.shields.io/badge/Laravel-12-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=111827)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![PWA](https://img.shields.io/badge/PWA-Enabled-0ea5e9?style=for-the-badge)
![i18n](https://img.shields.io/badge/Arabic%2FEnglish-Bilingual-16a34a?style=for-the-badge)

<br/>

> 🌱 Built for real operational breeding teams — not just dashboards.

</div>

---

## What is RedGerm?

RedGerm is a full-stack, domain-heavy agriculture platform that replaces fragmented spreadsheets and disconnected tools with one structured, evidence-based workflow. It connects every stage of a breeding program: from registering raw genetic material to releasing a variety — with full traceability at every step.

**The complete chain:**

```
Material → Breeding Unit → Crossing → Trial → Selection → Harvest → Seed Inventory → Variety Decision
```

No broken links. No data loss across generations. No spreadsheet chaos.

---

## Core Features

### 🧬 Breeding Management

**Plant Material Registry**
Register incoming seed accessions with full metadata — crop, generation (F1–F99 and BC series), pollination type, supported breeding methods (SSD, Pedigree, Bulk, Backcross, and more). Each material gets an auto-generated structured code (`TOM-M-001`).

**Breeding Units (Known Lineage)**
When a plant is harvested from a trial, the system automatically creates a Breeding Unit with traceable parentage. Generation is auto-incremented using a smart algorithm that handles F-series, BC-series, and nested generations correctly.

**Family Tree & Lineage**
Interactive visual family tree powered by React Flow and dagre layout. Navigate the full ancestry chain from any node — material, breeding unit, or seed lot. Nodes show live stock availability. Click any ancestor to jump to its detail page.

**Crossing Module**
Record hybridization crosses with parent compatibility validation, execution tracking, pollination method, and result recording. Crosses automatically feed into the lineage graph.

---

### 🌾 Field Trial Lifecycle

**7-Step Setup Wizard**
A guided wizard that structures trial creation from start to publish:
1. Trial information (crop, season, location, breeding method)
2. Entities — link materials/BUs with seed lots from inventory
3. Trial design — CRD, RCBD, Alpha Lattice, Split Plot, Augmented, P-Rep, or Custom
4. Plant map generation with automatic layout per design type
5. Visit schedule planning
6. Label printing
7. Publish to execution

**Experimental Design Engine**
Built-in support for standard agricultural trial designs with randomization:
- **CRD** — Completely Randomized Design (homogeneous environments)
- **RCBD** — Randomized Complete Block Design (field gradients)
- **Alpha Lattice** — for large entry counts
- **Split Plot** — two-factor experiments
- **Augmented** — new entries + replicated checks
- **P-Rep** — partially replicated designs
- **Custom** — manual row-by-row entry assignment

**Plant-Level Execution**
Each plant gets a unique code (`TR-2024-001-R01-P001`) with a QR label. During execution, engineers observe and score traits plant by plant — from a map view or via QR scan. Observations respect trait data types: numeric inputs, percentage sliders, boolean toggles, select dropdowns, and free text.

**Disease & Stress Recording**
Select from a structured Pest & Disease Library (general or crop-specific) with severity scales (1–5 or 1–9 IPGRI standard) and incidence percentage per plant per visit.

**Daily Environmental Logs**
Log temperature (max/min), humidity, soil EC, soil pH, rainfall, and notes per trial day — with photo upload.

---

### 📊 Selection & Analytics

**Selection Algorithm**
Set standard trait criteria with target values, direction (max/min/exact), and weights. The system calculates a weighted similarity score for every active plant and ranks them. Engineers review the ranked list, select manually or by threshold, and confirm. Non-selected plants are automatically marked as dropped.

**Breeding Analytics**
Trait distribution analysis, generation comparison across breeding cycles, segregation pattern visualization, and heritability insights — built for making evidence-based advancement decisions.

---

### 🌍 Variety Catalog & Evaluation

**Public Variety System**
Breeding engineers can request to publish a variety. After admin approval, it enters the public catalog where field trial engineers and external evaluators can access it.

Three visibility levels: `Private → Public → Released`

**Evaluation Trial System**
A simplified but complete trial system for field trial engineers evaluating named varieties. Supports multi-location comparison of the same variety across environments.

**External Evaluator Portal**
Restricted portal for external evaluators — they see only assigned public varieties, submit evaluations, and upload photos. No access to breeding data.

**Variety Advancement Pipeline**
Compile evaluation results, compute performance summaries, and make structured `Continue / Drop / Adopt` decisions backed by data.

---

### 🗄️ Seed Inventory & Storage

**Storage Mapping**
Define storage locations (freezers, cold rooms, dry stores, cabinets) with shelves and slots. Slot occupancy is computed dynamically — no stale flags.

**Seed Lots**
Each lot carries: source material/BU, quantity (grams or seed count — not both forced), germination %, purity %, harvest date, expiry date, supplier info, and storage slot assignment.

**Transaction Ledger**
Every movement is recorded: initial receipt, returns, and disposals. Running balance is maintained per transaction. No transaction can be soft-deleted — the audit trail is permanent.

**Inventory Reports**
Current stock, movement history, low stock alerts, expiry alerts, and a visual storage map showing what's in every slot.

---

### 🤖 AI Integration

RedGerm integrates with an AI gateway for:
- **Report generation** — AI-assisted narrative reports from trial and harvest data
- **Smart suggestions** — contextual hints during trial setup and wizard steps
- **Operational workflows** — AI-enabled actions embedded in the platform

---

### 🖨️ Printing Stack

**ZPL Label Printing**
Direct thermal printing via QZ Tray agent (installed locally on engineer's machine). Supports any ZPL-compatible printer (Zebra, TSC, Godex, Bixolon, and others). Label size is configurable: 30×20mm, 40×25mm, 50×30mm, 60×40mm, or custom dimensions. DPI-aware dot calculation.

**PDF Fallback**
A4 label grid PDF for engineers without a thermal printer. Server-side generation via DomPDF with embedded QR codes.

**Seed Passport PDF**
Formal A4 document for any seed lot — source, lineage chain, storage location, quantities, germination, expiry, and origin trial.

**Trial Report PDF**
Full trial report: summary, entities, field layout, environmental data, visit summary, trait statistics, disease summary, selection results, harvest output, and photo gallery.

---

### 🔐 Governance & Security

**Role-Based Access Control**
Fine-grained permissions via Spatie Laravel Permission. Roles include: Admin, Researcher, Breeding Engineer, Field Trial Engineer, Evaluator, and Viewer. Every route is permission-guarded.

**Data Isolation**
Each user sees only their own data by default. Admins see all. Public varieties are selectively visible based on approval status. No cross-user data leakage.

**Audit Trail**
Centralized audit log for sensitive actions — who did what, when, from where. Includes browser and OS fingerprint.

**Lock Screen**
Fast re-entry flow for shared workstations. After inactivity, the screen locks and the known user is prompted for password only — no need to re-enter email.

**No Public Registration**
Account creation is admin-controlled only. No self-signup endpoint exists.

---

### ⚡ Performance & Field Readiness

**PWA Support**
Full Progressive Web App with service worker and manifest. Engineers can install RedGerm on tablets and use it offline in the field. QR scanning works from the installed app.

**QR Scanning**
Camera-based QR scanning built into the observation workspace. Engineers scan a plant's label → jump directly to its observation form. Manual fallback input included.

**Bilingual (Arabic / English)**
Full RTL/LTR runtime switching. Every label, error, and tooltip is translated. Direction switches instantly without reload.

**Autosave**
Trial wizard steps autosave on field blur. Engineers never lose progress mid-setup.

---

## Project Scale

| Metric | Count |
|--------|-------|
| Controllers | 79 |
| Models | 60 |
| Database Migrations | 94 |
| Frontend Pages (TSX) | 89 |
| Feature & Unit Tests | 28 |

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Laravel 12, PHP 8.4 |
| Frontend | React 19, TypeScript, Inertia.js v2 |
| Database | PostgreSQL 16 |
| Auth | Laravel Fortify + Spatie Permission |
| Media | Spatie Media Library |
| Export | Laravel Excel, DomPDF |
| Printing | QZ Tray, Zebra ZPL |
| Analytics | Custom statistical engine |
| AI | AI gateway integration |
| UX | PWA manifest + service worker |
| i18n | English / Arabic with RTL switching |
| UI | shadcn/ui, Tailwind CSS |
| Visualization | React Flow, Recharts, dagre |

---

## Domain Coverage

```
Master Data          Crops, traits, seasons, locations, pest & disease library
Breeding             Materials, breeding units, crossings, lineage/family tree
Field Trials         Full lifecycle: design → execution → selection → harvest
Seed Inventory       Lots, transactions, storage mapping, expiry tracking
Evaluation           Evaluation trials, evaluator portal, variety advancement
Analytics            Trait analysis, segregation, heritability, generation comparison
AI                   Report generation, smart suggestions, operational workflows
Governance           Users, roles, permissions, audit log, lock screen
Printing             ZPL labels, PDF reports, seed passports
```

---

## Access

> This repository is a **portfolio showcase**. The source code is not public.
>
> For demo access, collaboration inquiries, or licensing, contact the author directly.

---

## Author

**Mohamed Hamed** — Full Stack Developer

Built as a production-grade agriculture platform combining deep domain knowledge with modern engineering.

[![GitHub](https://img.shields.io/badge/GitHub-m7amedenho-181717?style=flat-square&logo=github)](https://github.com/m7amedenho)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-m7amedenho-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/m7amedenho)
[![Portfolio](https://img.shields.io/badge/Portfolio-7amedenho.vercel.app-000?style=flat-square)](https://7amedenho.vercel.app)

---

<div align="center">

*RedGerm — Precision breeding management, built for the field.*

</div>
