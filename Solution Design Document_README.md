# 🧭 Solution Design Document (SDD)  
**Project:** Admira Autonomous Agent  
**Client:** Admiral University Nigeria  
**Consultant:** Solomon Okpuno 
Business & Power Platform Consultant  

---

## 1. Executive Summary  

The **Admira Autonomous Agent** is an AI-powered digital engagement system developed for **Admiral University Nigeria** to modernize student services through Microsoft’s **Power Platform**.  

Operating 24/7, it automates core academic and administrative processes such as **tuition inquiries**, **hostel booking**, **result checking**, and **admission status updates**, all delivered via a conversational interface powered by **Copilot Studio** and **Power Automate**.  

This initiative eliminates manual delays, boosts transparency, and enforces enterprise-grade governance within the university’s Microsoft 365 ecosystem. It is not just a chatbot but an intelligent, process-driven automation hub.

---

## 2. Business Drivers  

| Business Challenge | Impact | Strategic Opportunity |
|--------------------|---------|------------------------|
| High student inquiry volume | Long response times, overworked admin staff | Deploy an AI-driven assistant providing instant responses |
| Fragmented systems and manual processes | Duplicated data and operational inefficiencies | Centralize workflows using Power Platform for end-to-end automation |
| Limited visibility and auditability | Weak tracking and accountability | Introduce Power Automate and Teams-based approvals for audit traceability |
| Need for scalable innovation | Reactive IT support | Adopt governed, low-code delivery under Power Platform Center of Excellence standards |

---

## 3. Functional Overview  

### 🎓 Tuition Fee Breakdown  
The chatbot retrieves faculty- and level-specific tuition data from SharePoint and provides real-time breakdowns, improving accuracy and transparency.

### 🏘️ Hostel Application & Allocation  
Students apply for accommodation through the chatbot. Power Automate captures requests, updates SharePoint, and notifies administrators for approval via Teams adaptive cards.

### 📊 Semester Result Inquiry  
Students can access or verify academic results instantly, reducing physical queueing and manual email responses.

### 🧾 Admission Status Update  
Prospective students check admission decisions in seconds, ensuring consistency and immediate communication across departments.

---

## 4. Solution Architecture  

### 4.1 Logical Architecture  

![Solution Architecture](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Systematic%20Process%20to%20AI%20Build.png?raw=true)  
*Figure 1: Logical architecture connecting Copilot Studio, Power Automate, SharePoint, and Teams.*

| Layer | Component | Description |
|--------|------------|-------------|
| **Experience Layer** | Microsoft Copilot Studio | Conversational interface for student interaction |
| **Automation Layer** | Power Automate Cloud Flows | Executes backend workflows for tuition, hostel, and admissions |
| **Data Layer** | SharePoint Lists / Dataverse | Manages institutional data structures |
| **Notification Layer** | Microsoft Teams | Sends adaptive card alerts and collects approval decisions |
| **Governance Layer** | Power Platform Admin Center | Manages environments, roles, and solution versioning |

---

### 4.2 Data Flow Overview  

1. Student initiates a topic in **Copilot Studio**  
2. Chat intent triggers a **Power Automate flow**  
3. Flow reads or writes data in **SharePoint Lists**  
4. Admin receives **Teams Adaptive Card** for decisioning  
5. Decision updates **SharePoint** and sends response back to chatbot  

Each interaction is **traceable, auditable, and governed**, ensuring data integrity and accountability.

---

## 5. Integration Components  

### 5.1 Power Automate Connectors  

| Connector | Function |
|------------|-----------|
| **Copilot Studio Trigger** | Initiates automation directly from chatbot context |
| **Microsoft SharePoint** | Stores datasets such as tuition fees, hostel requests, and admissions |
| **Office 365 Outlook** | Sends email confirmations and escalations |
| **Microsoft Teams** | Manages adaptive approval cards |
| **Microsoft Dataverse (optional)** | Provides a unified schema for future analytics and expansion |

---

### 5.2 SharePoint / Excel Schema  

![Excel Data – Before Submission](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/BEFORE%20HOSTEL%20BOOKING%20WAS%20SUBMITTED%20.png?raw=true)  
![Excel Data – After Submission](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/AFTER%20HOSTEL%20BOOKING%20WAS%20SUBMITED.png?raw=true)  
*Figure 2: Data structure before and after hostel booking submission, demonstrating Power Automate’s ability to write structured records directly into Excel/SharePoint.*

| Column Name | Type | Description |
|--------------|------|-------------|
| FullName | Text | Student’s full name |
| MatricNumber | Text | Unique student identifier |
| Faculty | Choice | Academic faculty |
| Department | Text | Student’s department |
| Level | Number | Academic level (100–500) |
| HostelPreference | Choice | Hostel type (Male/Female) |
| RoomType | Choice | Room category (4-in-a-room, 6-in-a-room) |
| Status | Choice | Pending / Approved / Rejected |
| Email | Text | Student contact email |

---

### 5.3 Power Automate Flow – Hostel Workflow  

![Hostel Flow](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Accomodation%20Booking%20Cloud%20Automate%20Flow.png?raw=true)  
*Figure 3: Automated workflow managing hostel booking lifecycle.*

**Flow Logic:**  
1. Triggered by “Apply for Hostel” chatbot intent  
2. Captures inputs and writes to SharePoint  
3. Sends adaptive card to administrator  
4. Updates record based on approval/rejection  
5. Notifies student with final decision  

✅ *Approval turnaround reduced from 24 hours to under 10 minutes.*

---

### 5.4 Teams Adaptive Card Notification  

![Teams Notification](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/TEAMS%20NOTIFICATION.png?raw=true)  
*Figure 4: Adaptive approval card in Microsoft Teams.*

**Key Features:**  
- Displays student and request details  
- Approve/Reject buttons directly linked to Power Automate actions  
- Synchronization with SharePoint upon decision  
- Built-in audit log for accountability  

This feature ensures real-time visibility and faster response cycles.

---

## 6. Security & Governance  

| Domain | Control |
|---------|----------|
| **Environment Separation** | Dedicated DEV, TEST, and PROD environments via Power Platform Admin Center |
| **Access Management** | Azure AD-based roles (Student, Admin, Manager) |
| **Data Protection** | Encryption in transit and at rest within Microsoft 365 |
| **Change Management** | Managed solution deployment with version tracking |
| **Monitoring & Auditing** | CoE dashboards and flow run history reviews |
| **Governance Compliance** | Fully aligned with Microsoft Power Platform Center of Excellence (CoE) guidelines |

---

## 7. Scalability & Maintenance Plan  

| Area | Strategy |
|-------|-----------|
| **Topic Expansion** | Introduce new use cases (e.g., transcripts, ID renewal) without downtime |
| **Performance Optimization** | Apply concurrency control and retry logic in flows |
| **System Monitoring** | Weekly health checks via Admin Center |
| **Continuous Feedback** | Collect user satisfaction metrics to improve responses |
| **Archiving & Retention** | Auto-archive inactive records after 90 days |
| **Version Control** | Publish managed solution (`Admira_1_0_0_1.zip`) to GitHub for release tracking |

---

## 8. Dependencies & Assumptions  

| Category | Detail |
|-----------|--------|
| **Licensing** | Power Platform per-app or per-user plan required |
| **Infrastructure** | University operates under Microsoft 365 tenant |
| **Authentication** | Azure AD manages single sign-on (SSO) |
| **Data Ownership** | SharePoint data maintained by authorized admins |
| **System Support** | IT team monitors flows and lists |
| **User Training** | Staff and students onboarded via Teams workshops |

---

## 9. System Interconnection Overview  

![System Interconnection Overview](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/System%20Interconnection%20Overview.png?raw=true)

*Figure 5: End-to-end system connectivity — linking Copilot Studio, Power Automate, SharePoint, and Teams in a unified workflow.*

This diagram illustrates how each component interacts in real time:
- **Copilot Studio** handles user dialogue and triggers workflows  
- **Power Automate** executes backend logic  
- **SharePoint / Excel** stores data securely  
- **Teams** delivers actionable notifications  

Together, they form a fully governed automation ecosystem.

---

## 10. Summary  

The **Admira Autonomous Agent** sets a benchmark for **intelligent automation in higher education**, blending conversational AI with enterprise governance.  
It unifies data, workflows, and communication into a single Power Platform solution delivering faster response times, better accountability, and measurable efficiency gains.

> *Admira is more than a chatbot; it’s a digital operations partner designed to scale with the institution.*

---

📧 **Consultant:** [solomon.okpuno@outlook.com](mailto:solomon.okpuno@outlook.com)  
🌐 **LinkedIn:** [linkedin.com/in/solomon-okpuno-51a907312](https://linkedin.com/in/solomon-okpuno-51a907312)  
💼 **GitHub:** [github.com/okpunosolomon](https://github.com/okpunosolomon)
```

