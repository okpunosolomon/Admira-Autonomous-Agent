# 🤖 Admira Autonomous Agent – Admiral University Nigeria  
*AI-Powered Student Support Chatbot Built on Microsoft Power Platform*

---

## ![Banner](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/860c8b9c-f0f8-4644-b24a-297aeb2d8595.png?raw=true)

---

## 🏫 Executive Summary  

The **Admira Autonomous Agent** is an AI-driven Copilot Studio chatbot designed for **Admiral University Nigeria** to automate and enhance student engagement.  
It integrates conversational intelligence with Microsoft’s **Power Platform**, allowing students to access tuition details, check semester results, apply for hostel accommodation, and connect with support — all through a unified, intelligent interface.

This repository documents the **end-to-end development, automation, and governance framework** of the Admira solution — a flagship implementation of **Power Automate, SharePoint, and Microsoft Teams integration** within higher education.

---

## 💡 Business Context  

Universities face operational inefficiencies due to fragmented communication channels, delayed responses, and repetitive manual queries.  
**Admiral University** sought to modernize its service delivery through a **centralized, conversational support system** capable of handling:  

- High-volume student inquiries  
- Repetitive administrative tasks  
- Real-time notifications and escalation to human agents  

The Admira Agent addresses these challenges with a **low-code intelligent automation ecosystem**, enabling continuous engagement and service efficiency.

---

## 🧩 Solution Architecture  

![Architecture](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/89980a7b-7017-495f-8083-cf538fb7d7b5.png?raw=true)

| Layer | Component | Function |
|-------|------------|-----------|
| **Presentation** | Microsoft Copilot Studio | Conversational AI interface handling student interactions |
| **Automation** | Power Automate | Executes approval workflows, triggers notifications, and updates SharePoint lists |
| **Data Storage** | SharePoint Lists / Dataverse | Manages structured data for tuition, hostel, and student records |
| **Collaboration** | Microsoft Teams | Sends adaptive cards for admin and user notifications |
| **Integration** | JSON, Adaptive Cards, PowerFx | Handles data exchange between Copilot Studio and backend systems |

---

## 🚀 Features & Value Delivered  

| Feature | Description | Business Value |
|----------|--------------|----------------|
| 🎓 **Tuition Fee Breakdown** | Retrieves real-time fee details by faculty and level | Transparency for students and reduced staff load |
| 🏘️ **Hostel Application** | Submits and tracks accommodation requests | Automated approval workflow and allocation logs |
| 🧾 **Semester Result Check** | Provides guided access to student results | Reduced support dependency and 24/7 availability |
| 💬 **Teams Notifications** | Adaptive cards for both admin and user | Instant alerts and audit-friendly tracking |
| 🔁 **Escalation Pathway** | Transfers unresolved chats to a human agent | Seamless transition ensuring user satisfaction |
| 📊 **Governance Dashboard** *(Planned)* | Integrates Power BI for usage and ticket analysis | Data-driven decisions and performance tracking |

---

## ⚙️ Technology Stack  

| Category | Tools / Components |
|-----------|--------------------|
| **AI & Chatbot Framework** | Microsoft Copilot Studio (Power Virtual Agents) |
| **Automation Engine** | Power Automate Cloud Flows |
| **Data Layer** | Microsoft SharePoint Online, Dataverse |
| **Collaboration** | Microsoft Teams (Adaptive Card Integration) |
| **Governance** | Power Platform Admin Center, Environment Variables |
| **Security & Access** | Azure AD Role-Based Permissions |
| **Testing Tools** | Copilot Studio Test Chat, Flow Run History |
| **Development Environment** | ADMIRA Solution v1.0.0.1 (.zip) |

---

## 🔄 Automation Logic Overview  

### Example 1: Hostel Booking Workflow  
![Hostel Booking Flow](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Accomodation%20Booking%20Cloud%20Automate%20Flow.png?raw=true)

**Logic Summary:**
1. User submits hostel request via chatbot.  
2. Power Automate flow creates SharePoint record.  
3. Adaptive Card notifies admin in Teams for approval.  
4. Student receives confirmation message and record updates.

---

### Example 2: Tuition Fee Breakdown  

```json
{
  "faculty": "Engineering",
  "level": "400",
  "tuition": "₦450,000",
  "additional_fees": {
    "Library": "₦15,000",
    "ICT": "₦10,000"
  },
  "total": "₦475,000"
}
````

The chatbot retrieves data dynamically based on program and level using PowerFx expressions mapped to SharePoint data.

---

## 🧠 Implementation Results

| Metric                | Before Admira | After Admira   |
| --------------------- | ------------- | -------------- |
| Average response time | 48 hrs        | < 2 minutes    |
| Query resolution rate | 42%           | 92%            |
| Student satisfaction  | 65%           | 95%            |
| Manual intervention   | Frequent      | Reduced by 80% |

Admira redefined Admiral University’s digital service experience, achieving **scalable, low-code automation with human oversight**.

---

## 🗂️ Repository Map

```bash
Admira-Autonomous-Agent/
│
├── Solution Zip File/
│   └── Admira_1_0_0_1.zip
│
├── Test Chat/
│   ├── Admission Status (Topic).docx
│   ├── TUITION FEE BREAKDOWN (Topic).docx
│   ├── SEMESTER RESULT CHECK & HOSTEL BOOKING TEST CHAT.docx
│
├── Visuals/
│   ├── Copilot studio Interface.png
│   ├── Admira Custom Topics.png
│   ├── Admira Knowledge Base.png
│   ├── Systematic Process to AI Build.png
│   ├── TEAMS NOTIFICATION.png
│   ├── Project & Purpose.png
│   └── ... (support visuals for documentation)
│
└── README.md
```

---

## 🧭 Next Steps & Scalability

| Phase       | Enhancement            | Description                                                          |
| ----------- | ---------------------- | -------------------------------------------------------------------- |
| **Phase 2** | Power BI Integration   | Develop analytics dashboard for ticket and response metrics          |
| **Phase 3** | Multi-language Support | Enable English, Hausa, Yoruba, and Igbo conversation options         |
| **Phase 4** | ERP / SIS Integration  | Connect to student information system for real-time academic records |
| **Phase 5** | AI Builder Upgrade     | Integrate form processing and intent prediction for smarter routing  |

---

## 👨🏽‍💼 Consultant

**Solomon Okpuno**
*Business & Power Platform Consultant*
[LinkedIn](https://linkedin.com/in/solomon-okpuno-51a907312) | [GitHub](https://github.com/okpunosolomon)

---

## 📎 Additional Visuals

### Copilot Studio Interface

![Copilot Studio](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Copilot%20studio%20Interface.png?raw=true)

### System Topics & Knowledge Base

![Topics](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Admira%20System%20Topics.png?raw=true)
![Knowledge Base](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Admira%20Knowledge%20Base.png?raw=true)

### Teams Notification Example

![Teams Notification](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/TEAMS%20NOTIFICATION.png?raw=true)

---

### 🧱 Summary

The **Admira Autonomous Agent** embodies the fusion of **Power Platform innovation and intelligent automation**, proving how universities can **transform operations, reduce overhead, and deliver 24/7 digital assistance** — all with Microsoft’s low-code ecosystem.
It stands as a model of **adaptive digital transformation in higher education**.

```
```
