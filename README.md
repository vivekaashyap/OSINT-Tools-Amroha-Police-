# 🔗 OSINT Link Analysis Platform

> A visual link-analysis tool for cyber crime investigators — built for the Amroha Police Cybersecurity Internship Program, in collaboration with Shri Venkateshwar University, with potential showcase at Lucknow Cyber Headquarters.

![Status](https://img.shields.io/badge/status-prototype-orange)
![License](https://img.shields.io/badge/license-MIT-blue)
![Made with](https://img.shields.io/badge/made%20with-HTML%2FCSS%2FJS-yellow)

---

## 📋 Table of Contents

- [Problem Statement](#-problem-statement)
- [Solution Overview](#-solution-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Screenshots](#-screenshots)
- [How It Works](#-how-it-works)
- [Setup & Installation](#-setup--installation)
- [Usage Guide](#-usage-guide)
- [Cyber Law Integration](#-cyber-law-integration)
- [Comparison with Existing Tools](#-comparison-with-existing-tools)
- [Limitations](#-limitations)
- [Future Scope](#-future-scope)
- [Disclaimer](#-disclaimer)
- [Author](#-author)

---

## 🎯 Problem Statement

During cyber crime investigations, officers collect evidence from multiple disconnected sources — phone numbers, email addresses, fake domains, social media handles, IP addresses. This data is typically scattered across case diaries, spreadsheets, or an officer's memory, making it difficult to:

- Visually identify how pieces of evidence relate to one another
- Track which entity was added when, and by whom
- Maintain a tamper-proof record of evidence for court submission
- Quickly map out a crime network during active investigation

## 💡 Solution Overview

**OSINT Link Analysis Platform** lets an investigator manually input evidence as **nodes** (Phone, Email, Domain, Person, Social Media, IP Address) and connect them with labeled **relationships** (e.g., "owns", "contacts", "registered"). The tool renders this as an interactive graph, automatically generates a **SHA-256 hash** and timestamp for every piece of evidence added, and uses AI to suggest applicable **IT Act / BNS sections** and next investigative steps.

Think of it as a digital evidence board — the strings-and-pins conspiracy board from movies, rebuilt as a structured, court-aware digital tool.

---

## ✨ Features

### 🧩 Node Management
- Six node types: **Phone, Email, Domain, Person, Social Media, IP Address**
- Each type has a distinct color and shape on the graph for instant visual recognition
- Optional alias/label and free-text notes per node

### 🔗 Relationship Mapping
- Connect any two nodes with a custom relationship label
- Directed edges (arrows) show relationship direction
- Interactive force-directed graph layout (Cytoscape.js + cose-bilkent)

### 🔒 Evidence Integrity (Cyber Law Angle)
- **SHA-256 hash** auto-generated for every node at the moment of creation
- **ISO timestamp** logged for every node and edge
- Designed to support the chain-of-custody requirement for digital evidence in court

### 🤖 AI-Powered Case Analysis
- One-click **"ANALYZE"** sends the full case (nodes + relationships) to an AI model
- Returns:
  1. Risk Level (Critical / High / Medium / Low) with reasoning
  2. Likely crime pattern
  3. Relevant **IT Act** / **BNS** sections
  4. Suggested next investigation steps
- Runs on the free-tier Gemini API — no paid subscription required

### 📊 Node Registry & Inspection
- Scrollable sidebar list of all nodes in the case
- Click any node (on graph or in registry) to view full details: type, value, alias, notes, timestamp, SHA-256 hash, and an auto-assigned risk badge

### 📄 Reporting & Export
- **PDF Export** — generates a formatted investigation report with node table, relationship table, and AI analysis, ready for documentation
- **JSON Export** — full case backup in structured format

### 🎨 Interface
- Dark, cyber-themed UI built for low-light investigation environments
- Live status bar showing node count, edge count, and case integrity status
- Toast notifications for every action (success/error)

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Structure | HTML5 |
| Styling | Custom CSS (dark theme, no framework) |
| Logic | Vanilla JavaScript (no build step) |
| Graph Visualization | [Cytoscape.js](https://js.cytoscape.org/) + cose-bilkent layout |
| Hashing | Web Crypto API (native browser SHA-256) |
| PDF Generation | [jsPDF](https://github.com/parallax/jsPDF) + jsPDF-AutoTable |
| AI Analysis | Google Gemini API (`gemini-2.5-flash`, with automatic fallback) |
| Storage | Browser `localStorage` (for API key only — no case data persistence yet) |

No backend, no database, no build tools. Runs entirely client-side from a single HTML file.

---

## 📸 Screenshots

> Add screenshots here before pushing to GitHub:
> - Empty state (sidebar + empty graph)
> - Graph with multiple connected nodes
> - Node detail panel with SHA-256 hash visible
> - AI analysis result panel
> - Exported PDF report

```
/screenshots
  ├── 01-empty-state.png
  ├── 02-graph-with-nodes.png
  ├── 03-node-detail-panel.png
  ├── 04-ai-analysis.png
  └── 05-pdf-export.png
```

---

## ⚙️ How It Works

```
Officer adds a node (e.g. Phone: 9876543210)
        │
        ▼
Browser generates SHA-256 hash + ISO timestamp
        │
        ▼
Cytoscape.js renders the node on the graph
        │
        ▼
Officer links nodes with a relationship label
        │
        ▼
Officer clicks "ANALYZE"
        │
        ▼
Case data sent to Gemini API
        │
        ▼
AI returns risk level, crime pattern, IT Act/BNS sections, next steps
        │
        ▼
Officer exports PDF (court-ready) or JSON (raw backup)
```

---

## 🚀 Setup & Installation

### Prerequisites
- Any modern browser (Chrome, Edge, Firefox)
- A free [Google Gemini API key](https://aistudio.google.com/) for the AI analysis feature
- Internet connection (for CDN libraries and AI calls)

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/osint-link-analyzer.git
cd osint-link-analyzer

# 2. Open directly in browser
# Simply double-click index.html
# OR serve it locally for best results:
```

**Recommended: Use VS Code Live Server**
1. Open the folder in VS Code
2. Install the "Live Server" extension
3. Right-click `index.html` → "Open with Live Server"

No `npm install`, no build step — it just works.

---

## 📖 Usage Guide

1. **Add a node** — select a type from the dropdown, enter a value, optional alias/notes, click "Add Node"
2. **Link nodes** — select two existing nodes from the dropdowns, add a relationship label, click "Add Edge"
3. **Inspect a node** — click it on the graph or in the Node Registry sidebar
4. **Run AI analysis** — click "ANALYZE" (first time will prompt for your Gemini API key, which is then stored locally in your browser — never hardcoded in the file)
5. **Export** — use "EXPORT PDF" for a report or "JSON" for a raw data backup
6. **Clear case** — resets everything (with confirmation prompt)

> 🔑 **Security note:** Never commit your API key into `index.html` or any file pushed to GitHub. The tool is designed to ask for it once and store it only in your browser's local storage.

---

## ⚖️ Cyber Law Integration

This tool is built with Indian cyber law context in mind:

- **Evidence Integrity:** SHA-256 hashing + timestamps support the chain-of-custody principle required for digital evidence admissibility in Indian courts.
- **AI Law Mapping:** The analysis engine is prompted specifically to suggest relevant **Information Technology Act, 2000** and **Bharatiya Nyaya Sanhita (BNS)** sections based on the case pattern — not generic legal text.
- **Investigation Workflow:** Designed around how an Indian police cyber cell actually works (FIR → evidence collection → pattern identification → legal section mapping → report), not just a citizen-facing awareness tool.

---

## 📊 Comparison with Existing Tools

| Tool | Cost | Indian Law Mapping | Offline-Capable Core | Setup Complexity |
|---|---|---|---|---|
| Maltego | ~$999/year | ❌ No | ❌ No | High |
| SpiderFoot | Free | ❌ No | Partial | Medium |
| theHarvester | Free | ❌ No | ❌ No | Medium (CLI) |
| **This Project** | Free | ✅ Yes (IT Act/BNS) | ✅ Yes (graph core) | None (single file) |

This isn't a replacement for professional OSINT suites — it's a lightweight, accessible, India-context alternative aimed at smaller police units without enterprise tooling budgets.

---

## ⚠️ Limitations

Being transparent about what this currently **doesn't** do:

- **No live OSINT scraping** — all data is manually entered by the investigator. This is intentional: live scraping of phone/social/email databases raises real legal and privacy concerns and was avoided rather than worked around.
- **No persistent backend/database** — case data lives in browser memory during the session; closing the tab loses unsaved work unless exported as JSON beforehand.
- **No multi-user collaboration** — single-officer use only in current form.
- **No authentication/login system** — not designed for shared/public deployment as-is.
- This is a **prototype / proof-of-concept**, not production-ready law enforcement software.

## 🔭 Future Scope

- Node.js + Express backend with persistent case storage (database-backed)
- Multi-officer collaborative case editing
- Integration with [cybercrime.gov.in](https://cybercrime.gov.in) complaint data
- Role-based access control for different ranks/departments
- Mobile-responsive / native app version
- Offline AI model option for fully air-gapped use

---

## 📄 Disclaimer

This project is an academic prototype built for an educational cybersecurity internship program. It is **not an officially deployed or endorsed tool of any police department**. It does not perform live surveillance, scraping, or data collection from third-party platforms. All evidence in the tool is manually entered by the user for demonstration and investigative-workflow purposes only.

---

## 👤 Author

**Wei**
BTech CSE Student | Cybersecurity Internship Participant (Amroha Police × Shri Venkateshwar University)

---

## 📜 License

This project is open-sourced under the MIT License — see the [LICENSE](LICENSE) file for details.
