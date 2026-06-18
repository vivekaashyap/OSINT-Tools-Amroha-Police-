# OSINT Link Analysis Platform

## AI-Assisted Digital Evidence Mapping & Investigation Support System

**Developed during:** Amroha Police × Shri Venkateshwar University Cybersecurity Internship Program

---

# Executive Summary

Cybercrime investigations often involve multiple disconnected digital artifacts such as phone numbers, email addresses, social media profiles, IP addresses, domains, and suspect identities. Investigators frequently store this information across spreadsheets, notebooks, and case files, making correlation difficult.

The OSINT Link Analysis Platform provides a visual investigation environment where officers can map entities, establish relationships, maintain evidence integrity through hashing and timestamps, and receive AI-assisted investigative guidance based on Indian cyber law frameworks.

---

# Problem Statement

Current investigation workflows face several challenges:

## Data Fragmentation

Evidence is distributed across multiple sources.

## Relationship Discovery

Connections between entities are difficult to identify manually.

## Evidence Integrity

Maintaining a reliable chain of custody is challenging.

## Legal Mapping

Investigators must manually determine relevant IT Act and BNS sections.

## Reporting Delays

Preparing structured investigation reports consumes significant time.

---

# Proposed Solution

The OSINT Link Analysis Platform acts as a digital investigation board.

Investigators can:

- Create digital evidence nodes
- Connect related entities
- Visualize criminal networks
- Preserve evidence metadata
- Generate AI-assisted investigation insights
- Export investigation reports

---

# Key Features

## 1. Entity Management

Supported evidence types:

| Type | Description |
|--------|------------|
| Phone Number | Mobile numbers |
| Email | Email addresses |
| Domain | Websites/domains |
| Person | Suspects/Victims |
| Social Media | Social accounts |
| IP Address | Network identifiers |

Each entity contains:

- Unique ID
- Timestamp
- SHA-256 Hash
- Notes
- Alias
- Risk Label

---

## 2. Relationship Analysis

Create links between entities.

Examples:

| Source | Relationship | Target |
|----------|-------------|---------|
| Phone | Uses | Email |
| Email | Registered On | Domain |
| Person | Owns | Phone |
| IP | Accessed | Domain |

Visualization is performed through Cytoscape.js.

### Benefits

- Rapid network understanding
- Crime pattern visualization
- Evidence correlation

---

## 3. Evidence Integrity Module

Every entity automatically receives:

### SHA-256 Hash

Used for:

- Integrity verification
- Tamper detection
- Digital evidence preservation

### Timestamp

Records:

- Date
- Time
- Evidence entry sequence

Supports digital chain-of-custody requirements.

---

## 4. AI Investigation Assistant

One-click analysis using Gemini AI.

### Output Includes

#### Risk Assessment

- Critical
- High
- Medium
- Low

#### Crime Pattern Detection

Examples:

- UPI Fraud
- Phishing
- Identity Theft
- Social Engineering
- Fake Investment Scam

#### Legal Mapping

Suggests relevant:

- Information Technology Act, 2000
- Bharatiya Nyaya Sanhita (BNS)

#### Investigation Recommendations

Examples:

- Preserve logs
- Request CDR records
- Issue notices
- Conduct platform tracing
- Analyze linked entities

---

## 5. Investigation Registry

Centralized evidence panel displaying:

- Node Type
- Value
- Notes
- Alias
- Timestamp
- Hash
- Risk Score

---

## 6. Report Generation

### PDF Export

Generates:

- Evidence Table
- Relationship Table
- AI Analysis Summary
- Investigation Timeline

### JSON Export

Provides:

- Complete structured backup
- Case portability
- Future system integration

---

# Impact

The platform helps investigators:

- Visualize complex cybercrime networks
- Maintain evidence integrity using SHA-256 hashing
- Reduce manual investigation effort
- Generate structured investigation reports
- Map evidence with relevant IT Act and BNS provisions
- Improve digital evidence organization at district cyber cells

This makes the platform particularly useful for small and medium cyber police units that may not have access to enterprise-grade intelligence platforms.

---

# Innovation

Unlike traditional OSINT tools, this platform focuses on:

- Indian cyber law context
- Evidence integrity preservation
- AI-assisted legal mapping
- Zero-installation deployment
- Lightweight single-file architecture

The system is designed as an investigation-support platform rather than a data-collection platform.

---

# System Workflow

```text
Officer Adds Evidence
          │
          ▼
Generate SHA-256 Hash
          │
          ▼
Generate Timestamp
          │
          ▼
Create Investigation Node
          │
          ▼
Create Relationships
          │
          ▼
Visual Graph Generation
          │
          ▼
AI Case Analysis
          │
          ▼
Risk & Law Assessment
          │
          ▼
Export Investigation Report
```

---

# Technology Stack

| Component | Technology |
|------------|-------------|
| Frontend | HTML5 |
| Styling | CSS3 |
| Logic | JavaScript |
| Graph Engine | Cytoscape.js |
| Layout Engine | Cose-Bilkent |
| Hashing | Web Crypto API |
| PDF Reports | jsPDF |
| AI Analysis | Gemini 2.5 Flash |
| Storage | Browser LocalStorage |

---

# Cyber Law Relevance

## IT Act Alignment

The platform assists investigators in identifying potential applicability of:

- Section 66
- Section 66C
- Section 66D
- Section 67
- Section 69

*(AI suggestions are advisory only.)*

## BNS Alignment

The system can suggest sections associated with:

- Cheating
- Impersonation
- Fraud
- Criminal Conspiracy
- Digital Financial Crimes

---

# Operational Benefits for Police

### Faster Investigation

Visual mapping reduces manual correlation effort.

### Better Evidence Management

Hashing and timestamps improve evidence reliability.

### Reduced Report Preparation Time

Automated export functionality.

### Improved Crime Network Understanding

Graph visualization exposes hidden relationships.

### Useful for Small Cyber Cells

No expensive infrastructure required.

---

# Comparison with Existing Solutions

| Feature | Maltego | SpiderFoot | This Platform |
|----------|----------|------------|--------------|
| Visual Link Analysis | Yes | Limited | Yes |
| AI Investigation Support | No | No | Yes |
| IT Act Suggestions | No | No | Yes |
| Single File Deployment | No | No | Yes |
| Cost | High | Medium | Free |

---

# Current Limitations

- No live OSINT collection
- No database backend
- No user authentication
- No role-based access control
- Single-user environment
- Prototype stage only

---

# Future Enhancements

## Phase 2

- Backend Database
- Case Management System
- User Authentication
- Multi-Officer Collaboration

## Phase 3

- Complaint Import Integration
- AI-Powered Link Prediction
- Timeline Analysis
- Geolocation Visualization

## Phase 4

- Mobile Application
- Offline AI Models
- Advanced Intelligence Dashboard
- State-Level Deployment Architecture

---

# Potential Use Cases

## UPI Fraud Investigation

Track:

- Victim
- UPI ID
- Bank Account
- Phone Number
- Device Information

## Phishing Campaign Analysis

Track:

- Domain
- Email
- Hosting Infrastructure
- Suspect Accounts

## Social Media Harassment

Track:

- Fake Profiles
- Phone Numbers
- Email Accounts
- IP Addresses

## Digital Financial Fraud

Track:

- Wallets
- Accounts
- Devices
- Communication Channels

---

# Conclusion

The OSINT Link Analysis Platform demonstrates how affordable, lightweight technology can support cybercrime investigations by combining:

- Visual Link Analysis
- Evidence Integrity
- AI-Assisted Investigation
- Indian Cyber Law Context

The platform is designed as a practical proof-of-concept that can evolve into a full-scale cyber investigation support system for district-level cyber cells and law enforcement agencies.

---

# Author

**Vivek Kashyap**  
B.Tech CSE (Cyber Security)  
GLA University, Mathura

**Cybersecurity Intern**  
Amroha Police × Shri Venkateshwar University

GitHub: https://github.com/vivekaashyap

---

# License

This project is released under the MIT License.
