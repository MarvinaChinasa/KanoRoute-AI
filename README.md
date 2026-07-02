
```markdown
# 📍 KanoRoute AI: Secure Multi-Agent Territory Routing & Inventory Reconciler

[![Kaggle Hackathon](https://img.shields.io/badge/Kaggle-5--Day%20AI%20Agents-blueviolet?logo=kaggle)](https://www.kaggle.com)
[![Model](https://img.shields.io/badge/Gemini-2.5--Flash-orange?logo=googlegemini)](https://ai.google.dev)
[![Track](https://img.shields.io/badge/Track-Agents%20for%20Business-blue)](https://www.kaggle.com)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Bridging the Underspecification Gap in Regional FMCG Logistics Using Spec-Driven Architecture and Secure Model Context Protocol Engines**

---
---

## 1. Project Overview

**KanoRoute AI** is an intelligent, defensive multi-agent orchestration middleware system engineered for the **Agents for Business** track of the Kaggle 5-Day AI Agents Intensive. Built atop the official `google-genai` SDK, it securely transforms volatile, natural language field logistics text data into deterministic, optimal, and bounded distribution pathways.

---

## 2. Real-World Problem & The Human Cost

In the bustling open-air wholesale hubs of Northern Nigeria, distribution is a high-stakes daily battle. Consider **Alhaji Mansur & Sons Distribution Ltd.**, a mid-sized FMCG distributor coordinating fleet pipelines to thousands of micro-retailers throughout the **Kano Municipal Grid** (*Sabon Gari*, *Singa*, and *Kofar Mata* markets).

### The Daily Friction
* **Infrastructure Breakdown:** Gridlock near Kwari Market freezes field assets, wasting fuel while vans loaded to capacity idle for hours.
* **Volatile Demand Signals:** Wholesalers text message abrupt order variations due to competitor supply failures.
* **Unstructured Operational Noise:** Territory managers manage messy WhatsApp groups parsing natural language requests like *"Reroute Rep B to dodge construction; drop 50 units at the sub-depot instead."*

### Why Software Fails
Traditional ERP platforms are too rigid to digest unstructured chat records, while unshielded Large Language Models present catastrophic **"vibe coding liabilities"** (e.g., hallucinating inventory allocations or wiping transaction histories via prompt injections). Alhaji Mansur & Sons cannot risk thin margins on unshielded AI.

---

## 3. Architecture & Core Concepts

KanoRoute AI implements a secure, modular **Context-as-a-Perimeter** architecture that encloses reasoning engines within multi-layered guardrails.


```

[ Natural Language Field Report ]
│
▼
┌──────────────────────────────────────────────┐
│        L1 Central Agent Gateway              │ ──> [Context-as-a-Perimeter]
└──────────────────────────────────────────────┘
│
├─► [ Progressive Disclosure Check ]
│     Loads only: route_optimization.md / inventory_ledger.md
▼
┌──────────────────────────────────────────────┐
│    Secure Model Context Protocol (MCP)       │ ──> [Zero Ambient Authority]
└──────────────────────────────────────────────┘
│
▼
┌──────────────────────────────────────────────┐
│  Isolated Ephemeral Sandbox Container        │ ──> [Prevents State Corruptions]
└──────────────────────────────────────────────┘

```

* **Agent Skills & Progressive Disclosure:** Dynamically matches micro-scoped capability modules (`.md` specifications) based on intent. Prevents tool-bloat and cross-skill contamination.
* **Model Context Protocol (MCP Server):** Decouples internal logic from database tables (`sales_reps`, `inventory_ledger`) through strict JSON schemas instead of raw database connector code.
* **Zero Ambient Authority & Sandboxing:** Implements JIT token downscoping. Computational paths run in sandboxed contexts protected by an automated circuit breaker.

---

## 4. Project Structure

```text
KanoRoute-AI/
├── src/
│   └── agent_harness.py        # Core secure agent architecture and monkey-patch guards
├── notebooks/
│   └── kanoroute_agent_harness.ipynb  # Interactive Verification Notebook (ipywidgets UI)
├── skills/
│   ├── route_optimization.md   # Domain-specific constraints for route execution
│   └── inventory_ledger.md     # Structural bounds for ledger updates
├── README.md                   # Complete repository documentation
└── requirements.txt            # Python dependencies

```

---

## 5. Installation & Setup

### Prerequisites

* Python 3.10 or higher
* A Google Gemini API Key

### Step-by-Step Installation

1. **Clone the Repository:**
```bash
git clone [https://github.com/MarvinaChinasa/KanoRoute-AI.git](https://github.com/MarvinaChinasa/KanoRoute-AI.git)
cd KanoRoute-AI

```


2. **Install Dependencies:**
```bash
pip install -r requirements.txt

```


3. **Configure Environment Variables:**
* **Local Environment:**
```bash
export GEMINI_API_KEY="your_actual_api_key_here"

```


* **Kaggle Environment:** Add your key via **Add-ons -> Secrets** with the label name exactly matching `GEMINI_API_KEY`.



---

## 6. Verification & Sample Output

Run the interactive verification loop inside `notebooks/kanoroute_agent_harness.ipynb`.

### Step 1: Handling Underspecified Intents

Input prompt: *"Optimize weekly biscuit distribution itinerary for Reps A through E inside Kano Municipal grid."*

**Harness Defensive Intercept:**

```json
{
  "status": "pending_information",
  "message": "To optimize the weekly biscuit distribution itinerary for Reps A through E within the Kano Municipal grid, I require a list of specific distribution points (addresses or coordinates) for each representative. Please provide this information to proceed with route optimization.",
  "skill_invoked": "route_optimization.md"
}

```

### Step 2: Full Context Fulfillment

When parameter fields are supplied via the interactive `ipywidgets` interface, the system returns a safe, deterministic operational schedule:

```json
{
  "optimized_routes": [
    {
      "rep_id": "Rep A",
      "sequence_of_stops": ["Kano Central FMCG Warehouse, Zone 4", "Kofar Mata Market", "Kano Central FMCG Warehouse, Zone 4"],
      "estimated_distance_km": 10.0,
      "estimated_duration_hours": 1.0,
      "quantity_delivered_crates": 150
    },
    {
      "rep_id": "Rep B",
      "sequence_of_stops": ["Kano Central FMCG Warehouse, Zone 4", "Sabon Gari Market", "Kano Central FMCG Warehouse, Zone 4"],
      "estimated_distance_km": 14.0,
      "estimated_duration_hours": 1.2,
      "quantity_delivered_crates": 200
    }
  ],
  "total_distance_all_reps_km": 50.0,
  "total_duration_all_reps_hours": 5.0
}

```

---

## 7. Business Value & Telemetry Insights

* **Route Efficiency Index Optimization:** Consolidated five independent delivery matrices down to a clean **50.0 km cumulative route path**, slashing structural fuel expenditures.
* **Capacity Balancer Analytics:** Discovered real-time fleet load disparities (e.g., Rep D running at 60% capacity vs. Rep E at 18%), enabling instant scheduling re-allocations.
* **Unsupervised ML Telemetry Diagnostics:** Pipelines ingest conversational correction traces, processing them through text embeddings and **$K$-Means Clustering** to isolate underlying operational failure loops (e.g., chronic traffic blocks vs. vendor variations) for strategic business intelligence tracking.

---

*Developed as part of the Kaggle 5-Day AI Agents Course.*

```