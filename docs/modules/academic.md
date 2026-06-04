# Academic Management

The academic module handles all aspects of curriculum delivery and assessment — from configuring the CA structure through to generating printable terminal reports.

---

## Academic Calendar

sERP supports two calendar structures:

| Type | Terms per year | Typical use |
|------|---------------|-------------|
| **Trimester** | 3 | Most West African schools |
| **Semester** | 2 | Some higher secondary / vocational |

Configure the current term and academic year under **Settings → Academic Settings → Academic Calendar**. This setting is global — it affects which term is "live" for scoring and reporting.

---

## Grading Scales

Grading scales define the grade labels, score boundaries, and remarks for a subject category. Each class is assigned one grading scale. sERP ships with built-in scales for common West African exam bodies.

### Built-in scales

| Scale name | Exam body | Range |
|------------|-----------|-------|
| `primary` | Generic primary | A–F with numerical boundaries |

Additional scales can be created in **Settings → Academic Settings → Custom Grading Scales**.

### Creating a custom scale

1. Go to **Settings → Academic Settings → Custom Grading Scales**
2. Enter a **Scale Name** (used as the identifier in class settings, e.g. `ng_waec`)
3. Define score boundaries for each grade and a remark for each grade
4. Click **Save Scale**

!!! note
    Scale names must be unique. Once a scale is in use by one or more classes, changing its boundaries affects all past and future scores computed against it.

---

## CA / Exam Weight Configuration

The CA/Exam weight split determines how the terminal score is computed. It is set per class.

1. Go to **Academic → Classes**
2. Edit the class
3. Set the **CA Weight** and **Exam Weight** (must sum to 100%)
4. Click **Save**

The default split is determined by the [academic framework](../deployment/country-profiles.md#academic-frameworks) for the deployment's country.

### CA Components

Within the CA allocation, you can define multiple sub-components (e.g. Class Test 10%, Homework 5%, Mid-Term 15%). Components are configured in **Settings → Academic Settings → CA Components** and apply globally.

---

## Entering Scores

Teachers enter scores from the **Academic → Scores** section (or from the Teacher Portal).

1. Select the **Academic Year**, **Term**, **Class**, and **Subject**
2. A score entry table shows all enrolled students
3. Enter CA component scores and the exam score for each student
4. sERP computes the total automatically: `(CA total × CA weight%) + (Exam score × Exam weight%)`
5. Click **Save Scores**

sERP applies the class's grading scale automatically and displays the computed grade and remark.

---

## Terminal Reports

Terminal reports are generated automatically from the scores entered. They include:

- School name, logo, and term
- Student details (name, class, attendance summary)
- Subject-by-subject scores (CA, Exam, Total, Grade, Remark)
- Class position and average
- Head teacher's remarks
- Promotion status (if configured)

### Generating reports

1. Go to **Academic → Terminal Reports**
2. Select the **Term** and **Class**
3. Click **Generate Reports**
4. Print from the browser or click **Download PDF**

!!! tip
    Ensure all subject scores are entered before generating reports. Students with missing scores will show incomplete reports.

---

## Exam Timetable

1. Go to **Academic → Exam Timetable**
2. Select the **Term** and **Class**
3. Add entries for each exam session (date, time, subject, venue)
4. The timetable is visible to students via the student portal

---

## Assignments

1. Go to **Academic → Assignments**
2. Click **Add Assignment**
3. Set the **Class**, **Subject**, **Due Date**, and **Description**
4. Students see the assignment in the student portal
5. Track submissions and enter grades from **Academic → Assignments → View Submissions**

---

## Year Groups (WAEC / National Exam Cohorts)

Year groups are used to define cohorts of students sitting a national examination together (e.g. WAEC WASSCE, NECO, BECE).

1. Go to **Academic → Year Groups**
2. Click **Add Year Group**
3. Enter the year group label (e.g. `Year Group 2025/2026`)
4. Add students to the year group from their student record
