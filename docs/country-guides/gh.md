# Ghana (GH)

**Licensee:** Darrel Technologies Ltd  
**Platform URL:** schoolerpghana.com  
**Currency:** Ghana Cedi (GHS, ₵)  
**Timezone:** Africa/Accra (GMT+0)  
**Language:** English  

---

## Social Security & Payment Modes

| Setting | Value |
|---------|-------|
| Social security scheme | SSNIT |
| `SOCIAL_SECURITY_LABEL` | `SSNIT` |
| POS payment modes | Cash, MTN Mobile Money, Airtel Money, Tigo Cash, Vodafone Cash, Bank Deposit, Bank Transfer, Cheque |

---

## Country Profile Constants

```php
define('DEPLOYMENT_COUNTRY',    'GH');
define('CURRENCY_CODE',         'GHS');
define('CURRENCY_SYMBOL',       '₵');
define('CURRENCY_NAME',         'Cedi');
define('CURRENCY_SUBUNIT',      'Pesewa');
define('PHONE_COUNTRY_CODE',    '+233');
define('DEPLOYMENT_TIMEZONE',   'Africa/Accra');
define('DEPLOYMENT_LANG',       'en');
define('ACADEMIC_FRAMEWORK',    'gh_basic');
define('DATA_RESIDENCY_COUNTRY','GH');
```

---

## Academic Structure

Ghana's Basic Education (GES) structure maps to sERP as follows:

| sERP Division | Ghana Level | Classes |
|---------------|-------------|---------|
| KG / Pre-school | Kindergarten | KG 1, KG 2 |
| Primary | Primary | Primary 1–6 |
| JHS | Junior High School | JHS 1–3 |
| SHS | Senior High School | SHS 1–3 |

---

## Assessment Framework (`gh_basic`)

| Setting | Value |
|---------|-------|
| CA weight | 50% |
| Exam weight | 50% |
| Pass mark | 50 |
| Terms per year | 3 |
| Term label | Term |

---

## Built-in Grading Scales

### Primary (`primary`)

| Grade | Score Range | Remark |
|-------|-------------|--------|
| A | 80–100 | Excellent |
| B | 70–79 | Very Good |
| C | 60–69 | Good |
| D | 50–59 | Average |
| E | 40–49 | Below Average |
| F | 0–39 | Fail |

### BECE (`gh_bece`) — WAEC Basic Certificate

| Grade | Score Range | Remark |
|-------|-------------|--------|
| A1 | 80–100 | Excellent |
| B2 | 70–79 | Very Good |
| B3 | 65–69 | Good |
| C4 | 60–64 | Credit |
| C5 | 55–59 | Credit |
| C6 | 50–54 | Credit |
| D7 | 45–49 | Pass |
| E8 | 40–44 | Pass |
| F9 | 0–39 | Fail |

### WASSCE (`gh_wassce`) — WAEC Senior School Certificate

Same A1–F9 scale as BECE with identical grade boundaries.

---

## HR & Statutory Deductions

| Deduction | Employee | Employer | Notes |
|-----------|----------|----------|-------|
| Income Tax (PAYE) | Variable | — | GRA income tax bands |
| SSNIT | 5.5% | 13% | Gross salary |
| Tier 2 (Trustee) | 5% | — | Gross salary (configurable) |

Configure current rates in **Settings → HR Settings → Statutory Rates**.

For the current GRA income tax bands, see [gra.gov.gh](https://gra.gov.gh).

---

## Data Residency

Ghana deployments are hosted by Darrel Technologies Ltd within Ghana. Data is processed under the **Data Protection Act, 2012 (Act 843)** and the Data Protection Commission (DPC) framework.

---

## Notes

- Ghana operates on GMT+0 year-round (no daylight saving)
- The academic year runs approximately September to July
- BECE is sat at the end of JHS 3; WASSCE at the end of SHS 3
- WAEC grading uses A1 (highest) to F9 (fail) for both BECE and WASSCE
