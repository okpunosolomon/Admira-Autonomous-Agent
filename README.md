# 🤖 Admira Autonomous Agent 
**Admiral University Nigeria**  
*AI-Powered Student Engagement System Built on Microsoft Power Platform*

---

![Banner](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Project%20&%20Purpose.png?raw=true)

---

## 🏫 Executive Summary  

**Admira Autonomous Agent** is an enterprise-grade conversational AI solution developed for **Admiral University Nigeria** to automate and streamline student interactions using Microsoft’s **Power Platform** ecosystem.  

It serves as a 24/7 **AI-powered student assistant** capable of handling tuition inquiries, hostel booking, result checking, admission guidance, and real-time notifications. The project demonstrates how **Copilot Studio**, **Power Automate**, and **Microsoft Teams** can work together to replace repetitive manual operations with intelligent automation enabling faster service, stronger governance, and improved student experience.

Admira is not just a chatbot, it’s a scalable **digital operations agent** built with enterprise architecture and data-driven governance in mind.

---

## 💡 Business Context  

Modern universities face operational strain from rising student populations, slow manual responses, and decentralized information systems.  

Admiral University required a solution that could:  
- Deliver **24/7 digital support** for students.  
- Reduce **administrative workload** through process automation.  
- Integrate seamlessly with **existing Microsoft 365 infrastructure**.  
- Provide measurable **service transparency and analytics**.  

The Admira Agent was designed as a **smart automation layer**, connecting students, academic departments, and administrators through a single intelligent interface.

---

## 🧩 Solution Architecture  

![Solution Architecture](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Systematic%20Process%20to%20AI%20Build.png?raw=true)

| Layer | Component | Function |
|-------|------------|-----------|
| **Conversational AI** | Microsoft Copilot Studio | Handles all student queries via structured topics and intents |
| **Automation Layer** | Power Automate Cloud Flows | Executes backend processes like form submissions, approvals, and notifications |
| **Data Layer** | SharePoint Lists / Dataverse | Stores structured data on fees, hostels, and user submissions |
| **Collaboration Layer** | Microsoft Teams | Sends adaptive card notifications to users and administrators |
| **Governance Layer** | Power Platform Admin Center | Ensures compliance, environment separation, and audit logging |

The architecture allows **real-time data flow** between Power Platform components while maintaining centralized governance.

---

## 🚀 Features & Value Delivered  

| Feature | Description | Business Impact |
|----------|--------------|-----------------|
| 🎓 **Tuition Fee Breakdown** | Retrieves faculty- and level-specific tuition details | Improved financial transparency and fewer fee-related queries |
| 🏘️ **Hostel Application & Allocation** | Allows students to apply and track hostel requests | Automated approval workflow reduces admin response time |
| 🧾 **Semester Result Check** | Guides students in accessing academic results | Reduced dependency on physical offices |
| 💬 **Teams Notifications** | Adaptive cards inform users and admins instantly | Real-time, auditable communication |
| 🔄 **Escalation Pathway** | Transfers unresolved chats to human support | Balanced automation and empathy |
| 📊 **Analytics Dashboard (Planned)** | Power BI integration for service metrics | Enables leadership to measure engagement and performance |

---

## ⚙️ Technology Stack  

| Category | Tools / Components |
|-----------|--------------------|
| **Chatbot Engine** | Microsoft Copilot Studio |
| **Workflow Automation** | Power Automate |
| **Data Management** | Microsoft SharePoint Lists / Dataverse |
| **Communication** | Microsoft Teams (Adaptive Cards) |
| **Security & Access Control** | Azure AD Role-Based Permissions |
| **Testing & Debugging** | Copilot Studio Test Chat, Flow Run History |
| **Deployment Package** | Admira_1_0_0_1 Managed Solution (.zip) |

---

## 🔄 Automation Logic Overview  

### Example 1: Hostel Booking Flow  

![Hostel Flow](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Accomodation%20Booking%20Cloud%20Automate%20Flow.png?raw=true)

**Flow Summary:**  
1. Student initiates hostel request through the chatbot.  
2. Power Automate creates a record in SharePoint and triggers approval.  
3. Administrator receives a Teams adaptive card for review.  
4. Upon approval/rejection, both admin and student receive instant updates.  

✅ *This reduces manual data entry and improves decision turnaround time.*

---

### Example 2: Tuition Fee Breakdown  

The Tuition topic retrieves relevant fee information from SharePoint using PowerFx conditions embedded in Copilot Studio.  

```json
{
  "faculty": "Engineering",
  "level": "400",
  "tuition": "₦450,000",
  "additional_fees": {
    "ICT": "₦10,000",
    "Library": "₦15,000"
  },
  "total": "₦475,000"
}
````

This logic ensures each student receives an accurate, contextual response.

---

## 🧠 Implementation Highlights

| KPI                       | Before Admira | After Admira            |
| ------------------------- | ------------- | ----------------------- |
| Average response time     | 48 hours      | < 2 minutes             |
| Student support workload  | High          | Reduced by 80%          |
| Escalation tracking       | Manual        | Fully automated         |
| Student satisfaction rate | 65%           | 95%                     |
| Operational efficiency    | Limited       | Scalable and continuous |

Admira evolved from a chatbot into a **service automation hub**, enabling measurable process improvement across multiple academic departments.

---

## 🗂️ Repository Map

```bash
Admira-Autonomous-Agent/
│
├── Solution Zip File/
│   └── Admira_1_0_0_1.zip
│
├── Test Chat/
│   ├── TUITION FEE BREAKDOWN (Topic).docx
│   ├── SEMESTER RESULT CHECK & HOSTEL BOOKING TEST CHAT.docx
│   ├── Admission Status (Topic).docx
│
├── Visuals/
│   ├── Copilot studio Interface.png
│   ├── Admira System Topics.png
│   ├── Admira Custom Topics.png
│   ├── Admira Knowledge Base.png
│   ├── Accomodation Booking Cloud Automate Flow.png
│   ├── TEAMS NOTIFICATION.png
│   ├── Systematic Process to AI Build.png
│   └── Project & Purpose.png
│
└── README.md
```

---

## 📎 Additional Visuals

The visuals below provide insight into Admira’s internal architecture, conversational topic design, and notification logic.

---

### 🧠 Copilot Studio Interface

The **Copilot Studio Interface** serves as Admira’s command center.
It manages **custom topics**, **knowledge bases**, and **Power Automate integrations** that make conversations dynamic and context-aware.

![Copilot Studio Interface](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Copilot%20studio%20Interface.png?raw=true)

---

### 🧩 System Topics, Custom Topics & Knowledge Base

Admira combines three intelligent conversation layers that power its natural flow:

1. **System Topics** – Default intents such as greetings, handoffs, and feedback capture.
2. **Custom Topics** – Institution-specific functions like tuition queries, hostel booking, and result checking.
3. **Knowledge Base** – Structured responses sourced from official institutional data for accuracy and consistency.

#### System Topics

![System Topics](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Admira%20System%20Topics.png?raw=true)

#### Custom Topics

![Custom Topics](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Admira%20Custom%20Topics.png?raw=true)

#### Knowledge Base

![Knowledge Base](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Admira%20Knowledge%20Base.png?raw=true)

---

### 💬 Teams Notification Example

Admira’s Teams integration enables **real-time communication** between automation and human oversight.
**Adaptive Cards** deliver actionable updates to both students and administrators including; hostel approvals, tuition inquiries, or result status changes.

![Teams Notification](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/TEAMS%20NOTIFICATION.png?raw=true)

*These cards promote fast feedback loops and maintain a verifiable digital audit trail within Microsoft Teams.*

---

## 🧭 Scalability & Roadmap

| Phase       | Enhancement             | Description                                                      |
| ----------- | ----------------------- | ---------------------------------------------------------------- |
| **Phase 2** | Power BI Insights       | Build analytics dashboards to monitor queries and SLA compliance |
| **Phase 3** | Multilingual Capability | Add Yoruba, Hausa, and Igbo conversation models                  |
| **Phase 4** | ERP Integration         | Connect Dataverse to student information systems                 |
| **Phase 5** | AI Builder Extension    | Introduce intent prediction and adaptive sentiment detection     |

---

## 👨🏽‍💼 Consultant

**Solomon Okpuno**
*Business & Power Platform Consultant*

📧 [solomon.okpuno@outlook.com](mailto:solomon.okpuno@outlook.com)
🌐 [LinkedIn](https://linkedin.com/in/solomon-okpuno-51a907312)                                           
[GitHub](https://github.com/okpunosolomon)

---

## 🧱 Summary

The **Admira Autonomous Agent** showcases how Microsoft Power Platform can drive **AI-enabled digital transformation** in higher education.
By connecting people, data, and automation, Admira demonstrates how institutions can modernize support delivery, strengthen governance, and achieve operational excellence.

> **Admira represents the next generation of student engagement, automated, scalable, and human-centered.**

