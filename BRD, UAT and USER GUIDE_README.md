### `/Documentation/BRD.md`

```markdown
# 📘 Business Requirements Document (BRD)
**Project:** Admira Autonomous Agent  
**Client:** Admiral University Nigeria  
**Consultant:** Solomon Okpuno – Business & Power Platform Consultant  

---

## 🎯 Business Objectives
- Automate routine student interactions (tuition, hostel, results, admission).  
- Reduce administrative workload by 80 %.  
- Deliver a 24/7 digital self-service channel through Microsoft Power Platform.  
- Ensure data consistency and audit transparency using governed workflows.

---

## 📚 Scope

| In Scope | Out of Scope |
|-----------|--------------|
| Tuition query automation | Third-party payment gateway integration (future) |
| Hostel application flow | ERP integration (Phase 4) |
| Result check guidance | Direct grade upload by lecturers |
| Admission status support | Offline mobile support |

---

## 📊 Key Performance Indicators (KPIs)

| KPI | Baseline | Target (After Admira) |
|------|-----------|----------------------|
| Average response time | 48 hrs | < 2 mins |
| Student support emails per week | 300 + | ≤ 60 |
| Manual approval delay | 24 hrs | ≤ 10 mins |
| Student satisfaction | 65 % | ≥ 95 % |

---

## 👥 Stakeholder Mapping

| Role | Responsibility |
|------|----------------|
| **Project Sponsor** – Vice Chancellor | Strategic oversight and budget approval |
| **Product Owner** – IT Asset Manager | Defines requirements and acceptance criteria |
| **Consultant** – Solomon Okpuno | Solution design and implementation |
| **Admin Team** | Daily operation and support |
| **Students / End Users** | Interaction and feedback |

---

## 🧭 Success Criteria
- Full conversational coverage for key topics.  
- Measurable improvement in SLA response times.  
- Secure deployment following CoE governance policy.  
- Positive user feedback within first 30 days of launch.

---
```

---

### `/Documentation/UAT.md`

```markdown
# ✅ User Acceptance Testing (UAT)
**Project:** Admira Autonomous Agent  

---

## 🎯 Purpose
Confirm that each topic and workflow functions as expected before go-live.

---

## 🧪 Test Scenarios

| ID | Scenario | Steps | Expected Result | Status |
|----|-----------|--------|-----------------|--------|
| UAT-001 | Tuition Fee Breakdown | Student asks “Show Engineering fees.” | Displays correct faculty and level fees | ✅ Pass |
| UAT-002 | Hostel Application | Student applies for hostel room | Request logged to SharePoint and Teams card sent | ✅ Pass |
| UAT-003 | Approval Process | Admin approves hostel via Teams card | Status updated to *Approved* and student notified | ✅ Pass |
| UAT-004 | Result Check | Student asks “How can I see my result?” | Bot guides to portal link or API response | ✅ Pass |
| UAT-005 | Admission Status | Prospective student checks status | Returns “Admitted / Not Admitted” message | ✅ Pass |
| UAT-006 | Escalation Flow | Unhandled query detected | Transferred to human support queue | ✅ Pass |

---

## 🧾 Sign-off

| Role | Name | Signature | Date |
|-------|------|------------|------|
| Project Sponsor |   |   |   |
| Product Owner |   |   |   |
| Consultant | Solomon Okpuno | ✅ |   |

---
```

---

### `/Documentation/User-Guide.md`

```markdown
# 👩🏽‍💻 User Guide – Admira Autonomous Agent  
**Audience:** Students and Administrators of Admiral University Nigeria  

---

## 🧭 Access
1. Visit [https://make.powerapps.com](https://make.powerapps.com) or the university chat portal.  
2. Launch **Admira Autonomous Agent**.  
3. Sign in with your Microsoft 365 university account.

---

## 👤 User Roles

| Role | Capabilities |
|-------|----------------|
| Student | Ask questions, submit requests, view notifications |
| Admin | Approve/reject requests, view dashboards |
| IT Support | Manage flows, connections, and logs |

---

## 🧩 Key Topics & Actions

### 🎓 Tuition Inquiry
Type: “Show tuition fees for Science 300 level.”  
→ Admira displays faculty-specific fee breakdown with ICT and library charges.

### 🏘️ Hostel Application
1. Type “Apply for hostel.”  
2. Bot collects name, ID, hostel type.  
3. Confirmation sent to Teams and SharePoint record created.  
4. Admin approves or rejects via Teams adaptive card.  
5. Student receives status update instantly.

### 📊 Semester Result Check
Ask “How can I view my result?” → Bot guides to portal or fetches API summary.

### 🧾 Admission Status
Query “Check my admission status.” → Immediate confirmation with next steps.

---

## 💬 Teams Notifications
Admins receive adaptive cards with Approve/Reject buttons.  
Each action automatically updates SharePoint and notifies students in Teams chat.

---

## 🛠️ Troubleshooting

| Issue | Resolution |
|--------|-------------|
| Bot not responding | Check internet connection or Teams permissions. |
| Notification delay | Verify Power Automate flow run history. |
| Wrong data displayed | Confirm SharePoint list entries and faculty mapping. |

---

## 🧠 Support & Training
- Email: [support@sol-ltd.com](mailto:support@sol-ltd.com)  
- Contact: IT Support – Admiral University Nigeria  
- Consultant: Solomon Okpuno   

---

> *Admira simplifies student support through automation and collaboration — bringing every interaction closer to instant service.*
```

---

