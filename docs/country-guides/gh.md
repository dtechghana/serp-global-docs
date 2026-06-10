# Ghana (GH)

**Licensee:** Darrel Technologies Ltd  
**Platform URL:** dtechghana.com / schoolerpglobal.com  
**Currency:** Ghana Cedis (GHS, GH₵)  
**Timezone:** Africa/Accra (GMT, no daylight saving)  
**Language:** English  

---

## Social Security & Payment Modes

| Setting | Value |
|---------|-------|
| Social security scheme | SSNIT (Tiers 1 & 2) |
| POS payment modes | Cash, MTN Mobile Money, Airtel Money, Tigo Cash, Vodafone Cash, Bank Deposit, Bank Transfer, Cheque |

---

## Academic Structure

Ghana's GES / NaCCA framework maps to sERP as follows:

| sERP Division | Ghana Level | Classes |
|---------------|-------------|---------|
| Nursery / Pre-school | Kindergarten (KG) | KG 1–2 |
| Primary | Primary | Basic 1–6 |
| JHS | Junior High School | JHS 1–3 |
| SHS | Senior High School | SHS 1–3 |

---

## Assessment Framework (`gh_basic`)

| Setting | Value |
|---------|-------|
| Assessment label | SBA (School-Based Assessment) |
| CA weight | 50% |
| Exam weight | 50% |
| Pass mark | 50 |
| Terms per year | 3 |
| Term label | Term |

!!! note
    The 50/50 split reflects the current GES SBA policy. Weights can be adjusted per class under **Academic → Classes → Edit**.

---

## Grading Scales

### Primary (`primary`)

| Grade | Score Range | Remark |
|-------|-------------|--------|
| 1 | 80–100 | Excellent |
| 2 | 70–79 | Very Good |
| 3 | 60–69 | Good |
| 4 | 50–59 | Average |
| 5 | 40–49 | Below Average |
| 6 | 0–39 | Fail |

### BECE / JHS (`gh_bece`)

Used for JHS 1–3. The WAEC BECE grading scheme:

| Grade | Score Range | Remark |
|-------|-------------|--------|
| 1 | 80–100 | Excellent |
| 2 | 70–79 | Very Good |
| 3 | 60–69 | Good |
| 4 | 50–59 | Credit |
| 5 | 40–49 | Credit |
| 6 | 30–39 | Pass |
| 7 | 20–29 | Pass |
| 8 | 0–19 | Fail |

### WASSCE / SHS (`gh_wassce`)

Used for SHS 1–3. The WAEC WASSCE grading scheme:

| Grade | Score Range | Remark |
|-------|-------------|--------|
| A1 | 80–100 | Excellent |
| B2 | 75–79 | Very Good |
| B3 | 70–74 | Good |
| C4 | 65–69 | Credit |
| C5 | 60–64 | Credit |
| C6 | 55–59 | Credit |
| D7 | 50–54 | Pass |
| E8 | 45–49 | Pass |
| F9 | 0–44 | Fail |

Create or assign scales in **Settings → Academic Settings → Grading Scales**.

---

## HR & Statutory Deductions

### PAYE (Personal Income Tax)

Ghana PAYE is computed under the **Income Tax Act, 2015 (Act 896)** as amended. Tax is applied to chargeable income on graduated annual bands. Configure current bands in **Settings → HR Settings → Statutory Rates → PAYE Bands**.

For current rates, see GRA guidance at [gra.gov.gh](https://gra.gov.gh).

### SSNIT (Social Security)

Contributions are based on the **National Pensions Act, 2008 (Act 766)** as amended:

| Contribution | Rate | Basis |
|-------------|------|-------|
| Tier 1 — Employer (to SSNIT) | 11% | Basic salary |
| Tier 1 — Employee (to SSNIT) | 5.5% | Basic salary |
| Tier 2 — Employer (to pension trustee) | 2% | Basic salary |

The Tier 2 contribution (2%) is remitted to the school's chosen pension fund trustee (e.g. Enterprise Trustees, Stanbic, Databank). Monthly SSNIT contribution schedules can be exported from **HR → Payroll → [Month] → SSNIT Export**.

!!! note
    The employer's total mandatory contribution is 13% of basic salary (11% Tier 1 + 2% Tier 2). Voluntary Tier 3 contributions are not managed by sERP by default.

---

## deployment.conf.php Reference

When deploying sERP for a Ghana school, copy the following block into `deployment.conf.php` and fill in the school-specific values:

```php
define('VENDOR_ENTITY',         'Darrel Technologies Ltd');
define('VENDOR_URL',            'https://dtechghana.com');
define('ADMIN_ERROR_EMAIL',     'admin@dtechghana.com');
define('CURRENCY_SYMBOL',       'GH₵');
define('CURRENCY_NAME',         'Ghana Cedis');
define('CURRENCY_SUBUNIT',      'Pesewas');
define('CURRENCY_CODE',         'GHS');
define('DECIMAL_SEP',           '.');
define('THOUSANDS_SEP',         ',');
define('ASSESSMENT_LABEL',      'SBA');
define('PHONE_COUNTRY_CODE',    '233');
define('DATE_FORMAT',           'd/m/Y');
define('DEPLOYMENT_TIMEZONE',   'Africa/Accra');
define('DATA_RESIDENCY_COUNTRY','GH');
define('DEPLOYMENT_LANG',       'en');
define('SOCIAL_SECURITY_LABEL', 'SSNIT');
define('SMS_GATEWAY_URL',       'https://sms.dtechghana.com/api/v2');
define('DB_HOST',               'localhost');
define('DB_NAME',               'serp_gh');
define('DB_USER',               'root');
define('DB_PASS',               '');
define('APP_CRYPTO_KEY',        'change-this-key');
define('APP_CRYPTO_IV',         'change-this-iv');
```

---

## Notes

- Ghana operates on GMT year-round — no daylight saving
- The academic year typically runs September to July (three terms)
- WAEC BECE is sat by JHS 3 students; WAEC WASSCE is sat by SHS 3 students
- NABPTEX (National Accreditation Board for Technical & Professional Examinations) applies to technical/vocational schools — not modelled in the default SBA framework
- All billing and financial reports are denominated in Ghana Cedis (GH₵)
- VAT in Ghana is 15% (plus NHIL 2.5% and GETFund 2.5%) — applicable to Darrel Technologies Ltd's invoices to schools; not applied within sERP to school fee billing by default
