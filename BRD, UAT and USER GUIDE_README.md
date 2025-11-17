# 📄 BRD, UAT & User Guide  Admira Autonomous Agent  
**Client:** Admiral University Nigeria  
**Consultant:** Solomon Okpuno – Business & Power Platform Consultant  
**Platform:** Microsoft Power Platform (Copilot Studio, Power Automate, SharePoint, Teams)

---

## 🧭 Executive Overview  

The **Admira Autonomous Agent** is a 24/7 intelligent virtual assistant designed to modernize student engagement and administrative communication at **Admiral University Nigeria**.  
Built on Microsoft’s Power Platform, it automates repetitive student queries and workflows such as **tuition breakdowns, hostel applications, result inquiries, and admission status verification**.  

The project serves as a benchmark for how higher education institutions can combine **AI conversation design, Power Automate orchestration, and Microsoft 365 governance** into one secure, auditable solution.

---

## 🎯 Business Requirements Document (BRD)

### 1. Business Goals  
- Provide **always-available digital support** for students and applicants.  
- Reduce manual administrative workload through process automation.  
- Ensure **data accuracy, traceability, and compliance** with university policies.  
- Deliver measurable improvements in **service response time** and **student satisfaction**.  

---

### 2. Key Drivers & Challenges  

| Business Challenge | Pain Point | Strategic Response |
|--------------------|-------------|--------------------|
| Rising student inquiries | Long queues, delayed replies | Introduce a conversational AI interface |
| Manual hostel and tuition tracking | Errors, lost data | Automate request submission & approvals |
| Fragmented communication | No single information source | Unify Teams, SharePoint, and Copilot Studio |
| Poor visibility | Difficult to audit workflows | Add Power Automate logging & analytics layer |

---

### 3. Scope Definition  

| In Scope | Out of Scope |
|-----------|--------------|
| Tuition fee inquiry automation | Integration with bank/payment gateway (future) |
| Hostel application process & approvals | Offline chatbot support |
| Admission status & result inquiry | Integration with Student ERP (future phase) |
| Notifications via Teams Adaptive Cards | Direct SMS notification (optional) |

---

### 4. Success Metrics (KPIs)

| Metric | Baseline | Target |
|---------|-----------|--------|
| Average support response time | 48 hours | < 2 minutes |
| Manual approvals | 100% manual | 90% automated |
| Student satisfaction score | 65% | 95% |
| Admin workload | High | Reduced by 80% |
| Visibility of requests | Low | Fully auditable in SharePoint & Teams |

---

### 5. Stakeholder Matrix  

| Role | Department | Responsibility |
|------|-------------|----------------|
| **Project Sponsor** | Office of the Vice-Chancellor | Strategic oversight |
| **Product Owner** | ICT / MIS | Defines functional priorities |
| **Solution Consultant** | Enluka Consultancy (Solomon Okpuno) | Design, implementation, training |
| **IT Administrator** | IT Support | Flow management, user access |
| **End Users** | Students & Staff | Day-to-day chatbot interaction |

---

### 6. High-Level Requirements  

| Category | Description | Expected Outcome |
|-----------|-------------|------------------|
| Functional | AI chatbot handles tuition, hostel, and result requests | Reduced dependency on admin staff |
| Automation | Power Automate workflows trigger from chatbot | Real-time processing |
| Data | SharePoint stores structured records | Central data repository |
| Communication | Teams adaptive cards for notifications | Instant visibility & approval |
| Governance | Role-based access control | Secure & compliant environment |

---

### 7. Dependencies & Assumptions  

| Dependency | Assumption |
|-------------|-------------|
| Microsoft 365 tenant | Licensed and operational |
| Power Platform environment | DEV → TEST → PROD available |
| User authentication | Azure AD enforced |
| SharePoint lists | Properly maintained datasets |
| Teams connectivity | Enabled for all staff and admin roles |

---

## ✅ User Acceptance Testing (UAT)

### 1. UAT Purpose  
Validate that Admira performs all critical workflows accurately and consistently before production rollout.

---

### 2. UAT Environment Setup  
- **Environment:** TEST instance (Power Platform Sandbox)  
- **Participants:** Admin, Product Owner, End-User Representatives  
- **Duration:** 1 week (functional + regression testing)  
- **Data Source:** SharePoint Lists + Excel dataset  

---

### 3. Test Cases & Results  

| ID | Scenario | Expected Behaviour | Result | Status |
|----|-----------|--------------------|--------|--------|
| UAT-001 | Tuition Inquiry | Displays correct tuition details by faculty/level | Correct output | ✅ Pass |
| UAT-002 | Hostel Request Submission | Form captured and stored in SharePoint | Successful | ✅ Pass |
| UAT-003 | Hostel Approval | Teams adaptive card received by admin | Approval recorded | ✅ Pass |
| UAT-004 | Result Check | Student guided to result portal or summary | Correct redirection | ✅ Pass |
| UAT-005 | Admission Status Query | Bot responds with admission outcome | Works as expected | ✅ Pass |
| UAT-006 | Escalation Path | Unresolved query routed to human agent | Routed properly | ✅ Pass |
| UAT-007 | Notification Feedback | Adaptive card triggers acknowledgment | Response captured | ✅ Pass |

---

### 4. UAT Sign-Off  

| Role | Name | Signature | Date |
|------|------|------------|------|
| Product Owner | | | |
| IT Administrator | | | |
| Consultant | **Solomon Okpuno** | ✅ | |

---

## 👩🏽‍💻 User Guide  

### 1. Accessing Admira  

1. Navigate to the chatbot link or university portal.  
2. Sign in with your **Microsoft 365 university credentials**.  
3. Begin interaction via web chat or embedded Teams interface.  

---

### 2. User Roles & Permissions  

| Role | Description | Key Privileges |
|------|-------------|----------------|
| **Student** | General user | Submit requests, view responses |
| **Manager/Admin** | Departmental approver | Approve, reject, escalate |
| **IT Admin** | System owner | Manage flows, troubleshoot errors |
| **Consultant** | Governance advisor | Maintain ALM and CoE compliance |

---

### 3. Core Chatbot Topics  

#### 🎓 Tuition Fee Breakdown  
**Prompt Example:** “What’s my tuition for 400-level Engineering?”  
- Admira fetches relevant data from SharePoint.  
- Response includes base tuition + additional fees (ICT, Library, Health).  
- Option to download breakdown via adaptive card.  

#### 🏘️ Hostel Application & Allocation  
**Steps:**  
1. Type “Apply for hostel.”  
2. Fill details (name, level, hostel type).  
3. Flow logs data into SharePoint.  
4. Admin receives approval card in Teams.  
5. Approval outcome triggers student notification.  

#### 📊 Semester Result Inquiry  
**Prompt Example:** “Show me my semester result.”  
Admira guides the student to the secure result portal or displays a summary via preconfigured API reference.

#### 🧾 Admission Status Check  
Prospective students can confirm admission offers instantly with follow-up steps for enrollment and documentation.

---

### 4. Teams Notifications  

| Type | Description |
|------|-------------|
| **Approval Cards** | Sent to admin via Teams for real-time decisioning |
| **Student Alerts** | Confirm request submission or outcome |
| **Escalation Alerts** | Notify consultant or IT if a flow fails |

Each notification uses adaptive card JSON schema to provide interactive buttons and traceable responses.

---

### 5. Troubleshooting  

| Issue | Possible Cause | Resolution |
|--------|----------------|-------------|
| Chatbot not responding | User not authenticated | Sign out/in through Microsoft 365 |
| Wrong tuition data | Old SharePoint dataset | Verify and refresh dataset |
| Missing Teams notification | Flow timeout | Re-run flow or check connector |
| Rejected request not logged | Missing permissions | Reassign admin access in Azure AD |

---

### 6. Support & Training  

| Channel | Purpose | Contact |
|----------|----------|----------|
| Teams Chat | Quick help & real-time troubleshooting | IT Admin |
| Email | Issue escalation or bug report | support@sol-ltd.com |
| Training Session | End-user enablement | Monthly via Teams |
| Consultant | Project advisory | **Solomon Okpuno** |

---

### 7. Governance & Compliance Highlights  

- **Deployment Type:** Managed solution (Admira_1_0_0_1.zip)  
- **Environment Control:** DEV → TEST → PROD with version tracking  
- **Audit Logging:** Power Automate run history retained for 90 days  
- **Security:** Azure AD role enforcement and DLP policies applied  
- **Backup Strategy:** Weekly export of SharePoint data and solution package  

---

## 🧩 Continuous Improvement Roadmap  

| Phase | Enhancement | Description |
|--------|--------------|-------------|
| **Phase 2** | Power BI Dashboards | Visualize chatbot performance and SLA metrics |
| **Phase 3** | Multilingual Support | Enable Yoruba, Hausa, Igbo |
| **Phase 4** | ERP Integration | Connect Dataverse to student information systems |
| **Phase 5** | Predictive Analytics | Use AI Builder for trend and intent prediction |

---

## 🧠 Conclusion  

Admira Autonomous Agent has transformed student engagement from manual to intelligent automation.  
By combining **Copilot Studio, Power Automate, Teams, and SharePoint**, Admiral University now operates with faster communication, better governance, and higher transparency.

> *“Admira proves that when AI meets governance, institutions evolve from reactive service to proactive experience.”*

---

📧 **Consultant:** [solomon.okpuno@outlook.com](mailto:solomon.okpuno@outlook.com)  
🌐 **LinkedIn:** [linkedin.com/in/solomon-okpuno-51a907312](https://linkedin.com/in/solomon-okpuno-51a907312)  
💼 **GitHub:** [github.com/okpunosolomon](https://github.com/okpunosolomon)
```
