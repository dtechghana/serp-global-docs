# deployment.conf.php Reference

`includes/deployment.conf.php` is the per-deployment configuration file. It is excluded from version control and must be created manually for each school deployment. **Never commit this file** — it contains database credentials and cryptographic keys.

---

## Full Example

```php
<?php
// ── Database ──────────────────────────────────────────────────────────────
define('DB_HOST',              'localhost');
define('DB_NAME',              'serp_schoolname');
define('DB_USER',              'serp_user');
define('DB_PASS',              'a-strong-password');

// ── Cryptography ──────────────────────────────────────────────────────────
define('APP_CRYPTO_KEY',       'replace-with-random-32-char-key');
define('APP_CRYPTO_IV',        'replace-with-random-16-char-iv');

// ── Locale ────────────────────────────────────────────────────────────────
define('DEPLOYMENT_COUNTRY',   'NG');
define('CURRENCY_CODE',        'NGN');
define('CURRENCY_SYMBOL',      '₦');
define('CURRENCY_NAME',        'Naira');
define('CURRENCY_SUBUNIT',     'Kobo');
define('PHONE_COUNTRY_CODE',   '+234');
define('DEPLOYMENT_TIMEZONE',  'Africa/Lagos');
define('DEPLOYMENT_LANG',      'en');

// ── Academic ──────────────────────────────────────────────────────────────
define('ACADEMIC_FRAMEWORK',   'ng_basic');

// ── HR / Payroll ──────────────────────────────────────────────────────────
define('SOCIAL_SECURITY_LABEL','RSA / NHF');

// ── Data residency ────────────────────────────────────────────────────────
define('DATA_RESIDENCY_COUNTRY','NG');
```

---

## Constants Reference

### Database

| Constant | Required | Default | Description |
|----------|----------|---------|-------------|
| `DB_HOST` | Yes | `localhost` | MySQL host |
| `DB_NAME` | Yes | `serp_global` | Database name |
| `DB_USER` | Yes | `root` | MySQL username |
| `DB_PASS` | Yes | *(empty)* | MySQL password |

### Cryptography

| Constant | Required | Description |
|----------|----------|-------------|
| `APP_CRYPTO_KEY` | Yes | AES encryption key. Generate a random 32-character string per deployment. |
| `APP_CRYPTO_IV` | Yes | AES initialisation vector. Generate a random 16-character string per deployment. |

!!! danger "Change these per deployment"
    Never reuse the same crypto key and IV across different school deployments. Each school's sensitive data (e.g. stored passwords) is encrypted with these values. If you copy an installation, regenerate both constants.

### Locale

| Constant | Required | Example | Description |
|----------|----------|---------|-------------|
| `DEPLOYMENT_COUNTRY` | Yes | `NG` | ISO 3166-1 alpha-2 country code (uppercase) |
| `CURRENCY_CODE` | Yes | `NGN` | ISO 4217 currency code |
| `CURRENCY_SYMBOL` | Yes | `₦` | Currency symbol as displayed in the UI |
| `CURRENCY_NAME` | Yes | `Naira` | Full currency name (used in amount-in-words) |
| `CURRENCY_SUBUNIT` | Yes | `Kobo` | Subunit name (used in amount-in-words) |
| `PHONE_COUNTRY_CODE` | Yes | `+234` | International dial code including `+` |
| `DEPLOYMENT_TIMEZONE` | Yes | `Africa/Lagos` | PHP timezone string from the [tz database](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) |
| `DEPLOYMENT_LANG` | No | `en` | ISO 639-1 language code. Defaults to `en` if omitted. |

### HR / Payroll

| Constant | Required | Example | Description |
|----------|----------|---------|-------------|
| `SOCIAL_SECURITY_LABEL` | No | `RSA / NHF` | Short name of the national social security / pension scheme. Shown in payroll search labels, validation messages, and user permission rows. Defaults to `SSNIT` if omitted (preserves backward compatibility with existing Ghana deployments). |

### Academic

| Constant | Required | Example | Description |
|----------|----------|---------|-------------|
| `ACADEMIC_FRAMEWORK` | No | `ng_basic` | Framework file basename (without `.php`) from `config/frameworks/`. Defaults to `gh_basic` if omitted. |

### Data Residency

| Constant | Required | Example | Description |
|----------|----------|---------|-------------|
| `DATA_RESIDENCY_COUNTRY` | No | `NG` | ISO code of the country where data is hosted. Used for display purposes in **Settings → Deployment Info**. |

---

## Generating This File

Use the deployment wizard at `/setup/` (accessible from localhost only) to:

1. Select the target country
2. Get a pre-filled `_conf_snippet` with all locale constants
3. Copy and paste into `deployment.conf.php`
4. Fill in the DB credentials and crypto keys manually

---

## Fallback Behaviour

If `deployment.conf.php` does not exist or a constant is not defined, `LocaleConfig` and the PDO class fall back to safe defaults. **This is intended only for development** — production deployments must have all constants set.

| Fallback constant | Default value |
|-------------------|---------------|
| `DB_HOST` | `localhost` |
| `DB_NAME` | `serp_global` |
| `DB_USER` | `root` |
| `DB_PASS` | *(empty)* |
| `APP_CRYPTO_KEY` | `change-this-secret-key-per-deployment` |
| `APP_CRYPTO_IV` | `change-this-iv-seed` |
| `DEPLOYMENT_LANG` | `en` |
