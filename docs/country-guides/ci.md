# Côte d'Ivoire (CI)

**Licensee:** *(contact Darrel Technologies Ltd)*  
**Currency:** West African CFA Franc (XOF, CFA)  
**Timezone:** Africa/Abidjan (GMT+0)  
**Language:** French  

---

## Social Security & Payment Modes

| Setting | Value |
|---------|-------|
| Social security scheme | CNPS |
| `SOCIAL_SECURITY_LABEL` | `CNPS` |
| POS payment modes | Cash, Orange Money, MTN Mobile Money, Wave, Bank Transfer, Cheque |

---

## Country Profile Constants

```php
define('DEPLOYMENT_COUNTRY',    'CI');
define('CURRENCY_CODE',         'XOF');
define('CURRENCY_SYMBOL',       'CFA');
define('CURRENCY_NAME',         'Franc CFA');
define('CURRENCY_SUBUNIT',      'Centime');
define('PHONE_COUNTRY_CODE',    '+225');
define('DEPLOYMENT_TIMEZONE',   'Africa/Abidjan');
define('DEPLOYMENT_LANG',       'fr');
define('ACADEMIC_FRAMEWORK',    'francophone_basic');
define('DATA_RESIDENCY_COUNTRY','CI');
```

---

## Academic Structure

Côte d'Ivoire's MENA (Ministère de l'Éducation Nationale) system:

| sERP Division | CI Level | Classes |
|---------------|----------|---------|
| Préscolaire | Maternelle | Petite, Moyenne, Grande Section |
| Primaire | École primaire | CP1, CP2, CE1, CE2, CM1, CM2 |
| Collège | Collège | 6ème, 5ème, 4ème, 3ème |
| Lycée | Lycée | Seconde, Première, Terminale |

---

## Assessment Framework (`francophone_basic`)

| Setting | Value |
|---------|-------|
| CA weight | 40% |
| Exam weight | 60% |
| Pass mark | 50 |
| Terms per year | 3 |
| Term label | Trimestre |

---

## National Examinations

| Exam | Level | Awarding body |
|------|-------|---------------|
| CEP (Certificat d'Études Primaires) | CM2 | MENA |
| BEPC (Brevet d'Études du Premier Cycle) | 3ème | MENA / DECO |
| BAC (Baccalauréat) | Terminale | MENA / DECO |

---

## HR & Statutory Deductions

| Deduction | Rate | Body |
|-----------|------|------|
| IRPP (Impôt sur les Revenus des Personnes Physiques) | Progressive bands | DGI |
| CNPS — Retraite (employee) | 3.2% | CNPS |
| CNPS — Retraite (employer) | 7.7% | CNPS |
| CNPS — Accident du travail (employer) | 2–5% (by sector) | CNPS |
| IS (Impôt Spécial Équivalent) | 1.2% | DGI |

!!! warning
    Ivorian statutory rates are subject to the annual Finance Law (Loi de Finances). Verify current rates before running payroll.

---

## Notes

- CFA Franc (XOF) is shared with Senegal and other UEMOA countries
- The academic year runs from September to June
- Côte d'Ivoire operates on GMT+0 year-round (same as Ghana/Accra)
- French is the language of instruction; sERP labels can be adjusted per deployment
