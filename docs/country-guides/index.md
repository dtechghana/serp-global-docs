# Country Guides Overview

sERP ships with profiles for 18 countries across West and East Africa. Each deployment loads a **country profile** (`config/profiles/XX.php`) that sets the locale, currency, timezone, and academic framework.

Select your country from the navigation for deployment-specific details.

---

## West Africa

| Country | Currency | Timezone | Lang | Framework | Licensee |
|---------|----------|----------|------|-----------|---------|
| [Nigeria](ng.md) | NGN (₦) | Africa/Lagos | en | ng_basic | PerAnkh Limited |
| [Côte d'Ivoire](ci.md) | XOF (CFA) | Africa/Abidjan | fr | francophone_basic | *(contact Darrel Technologies)* |
| [Senegal](sn.md) | XOF (CFA) | Africa/Dakar | fr | francophone_basic | *(contact Darrel Technologies)* |
| [Cameroon](cm.md) | XAF (FCFA) | Africa/Douala | fr | francophone_basic | *(contact Darrel Technologies)* |
| [Sierra Leone](sl.md) | SLE (Le) | Africa/Freetown | en | gh_basic | *(contact Darrel Technologies)* |
| [Liberia](lr.md) | LRD (L$) | Africa/Monrovia | en | gh_basic | *(contact Darrel Technologies)* |
| [The Gambia](gm.md) | GMD (D) | Africa/Banjul | en | gh_basic | *(contact Darrel Technologies)* |
| [Benin](bj.md) | XOF (FCFA) | Africa/Porto-Novo | fr | francophone_basic | *(contact Darrel Technologies)* |
| [Burkina Faso](bf.md) | XOF (FCFA) | Africa/Ouagadougou | fr | francophone_basic | *(contact Darrel Technologies)* |
| [Mali](ml.md) | XOF (FCFA) | Africa/Bamako | fr | francophone_basic | *(contact Darrel Technologies)* |
| [Niger](ne.md) | XOF (FCFA) | Africa/Niamey | fr | francophone_basic | *(contact Darrel Technologies)* |
| [Togo](tg.md) | XOF (FCFA) | Africa/Lome | fr | francophone_basic | *(contact Darrel Technologies)* |
| [Guinea](gn.md) | GNF (FG) | Africa/Conakry | fr | francophone_basic | *(contact Darrel Technologies)* |

---

## East Africa

| Country | Currency | Timezone | Lang | Framework | Licensee |
|---------|----------|----------|------|-----------|---------|
| [Kenya](ke.md) | KES (KSh) | Africa/Nairobi | en | ke_basic | *(contact Darrel Technologies)* |
| [Uganda](ug.md) | UGX (USh) | Africa/Kampala | en | ug_basic | *(contact Darrel Technologies)* |
| [Tanzania](tz.md) | TZS (TSh) | Africa/Dar_es_Salaam | en/sw | tz_basic | *(contact Darrel Technologies)* |
| [Rwanda](rw.md) | RWF (RF) | Africa/Kigali | en/fr | rw_basic | *(contact Darrel Technologies)* |
| [Ethiopia](et.md) | ETB (Br) | Africa/Addis_Ababa | am/en | et_basic | *(contact Darrel Technologies)* |

---

## What Varies by Country

| Setting | Configured via |
|---------|----------------|
| Currency symbol and name | Country profile |
| Timezone | Country profile |
| CA/Exam weight split (default) | Academic framework file |
| Statutory payroll deductions | HR settings → Statutory Rates |
| Built-in grading scales | Database seed + `grades_class.inc` |
| Data residency | Country profile |

All other settings — class structure, school name, campus configuration — are configured per-school within the application.
