# sERP Global Documentation

**sERP Global** is a comprehensive school management and administration platform for West African educational institutions — from pre-school through secondary (A-Level / WASSCE / BACCALAURÉAT). It is built and maintained by [Darrel Technologies Ltd](https://dtechghana.com) and is distributed through country-specific licensees.

---

## Supported Countries

| Country | Licensee | Domain |
|---------|----------|--------|
| 🇬🇭 Ghana | Darrel Technologies Ltd | schoolerpghana.com |
| 🇳🇬 Nigeria | PerAnkh Limited | schoolerpnigeria.com |
| 🇨🇮 Côte d'Ivoire | *(contact Darrel Technologies)* | — |
| 🇸🇳 Senegal | *(contact Darrel Technologies)* | — |
| 🇨🇲 Cameroon | *(contact Darrel Technologies)* | — |

---

## Core Modules

- **Students & Admissions** — complete student register, multi-campus enrolment, attendance, health, and disciplinary records
- **Academic Management** — CA-driven assessments, configurable grading scales, terminal reports, and exam timetabling
- **Fees & Finance** — billing, collections, partial payments, receipts, debtors, and financial reports
- **HR & Payroll** — staff records, monthly payroll, statutory deductions (country-specific), pay slips
- **Communication & SMS** — bulk SMS to parents/staff, automated alerts, in-app messaging
- **Portals** — parent, student, and teacher self-service portals with role-based access

---

## Architecture

sERP Global is a **siloed, per-school deployment**. Each school runs its own instance with:

- A dedicated subdomain (e.g. `yourschool.schoolerpghana.com`)
- Its own isolated MySQL database
- A `deployment.conf.php` file that configures locale, currency, and credentials

The platform runs on a standard **LAMP stack** (PHP 7.4+, MySQL 8.0+, Apache 2.4+). There is no shared database or multi-tenant infrastructure.

---

## Quick Links

- [Initial Setup Guide](getting-started/index.md)
- [Deployment & Country Profiles](deployment/index.md)
- [deployment.conf.php Reference](deployment/conf-reference.md)
- [Country Guides](country-guides/index.md)
