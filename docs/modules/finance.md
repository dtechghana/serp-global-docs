# Fees & Finance

The finance module covers the complete billing lifecycle — from setting up fee schedules through to end-of-term financial summaries. All amounts are in the local currency of the deployment (set by `CURRENCY_CODE` in `deployment.conf.php`).

---

## Fee Items

Fee items are the line items that appear on student invoices (e.g. Tuition, PTA Levy, Exam Fees, Development Levy).

Add fee items in **Settings → Finance Settings → Fee Items**.

---

## Fee Schedules

A fee schedule defines how much each class owes for a given term.

1. Go to **Finance → Fee Schedules**
2. Click **Add Fee Schedule**
3. Select **Academic Year**, **Term**, **Class** (or all classes in a division)
4. Add each fee item with its amount
5. Click **Save Schedule**

!!! tip
    You can duplicate a schedule from a previous term and adjust amounts rather than starting from scratch.

---

## Preparing Student Bills

Before a student can make a payment, their bill must be prepared from the fee schedule.

1. Go to **Finance → Prepare Bills**
2. Select the **Term** and **Class**
3. Click **Prepare Bills** — sERP generates a bill for every student in the class based on the fee schedule
4. You can adjust individual student bills from **Finance → Student Bill** if a student has a discount or additional charge

---

## Recording Payments

1. Go to **Finance → Collect Payment** (or search for a student)
2. Find the student by name or ID
3. Enter the **Amount Paid**, **Payment Date**, **Payment Method** (cash, bank transfer, cheque), and any **Reference**
4. Click **Record Payment**

sERP automatically updates the student's outstanding balance and can print a receipt immediately.

### Partial and Instalment Payments

sERP fully supports partial payments. If a parent pays part of their bill, the system records the partial amount and shows the outstanding balance on the debtors list.

---

## Receipts

After recording a payment, a printable receipt is generated automatically. To reprint a receipt:

1. Go to **Finance → Payment History**
2. Find the payment and click **Print Receipt**

---

## Debtors List

1. Go to **Finance → Debtors**
2. Filter by **Term** and **Class** (optional)
3. The list shows all students with outstanding balances
4. Use the **Send SMS Reminder** button to send a bulk fee reminder to guardians of all students on the list

---

## Expenditure

Record school expenditure:

1. Go to **Finance → Expenditure**
2. Click **Add Expenditure**
3. Enter the **Date**, **Category**, **Description**, and **Amount**
4. Click **Save**

---

## Financial Reports

| Report | Location |
|--------|----------|
| Term collection summary | Finance → Reports → Term Summary |
| Class-level fee collection | Finance → Reports → By Class |
| Income & expenditure statement | Finance → Reports → I&E |
| End-of-year financial summary | Finance → Reports → Annual Summary |

---

## Banking

Record bank lodgements and cheque management:

1. Go to **Finance → Banking**
2. Log each bank lodgement with amount, bank name, and date
3. Track cheques received, presented, and cleared

---

## SMS Fee Reminders

Automated SMS reminders can be sent to guardians with outstanding balances:

1. Go to **Finance → Debtors**
2. Filter to the term and class you want to target
3. Click **Send SMS Reminder**
4. Confirm the message template (editable) and click **Send**

SMS usage is deducted from the school's SMS credit balance.

---

## Fee Credits &amp; Advance Payments

Record a credit against a student's account before a bill is raised — for example, when a parent pays a term early or a scholarship credit needs to be applied.

1. Go to **Finance → Student Account → Add Credit**
2. Enter the **Amount**, **Date**, and **Reference**
3. Click **Save** — the credit appears on the student's account immediately

When the next bill is prepared for that student, any available credit is automatically applied and the payable balance is reduced accordingly. Credits are visible on the student's statement of accounts and on receipts.

---

## Payment Refunds

Issue a formal refund when a payment needs to be returned to a parent or guardian.

1. Go to **Finance → Payment History**
2. Find the original payment and click **Refund**
3. Enter the **Refund Amount** (full or partial), **Date**, and **Reason**
4. Click **Process Refund**

Every refund is date-stamped, attributed to the processing staff member, and reflected in the student's statement of accounts. Refunds do not alter or delete the original payment record.

---

## Bill Write-offs

Write off a balance that cannot be recovered — keeping accounts clean and reports accurate without deleting historical data.

1. Go to **Finance → Student Account**
2. Find the student and click **Write Off Balance**
3. Enter the **Amount**, **Date**, and **Reason**
4. Click **Confirm Write-off**

Written-off amounts appear on the student's statement with a "Write-off" label. The original bill and any payments remain intact.

---

## Student Statement of Accounts

A complete, chronological financial statement per student — every bill, payment, credit, refund, and write-off in a single view.

1. Go to **Finance → Student Account** and search for the student
2. Click **View Statement**
3. Filter by **Date Range** or view the full history
4. Click **Print** to generate a printable PDF statement

The statement can be shared with parents during fee discussions or provided on request as a formal account summary.

---

## Fixed Assets Register

Track every physical asset owned by the school — from buildings and ICT equipment to laboratory apparatus and vehicles.

### Asset Categories

Go to **Fixed Assets → Categories** to manage categories. Each category defines a default useful life (years) and depreciation rate. Seven categories are pre-seeded (Buildings, Vehicles, ICT Equipment, Fixtures & Fittings, Furniture, Land, Laboratory Equipment).

### Adding an Asset

1. Go to **Fixed Assets → Register → Add Asset**
2. Select a category — the asset code is generated automatically (e.g. `FA-ICT-0001`)
3. Enter acquisition date, cost, salvage value, useful life, and depreciation method (Straight-Line or Declining Balance)

### Depreciation

Go to **Fixed Assets → Depreciation** to compute annual depreciation in bulk or per asset. Results show opening value, annual charge, and closing book value for each year.

### Disposals

Open an asset's detail view and click **Dispose** to record a sale, write-off, or damage event. The asset status updates automatically.

---

## Double-Entry Accounting

A complete double-entry bookkeeping system with automatic posting of school financial transactions.

### Chart of Accounts

Go to **Accounting → Chart of Accounts** to manage accounts. Five account types are supported: Asset, Liability, Equity, Revenue, and Expense. A default chart is seeded on installation and can be extended or customised.

### Financial Periods

Create periods under **Accounting → Periods** (e.g. "Term 1 2025"). Close a period to lock it against further posting.

### Journals

| Type | Purpose |
|------|---------|
| Receipt | Income received |
| Payment | Expenditure paid |
| Contra | Internal transfer between accounts |
| Journal | Manual general ledger adjustment |
| Payroll | Monthly payroll entry |

Every journal must balance (debits = credits). Journals can be reversed, creating a mirror entry.

### Auto-Posting

The following transactions post to the ledger automatically:

- Fee payments (billable and non-billable)
- POS / store sales
- Canteen payments
- Expenditure records
- Monthly payroll (via **Accounting → Sync → Payroll**)

Posting failures are logged under **Accounting → Posting Failures**.

### Financial Reports

| Report | Description |
|--------|-------------|
| Trial Balance | Debit/credit totals per account |
| Income Statement | Revenue vs expenses (surplus/deficit) |
| Balance Sheet | Assets, liabilities, equity as at a date |
| General Ledger | Running balance for one account |
| Budget vs Actual | Budgeted vs actual per period |

Export data to **CSV** or **IIF** (QuickBooks import format) from the Reports page.
