# AI-Powered Cybersecurity Alert Triage 🤖
## Project Goal
Use AI to automatically identify real cybersecurity threats and filter out noise from thousands of alerts, saving time, money, and effort for analysts.

---


## 1. The Problem: Too Many Alerts

- Security systems (EDR) generate **thousands of logs daily**.
- Human analysts experience **alert fatigue** and can miss real attacks.
- Sending every single log to AI is **expensive and slow**.

---


## 2. Project Setup (The Lab)

- **System:** Ubuntu Server running Docker containers  
- **Core Components:**  
  - **Wazuh Manager** – Threat detection & log analysis  
  - **Wazuh Agent** – Installed on Ubuntu host  
  - **auditd** – Linux auditing system for syscall-level monitoring  
  - **n8n** – Workflow automation & AI orchestration  
  - **Gemini AI** – Intelligent alert triage engine  

- **Testing & Simulation:**  
  - **Atomic Red Team** – Simulates real-world attack techniques (MITRE ATT&CK)  

---


## 3. The Smart Trick: Aggregation

- Instead of analyzing hundreds of logs one by one, the agent **groups similar alerts** together.
- Example: 301 routine system logs → counted as **one group**, freeing the AI to focus on unusual events.
- Benefits:
  - Saves compute resources
  - Reduces unnecessary AI queries
  - Highlights unique, potentially dangerous alerts

---


## 4. Live Demo Results

- **Scenario:** 305 alerts in 24 hours
- **AI Triage Outcome:**
  - **Noise:** 301 routine system checks → ignored
  - **Real Threats:** 2 suspicious logins and 1 unauthorized USB connection → flagged
- Analysts are directed to **ignore noise and act on real threats immediately**

---


## 5. Why This Matters

- **Fast:** Triage in seconds instead of hours
- **Accurate:** Uses "grounding" to rely on real data from Wazuh
- **Cost-effective:** 90% fewer tokens used by aggregating logs before AI analysis

---


6. References

EDR Alert Fatigue
Wazuh Official
Atomic Red Team
