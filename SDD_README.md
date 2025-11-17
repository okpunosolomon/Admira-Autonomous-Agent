# 🧭 Solution Design Document (SDD)  
**Project:** Admira Autonomous Agent  
**Client:** Admiral University Nigeria  
**Consultant:** Solomon Okpuno – Business & Power Platform Consultant  

---

## 1. Executive Summary  

The **Admira Autonomous Agent** is a 24/7 AI-powered student engagement system built for **Admiral University Nigeria** using **Microsoft Power Platform**.  
It automates key academic and administrative interactions such as **tuition inquiries**, **hostel applications**, **semester result checks**, and **admission status updates**, all through a conversational interface powered by **Copilot Studio** and **Power Automate**.  

The project eliminates manual delays, enhances transparency, and provides an enterprise-grade governance framework within the university’s Microsoft 365 ecosystem.

---

## 2. Business Drivers  

| Business Challenge | Impact | Strategic Opportunity |
|--------------------|---------|------------------------|
| High student inquiry volume | Long response times, overworked admin staff | Deploy an AI-driven digital assistant for continuous support |
| Fragmented systems and manual processes | Duplicated data and errors | Centralize workflows in Power Platform for end-to-end automation |
| Limited visibility and auditability | Poor tracking and accountability | Implement Power Automate and Teams-based notifications |
| Need for sustainable scalability | Reactive IT management | Adopt governed, low-code development via Power Platform CoE model |

---

## 3. Functional Overview  

### 🎓 Tuition Fee Breakdown  
The chatbot dynamically retrieves faculty- and level-specific tuition data from SharePoint and returns accurate cost summaries.

### 🏘️ Hostel Application & Allocation  
Students apply for hostel accommodation via the chatbot. Power Automate registers the request, notifies admins, and manages approval through Teams adaptive cards.

### 📊 Semester Result Inquiry  
Students can check academic results or receive guidance to secure portals, reducing in-person queueing and email backlogs.

### 🧾 Admission Status Update  
Prospective students can verify admission decisions and next steps instantly, maintaining transparency across the academic intake process.

---

## 4. Solution Architecture  

### 4.1 Logical Architecture  

![Solution Architecture](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Systematic%20Process%20to%20AI%20Build.png?raw=true)  
*Figure 1: Logical architecture linking Copilot Studio, Power Automate, SharePoint, and Teams.*

| Layer | Component | Description |
|--------|------------|-------------|
| **Experience Layer** | Microsoft Copilot Studio | Conversational interface for student interaction |
| **Automation Layer** | Power Automate Cloud Flows | Executes logic for hostel, tuition, and admission processes |
| **Data Layer** | SharePoint Lists / Dataverse | Manages institutional datasets |
| **Notification Layer** | Microsoft Teams | Sends adaptive card alerts and collects decisions |
| **Governance Layer** | Power Platform Admin Center | Controls environment separation, versioning, and monitoring |

---

### 4.2 Data Flow Overview  

1. Student initiates a query in **Copilot Studio**  
2. Topic triggers a **Power Automate** flow via webhook  
3. Flow reads/writes records in **SharePoint List**  
4. Admin receives **Teams Adaptive Card** for approval  
5. Decision updates **SharePoint** and notifies student automatically  

This closed-loop ensures every interaction is logged, auditable, and consistent.

---

## 5. Integration Components  

### 5.1 Power Automate Connectors  

| Connector | Function |
|------------|-----------|
| **Copilot Studio Trigger** | Initiates workflows from chatbot context |
| **Microsoft SharePoint** | Stores structured datasets (Fees, Hostel, Admissions) |
| **Office 365 Outlook** | Sends email confirmations |
| **Microsoft Teams** | Delivers adaptive approval cards |
| **Microsoft Dataverse (optional)** | Central data model for analytics expansion |

---

### 5.2 SharePoint / Excel Schema  
![SharePoint and Excel Data Schema](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/1ad4fad1-50a7-4123-b7b6-3b450b93bd1d.png?raw=true)
*Figure 2: Data schema illustrating structured storage for student hostel applications and tuition records.*

*Figure 2: Hostel_Applications schema showing key data columns.*

| Column Name | Type | Description |
|--------------|------|-------------|
| Student_Name | Text | Student’s full name |
| Student_ID | Number | Unique student identifier |
| Hostel_Type | Choice | Hostel category (Male/Female, Standard/Premium) |
| Application_Date | Date/Time | Date the request was submitted |
| Status | Choice | Pending / Approved / Rejected |
| Approver | Person | Assigned administrator |

---

### 5.3 Power Automate Flow – Hostel Workflow  

![Hostel Flow](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Accomodation%20Booking%20Cloud%20Automate%20Flow.png?raw=true)  
*Figure 3: Cloud flow automating hostel request lifecycle.*

**Workflow Logic**

1. Triggered by chatbot intent (“Apply for Hostel”)  
2. Captures form inputs → creates a record in SharePoint  
3. Sends adaptive card to admin via Teams  
4. Updates record based on decision outcome  
5. Returns confirmation to student  

✅ *Average approval time reduced from 24 hours to less than 10 minutes.*

---

### 5.4 Teams Adaptive Card Notification  

![Teams Notification](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/TEAMS%20NOTIFICATION.png?raw=true)  
*Figure 4: Adaptive card approval in Microsoft Teams.*

The adaptive card includes:
- Student details and request summary  
- Approve/Reject buttons bound to Power Automate actions  
- Real-time synchronization with SharePoint  
- Audit logging of each decision  

This design improves traceability and staff responsiveness.

---

## 6. Security & Governance  

| Domain | Control |
|---------|----------|
| **Environment Separation** | Distinct DEV, TEST, and PROD environments configured via Power Platform Admin Center |
| **Access Control** | Azure AD role assignments (Student, Admin, Manager) |
| **Data Protection** | Encryption in transit and at rest across Microsoft 365 |
| **Change Management** | Managed solution deployment with version tracking |
| **Monitoring & Auditing** | Power Automate run history, CoE audit dashboard |
| **Governance Policy** | Aligned with Microsoft Center of Excellence (CoE) standards |

---

## 7. Scalability & Maintenance Plan  

| Area | Strategy |
|-------|-----------|
| **Topic Expansion** | Add new conversational topics (e.g., transcripts, library access) without system downtime |
| **Performance Optimization** | Enable concurrency control and retry policies in Power Automate |
| **Monitoring** | Weekly environment health checks via Admin Center analytics |
| **Feedback Loop** | Collect chatbot satisfaction data for continuous improvement |
| **Archiving** | Auto-archive records older than 90 days |
| **Version Control** | Managed solution exported to GitHub (`Admira_1_0_0_1.zip`) for release tracking |

---

## 8. Dependencies & Assumptions  

| Category | Detail |
|-----------|--------|
| **Licensing** | Requires Power Platform per-app or per-user license |
| **Connectivity** | University operates on Microsoft 365 tenant |
| **Security** | Authentication handled via Azure AD |
| **Data Accuracy** | SharePoint datasets maintained by administrators |
| **Maintenance** | IT support monitors Power Automate and SharePoint |
| **Training** | End-users onboarded via Teams workshop and guide |

---

## 9. Visual Summary — System Interconnection  

![System Interconnection](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/860c8b9c-f0f8-4644-b24a-297aeb2d8595.png?raw=true)  
*Figure 5: End-to-end system interconnection between Copilot Studio, Power Automate, SharePoint, and Teams.*

This diagram illustrates how data and automation flow seamlessly across the platform, forming a unified digital ecosystem.

---

## 10. Summary  

The **Admira Autonomous Agent** represents a scalable model for intelligent service automation in higher education.  
It unifies conversational AI, process automation, and governance into a single Power Platform solution—reducing manual workload, improving service speed, and strengthening institutional data integrity.

> *Admira stands as a real-world example of enterprise-level automation delivered through low-code innovation.*

---

📧 **Consultant:** [solomon.okpuno@outlook.com](mailto:solomon.okpuno@outlook.com)  
🌐 **LinkedIn:** [linkedin.com/in/solomon-okpuno-51a907312](https://linkedin.com/in/solomon-okpuno-51a907312)  
💼 **GitHub:** [github.com/okpunosolomon](https://github.com/okpunosolomon)
```

