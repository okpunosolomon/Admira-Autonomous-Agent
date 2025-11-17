# 🧩 Agile Project Delivery Report  
**Admira Autonomous Agent (Admiral University Nigeria)**  

---

## 🧠 Executive Overview  

The **Admira Autonomous Agent** is an enterprise-grade, AI-powered student engagement system built on the **Microsoft Power Platform**.  
It streamlines student services—**tuition fee inquiries**, **hostel booking**, **result checking**, and **admission status verification**—into a single, intelligent conversational interface powered by **Copilot Studio** and **Power Automate**.  

**Objective:**  
Deliver a secure, scalable, and fully governed automation framework that enhances responsiveness, transparency, and student experience across Admiral University’s academic operations.

---

## 🧱 Project Delivery Framework  

| Parameter | Details |
|------------|----------|
| **Methodology** | Scrum (3 sprints × 2 weeks) |
| **Toolchain** | Azure DevOps, Power Platform, GitHub |
| **Project Manager / Scrum Master** | Solomon Okpuno |
| **Product Owner** | University ICT Lead |
| **Delivery Roles** | Business Analyst, Power Platform Developer, QA, End-User Representative |
| **Environments** | DEV / TEST / PROD (Power Platform Environments) |
| **Repository** | [Admira-Autonomous-Agent on GitHub](https://github.com/okpunosolomon/Admira-Autonomous-Agent) |

---

## 🗺️ Azure DevOps Kanban Overview  

The **Azure DevOps Board** tracked all work items from backlog creation to bug resolution, maintaining full visibility and control of sprint progress.  

![Azure DevOps Overview Board](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/Azure%20DevOps%20Overview%20Board.png?raw=true)
*Figure 1: Admira project Kanban view showing Backlog → In Progress → Testing → Bugs.*

This board ensured traceability between epics, user stories, and deployment milestones.

---

## 🗂️ Sprint 1 – Foundation & Environment Setup  

**Focus:** Environment configuration, schema creation, and chatbot architecture setup.  

| Epic | Feature | Description | Acceptance Criteria | Status |
|------|----------|--------------|---------------------|--------|
| **E1** | Environment Setup | Create DEV, TEST, and PROD Power Platform environments | Configured and linked to GitHub | ✅ |
| **E2** | SharePoint Schema | Define data structure for Tuition, Hostel, Results, and Admissions | Lists tested for CRUD operations | ✅ |
| **E3** | Copilot Architecture | Build conversation flow and topic logic | Core intents deployed successfully | ✅ |
| **E4** | Security Model | Implement Azure AD roles (Student, Admin, Support) | Access validated | ✅ |

**Key Deliverables**
- Power Platform environment structure  
- SharePoint data model and relationships  
- Conversation topic maps and user flow diagrams  
- Security and DLP governance policies  

---

## 🚀 Sprint 2 – Core Functionality & Automation  

**Focus:** Integrate chatbot triggers with Power Automate workflows and Teams-based adaptive notifications.  

| Epic | Feature | Description | Acceptance Criteria | Status |
|------|----------|--------------|---------------------|--------|
| **E5** | Tuition Fee Breakdown | Retrieve and present accurate fee data by faculty and level | Verified in Copilot Studio | ✅ |
| **E6** | Hostel Booking Workflow | Automate accommodation requests via SharePoint and Teams | Admin approval functioning | ✅ |
| **E7** | Escalation Flow | Route unresolved inquiries to human support | Escalation logs tested | ✅ |
| **E8** | Adaptive Notifications | Adaptive cards sent to admins for approval | Teams notifications verified | ✅ |

**Workflow Reference**  
The following workflow illustrates end-to-end automation from student inquiry to resolution.  

![Process Workflow](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/d5c67f8f-57e0-4992-beeb-32a3d3d90b5e.png?raw=true)  
*Figure 2: Automation workflow linking Copilot Studio, Power Automate, SharePoint, and Teams.*

**Resolved Bugs**
- *B-01:* SharePoint connector timeout → fixed connection reference  
- *B-02:* Duplicate approval trigger → introduced branch control  
- *B-03:* Teams notification not sent → updated connector  

---

## 📊 Sprint 3 – Testing, Reporting & Deployment  

**Focus:** User acceptance testing, Power BI reporting integration, and managed solution deployment.  

| Epic | Feature | Description | Acceptance Criteria | Status |
|------|----------|--------------|---------------------|--------|
| **E9** | Power BI Insights | Build chatbot performance dashboard | Real-time metrics validated | ✅ |
| **E10** | User Acceptance Testing | Validate all conversational topics | All test cases passed | ✅ |
| **E11** | Deployment & Governance | Migrate solution to PROD | Version Admira_1_0_0_1 deployed | ✅ |
| **E12** | Training & Knowledge Transfer | Deliver admin and student workshops | 100% attendance and sign-off | ✅ |

---

## 🧮 Agile Metrics Summary  

| Category | Count | Notes |
|-----------|--------|-------|
| **Epics** | 12 | Across the solution lifecycle |
| **Features** | 22 | Delivered over three sprints |
| **User Stories** | 35 | Focused on usability and integration |
| **Tasks** | 45 | Managed through Azure DevOps |
| **Bugs** | 7 | All resolved before go-live |

---

## 💼 Business Value Delivered  

- **Response time reduced:** 48 hrs → <2 mins  
- **Admin workload:** Reduced by 80% via automation  
- **Data accuracy:** 100% due to SharePoint schema integration  
- **User satisfaction:** 95% positive feedback in UAT  
- **Governance:** Centralized audit logging and DLP compliance  

---

## ⚙️ Governance & DevOps Alignment  

| Area | Practice |
|------|-----------|
| **Version Control** | Managed GitHub releases for each build |
| **CI/CD Pipeline** | Automated DEV → TEST → PROD deployment |
| **DLP & Security** | Enforced via Power Platform Admin Center |
| **Testing** | Manual + automated DevOps Test Plans |
| **Monitoring** | Power Platform CoE analytics & error tracking |
| **Documentation** | BRD, UAT, and User Guide maintained under `/Documentation/` |

---

## 🧭 Lessons Learned  

| Observation | Resolution |
|--------------|-------------|
| Flow trigger overlap | Introduced controller orchestration flow |
| Manual testing fatigue | Added automated test scripts |
| Delayed admin actions | Teams notifications improved response rate |
| Missing user feedback | Designed post-chat satisfaction survey |

---

## 🚀 Scalability Roadmap  

| Phase | Enhancement | Objective |
|--------|--------------|------------|
| **Phase 2** | Power BI Analytics | Real-time service tracking |
| **Phase 3** | Multilingual Support | Expand to Yoruba, Hausa, Igbo |
| **Phase 4** | Student ERP Integration | Dataverse sync with admission records |
| **Phase 5** | AI Builder Extension | Add intent prediction and sentiment detection |

---

## 📁 Repository Reference Map  

```bash
📂 Admira-Autonomous-Agent/
┣ 📁 Documentation/
┃  ┣ BRD-UAT-UserGuide.md
┃  ┗ AzureDevOps_DeliveryReport.md ← (this file)
┣ 📁 Visuals/
┃  ┣ Azure DevOps Overview Board.png
┃  ┣ Process Workflow.png
┃  ┣ TEAMS NOTIFICATION.png
┃  ┗ Accomodation Booking Cloud Automate Flow.png
┣ 📁 Solution Zip File/
┃  ┗ Admira_1_0_0_1.zip
┗ README.md
````

---

## 👨🏽‍💼 Contact

**Consultant / Scrum Master:** **Solomon Okpuno**
📧 [solomon.okpuno@outlook.com](mailto:solomon.okpuno@outlook.com)
🔗 [linkedin.com/in/solomon-okpuno-51a907312](https://linkedin.com/in/solomon-okpuno-51a907312)
💻 [github.com/okpunosolomon](https://github.com/okpunosolomon)

---

> *This DevOps delivery summary demonstrates how AI-driven automation, built through Power Platform, can redefine student support operations in higher education — uniting speed, governance, and intelligent workflow management.*

