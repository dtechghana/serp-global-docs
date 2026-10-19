# Fees & Finance

The finance module covers the complete billing lifecycle — from setting up fee schedules through to end-of-term financial summaries. All amounts are in the local currency of the deployment (set by `CURRENCY_CODE` in `deployment.conf.php`).

!!! note
    For schools with more than one campus, a staff user restricted to a single campus (see [User Management](../getting-started/user-management.md)) only sees and manages fees, bills, reminders, and debtors belonging to their own campus throughout this module.

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

!!! note
    A student's fee items only appear as payable on the payment screen once their bill has actually been prepared for that term. Arrears carried over from an already-billed prior term are unaffected and always show, regardless of whether the current term's bill has been prepared yet.

---

## Recording Payments

1. Go to **Finance → Collect Payment** (or search for a student)
2. Find the student by name or ID
3. Enter the **Amount Paid**, **Payment Date**, **Payment Method** (cash, bank deposit, cheque, mobile money), and any **Reference**
4. Click **Record Payment**

sERP automatically updates the student's outstanding balance and can print a receipt immediately.

!!! note
    For **Bank Deposit**, the bank field selects one of the school's own accounts (set up under [Banking](#banking)) — the payment is automatically posted there too, updating that account's running balance. For **Cheque**, the bank field instead identifies the *payer's* bank, from a generic reference list, for reconciliation purposes — this is a different field from Bank Deposit's, since a cheque's bank isn't one of the school's own accounts. If a Bank Deposit payment is later cancelled, the posted amount is automatically reversed from the account.

### Partial and Instalment Payments

sERP fully supports partial payments. If a parent pays part of their bill, the system records the partial amount and shows the outstanding balance on the debtors list.

---

## Online Payments

Parents and students can pay school fees online by card, mobile money, or bank transfer, via [Paystack](https://paystack.com).

**Setup (admin, one-time):**

1. Go to **Settings → Payment Gateway**
2. Enter your school's Paystack **Public Key** and **Secret Key**, from your Paystack dashboard
3. Save — online payments are unavailable until both are configured

!!! note
    The Secret Key is encrypted at rest. Once saved, the field shows a placeholder instead of the actual key — leave it blank when saving other changes to keep the existing key, or enter a new one to replace it.

**Paying online (parent/student portal):**

1. From the portal's **Fees** page, click **Pay Online Now**
2. Enter an email address and the amount to pay
3. Submit — this redirects to Paystack's hosted checkout page to complete payment

Once Paystack confirms the transaction, the payment is posted to the student's fee account the same way an admin-recorded payment is — arrears, custom bills, and fee items are settled in the same priority order, any overpayment is credited to the student's account, and a receipt and SMS confirmation are sent automatically.

---

## Receipts

After recording a payment, a printable receipt is generated automatically. To reprint a receipt:

1. Go to **Finance → Payment History**
2. Find the payment and click **Print Receipt**

!!! note
    sERP can also automatically email a PDF copy of the receipt to the student's registered guardian email address when a payment is recorded, alongside the existing SMS confirmation. This is configured by your licensee as part of your installation's mail settings.

---

## Debtors List

1. Go to **Finance → Debtors**
2. Filter by **Term** and **Class** (optional)
3. The list shows all students with outstanding balances, with a totals row summing bills, payments, and amounts owed across everyone shown
4. Use the **Send SMS Reminder** button to send a bulk fee reminder to guardians of all students on the list
5. Click **Export CSV** to download the current filtered list, including the totals row, as a spreadsheet

!!! tip
    Add an **As Of Date** to see the debtors position as it stood on a past date, rather than today — useful for reconstructing what was actually owed at a specific point in the term.

---

## Expenditure

Record school expenditure:

1. Go to **Finance → Expenditure**
2. Click **Add Expenditure**
3. Enter the **Date**, **Category**, **Description**, and **Amount**
4. Select a **Payment Type** — Cash, Cheque, Bank Deposit, Mobile Money, or Other
5. Click **Save**

!!! note
    For Cheque and Bank Deposit, a **Bank Account** field appears — select which of the school's own accounts (set up under [Banking](#banking)) the money is being paid from. Both payment types draw on the school's own account here, since an expenditure cheque is one the school writes itself rather than receives. If no bank account has been set up yet, a warning links directly to the Banking module to add one.

---

## Financial Reports

| Report | Location |
|--------|----------|
| Term collection summary | Finance → Reports → Term Summary |
| Class-level fee collection | Finance → Reports → By Class |
| Income & expenditure statement | Finance → Reports → I&E |
| End-of-year financial summary | Finance → Reports → Annual Summary |
| Bill payments received | Finance → Reports → Bill Payment Reports |
| Non-bill payments received (e.g. canteen top-ups, miscellaneous fees) | Finance → Reports → Non-Bill Payment Reports |

Any report here that offers a **Download PDF** button also offers **Export CSV** alongside it, for further analysis in a spreadsheet. The two payment reports above can also be filtered by searching for a student by name, and both list each payment's Student ID and Class alongside the usual date/amount/method columns.

---

## Banking

Manage the school's own bank accounts, and track lodgements and cheque transactions against them:

1. Go to **Finance → Banking**
2. Add each of the school's bank accounts (bank name, account number, account name)
3. Log each bank lodgement or cheque transaction with amount and date
4. Each account keeps a running balance, computed from its own transaction history

!!! note
    This is where "Bank Deposit" payments recorded elsewhere in sERP — fee payments and expenditure — actually post to. A fee payment credits the selected account automatically; an expenditure debits it. Cancelling a Bank Deposit fee payment automatically posts a reversing debit, so the account's balance always reflects what's actually still outstanding. These automatic entries appear in the account's transaction history alongside manually-entered lodgements and cheques, distinguishable by their "finance" source.

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

## Store & Inventory (Point of Sale)

Record direct sales of school store/shop stock (uniforms, stationery, snacks, and similar items) to students or walk-in customers — separate from fee billing. Each sale automatically decrements the stock quantity of every item sold.

!!! note
    For schools with more than one campus, a staff user restricted to a single campus only sees and manages Store & Inventory sales belonging to their own campus throughout this module.

### Recording a Sale

1. Go to **Finance → Store & Inventory → New Sale**
2. Select the student (or enter walk-in customer details) the sale is for
3. Add each item being sold, with its quantity
4. Click **Save** — sERP generates a receipt and deducts the quantity sold from each item's stock

### Cancelling a Sale

Cancel a sale that was recorded in error — for example, a wrong item or quantity.

1. Go to **Finance → Store & Inventory → Sales**
2. Click the **Cancel Sale** icon next to the sale in the list, or open the sale's receipt and click **Cancel Sale**
3. Enter a **Reason** for cancelling
4. Click **Cancel Sale** to confirm

Cancelling reverses the stock for every item in the sale — the quantity sold is added back to inventory automatically, and logged in each item's own stock adjustment history. The sale record itself is never deleted: it's kept with a "Cancelled" status, along with who cancelled it, when, and why, all shown if the sale is viewed or a cancellation is attempted again. A cancelled sale no longer appears in the default Sales list (which only shows completed sales), but remains reachable directly via its receipt link, which shows a "Cancelled" badge in place of the usual print option.

A cashier can cancel a sale they recorded themselves; an admin or super admin can cancel any sale. Cancelling is controlled by its own access permission, separate from viewing the module or recording a sale — an admin must grant it explicitly for staff who need to cancel sales.

---

## Fixed Assets Register

Track every physical asset owned by the school — from buildings and ICT equipment to laboratory apparatus and vehicles.

### Asset Categories

Go to **Fixed Assets → Categories** to manage categories. Each category defines a default useful life (years) and depreciation rate. Seven categories are pre-seeded (Buildings, Vehicles, ICT Equipment, Fixtures & Fittings, Furniture, Land, Laboratory Equipment).

### Adding an Asset

1. Go to **Fixed Assets → Register → Add Asset**
2. Select a category — the asset code is generated automatically (e.g. `FA-ICT-0001`)
3. Enter acquisition date, cost, salvage value, useful life, and depreciation method (Straight-Line or Declining Balance)
4. Choose a **Payment Record** option: **Record a new payment now** (captures payment type, bank account, cheque number as needed, and creates an Expenditure entry for the purchase automatically), **Link an existing expenditure record** (if Accounts already recorded the purchase separately before the asset itself was added to the register), or **No expenditure record** (for an asset that cost the school nothing, e.g. donated)

!!! note
    Editing an asset's name, cost, or acquisition date later automatically updates its linked expenditure record to match, if it has one. An asset's linked expenditure record (if any) is shown on both its detail view and its edit page.

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
