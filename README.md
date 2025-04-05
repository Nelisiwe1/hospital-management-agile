# hospital-management-agile

# Agile Planning Document



## 1. User Stories

### User Stories Table
| Story ID | User Story | Acceptance Criteria | Priority (High/Medium/Low) |
|----------|-----------|---------------------|---------------------------|
| US-001 | As a patient, I want to book an appointment online so that I can secure a consultation easily. | Appointment is confirmed and recorded in the system. | High |
| US-002 | As a doctor, I want to access patient medical records so that I can review their history before consultation. | Patient records load in ≤3 seconds. | High |
| US-003 | As a receptionist, I want to check in patients using their medical ID so that I can update their arrival status. | Patient is marked as checked-in. | Medium |
| US-004 | As a system admin, I want to encrypt user data with AES-256 so that security compliance is met. | Data is securely stored and encrypted. | High |
| US-005 | As a patient, I want to receive automated reminders for my upcoming appointments so that I don’t miss them. | Reminder is sent via email/SMS. | Medium |
| US-006 | As a nurse, I want to update medication schedules in real-time so that patient treatments remain accurate. | Updates reflect immediately in patient records. | High |
| US-007 | As a hospital administrator, I want to generate financial and operational reports so that I can analyze hospital performance. | Reports are generated in <5 seconds. | High |
| US-008 | As an emergency responder, I want critical cases to be flagged with priority indicators so that urgent patients receive immediate attention. | Emergency cases are highlighted and prioritized. | High |

## 2. Product Backlog

### Backlog Table
| Story ID | User Story | Priority (MoSCoW) | Effort Estimate | Dependencies |
|----------|-----------|------------------|----------------|--------------|
| US-001 | Book an appointment online | Must-have | 3 | None |
| US-002 | Access patient medical records | Must-have | 5 | US-001 |
| US-003 | Check-in patient using medical ID | Should-have | 4 | US-002 |
| US-004 | Encrypt user data with AES-256 | Must-have | 5 | None |
| US-005 | Send automated appointment reminders | Should-have | 3 | US-001 |
| US-006 | Update medication schedules in real-time | Must-have | 4 | US-002 |
| US-007 | Generate hospital financial and operational reports | Could-have | 5 | US-006 |
| US-008 | Flag emergency cases for priority attention | Must-have | 4 | None |

> **Justification:** Must-have stories align with core hospital functionality and patient care efficiency. The prioritization is based on essential service continuity, security compliance, and patient experience.

## 3. Sprint Planning

### Sprint Goal Statement
**Sprint Goal:** Deliver key hospital management features, focusing on appointment booking, patient check-in, record access, and emergency handling, ensuring usability, security, and efficiency.

### Sprint Backlog Table
| Task ID | Task Description | Assigned To | Estimated Hours | Status (To Do/In Progress/Done) |
|---------|----------------|-------------|----------------|------------------------|
| T-001 | Develop appointment booking functionality | Dev Team | 8 | To Do |
| T-002 | Create UI for booking and check-in | UX Designer | 6 | To Do |
| T-003 | Implement patient record access API | Dev Team | 10 | In Progress |
| T-004 | Integrate AES-256 encryption for sensitive data | Security Team | 5 | To Do |
| T-005 | Implement automated appointment reminder system | Dev Team | 6 | To Do |
| T-006 | Develop emergency case flagging functionality | Dev Team | 7 | To Do |
| T-007 | Conduct system security testing | QA Team | 6 | To Do |
| T-008 | Validate performance with 1000 concurrent users | Dev Team | 8 | To Do |

## 4. Links

- [Template_Analysis](template_analysis.md)
- [ReadmeKanban](ReadmeKanban.md)
- [Kanban_Explanation](kanban_explanation.md)
- [reflection](reflection.md)
- [Assessment8](Assessment8.md)

## 4. Reflection
**Challenges Faced in Prioritization, Estimation, and Agile Alignment:**

1. **Understanding Stakeholder Needs**
   - Challenge: Translating broad hospital requirements into actionable user stories.
   - Solution: Conducted stakeholder analysis and refined stories for clarity.

2. **Defining Clear Use Case Boundaries**
   - Challenge: Overlapping system interactions made defining use cases difficult.
   - Solution: Used inclusion and generalization to clarify relationships.

3. **Creating Effective Test Cases**
   - Challenge: Ensuring functional and non-functional coverage.
   - Solution: Developed structured test case tables covering usability, security, and performance.

4. **Ensuring System Scalability and Security**
   - Challenge: Managing concurrent users and protecting sensitive data.
   - Solution: Introduced security measures, stress testing, and scalability improvements.

5. **Maintaining Consistency Across Assignments**
   - Challenge: Aligning Agile artifacts with prior requirements.
   - Solution: Regular cross-referencing ensured traceability and seamless transitions.

6. **Estimating Task Effort Accurately**
   - Challenge: Variability in development complexity across different user stories.
   - Solution: Used Fibonacci story points to improve estimation accuracy and task balancing.



