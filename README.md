# CostOps Copilot — AI for Enterprise Cost Intelligence & Autonomous Action

**Team:** Avengers  
**Team Leader:** Nithya Sri R  
**Team Members:** Bhuvana P, Suja J, Tharanishree R

## Problem
Enterprises lose money through hidden cost leakage and inefficiencies across procurement, vendors, operations, and SLAs. Dashboards show data, but they do not prevent loss.

**Goal:** Build an AI system that goes beyond dashboards. It should continuously monitor enterprise data, detect cost leakage patterns, and initiate corrective actions with quantifiable financial impact, while working within enterprise approval workflows.

## Solution (What we built)
**CostOps Copilot** is an AI-driven CostOps system that:
- Continuously monitors spend and operational signals
- Detects leakage patterns (duplicates, rate drift, penalty risk, idle resources)
- Produces evidence-backed findings with confidence scores
- Computes **₹ impact (show the math)**
- Triggers **approved actions** (not just reports)
- Maintains an audit log and savings ledger

## Key Features
### 1) Spend Intelligence (Duplicate Invoice Detection)
- Detects likely duplicate invoices using vendor, amount, PO, date, and reference matching
- Generates a recommended playbook
- Proposes action: **Request approval to hold payment** and **Create AP ticket**

### 2) Enterprise Approval Workflow (Action, not just insight)
- Action lifecycle: **Proposed → Approved → Executed → Audited**
- Approver options: Approve, Reject, Ask for info
- Full audit trail for enterprise compliance

### 3) Quantified Business Impact (Show the Math)
Every finding includes a clear impact calculation and is tracked in a savings ledger.

**Example (Duplicate invoice)**
- Amount at risk: ₹84,500  
- Action: Hold payment approval + AP ticket  
- Prevented payout: **₹84,500 saved**

## Architecture (Technical Depth)
**Data Integration Layer**
- Procurement and invoice data
- Vendor master and contract/policy text
- Operational signals (SLA metrics, queues, service events)
- Resource utilization (tools/cloud/licenses)

**Intelligence Layer**
- Rules + anomaly detection for precise leakage detection
- Contract/policy validation (RAG)
- LLM for explanations and playbook generation

**Action & Governance Layer**
- Approval workflow and policy gates
- Downstream workflow triggers (tickets, payment hold request)
- Audit log and savings ledger

## Live Demo Flow (What judges will see)
1. New invoice / ops signals arrive
2. System generates a **Finding** with evidence + confidence + ₹ impact
3. User clicks **Request approval**
4. Finance approves in **Approval Workflow**
5. System triggers workflow (ticket/payment hold)
6. Savings ledger updates with quantified impact + audit log

## Screens (Prototype)
- Executive Dashboard
- Finding Detail (Duplicate Invoice)
- Approval Workflow Inbox

## Repository Structure (Suggested)
- `/docs` — pitch deck, screenshots, architecture notes
- `/data` — sample CSVs (sanitized)
- `/src` — detection logic + orchestration (optional, based on implementation)

## Notes
- No secrets should be committed (API keys, credentials).
- Demo data is sanitized / mock data for presentation purposes.
