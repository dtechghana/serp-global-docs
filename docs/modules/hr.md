# HR & Payroll

The HR module manages staff records, employment information, monthly payroll, and country-specific statutory deductions.

---

## Adding a Staff Member

1. Go to **HR → Add Staff**
2. Fill in required fields:
    - **First name**, **Last name**
    - **Date of birth**, **Gender**, **Nationality**
    - **Department**, **Designation** (staff type)
    - **Employment date**, **Employment type** (permanent, contract, part-time)
    - **Contact details** and **emergency contacts**
3. Upload a passport photo (optional)
4. Click **Save Staff**

A staff ID is auto-generated using the Staff ID Prefix configured in settings.

---

## Departments and Designations

Before adding staff, set up:

- **Departments** — go to **HR → Departments** (e.g. Teaching, Administration, Security)
- **Designations** — go to **Settings → HR Settings → Staff Types** (e.g. Head Teacher, Class Teacher, Accountant)

---

## Salary Structure

Each staff member has a salary structure comprising a basic salary and one or more allowances.

1. Open a staff record → **Payroll** tab
2. Set the **Basic Salary**
3. Add allowances (e.g. Housing Allowance, Transport Allowance) with amounts
4. Statutory deductions are calculated automatically based on the deployment's country

---

## Running Monthly Payroll

1. Go to **HR → Payroll → Run Payroll**
2. Select the **Month** and **Year**
3. Review the payroll summary — each staff member's gross, deductions, and net pay
4. Click **Confirm & Generate Payroll**
5. Generate pay slips and bank advice letters from the payroll run record

---

## Social Security Number

Each staff record stores a national social security or pension registration number. The field label in the UI is driven by the deployment's `SOCIAL_SECURITY_LABEL` constant (set in `deployment.conf.php` from the country profile):

| Country | Label | Scheme |
|---------|-------|--------|
| Ghana | SSNIT | Social Security and National Insurance Trust |
| Nigeria | RSA / NHF | Retirement Savings Account / National Housing Fund |
| Côte d'Ivoire | CNPS | Caisse Nationale de Prévoyance Sociale |
| Senegal | IPRES / CSS | Institut de Prévoyance Retraite du Sénégal / Caisse de Sécurité Sociale |
| Cameroon | CNPS | Caisse Nationale de Prévoyance Sociale |

This label also appears in the payroll staff search, bank advice search, and user permission rows.

---

## Statutory Deductions

Statutory deductions are computed automatically based on the country profile:

=== "Ghana (GH)"
    | Deduction | Basis |
    |-----------|-------|
    | Income Tax (PAYE) | GRA income tax bands (PITA Ghana) |
    | SSNIT (employee 5.5%) | Gross salary |
    | SSNIT (employer 13%) | Gross salary |
    | Tier 2 / Trustee | Configurable % of salary |

=== "Nigeria (NG)"
    | Deduction | Basis |
    |-----------|-------|
    | Income Tax (PAYE) | PITA bands + state schedule |
    | Pension — Employee (8%) | Basic + Housing + Transport |
    | Pension — Employer (10%) | Basic + Housing + Transport |
    | NHF (2.5%) | Basic salary |

=== "Francophone (CI / SN / CM)"
    | Deduction | Basis |
    |-----------|-------|
    | IRPP / IGR (income tax) | Country-specific brackets |
    | CNPS (social security) | Gross salary |

!!! note
    Statutory rates are periodically revised by national revenue authorities. Check your country guide for the current rates and update the configuration under **Settings → HR Settings → Statutory Rates** when rates change.

---

## Pay Slips

After running payroll, generate individual pay slips:

1. Go to **HR → Payroll → [Month] → Pay Slips**
2. Select **All Staff** or an individual staff member
3. Click **Print Pay Slips** or **Download PDF**

---

## Bank Advice Letters

Bank advice letters list each staff member's net pay for direct bank lodgement or electronic transfer instruction.

1. Go to **HR → Payroll → [Month] → Bank Advice**
2. Select the bank (if multiple banks are used)
3. Click **Print / Download**

---

## Staff Attendance & Leave

### Recording staff attendance

1. Go to **HR → Staff Attendance**
2. Select the **Date** and mark each staff member
3. Click **Save**

### Leave management

1. Go to **HR → Leave**
2. Click **Add Leave Record**
3. Select the staff member, leave type (annual, sick, maternity, etc.), start and end dates
4. Approved leave is deducted from the staff member's leave balance

---

## Documents

Attach employment documents (offer letters, certifications, ID scans) to a staff record:

1. Open the staff record → **Documents** tab
2. Click **Upload Document**
3. Select the document type and upload the file
