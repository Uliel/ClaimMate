# ClaimMate AI: Vision

**Objective:** Make medical and financial rights accessible to policyholders in Israel under the National Health Basket (Sal HaBriut), HMO supplemental insurance plans (Shaban), and personal accident insurance, while ensuring absolute mathematical accuracy and preventing AI hallucinations[cite: 8].

**Architecture Principle:** Strict dual-pane separation[cite: 8]:
* **Right Pane (Deterministic Search):** Pure Python keyword search over official local health and insurance text documents (no AI)[cite: 8].
* **Left Pane (Personal AI Assistant):** Multi-step conversational agent combining RAG, deterministic Tool Calling, and an Agent Loop[cite: 8].

| Component | System Role | Implementation File |
| :--- | :--- | :--- |
| **RAG** | Retrieves official legal and insurance clauses from local files as context to prevent hallucinations[cite: 8] | `src/rag_engine.py`[cite: 8] |
| **Tool Calling** | Executes deterministic Python functions for 80% reimbursement (up to 650 ILS), 75% accident pay, and ambulance exemptions[cite: 8] | `src/tools.py`[cite: 8] |
| **Agent Loop** | Conducts clarifying dialogue to gather missing details (age, daily wage, fracture) and guides claim submission[cite: 8] | `src/agent.py`[cite: 8] |
| **User Interface** | Streamlit web app with a user profile sidebar, direct search pane, and AI chat pane[cite: 9] | `src/app.py`[cite: 9] |

## Covered Knowledge Domains
1. **Dental Care:** Free dental basket up to age 18, subsidized care for ages 72+, and Shaban root canal subsidies[cite: 8].
2. **Personal Accidents:** Ambulance fee exemptions (fracture/hospitalization) and National Insurance accident pay (75% of salary up to 90 days)[cite: 8].
3. **Specialist Consultations:** Up to 3 consultations per calendar year with 80% reimbursement capped at 650 ILS[cite: 8].
4. **Pregnancy & Childbirth:** Cumulative Shaban budget of up to 8,000 ILS for genetic tests, private scans, and doula services[cite: 8].

## Target End-to-End Flow
A 24-year-old policyholder reports a broken ankle, ambulance evacuation, and 14 missed workdays (300 ILS daily wage)[cite: 9]. The agent identifies both HMO and National Insurance claims, verifies full ambulance exemption via RAG (`accidents_rights.txt`), computes exact compensation of **3,150 ILS** via `calculate_accident_compensation(300, 14)`, and instructs the user to submit National Insurance Form 283[cite: 9].