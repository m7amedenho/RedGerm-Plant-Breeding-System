
<div align="center">

<pre>
██████╗ ███████╗██████╗  ██████╗ ███████╗██████╗ ███╗   ███╗
██╔══██╗██╔════╝██╔══██╗██╔════╝ ██╔════╝██╔══██╗████╗ ████║
██████╔╝█████╗  ██║  ██║██║  ███╗█████╗  ██████╔╝██╔████╔██║
██╔══██╗██╔══╝  ██║  ██║██║   ██║██╔══╝  ██╔══██╗██║╚██╔╝██║
██║  ██║███████╗██████╔╝╚██████╔╝███████╗██║  ██║██║ ╚═╝ ██║
╚═╝  ╚═╝╚══════╝╚═════╝  ╚═════╝ ╚══════╝╚═╝  ╚═╝╚═╝     ╚═╝
</pre>

### **Enterprise Plant Breeding & Trial Management System**

*From genetic material to variety release — one unified platform.*

<br/>

![Laravel](https://img.shields.io/badge/Laravel-12-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=111827)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![R](https://img.shields.io/badge/R_Lang-Statistical_Analysis-276DC3?style=for-the-badge&logo=r&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![jsreport](https://img.shields.io/badge/jsreport-000000?style=for-the-badge&logo=javascript&logoColor=white)
![OpenWeb_UI](https://img.shields.io/badge/OpenWeb_UI-000000?style=for-the-badge)
![PWA](https://img.shields.io/badge/PWA-Enabled-0ea5e9?style=for-the-badge)
![i18n](https://img.shields.io/badge/Arabic%2FEnglish-Bilingual-16a34a?style=for-the-badge)

<br/>

> Built for real operational breeding teams — not just dashboards.

</div>

---

## What is RedGerm?

RedGerm is a full-stack, domain-heavy agriculture platform that replaces fragmented spreadsheets and disconnected tools with one structured, evidence-based workflow. It connects every stage of a breeding program: from registering raw genetic material to releasing a variety — with full traceability at every step.

**The complete chain:**

```text
Material → Breeding Unit → Crossing → Trial → Selection → Harvest → Seed Inventory → Variety Decision
````

No broken links. No data loss across generations. No spreadsheet chaos.

-----

## System Architecture: Distributed Microservices Ecosystem

To ensure high availability, scalability, and optimal performance for computationally heavy tasks, RedGerm is designed around a **Microservices-oriented architecture**. Instead of relying on a single monolithic bottleneck, domain-specific tasks are delegated to specialized services.

The main **Laravel** application acts as the Core API and Orchestrator, delegating intensive workloads (like statistical analysis, AI processing, heavy reporting, and data crunching) to dedicated microservices written in the most suitable languages (**R**, **Python**, **Java**, and **Node.js** via jsreport).

### Architecture Flow

```text
                                  +-----------------------+
                                  |    User Interface     |
                                  | (React 19 + Inertia)  |
                                  +-----------+-----------+
                                              |
                                              v
+----------------+               +-------------------------+                +------------------+
|   AI Portal    | <-----------> |   CORE ORCHESTRATOR     | <------------> |    Database      |
| (OpenWeb UI)   |               | (Laravel 12 / PHP 8.4)  |                | (PostgreSQL 16)  |
+-------+--------+               |  - Auth & Governance    |                +------------------+
        |                        |  - Business Logic       |
        v                        |  - API Gateway          |
+----------------+               |  - Job Queue Management |                +------------------+
| Python Service | <-------------+-----------+-------------+--------------> | Enterprise Print |
| - AI Gateway   |               |           |             |                | & Reporting Node |
| - ML Models    |               |           v             |                |    (jsreport)    |
+----------------+      +-------------------+   +-------------------+       +------------------+
                        |   Java Service    |   |     R Service     |
                        | - Heavy Crunching |   | - Stat. Analysis  |
                        | - ZPL Queue Mgmt  |   | - Heritability    |
                        +-------------------+   +-------------------+
```

### Service Breakdown

**1. Core Orchestrator (Laravel 12)**
Acts as the central nervous system. Handles HTTP requests, Role-Based Access Control (RBAC), database transactions, and overall state management. Dispatches asynchronous events and jobs to the worker services so the main thread is never blocked by heavy operations.

**2. Statistical & Agronomic Engine (R Language)**
Dedicated purely to the mathematics of plant breeding. Receives raw trial datasets and computes rigorous agricultural statistics, including ANOVA, heritability estimates, trait segregation patterns, and principal component analysis (PCA) for multi-environment trials.

**3. AI & Data Science Node (Python)**
Dedicated environment for machine learning. Handles the Selection Algorithm computations and structures unstructured data. Acts as the backend for the AI Gateway, generating narrative reports from raw harvest data.

**4. Interactive AI Interface (OpenWeb UI)**
A self-hosted, highly customizable user interface for interacting with the AI models. Provides breeding engineers with a conversational portal to query trial data, ask for smart suggestions during setup, or request specific analytics from the Python node.

**5. High-Performance Computation Node (Java)**
Utilized for CPU-intensive, multi-threaded background processing. Manages complex data transformations (like resolving deep lineage and family trees across thousands of generations) and handles high-throughput integrations, such as batching and streaming massive ZPL print queues to thermal printers seamlessly.

**6. Dedicated Reporting Engine (jsreport)**
Offloads the memory-intensive task of generating enterprise-grade PDFs from PHP. Compiles complex templates (Trial Reports, Seed Passports with QR codes, images, and charts) using standard web technologies (HTML/CSS/JS) and converts them to high-fidelity PDFs efficiently.

-----

## Core Features

### Breeding Management

**Plant Material Registry**
Register incoming seed accessions with full metadata — crop, generation (F1–F99 and BC series), pollination type, supported breeding methods (SSD, Pedigree, Bulk, Backcross, and more). Each material gets an auto-generated structured code (`TOM-M-001`).

**Breeding Units (Known Lineage)**
When a plant is harvested from a trial, the system automatically creates a Breeding Unit with traceable parentage. Generation is auto-incremented using a smart algorithm that handles F-series, BC-series, and nested generations correctly.

**Family Tree & Lineage**
Interactive visual family tree powered by React Flow and dagre layout. Navigate the full ancestry chain from any node — material, breeding unit, or seed lot. Nodes show live stock availability. Click any ancestor to jump to its detail page.

**Crossing Module**
Record hybridization crosses with parent compatibility validation, execution tracking, pollination method, and result recording. Crosses automatically feed into the lineage graph.

### Field Trial Lifecycle

**7-Step Setup Wizard**
A guided wizard that structures trial creation from start to publish:

1.  Trial information (crop, season, location, breeding method)
2.  Entities — link materials/BUs with seed lots from inventory
3.  Trial design — CRD, RCBD, Alpha Lattice, Split Plot, Augmented, P-Rep, or Custom
4.  Plant map generation with automatic layout per design type
5.  Visit schedule planning
6.  Label printing
7.  Publish to execution

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

### Selection & Analytics

**Selection Algorithm**
Set standard trait criteria with target values, direction (max/min/exact), and weights. The system calculates a weighted similarity score for every active plant and ranks them. Engineers review the ranked list, select manually or by threshold, and confirm. Non-selected plants are automatically marked as dropped.

**Breeding Analytics**
Trait distribution analysis, generation comparison across breeding cycles, segregation pattern visualization, and heritability insights computed via the R microservice — built for making evidence-based advancement decisions.

### Variety Catalog & Evaluation

**Public Variety System**
Breeding engineers can request to publish a variety. After admin approval, it enters the public catalog where field trial engineers and external evaluators can access it. Visibility levels: `Private → Public → Released`.

**Evaluation Trial System**
A simplified but complete trial system for field trial engineers evaluating named varieties. Supports multi-location comparison of the same variety across environments.

**Variety Advancement Pipeline**
Compile evaluation results, compute performance summaries, and make structured `Continue / Drop / Adopt` decisions backed by data.

### Seed Inventory & Storage

**Storage Mapping**
Define storage locations (freezers, cold rooms, dry stores, cabinets) with shelves and slots. Slot occupancy is computed dynamically — no stale flags.

**Transaction Ledger**
Every movement is recorded: initial receipt, returns, and disposals. Running balance is maintained per transaction. No transaction can be soft-deleted — the audit trail is permanent.

### Printing Stack

**ZPL Label Printing**
Direct thermal printing via QZ Tray agent. Supports any ZPL-compatible printer. Label size is configurable with DPI-aware dot calculation. Processed efficiently via the Java microservice.

**Reporting Engine**
High-fidelity Trial Report PDFs and Seed Passports generated dynamically via the dedicated jsreport node.

### Governance & Security

**Role-Based Access Control**
Fine-grained permissions. Roles include: Admin, Researcher, Breeding Engineer, Field Trial Engineer, Evaluator, and Viewer. Every route is permission-guarded.

**Audit Trail**
Centralized audit log for sensitive actions — who did what, when, from where. Includes browser and OS fingerprint.

### Performance & Field Readiness

**PWA Support**
Full Progressive Web App with service worker and manifest. Engineers can install RedGerm on tablets and use it offline in the field.

**Bilingual (Arabic / English)**
Full RTL/LTR runtime switching. Every label, error, and tooltip is translated. Direction switches instantly without reload.

-----

## Project Scale

| Metric | Count |
|--------|-------|
| Controllers | 79 |
| Models | 60 |
| Database Migrations | 94 |
| Frontend Pages (TSX) | 89 |
| Feature & Unit Tests | 28 |

-----

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Core Backend | Laravel 12, PHP 8.4 |
| Frontend | React 19, TypeScript, Inertia.js v2 |
| Database | PostgreSQL 16 |
| Statistical Analysis | R Language |
| AI / Data Science Node | Python |
| Heavy Computation Node| Java |
| Print & Report Node | Node.js, jsreport |
| AI Interface | OpenWeb UI |
| Auth & Security | Laravel Fortify + Spatie Permission |
| UI Framework | shadcn/ui, Tailwind CSS |
| Visualization | React Flow, Recharts, dagre |

-----

## Domain Coverage

```text
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

-----

## Access

> This repository is a **portfolio showcase**. The source code is not public.
>
> For demo access, collaboration inquiries, or licensing, contact the author directly.

-----

## Author

**Mohamed Hamed**

Built as a production-grade agriculture platform combining deep domain knowledge with modern distributed systems engineering.

[](https://github.com/m7amedenho)
[](https://linkedin.com/in/m7amedenho)
[](https://7amedenho.vercel.app)

-----

<div align="center"\>

*RedGerm — Precision breeding management, built for the field.*

</div\>
