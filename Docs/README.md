# ⚙️ Modular Documentation Admira Autonomous Agent  
*Comprehensive Developer & Governance Reference*

---

## 📘 Overview  

The **Modular Documentation Suite** provides a structured, developer-friendly reference for understanding, maintaining, and extending the **Admira Autonomous Agent**, an enterprise-grade AI-powered student support system built for **Admiral University Nigeria** using **Microsoft Power Platform**.  

This documentation is designed for business analysts, developers, and administrators involved in **solution lifecycle management**, ensuring transparency, governance, and continuous scalability.

---

## 🧭 Documentation Map  

```

/docs/
│
├── Architecture.md
├── Topics.md
├── Automation.md
└── Notifications.md

````

Each module focuses on a specific technical or functional domain within the solution, from architecture and topic logic to automation workflows and notification schemas.

---

## 🧩 1. Architecture.md  

### Purpose  
To describe the **logical architecture, integration points, and system governance** of the Admira Autonomous Agent.  
This section outlines how Microsoft Copilot Studio, Power Automate, SharePoint, and Microsoft Teams interact in a fully governed ecosystem.

### 🔷 Architecture Overview  

![System Interconnection Overview](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/System%20Interconnection%20Overview.png?raw=true)  
*Figure 1: End-to-end architecture connecting Copilot Studio, Power Automate, SharePoint, and Teams.*

| Layer | Component | Description |
|--------|------------|-------------|
| **Experience Layer** | Microsoft Copilot Studio | Conversational interface that manages topic flows and user sessions |
| **Automation Layer** | Power Automate | Executes backend processes for tuition, hostel, and admission logic |
| **Data Layer** | SharePoint / Excel / Dataverse | Stores student, fee, and hostel request records |
| **Notification Layer** | Microsoft Teams | Sends adaptive approval and feedback cards to administrators |
| **Governance Layer** | Power Platform Admin Center | Provides environment isolation, auditing, and solution version control |

### 🔁 Data Flow  

1. Student initiates a query in **Copilot Studio**.  
2. Copilot Studio triggers a **Power Automate Flow** through webhook.  
3. The flow processes the logic and interacts with **SharePoint/Excel**.  
4. A **Teams Adaptive Card** is sent for admin action.  
5. Results and notifications are logged and synced across services.

---

## 💬 2. Topics.md  

### Purpose  
To document the **conversational intelligence** layer of Admira — covering Copilot Studio topics, logic design, and PowerFx expressions.

### 🧠 Topic Architecture  

Each topic defines a **business intent** (e.g., checking results, applying for hostel, querying fees) with:
- Entry triggers  
- Entity recognition  
- PowerFx conditions  
- Response and escalation paths  

**Sample Screenshot:**  
![Copilot Studio Interface](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Copilot%20studio%20Interface.png?raw=true)

### Example Topics and Logic

| Topic | Description | Example PowerFx Expression |
|--------|--------------|-----------------------------|
| **Tuition Fee Breakdown** | Returns accurate fee data by faculty and level | `If(Faculty="Engineering", "₦450,000", "₦400,000")` |
| **Hostel Application** | Captures and validates student hostel preferences | `Set(HostelStatus, "Pending Approval")` |
| **Result Check** | Guides students to academic portal verification | `If(IsBlank(StudentID), "Provide your ID", "Fetching result...")` |
| **Admission Status** | Confirms admission result and next steps | `Switch(Result, "Admitted", "Welcome!", "Pending", "Please check back.")` |

**Screenshot – Custom Topic:**  
![Custom Topics](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Admira%20Custom%20Topics.png?raw=true)

### Best Practices
- Use **named variables** (e.g., `FacultyName`, `TuitionAmount`) for clarity.  
- Always define **fallback topics** for unrecognized inputs.  
- Keep **PowerFx** logic lightweight for optimal response time.  

---

## 🔄 3. Automation.md  

### Purpose  
To explain the **backend workflows** that make Admira’s chatbot intelligent and action-oriented.

### ⚙️ Power Automate Overview  

Admira’s workflows manage the lifecycle of each request, from form capture to approval and notification.

![Automation Flow](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Accomodation%20Booking%20Cloud%20Automate%20Flow.png?raw=true)  
*Figure 2: Hostel Booking Workflow powered by Power Automate.*

### 🧱 Workflow Logic  

| Step | Description |
|------|--------------|
| 1 | Student initiates chatbot topic (e.g., "Apply for Hostel"). |
| 2 | Flow captures data and creates a new record in SharePoint. |
| 3 | Admin receives a Teams Adaptive Card for approval/rejection. |
| 4 | Decision updates SharePoint automatically. |
| 5 | Notification sent to the student with status confirmation. |

### 🔍 Flow Governance  

| Control Area | Implementation |
|---------------|----------------|
| **Concurrency Control** | Ensures duplicate submissions are prevented. |
| **Error Handling** | Flow termination with conditional branches and failure emails. |
| **Environment Variables** | Standardized parameters for tenant independence. |
| **Telemetry** | Flow run history used for analytics and optimization. |

---

## 💬 4. Notifications.md  

### Purpose  
To define **Teams Adaptive Card notifications**, their structure, and Power Automate JSON payloads.

### 📬 Adaptive Card Notification Example  

![Teams Notification](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/TEAMS%20NOTIFICATION.png?raw=true)  
*Figure 3: Admin Approval Card delivered through Microsoft Teams.*

### 🧱 Schema Reference  

```json
{
  "type": "AdaptiveCard",
  "body": [
    { "type": "TextBlock", "text": "Hostel Application Request", "weight": "Bolder", "size": "Medium" },
    { "type": "TextBlock", "text": "Student: Solomon Okpuno", "wrap": true },
    { "type": "TextBlock", "text": "Faculty: Engineering" }
  ],
  "actions": [
    { "type": "Action.Submit", "title": "Approve", "data": { "action": "approve" } },
    { "type": "Action.Submit", "title": "Reject", "data": { "action": "reject" } }
  ],
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "version": "1.4"
}
````

### 🧩 Integration Flow

1. Flow captures student request.
2. Builds JSON card dynamically from input data.
3. Sends to Microsoft Teams via connector.
4. Captures admin decision and updates SharePoint.
5. Logs interaction for audit compliance.

### 📊 Benefits

* Instant actionable communication.
* Eliminates manual email approvals.
* Provides full decision history for administrators.

---

## 🔐 Governance & Version Control

| Domain                 | Governance Measure                                                 |
| ---------------------- | ------------------------------------------------------------------ |
| **Environment Setup**  | DEV, TEST, PROD isolated environments managed through Admin Center |
| **Change Control**     | Updates deployed via managed solutions                             |
| **Audit Trail**        | Flow logs and Teams activity preserved for compliance              |
| **Version Tracking**   | Maintained on GitHub under tagged releases (e.g., `v1.0.0.1`)      |
| **Backup & Restore**   | Weekly Dataverse backup snapshots                                  |
| **Documentation Sync** | `/docs/` folder auto-synced with solution releases                 |

---

## 🧠 Summary

The **Modular Documentation** structure provides Admira’s project stakeholders with a transparent, well-governed framework.
Each `.md` file forms part of a complete **operational blueprint**, enabling faster onboarding, simplified maintenance, and reliable scalability.

> **Admira Autonomous Agent** stands as a living model of Power Platform governance  combining conversational AI, workflow automation, and data intelligence under one unified system.

---

👨🏽‍💼 **Consultant:** [Solomon Okpuno](https://linkedin.com/in/solomon-okpuno-51a907312)
*Business & Power Platform Consultant*

📧 [solomon.okpuno@outlook.com](mailto:solomon.okpuno@outlook.com)
🌐 [GitHub Profile](https://github.com/okpunosolomon)

```
