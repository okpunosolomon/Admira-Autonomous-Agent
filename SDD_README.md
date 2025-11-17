# 🧭 Solution Design Document (SDD)  
**Project:** Admira Autonomous Agent  
**Client:** Admiral University Nigeria  
**Consultant:** Solomon Okpuno – Business & Power Platform Consultant  

---

## 1. Executive Summary  

The **Admira Autonomous Agent** is an enterprise-grade automation and AI solution designed to modernize student engagement at **Admiral University Nigeria**.  

By integrating **Microsoft Copilot Studio**, **Power Automate**, **SharePoint**, and **Microsoft Teams**, the system transforms routine university operations—like tuition queries, hostel booking, and admission checks—into **intelligent, automated workflows**.  

The project’s key objective was to deliver a **24/7, scalable digital support system** that enhances service delivery, ensures governance, and creates a consistent student experience.

---

## 2. Business Drivers  

| Business Challenge | Impact | Opportunity |
|--------------------|---------|--------------|
| High student query volume | Slow responses, operational delays | Introduce conversational AI for 24/7 service |
| Manual processing of hostel and fee data | Error-prone and time-intensive | Automate workflows via Power Automate and SharePoint |
| Lack of audit trail and visibility | Limited accountability | Implement Teams-based adaptive card notifications |
| Fragmented data across departments | Redundant entries, misalignment | Centralize data through Dataverse/SharePoint integration |

---

## 3. Functional Overview  

### 🎓 Tuition Fee Breakdown  
Students request tuition details based on faculty and level. The chatbot retrieves live data from SharePoint, applies validation logic, and returns accurate, itemized fees.

### 🏘️ Hostel Application & Allocation  
Students apply for accommodation directly in the chatbot. A Power Automate flow logs each application in SharePoint and sends **Teams approval cards** to administrators for instant action.

### 📊 Semester Result Check  
Admira guides students to access semester results or provides summary feedback based on validated university records.

### 🧾 Admission Status Inquiry  
Prospective students can verify admission outcomes and next steps within the same conversational interface.

---

## 4. Solution Architecture  

### 4.1 Logical Overview  

![Solution Architecture](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Systematic%20Process%20to%20AI%20Build.png?raw=true)

| Layer | Component | Description |
|--------|------------|-------------|
| **Experience Layer** | Copilot Studio | Conversational interface for tuition, hostel, and admission topics |
| **Automation Layer** | Power Automate Cloud Flows | Executes business logic and backend data transactions |
| **Data Layer** | SharePoint / Dataverse | Stores structured student and operations data |
| **Notification Layer** | Microsoft Teams (Adaptive Cards) | Real-time approvals and notifications |
| **Governance Layer** | Power Platform Admin Center | Environment separation and compliance auditing |

---

### 4.2 Data Flow  

1. Student triggers topic in **Copilot Studio**  
2. **Power Automate** flow receives context (e.g., “Hostel Booking”)  
3. Flow logs request in **SharePoint List**  
4. Admin receives **Teams Adaptive Card** for approval  
5. Decision updates Dataverse and notifies user instantly  

---

## 5. Integration Components  

### 5.1 Power Automate Connectors  

| Connector | Function |
|------------|-----------|
| **Copilot Studio Trigger** | Captures chatbot intents and starts workflow |
| **Microsoft SharePoint** | Stores hostel, tuition, and admission records |
| **Office 365 Outlook** | Sends email alerts |
| **Microsoft Teams** | Pushes adaptive approval cards |
| **Microsoft Dataverse** | Centralized logging and analytics (future phase) |

---

### 5.2 SharePoint Schema (Hostel Applications)  

Below is the actual SharePoint/Excel schema used for hostel requests, stored under **Hostel_Applications**.  

![Excel Schema](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/89980a7b-7017-495f-8083-cf538fb7d7b5.png?raw=true)

| Column Name | Type | Description |
|--------------|------|-------------|
| Student_Name | Text | Student’s full name |
| Student_ID | Number | Unique student identification number |
| Hostel_Type | Choice | Category of hostel (Male/Female, Standard/Premium) |
| Application_Date | Date/Time | Time of submission |
| Status | Choice | Pending / Approved / Rejected |
| Approver | Person | Administrator assigned for review |

---

### 5.3 Power Automate Workflow Example  

![Power Automate Flow](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Accomodation%20Booking%20Cloud%20Automate%20Flow.png?raw=true)

**Workflow Description**  
- **Trigger:** User submits hostel request via chatbot  
- **Process:** Power Automate validates request → logs to SharePoint → sends Teams approval card  
- **Response:** Admin approves/rejects → flow updates record and sends confirmation to student  

✅ *Average approval turnaround reduced from 24 hours to under 10 minutes.*

---

### 5.4 Teams Adaptive Card Example  

![Teams Adaptive Card](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/TEAMS%20NOTIFICATION.png?raw=true)

The adaptive card provides real-time approval options for administrators, containing:
- Student details  
- Hostel type  
- Submission date  
- Approve / Reject buttons linked to Power Automate  

---

## 6. Security & Governance  

| Area | Governance Practice |
|-------|----------------------|
| **Environment Management** | Separate **DEV**, **TEST**, and **PROD** environments in Power Platform |
| **Role-Based Access Control** | Permissions segmented by role (Student, Admin, Manager) via Azure AD |
| **Data Security** | SharePoint and Dataverse encrypted at rest and in transit |
| **Change Control** | Managed solution deployment pipeline |
| **Monitoring** | Flow run history, environment analytics, and audit logs |

> The governance framework aligns with Microsoft’s **Center of Excellence (CoE)** standards to ensure traceability and sustainable administration.

---

## 7. Scalability & Maintenance Plan  

| Area | Strategy |
|-------|----------|
| **Topic Growth** | Modular topic design for additional student services |
| **Performance** | Power Automate concurrency and retry policy enabled |
| **Monitoring** | Scheduled audits via Admin Center insights |
| **Feedback Capture** | Built-in satisfaction survey topic for iterative improvement |
| **Data Retention** | Logs archived every 90 days via automated flow |
| **Version Control** | Solution versions managed through GitHub repository commits |

---

## 8. Dependencies & Assumptions  

| Category | Detail |
|-----------|--------|
| **Licensing** | Requires Power Platform per-app or per-user license |
| **Connectivity** | Reliable institutional Microsoft 365 tenant |
| **Security** | Azure AD governs authentication and authorization |
| **Data Reliability** | Assumes SharePoint lists are current and verified |
| **Support** | IT Admins maintain Power Automate flows and SharePoint lists |
| **End-User Access** | Staff and students use authenticated Microsoft accounts |

---

## 9. Visual Summary — System Interconnection  

![Solution Overview](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/860c8b9c-f0f8-4644-b24a-297aeb2d8595.png?raw=true)

This illustration captures the **end-to-end automation ecosystem**, showing how Copilot Studio interacts with SharePoint, Power Automate, and Microsoft Teams in real time.

---

## 10. Summary  

The **Admira Autonomous Agent** exemplifies a well-architected Power Platform deployment that blends automation, AI, and governance into a single cohesive framework.  

By automating repetitive student interactions and ensuring data integrity, it delivers tangible efficiency gains and builds a scalable foundation for institutional digital transformation.  

> *Admira isn’t just a chatbot — it’s a structured automation ecosystem designed for longevity, scalability, and measurable business value.*

---

📧 **Consultant:** [solomon.okpuno@outlook.com](mailto:solomon.okpuno@outlook.com)  
🌐 **LinkedIn:** [linkedin.com/in/solomon-okpuno-51a907312](https://linkedin.com/in/solomon-okpuno-51a907312)  
💼 **GitHub:** [github.com/okpunosolomon](https://github.com/okpunosolomon)
```

