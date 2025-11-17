# 🧭 Solution Design Document (SDD)  
**Project:** Admira Autonomous Agent  
**Client:** Admiral University Nigeria  
**Consultant:** Solomon Okpuno – Business & Power Platform Consultant  

---

## 1. Executive Summary  

The **Admira Autonomous Agent** is an enterprise chatbot and automation framework designed to streamline student engagement and administrative workflows at **Admiral University Nigeria**.  

Built entirely on **Microsoft Power Platform**, the solution leverages **Copilot Studio**, **Power Automate**, **SharePoint**, and **Microsoft Teams** to automate key university services such as **tuition fee inquiries**, **hostel booking**, **semester result access**, and **admission status updates**.  

The project’s goal was to reduce operational friction, enhance response accuracy, and provide 24/7 accessibility while maintaining strong data governance and scalability.  

---

## 2. Business Drivers  

| Business Challenge | Impact | Opportunity |
|--------------------|---------|--------------|
| High student support volume and delayed responses | Student dissatisfaction, manual workload | Implement an AI-driven 24/7 support agent |
| Fragmented data and processes across departments | Inefficient communication and data redundancy | Centralize data through Dataverse / SharePoint integration |
| Lack of visibility into service metrics | Limited analytics and accountability | Deploy Power BI dashboards and adaptive notifications |
| Resource-heavy administrative processes | Increased staff dependency | Automate common workflows with Power Automate and Teams |

---

## 3. Functional Overview  

### 🎓 Tuition Fee Breakdown  
Students can request real-time fee details by faculty and level.  
The chatbot dynamically retrieves data from SharePoint, performs calculations, and displays structured tuition components.

### 🏘️ Hostel Application & Allocation  
The system captures hostel booking requests via chatbot inputs, records data in SharePoint, and triggers approval workflows through Power Automate.  
Admin staff receive **Teams adaptive cards** to approve or reject applications instantly.

### 📊 Semester Result Check  
Students can inquire about their semester results. Admira directs them to authenticated portals or returns available academic summaries through the knowledge base.

### 🧾 Admission Status Inquiry  
Prospective students can verify admission updates, guided through step-by-step chatbot interactions linked to official data sources.

---

## 4. Solution Architecture  

### 4.1 Logical Architecture  

![Solution Architecture](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Systematic%20Process%20to%20AI%20Build.png?raw=true)

| Layer | Component | Description |
|--------|------------|-------------|
| **Experience Layer** | Copilot Studio | Conversational interface that manages all topics, knowledge sources, and handoff logic |
| **Automation Layer** | Power Automate Cloud Flows | Executes logic for tuition, hostel, and result operations |
| **Data Layer** | SharePoint Lists / Dataverse | Stores structured datasets (e.g., Fees, Hostel Applications, Admissions) |
| **Notification Layer** | Microsoft Teams Adaptive Cards | Sends real-time approval or confirmation alerts |
| **Governance Layer** | Power Platform Admin Center | Enforces ALM, environment separation, and compliance standards |

---

### 4.2 Data Flow  

1. Student initiates query → Copilot Studio triggers relevant topic  
2. Topic condition routes request → Power Automate Flow  
3. Flow retrieves/updates data → SharePoint or Dataverse  
4. Result → Teams notification and chatbot response  
5. Logs and approvals recorded → Dataverse audit trail  

---

## 5. Integration Components  

### 5.1 Power Automate Connectors  

| Connector | Purpose |
|------------|----------|
| **Microsoft Dataverse** | Central data repository and audit log |
| **SharePoint Online** | Stores tuition, hostel, and admission datasets |
| **Office 365 Outlook** | Email notifications to students and staff |
| **Microsoft Teams** | Adaptive card alerts for approvals |
| **Copilot Studio Trigger** | Initiates flow based on user intent |

---

### 5.2 SharePoint Schema Example  

**List:** Hostel_Applications  
| Column Name | Data Type | Description |
|--------------|------------|-------------|
| Student_Name | Single line of text | Name of applicant |
| Student_ID | Number | Unique student ID |
| Hostel_Type | Choice | (Male/Female, Standard/Premium) |
| Application_Date | Date/Time | Date of request |
| Status | Choice | Pending / Approved / Rejected |
| Approver | Person or Group | Admin responsible for review |

---

### 5.3 Teams Adaptive Card Sample  

![Teams Notification](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/TEAMS%20NOTIFICATION.png?raw=true)

The adaptive card displays:
- Request details (e.g., student name, hostel type, timestamp)  
- Approve/Reject buttons  
- Auto-refresh logic to sync status in SharePoint and notify the user instantly  

---

## 6. Security & Governance  

| Aspect | Design Control |
|---------|----------------|
| **Environment Separation** | Distinct DEV and PROD environments configured in Power Platform Admin Center |
| **Role-Based Access Control (RBAC)** | Access segregated by roles: Admin, Manager, Student |
| **Data Protection** | SharePoint and Dataverse secured under university Microsoft 365 tenant with encryption at rest |
| **Auditing & Logging** | Flow run history, Dataverse audit tables, and Teams message logs |
| **Change Management** | Managed solution deployment via ALM pipelines and Solution Checker validation |

> Governance was implemented following Power Platform Center of Excellence (CoE) principles to ensure continuous compliance and traceability.

---

## 7. Scalability & Maintenance Plan  

| Area | Approach |
|-------|-----------|
| **Topic Expansion** | Add modular topics (Library Access, Transcript Request, Course Registration) without re-deploying the core agent |
| **Load Handling** | Power Automate concurrency control and environment throttling |
| **Monitoring** | Flow analytics and Teams error logging for proactive resolution |
| **User Feedback Loop** | Feedback topic integrated to capture user satisfaction and training data |
| **Data Retention Policy** | 90-day auto-archive for conversation logs and requests |
| **Versioning** | All updates packaged as managed solutions with version control on GitHub |

---

## 8. Dependencies & Assumptions  

| Category | Details |
|-----------|----------|
| **Licensing** | Power Platform per-user or per-app license required |
| **Connectivity** | Stable institutional Microsoft 365 and SharePoint infrastructure |
| **Security** | University-managed Azure AD policies govern authentication |
| **Data Accuracy** | Assumes source data in SharePoint is verified and up-to-date |
| **User Adoption** | Relies on proper onboarding of students and administrative staff |
| **Maintenance Ownership** | IT Support Team responsible for monitoring Power Automate health and SharePoint integrity |

---

## 9. Summary  

The **Admira Autonomous Agent** successfully transforms university service delivery into a **digitally intelligent workflow ecosystem**.  
By fusing conversational AI, process automation, and collaborative governance, Admira delivers measurable operational efficiency and a scalable foundation for future institutional automation.

> *The design prioritizes resilience, modularity, and real-world usability—hallmarks of enterprise-grade Power Platform solutions.*

---

📧 **Consultant:** [solomon.okpuno@outlook.com](mailto:solomon.okpuno@outlook.com)  
🌐 **LinkedIn:** [linkedin.com/in/solomon-okpuno-51a907312](https://linkedin.com/in/solomon-okpuno-51a907312)  
💼 **GitHub:** [github.com/okpunosolomon](https://github.com/okpunosolomon)
```
