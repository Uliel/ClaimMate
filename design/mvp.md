# ClaimMate AI: MVP

Pain: policyholders in Israel struggle to understand their medical and financial rights across the National Health Basket, HMO supplemental plans (Shaban), and accident insurance, leading to missed reimbursements and inconsistent answers from complex circulars.

Product: an assistant for policyholders that combines a deterministic keyword search engine for instant retrieval of official clauses with a personal AI agent. For each user inquiry, it retrieves verified regulations, asks clarifying questions when details are missing, calculates exact payouts and exemptions using Python tools, and guides the user on how to submit a claim.

| Feature                                                                      | Technique                 |
| ---------------------------------------------------------------------------- | ------------------------- |
| Searching keywords directly in local official health and insurance files     | Ordinary code (not AI)    |
| Retrieving official legal and insurance clauses from the knowledge base     | RAG                       |
| Calculating 80% reimbursement caps, 75% accident pay, and ambulance exemption | Tool calling              |
| Clarifying missing user details (age, daily wage, fracture) and guiding claims | Agent loop / Multi-turn   |
| Displaying user profile, direct search, and AI chat in a dual-pane interface | Ordinary code (Streamlit) |