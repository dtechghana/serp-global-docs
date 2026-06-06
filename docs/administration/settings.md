# System Settings

The settings area in sERP covers global configuration options that affect all users and modules. Settings are grouped into sections accessible from **Settings** in the main navigation.

---

## General Settings

| Setting | Description |
|---------|-------------|
| School Name | Full name of the school — appears on reports, receipts, and the login page |
| School Logo | PNG/JPG logo used on terminal reports and the nav header |
| School Address | Printed on official documents |
| School Phone / Email | Printed on official documents and used in automated messages |
| Student ID Prefix | Prefix for auto-generated student IDs |
| Staff ID Prefix | Prefix for auto-generated staff IDs |

---

## Academic Settings

### Academic Calendar

Manage calendar entries and set the active term from a single page. Access it via **Settings → Academic → wrench icon** next to *Default Academic Year / Term*.

The page has three areas:

- **Add Calendar Entry** (left form) — create a new entry
- **Active Calendars** (top-right panel) — shows the currently active entry for Trimester and for Semester
- **All Entries** (table) — lists every entry with Activate and Delete actions

#### Adding an entry

| Field | Description |
|-------|-------------|
| Academic Year | Start and end years, e.g. `2025 / 2026` |
| Label | Optional display name — defaults to `Default` if left blank |
| Category | `Trimester` or `Semester` |
| Term/Semester | `First`, `Second`, or `Third` |
| Begins | First day of the term/semester |
| Ends | Last day of the term/semester |

Click **Add Entry**. The row is injected into the All Entries table immediately without a page reload.

#### Activating an entry

Click **Activate** on any row. The Active Calendars panel refreshes instantly and the row is highlighted green. Only one entry per category can be active at a time; the previously active entry reverts to inactive automatically.

#### Deleting an entry

Click the trash icon on a row and confirm. Two restrictions apply:

- An **active** entry cannot be deleted — activate a different entry first, then delete the old one.
- The delete button is only shown to users with **administrator access** (access level 100).

### CA Components

Define the sub-components of the CA allocation (e.g. Class Test 10%, Mid-Term 10%, Homework 10%). These are global and apply to all classes unless overridden.

### Grading Scales

See the dedicated [Grading Scales](grading-scales.md) documentation.

---

## Finance Settings

| Setting | Description |
|---------|-------------|
| Fee Items | List of billable line items (e.g. Tuition, PTA Levy) |
| Discount Types | Predefined discount categories (e.g. Staff Child, Scholarship) |
| Payment Methods | Accepted payment methods shown on receipts |
| Invoice Prefix | Prefix for auto-generated invoice numbers |

---

## HR Settings

| Setting | Description |
|---------|-------------|
| Staff Types (Designations) | Job titles/grades (e.g. Head Teacher, Accountant) |
| Leave Types | Types of leave and annual entitlement per type |
| Statutory Rates | PAYE bands, pension rates, NHF — see country guide for current values |
| Bank List | Banks used for payroll bank advice letters |

---

## SMS Settings

| Setting | Description |
|---------|-------------|
| SMS Gateway | API endpoint and credentials (provided by licensee) |
| Sender ID | The name or number that appears as the SMS sender |
| Absence Alert | Toggle automated absence SMS to parents |
| Fee Reminder | Template for fee reminder SMS |
| Result Notification | Toggle result published SMS |
| Payment Confirmation | Toggle payment receipt SMS |

Test the gateway configuration using the **Send Test SMS** button after saving credentials.

---

## Deployment Info

**Settings → Deployment Info** is a read-only page showing the active deployment configuration derived from `deployment.conf.php` and the loaded country profile:

- Country, timezone (with live current time), language
- Currency code, symbol, name, and subunit
- Active academic framework
- Data residency country
- A warning banner if any required constants are missing or set to placeholder values

This page is useful for verifying configuration after setup or after an update.
