# Canteen

The canteen module tracks daily meal subscriptions for students — recording which students have canteen access, logging daily payments, and producing attendance and payment reports.

---

## Setup

### Enable Canteen per Student or Class

Before recording payments, activate canteen tracking for the relevant students.

1. Go to **Canteen → Setup**
2. Select a **Class** from the dropdown
3. For each student, toggle canteen status **On** or **Off** and enter their daily canteen fee amount
4. Click **Save**

Students with canteen enabled appear on the daily payment screen. Students without canteen access are excluded.

---

## Recording Daily Payments

1. Go to **Canteen → Daily Payment**
2. Select the **Class** and **Date**
3. The list shows all canteen-enabled students in that class
4. Check the box next to each student who paid for that day
5. Click **Record Payments**

Payments are date-stamped and attributed to the recording staff member. A student can be marked as paid only once per day.

---

## Payment Tracking

View a student's canteen payment history:

1. Go to **Canteen → Payment Tracking**
2. Search for the student by name or ID
3. The record shows each day the student paid, the amount, and the recording date

---

## Reports

| Report | Location | Description |
|--------|----------|-------------|
| Class canteen summary | Canteen → Reports | Total payments per student for a period |
| Daily collection | Canteen → Reports | Total collected on a given day |
| Term summary | Canteen → Reports | Aggregate canteen income by class and term |

Filter reports by **Class**, **Date Range**, **Term**, or **Academic Year**.

---

## Notes

- Canteen income is posted automatically to the double-entry ledger if the Accounting module is active (requires the relevant income account to be mapped in **Accounting → Settings**).
- Each school day is tracked independently; there is no automatic carry-forward for absent students.
- Daily canteen fees can differ per student — useful if different meal packages are offered.
