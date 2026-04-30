# Deployment Overview

Each sERP Global installation is a **standalone, single-school deployment**. There is no shared database or multi-tenant infrastructure — every school runs its own isolated instance.

---

## What a Deployment Consists Of

| Component | Description |
|-----------|-------------|
| Web application | PHP 7.4+ codebase on Apache |
| Database | A dedicated MySQL 8.0+ database for the school |
| `deployment.conf.php` | Per-deployment constants: DB credentials, locale settings, crypto keys |
| Country profile | Loaded at runtime from `config/profiles/XX.php`; sets timezone, currency, locale |
| Subdomain | A school-specific subdomain (e.g. `schoolname.schoolerpghana.com`) |

---

## Deployment Steps (for system administrators)

1. **Provision a server** meeting the [server requirements](server-requirements.md)
2. **Clone or copy** the sERP Global codebase to the webroot
3. **Create the database** and import the base schema (`db/schema.sql`)
4. **Copy `includes/deployment.conf.php.example`** to `includes/deployment.conf.php`
5. **Fill in all constants** in `deployment.conf.php` — use the [configuration reference](conf-reference.md)
6. **Load the country profile** for the target country — see [Country Profiles](country-profiles.md)
7. **Configure Apache/Nginx** to point the subdomain to the installation
8. **Enable HTTPS** (required; use Let's Encrypt or a purchased certificate)
9. **Run the setup wizard** by visiting `/setup/` from `localhost` — generates the initial admin account
10. Complete the [Initial Setup](../getting-started/index.md) steps inside the application

---

## Folder Structure (key locations)

```
serp-global/
├── includes/
│   ├── deployment.conf.php        ← per-school config (not in version control)
│   └── classes/
│       ├── locale_config.inc      ← LocaleConfig static accessor
│       └── country_profile.inc    ← CountryProfile loader
├── config/
│   ├── profiles/                  ← gh.php, ng.php, ci.php, sn.php, cm.php
│   └── frameworks/                ← gh_basic.php, ng_basic.php, ...
├── setup/
│   └── index.php                  ← IP-restricted deployment wizard
├── settings/
│   └── deployment.php             ← Admin read-only deployment info page
└── db/
    └── schema.sql                 ← Base database schema
```

---

## The Deployment Wizard

The file `setup/index.php` is an IP-restricted utility (localhost only) that:

- Lets you select a country profile from a dropdown
- Shows all locale metadata for the selected profile
- Generates the complete `deployment.conf.php` snippet with all `define()` calls
- Includes a one-click copy button

After running the wizard and saving `deployment.conf.php`, the setup page should be **access-restricted or removed** in production.

---

## Updating an Existing Deployment

1. Back up the database
2. Pull the latest codebase (or replace files)
3. Run any pending migrations in `db/migrations/`
4. Check the [changelog](https://github.com/dtechghana/serp-global/releases) for any new `deployment.conf.php` constants
5. Clear any opcode cache (`php opcache_reset()` or restart PHP-FPM)

!!! warning
    Never overwrite `includes/deployment.conf.php` during an update — it is excluded from version control (`.gitignore`) precisely to prevent this.
