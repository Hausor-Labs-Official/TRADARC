# 🌐 TradArc: The Generative AI Cross-Border Procurement Co-Pilot

Your One-Sentence Cross-Border Procurement Co-Pilot for the Global South.

## 📝 Executive Summary
TradArc is a generative AI-powered process automation tool built on IBM watsonx Orchestrate. It tackles the single biggest barrier to economic growth in the Global South: Cross-Border Trade Friction. By condensing weeks of manual procurement work—including supplier sourcing, tariff compliance, PO generation, and payments—into a single natural language command, TradArc turns a complex, multi-week economic bottleneck into a 5-minute digital workflow.

### Problem Statement
Intra-regional trade in emerging markets is at record lows (e.g., 17% in Africa) due to fragmented regulatory frameworks, manual compliance checks, and complex payment settlements.

## ✨ Core Solution: Agentic Workflow
TradArc is not a chatbot; it is an Agentic Workflow that executes tasks. The entire procurement process is initiated from a simple command in an interface like Slack or MS Teams.

**Example Command:**
Buy 500 tons of maize from Zambia for my Kenyan factory, price under $300/ton, ensure AfCFTA compliance, pay 30% advance and 70% upon Bill of Lading.


### The 7-Step Orchestration Flow
The agent performs the following steps in under 5 minutes:

1. **Intent Recognition:** Parses the Slack command to extract key variables (Item, Origin, Destination, Price Cap, Payment Terms).  
2. **Supplier Sourcing:** Queries ZoomInfo for verified suppliers (e.g., "Maize Exporters in Zambia").  
3. **RFQ Automation:** Generates and sends professional emails to identified suppliers via Gmail/Outlook.  
4. **Regulatory Check (AI):** Consults the AfCFTA rulebook and uses watsonx.ai (Granite LLM) to analyze trade rules, verify Rules of Origin, and confirm if goods qualify for 0% tariffs.  
5. **Contract Generation:** Creates a Purchase Order (PO) and a Certificate of Origin using DocuSign, sending it to the manager for a "One-Click Approval".  
6. **Smart Payment (Phase 1):** Upon approval, triggers a 30% advance payment via the Flutterwave custom skill.  
7. **Delivery Validation (Phase 2):**  
   - **Trigger:** watsonx watches a specific Google Drive folder for the Bill of Lading PDF upload.  
   - **Validation:** watsonx "reads" the PDF to verify the shipment weight.  
   - **Settlement:** The Agent releases the remaining 70% payment and updates the Google Sheet Audit Log.  

## ⚙️ Technical Architecture & Tools

TradArc is 100% built within the IBM Cloud ecosystem, utilizing watsonx Orchestrate as the central brain.

| Layer           | Component             | Tool Used                  | Implementation Type       |
|-----------------|---------------------|----------------------------|--------------------------|
| Interface       | User Command         | Slack (or MS Teams)        | Pre-built Connector      |
| Reasoning       | Decision Logic & NLP | watsonx.ai (Granite Models)| Native Integration       |
| Data Source     | Supplier Intelligence| ZoomInfo                   | Pre-built Connector      |
| Communication   | Vendor Outreach      | Gmail / Outlook            | Pre-built Connector      |
| Documentation   | POs & Contracts      | DocuSign                   | Pre-built Connector      |
| Compliance      | Document Analysis    | watsonx.ai + Drive         | Native + Pre-built       |
| Payments        | Financial Settlement | Flutterwave (Africa)       | Custom Skill (OpenAPI)   |
| Audit           | ERP/Record Keeping   | Google Sheets              | Pre-built Connector      |

## 🌍 Global Scalability: The Modular Advantage
The core architecture of TradArc is modular. By swapping the Regulatory Knowledge Base and the Payment Gateway, the system adapts immediately to new regions, maximizing its commercial potential.

### The LatAm Configuration: "Mercosur Connect"

| Swap Element         | Africa (Default)       | Latin America (LatAm)                    |
|---------------------|----------------------|----------------------------------------|
| Regulatory Knowledge | AfCFTA Rulebook       | ACE 14 and Mercosur Common External Tariff rules |
| Payment Gateway      | Flutterwave           | Mercado Pago or dLocal (Custom Skill)  |
| Language             | English (Granite prompt)| Spanish/Portuguese (Granite prompt)   |
| Compliance Check     | AfCFTA documents      | Certificado de Origen Digital (COD)    |

## 🚀 Deployment Readiness
TradArc is a functional Proof-of-Concept (PoC) built using features available in watsonx Orchestrate as of November 2025.

- **Implementation Notes:** The logic is parameterized, enabling the LatAm module instantly by swapping prompts and APIs.  
- **Status:** It is a ready-to-deploy enterprise agent that lives inside an organization's watsonx Orchestrate instance.  
- **Catalog Candidate:** This solution is built to be a reference-grade implementation, suitable for future inclusion in the IBM watsonx Orchestrate Agent Catalog as a supply-chain template.

## 🔗 Repository & Assets
https://github.com/Hausor-Labs-Official/TRADARC
