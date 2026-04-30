# Portals & Self-Service

sERP provides dedicated portals for parents, students, and teaching staff — reducing administrative overhead by giving each group direct access to the information relevant to them.

---

## Parent Portal

Parents log in with the credentials created for them under [User Management](../getting-started/user-management.md). A parent account can be linked to one or more students.

### What parents can access

| Feature | Description |
|---------|-------------|
| **Fee balance** | Outstanding balance for each linked student, term-by-term |
| **Academic results** | Published terminal report scores and grades |
| **Attendance** | Daily attendance record with absent/late status |
| **Messages** | Two-way messaging with class teacher or admin |
| **Announcements** | School notice board |
| **Timetable** | Class timetable for the linked student |

### Fee payment view

Parents can view their child's full bill, outstanding balance, and payment history. They cannot make payments through the portal directly — payments are recorded by staff.

---

## Student Portal

Students log in with their own credentials. The student portal is typically used at secondary level.

### What students can access

| Feature | Description |
|---------|-------------|
| **Assignments** | Assigned tasks with due dates and submission status |
| **Timetable** | Class and exam timetable |
| **Academic results** | Published scores and terminal report |
| **Announcements** | School and class notice board |
| **Messages** | Inbox for messages from teachers |

---

## Teacher Portal

The teacher portal gives teaching staff a focused interface for academic work without exposing administrative functions.

### What teachers can access

| Feature | Description |
|---------|-------------|
| **Score entry** | Enter CA and exam scores for their assigned classes/subjects |
| **Attendance** | Mark daily attendance for their class |
| **Assignments** | Create, assign, and grade student assignments |
| **Lesson plans** | Create and manage lesson plans per subject/week |
| **Messages** | Communicate with students and parents |
| **Class list** | View enrolled students and their details |

!!! note
    Teachers only see data for the classes and subjects they are assigned to. Assignment is managed under **Academic → Classes → Edit Class → Assign Teachers**.

---

## Role-Based Access Control

Every user account has a **role** that determines which sections of the application they can access. Admin accounts can override individual permissions.

### Default permission sets

| Role | Admin Panel | Finance | HR | Academic | Portals |
|------|-------------|---------|-----|---------|---------|
| Admin | Full | Full | Full | Full | — |
| Finance Staff | — | Full | View | — | — |
| HR Staff | — | — | Full | — | — |
| Teaching Staff | — | — | — | Assign/Grade | Teacher Portal |
| Student | — | — | — | — | Student Portal |
| Guardian | — | — | — | — | Parent Portal |

Permissions can be expanded or restricted at the individual user level.

---

## Audit Log

Every action taken by every user in the system is recorded in the audit log.

1. Go to **Admin → Audit Log**
2. Filter by **User**, **Action Type**, or **Date Range**
3. Each entry shows the user, action, affected record, and timestamp

The audit log is read-only — entries cannot be edited or deleted.

---

## Multi-Factor Authentication (MFA)

MFA is available for admin and finance staff accounts. When enabled, the user receives a one-time code by SMS or email at login.

Enable MFA per user in **Admin → Manage Users → Edit User → Enable MFA**.
