# Country Guides Overview

SchoolERP (sERP) ships with profiles for five countries (all currently in West/Central Africa), but the architecture supports deployment in any African country. Each deployment loads a **country profile** (`config/profiles/XX.php`) that sets the locale, currency, timezone, and academic framework.

Select your country from the navigation for deployment-specific details.

---

## At a Glance

| Country | Currency | Timezone | Lang | Exam Bodies | Licensee |
|---------|----------|----------|------|-------------|---------|
| [Ghana](gh.md) | GHS (₵) | Africa/Accra | en | WAEC (BECE, WASSCE) | Darrel Technologies Ltd |
| [Nigeria](ng.md) | NGN (₦) | Africa/Lagos | en | WAEC (WASSCE), NECO | PerAnkh Limited |
| [Côte d'Ivoire](ci.md) | XOF (CFA) | Africa/Abidjan | fr | BEPC, BAC | *(contact Darrel Technologies)* |
| [Senegal](sn.md) | XOF (CFA) | Africa/Dakar | fr | BFEM, BAC | *(contact Darrel Technologies)* |
| [Cameroon](cm.md) | XAF (FCFA) | Africa/Douala | fr | GCE, BAC | *(contact Darrel Technologies)* |

---

## What Varies by Country

| Setting | Configured via |
|---------|----------------|
| Currency symbol and name | Country profile → `deployment.conf.php` |
| Timezone | Country profile → `deployment.conf.php` |
| CA/Exam weight split (default) | Academic framework file |
| Statutory payroll deductions | HR settings → Statutory Rates |
| Built-in grading scales | Database seed + `grades_class.inc` |
| Data residency | `DATA_RESIDENCY_COUNTRY` constant |

All other settings — class structure, school name, campus configuration — are configured per-school within the application.
