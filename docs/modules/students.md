# Students & Admissions

The students module manages the complete lifecycle of a student — from first admission through to archiving as an alumnus.

---

## Adding a Student

1. Go to **Students → Add Student**
2. Fill in the required fields:
    - **Student ID** (auto-generated if prefix is configured)
    - **First name**, **Last name**, **Middle name**
    - **Date of birth**, **Gender**, **Nationality**
    - **Class** and **Campus**
    - **Guardian / Parent** contact details
3. Upload a passport photo (optional but recommended)
4. Click **Register Student**

---

## Student ID Generation

Student IDs are generated automatically in the format:

```
[PREFIX]-[CLASS CODE]-[SEQUENCE NUMBER]
```

For example, with prefix `KAS` and class code `JSS1A`, the first student gets `KAS-JSS1A-001`.

Configure the prefix in **Settings → General Settings → Student ID Prefix**.

---

## Class Transfers

To move a student to a different class:

1. Go to **Students → Student List** and open the student's record
2. Click **Transfer Student**
3. Select the **New Class** and **Effective Date**
4. Click **Confirm Transfer**

The student's previous class is retained in the transfer history.

---

## Multi-Campus Enrolment

Students are enrolled in one campus at a time. To transfer between campuses:

1. Open the student's record
2. Click **Change Campus**
3. Select the new campus and click **Save**

---

## Attendance

### Recording attendance

1. Go to **Students → Attendance**
2. Select the **Class** and **Date**
3. Mark each student as **Present**, **Absent**, or **Late**
4. Click **Save Attendance**

### Automated absence SMS

When a student is marked absent, an automated SMS can be sent to the student's guardian. To enable this:

1. Go to **Settings → SMS Settings**
2. Toggle **Absence Alert SMS** to on

---

## Health Records

Student health information is stored under the student's record:

1. Open the student record → **Health** tab
2. Add blood group, known conditions, allergies, and emergency contacts
3. Log clinic visits with date, presenting complaint, and treatment notes

---

## Disciplinary Records

Log disciplinary incidents for a student:

1. Open the student record → **Disciplinary** tab
2. Click **Add Incident**
3. Enter the date, nature of the offence, action taken, and the staff member involved

---

## Student Lists and Reports

| Report | Location |
|--------|----------|
| Class list (printable register) | Students → Class List |
| Parent contact list | Students → Parent Contacts |
| Enrolment statistics by class/campus | Students → Analytics |
| Admission register | Students → Admission Register |

---

## Withdrawing a Student

1. Open the student record
2. Click **Withdraw Student**
3. Enter the withdrawal date and reason
4. Click **Confirm**

Withdrawn students are moved to the **Alumni / Archive** section. Their records and academic history are preserved.

---

## Alumni

Former students are accessible under **Students → Alumni**. You can view their full academic history, generate past reports, and re-enrol them if they return.
