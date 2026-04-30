# Initial Setup

This guide walks you through the steps required to prepare a new sERP installation for first use. Complete these steps in order before onboarding students and staff.

---

## 1. Change the Default Admin Password

Your welcome email contains a temporary admin password. Change it immediately after first login.

1. From the top navigation, click your username → **Change Password**
2. Enter your current password, then your new password (twice)
3. Click **Change Password**

!!! tip "Password guidelines"
    Use at least 8 characters, mixing uppercase, lowercase, numbers, and a special character (e.g. `!`, `@`, `#`).

---

## 2. Configure School Details

Enter your school's name, logo, address, and contact information. This information appears on reports, receipts, and communications.

1. Go to **Settings → General Settings**
2. Fill in all fields in the **School Details** section
3. Upload your school logo (PNG or JPG, recommended size: 300×100 px)
4. Click **Save**

---

## 3. Configure Student ID Prefix

sERP auto-generates student IDs in the format `[PREFIX]-[CLASS CODE]-[SEQUENCE]`. Set the prefix before adding any students.

1. Go to **Settings → General Settings**
2. Find **Student ID Prefix** and click the edit (✏️) icon
3. Enter your preferred prefix (e.g. `KAS` for Kasoa Academy School)
4. Click **Save**

---

## 4. Configure Staff ID Prefix

Similarly, set the staff ID prefix before adding staff records.

1. Go to **Settings → General Settings**
2. Find **Staff ID Prefix** and click the edit icon
3. Enter your prefix (e.g. `KAS-STF`)
4. Click **Save**

---

## 5. Add Campuses

If your school operates from a single location, add one campus with your school's name. For multi-campus schools, add each campus separately.

1. Go to **Students → Campuses**
2. In the **Add Campus** panel, enter the campus name
3. Click **Add Campus**

!!! tip
    You can add multiple campuses at once by clicking the **(+)** icon before submitting.

---

## 6. Add Divisions

Divisions are broad groupings of classes (e.g. Primary, JSS, SSS; or Basic, JHS, SHS). They affect how reports and analytics are segmented.

1. Go to **Academic → Divisions**
2. Enter the division name and click **Add Division**

---

## 7. Configure the Academic Calendar

The academic calendar setting tells sERP the current term and academic year. sERP supports both a **Trimester** (3-term) and **Semester** (2-term) structure.

1. Go to **Settings → Academic Settings → Academic Calendar**
2. Set the current **Academic Year** and **Term** for each calendar category in use
3. Click **Save**

!!! note
    Most West African schools operate on a trimester (3-term) calendar. Configure the "Trimester" calendar at minimum.

---

## 8. Add Classes

Add all classes your school currently runs.

1. Go to **Academic → Classes**
2. Click the dropdown arrow to expand the **Add Class** form
3. Fill in:
    - **Academic Calendar**: select Trimester or Semester
    - **Class Name**: the name as it should appear on reports (e.g. `Primary 1A`)
    - **Campus**: the campus this class belongs to
    - **Division**: the division grouping (e.g. Primary)
    - **Class Teacher**: assign a class teacher (staff must already be added)
    - **Class Code**: a short code used for student ID generation (e.g. `P1A`)
4. Click **Add Class**

---

## 9. Add Staff Departments

Group your staff into departments before adding staff records.

1. Go to **HR → Departments**
2. Enter the department name (e.g. `Teaching`, `Administration`, `Support`) and click **Add Department**

---

## 10. Add Staff Designations

Staff designations represent job titles or grades (e.g. Head Teacher, Class Teacher, Accountant).

1. Go to **Settings → HR Settings**
2. Click the edit icon next to **Staff Types Added**
3. Enter the designation and click **Add Staff Type**

---

## 11. Add Fee Items

Fee items are the billable line items on student invoices (e.g. Tuition, PTA Levy, Exam Fees).

1. Go to **Settings → Finance Settings**
2. Click the edit icon next to **Fee Items**
3. Enter each fee item name and click **Add**

---

## 12. Configure SMS

sERP uses an SMS gateway to send automated and bulk messages. Configure the gateway before enabling any automated SMS features.

1. Go to **Settings → SMS Settings**
2. Enter your API credentials (provided by your country licensee or SMS gateway partner)
3. Send a test SMS to verify the configuration

---

## Next Steps

Once setup is complete:

- Add staff records: **HR → Staff**
- Add student records: **Students → Add Student**
- Configure grading scales: **Settings → Academic Settings → Grading Scales**
- Set fee schedules: **Finance → Fee Schedules**
- Set up user accounts: [User Management](user-management.md)
