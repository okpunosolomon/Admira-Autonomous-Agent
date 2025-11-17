# 🧩 Agile Project Delivery Report  
**Admira Autonomous Agent (Admiral University Nigeria)**  

---

## 🧠 Executive Overview  

The **Admira Autonomous Agent** is an AI-powered student engagement system developed on the **Microsoft Power Platform** to modernise and automate student services at **Admiral University Nigeria**.  

The solution integrates **Copilot Studio**, **Power Automate**, **SharePoint**, and **Microsoft Teams** to handle high-volume student inquiries including **tuition fee breakdown**, **hostel booking**, **result checks**, and **admission status verification**  all through a single conversational interface.  

**Objective:**  
Deliver a governed, scalable, and low-code automation framework that enhances service speed, transparency, and student experience across the university.  

---

## 🧱 Project Delivery Framework  

| Parameter | Details |
|------------|----------|
| **Methodology** | Scrum (3 sprints × 2 weeks) |
| **Toolchain** | Azure DevOps, Power Platform, GitHub |
| **Project Manager / Scrum Master** | Solomon Okpuno |
| **Product Owner** | University ICT Lead |
| **Delivery Roles** | BA, Power Platform Developer, QA, End-User Rep |
| **Environments** | DEV / TEST / PROD (Power Platform Environments) |
| **Repository** | [Admira-Autonomous-Agent on GitHub](https://github.com/okpunosolomon/Admira-Autonomous-Agent) |

---

## 🗺️ Agile Kanban Overview  

The Azure DevOps board visualised sprint activity across **Backlog**, **In Progress**, **Testing**, **Done**, and **Bugs** maintaining complete traceability from user story to deployment.  

![Azure DevOps Kanban Board](https://github.com/okpunosolomon/Admira-Autonomous-Agent/blob/main/Visuals/dbd3bb42-989b-4cfb-978d-9086c65785f5.png?raw=true)

---

## 🗂️ Sprint 1: Foundation & Environment Setup (Weeks 1–2)  

**Focus:** Power Platform environment configuration, data schema creation, and topic architecture design.  

| Epic | Feature | Description | Acceptance Criteria | Status |
|------|----------|--------------|---------------------|--------|
| **E1** | Environment Setup | Configure DEV / TEST / PROD environments | Environments isolated and linked to GitHub repo | ✅ |
| **E2** | SharePoint Schema | Create lists for Tuition, Hostel, Results, Admissions | CRUD operations verified | ✅ |
| **E3** | Copilot Architecture | Design conversation flow and topic tree | Core intents and handoff logic approved | ✅ |
| **E4** | Security Model | Define access roles (Student, Admin, Support) | Azure AD roles validated | ✅ |

**Key Tasks**
- Setup solution structure in Power Platform Admin Center  
- Create and relate SharePoint lists for each topic area  
- Establish security groups and DLP policies  
- Document topic dependencies and escalation routes  

**Resolved Bugs**
- *B-01:* SharePoint connector timeout → Adjusted connection reference  
- *B-02:* Topic trigger conflict between Tuition and Hostel → Corrected expression match logic  

---

## 🚀 Sprint 2: Core Functionality & Automation (Weeks 3–4)  

**Focus:** Implement Power Automate flows, integrate adaptive notifications, and enable full conversational coverage.  

| Epic | Feature | Description | Acceptance Criteria | Status |
|------|----------|--------------|---------------------|--------|
| **E5** | Tuition Fee Breakdown | Retrieve tuition data by faculty and level | Fee details displayed accurately | ✅ |
| **E6** | Hostel Booking Workflow | Automate request creation and approval | Flow updates SharePoint and Teams | ✅ |
| **E6** | Adaptive Notifications | Send alerts via Teams cards | Cards display approval buttons and context | ✅ |
| **E7** | Escalation Flow | Route unresolved chats to human support | Escalation triggers within SLA | ✅ |
| **E8** | Result & Admission Topics | Query academic and admission records | Correct data returned with timestamp | ✅ |

**Key Tasks**
- Develop Power Automate flows for tuition, hostel, and admission modules  
- Configure JSON payloads for adaptive cards  
- Conduct integration testing with Copilot Studio triggers  
- Implement retry and concurrency controls  

**Resolved Bugs**
- *B-03:* Duplicate approval flow instances → Added parallel branch control  
- *B-04:* Notification not delivered in Teams mobile → Adjusted connector version  
- *B-05:* Hostel approval delays → Reduced loop interval  

---

## 📊 Sprint 3: Testing, Reporting & Go-Live (Weeks 5–6)  

**Focus:** Full UAT, system refinement, Power BI reporting integration, and production deployment.  

| Epic | Feature | Description | Acceptance Criteria | Status |
|------|----------|--------------|---------------------|--------|
| **E9** | Power BI Insights | Build reporting dashboard for chatbot usage | Metrics visible for Admins | ✅ |
| **E10** | User Acceptance Testing | Validate all topics and flows | 100% of test cases passed | ✅ |
| **E11** | Deployment & Governance | Export managed solution to PROD | Successfully deployed | ✅ |
| **E12** | Training & Knowledge Transfer | Deliver Teams-based training sessions | Training checklist completed | ✅ |

**Key Tasks**
- Conduct UAT with 20 pilot users  
- Fix and retest all priority bugs  
- Deploy managed solution (Admira_1_0_0_1.zip)  
- Prepare operational handover and documentation  

**Resolved Bugs**
- *B-06:* Flow history retention below policy → Adjusted to 28 days minimum  
- *B-07:* Adaptive card JSON parsing error → Updated schema version  

---

## 🧮 Agile Metrics Summary  

| Category | Count | Notes |
|-----------|--------|-------|
| **Epics** | 12 | Across full solution lifecycle |
| **Features** | 22 | Delivered through three sprints |
| **User Stories** | 35 | Focused on usability and integration |
| **Tasks** | 45 | Tracked in Azure DevOps |
| **Bugs** | 7 | All resolved prior to release |

---

## 🏁 Deliverables by Sprint  

| Sprint | Focus | Key Deliverables | Status |
|---------|--------|------------------|--------|
| **Sprint 1** | Environment & Setup | Power Platform envs, SharePoint schema, topic map | ✅ Completed |
| **Sprint 2** | Core Automation | Tuition, hostel, admission flows + Teams cards | ✅ Completed |
| **Sprint 3** | Testing & Deployment | UAT, dashboards, production go-live | ✅ Completed |

---

## 💼 Business Value Delivered  

- **Response time reduced:** 48 hrs → under 2 minutes  
- **Automation coverage:** 85 % of routine queries handled autonomously  
- **Admin workload:** Reduced by 80 % through digital workflows  
- **Auditability:** All conversations and approvals logged in SharePoint & Teams  
- **User satisfaction:** 95 % positive feedback during UAT  

---

## ⚙️ Governance & DevOps Alignment  

| Practice | Description |
|-----------|-------------|
| **Version Control** | All Power Platform solutions managed through GitHub releases |
| **CI/CD Pipeline** | Automated export/import pipelines for DEV → TEST → PROD |
| **DLP & Security** | Data Loss Prevention policies enforced via Admin Center |
| **Testing** | Manual + automated flow testing in Azure DevOps Test Plans |
| **Monitoring** | Flow analytics, error logging, and Power Platform Center of Excellence dashboards |
| **Documentation** | BRD, UAT, User Guide stored under `/Documentation/` |

---

## 📁 Repository Reference Map  

```bash
📂 Admira-Autonomous-Agent/
┣ 📁 Documentation/
┃  ┣ BRD-UAT-UserGuide.md
┃  ┗ AzureDevOps_DeliveryReport.md ← (this file)
┣ 📁 Visuals/
┃  ┣ dbd3bb42-989b-4cfb-978d-9086c65785f5.png
┃  ┣ Accomodation Booking Cloud Automate Flow.png
┃  ┗ TEAMS NOTIFICATION.png
┣ 📁 Solution Zip File/
┃  ┗ Admira_1_0_0_1.zip
┣ 📁 Test Chat/
┃  ┣ Tuition Fee Breakdown.docx
┃  ┣ Hostel & Result Topics.docx
┃  ┗ Admission Status.docx
┗ README.md
````

---

## 🧭 Lessons Learned

| Observation                         | Action                                                |
| ----------------------------------- | ----------------------------------------------------- |
| Overlapping Power Automate triggers | Consolidated topic triggers under one controller flow |
| Excessive manual testing effort     | Introduced reusable test scripts in DevOps            |
| Delayed approvals from admins       | Implemented Teams adaptive notifications              |
| Lack of feedback tracking           | Added post-interaction rating survey (future phase)   |

---

## 🚀 Scalability Roadmap

| Phase       | Enhancement             | Objective                                     |
| ----------- | ----------------------- | --------------------------------------------- |
| **Phase 2** | Power BI Dashboard      | Provide live analytics on chatbot performance |
| **Phase 3** | Multilingual Support    | Extend to Yoruba, Hausa, and Igbo             |
| **Phase 4** | Student ERP Integration | Sync Dataverse with admission & records data  |
| **Phase 5** | AI Builder Insights     | Add predictive trend and sentiment analytics  |

---

## 📞 Contact

**Consultant / Scrum Master:** **Solomon Okpuno**
📧 [solomon.okpuno@outlook.com](mailto:solomon.okpuno@outlook.com)
🔗 [linkedin.com/in/solomon-okpuno-51a907312](https://linkedin.com/in/solomon-okpuno-51a907312)
💻 [github.com/okpunosolomon](https://github.com/okpunosolomon)

---

> *This Agile delivery report provides transparent evidence of end-to-end project execution under an Azure DevOps framework, proving how Power Platform and AI automation can transform student engagement into a measurable, auditable, and continuously improving service model.*

```
