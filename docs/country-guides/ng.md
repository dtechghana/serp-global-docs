# Nigeria (NG)

**Licensee:** PerAnkh Limited  
**Platform URL:** schoolerpnigeria.com  
**Currency:** Nigerian Naira (NGN, ₦)  
**Timezone:** Africa/Lagos (WAT, GMT+1)  
**Language:** English  

---

## Social Security & Payment Modes

| Setting | Value |
|---------|-------|
| Social security scheme | RSA (PenCom) / NHF |
| POS payment modes | Cash, Bank Transfer, Bank Deposit, POS Terminal, USSD Transfer, Cheque |

---

## Academic Structure

Nigeria's UBE / NERDC system maps to sERP as follows:

| sERP Division | Nigeria Level | Classes |
|---------------|---------------|---------|
| Nursery / Pre-school | Early Childhood Care & Education (ECCE) | Nursery 1–2, KG |
| Primary | Primary | Primary 1–6 |
| JSS | Junior Secondary School | JSS 1–3 |
| SSS | Senior Secondary School | SSS 1–3 |

---

## Assessment Framework (`ng_basic`)

| Setting | Value |
|---------|-------|
| CA weight | 30% |
| Exam weight | 70% |
| Pass mark | 40 |
| Terms per year | 3 |
| Term label | Term |

!!! note
    The 30/70 CA/Exam split is the default per UBE guidelines. It can be adjusted per class under **Academic → Classes → Edit**.

---

## Grading Scales

### Primary (`primary`)

| Grade | Score Range | Remark |
|-------|-------------|--------|
| A | 80–100 | Excellent |
| B | 65–79 | Very Good |
| C | 50–64 | Good |
| D | 40–49 | Average |
| F | 0–39 | Fail |

### WAEC WASSCE / NECO

For JSS and SSS levels, create a custom grading scale using the WAEC A1–F9 scheme:

| Grade | Score Range | Remark |
|-------|-------------|--------|
| A1 | 75–100 | Excellent |
| B2 | 70–74 | Very Good |
| B3 | 65–69 | Good |
| C4 | 60–64 | Credit |
| C5 | 55–59 | Credit |
| C6 | 50–54 | Credit |
| D7 | 45–49 | Pass |
| E8 | 40–44 | Pass |
| F9 | 0–39 | Fail |

Create this scale in **Settings → Academic Settings → Custom Grading Scales** with name `ng_waec` (or similar) and assign it to JSS/SSS classes.

---

## HR & Statutory Deductions

### PAYE (Personal Income Tax)

Nigeria PAYE is computed under the **Personal Income Tax Act (PITA)** as amended. Taxable income = gross income minus statutory reliefs.

| Statutory Relief | Rate |
|-----------------|------|
| Consolidated Relief Allowance | Higher of ₦200,000 or 1% of gross income, plus 20% of gross income |

Tax is then applied to chargeable income on graduated bands. Configure current bands in **Settings → HR Settings → Statutory Rates → PAYE Bands**.

For current rates, see FIRS guidance at [firs.gov.ng](https://firs.gov.ng).

### Pension (PenCom / RSA)

Contributions are based on the **Pension Reform Act 2014**:

| Deduction | Rate | Pensionable Earnings |
|-----------|------|---------------------|
| Employee contribution | 8% | Basic + Housing + Transport |
| Employer contribution | 10% | Basic + Housing + Transport |

PFA (Pension Fund Administrator) name and RSA PIN are stored per staff member on their payroll record. Monthly contribution schedules can be exported from **HR → Payroll → [Month] → Pension Export** for remittance to the PFA.

### NHF (National Housing Fund)

NHF contributions are deducted from all eligible employees:

| Deduction | Rate | Basis |
|-----------|------|-------|
| NHF | 2.5% | Basic salary |

---

## Data Residency & Compliance

Nigeria deployments are hosted in GDPR-compliant data centres. PerAnkh Limited processes school data in compliance with the **Nigerian Data Protection Act 2023 (NDPA)** and the **Nigeria Data Protection Regulation (NDPR) 2019**.

- Each school has an isolated database — no cross-school data access
- A **Data Processing Agreement (DPA)** is available on request from PerAnkh Limited

---

## Notes

- Nigeria operates on WAT (West Africa Time, GMT+1) year-round — no daylight saving
- The academic year typically runs September to July (three terms)
- WAEC WASSCE is sat by SSS 3 students; NECO is an alternative national examination
- JAMB (UTME) is a university entrance exam — not assessed within sERP directly
- All billing, receipts, and financial reports are denominated in Nigerian Naira (₦); there is no foreign currency billing
- VAT in Nigeria is 7.5% (Finance Act 2019) — applicable to PerAnkh Limited's invoices to schools
