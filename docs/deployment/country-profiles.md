# Country Profiles

A **country profile** is a PHP file in `config/profiles/` that provides all locale constants for a specific country deployment. It is loaded at runtime by `CountryProfile::load()` and its constants are applied via `LocaleConfig`.

---

## How Profiles Are Loaded

`CountryProfile::load(string $iso2)` reads the corresponding file and caches the result in-process:

```php
$profile = CountryProfile::load('ng'); // loads config/profiles/ng.php
```

The profile is loaded automatically when `deployment.conf.php` contains a `DEPLOYMENT_COUNTRY` constant matching a profile ISO 2-letter code. You don't typically call `CountryProfile::load()` directly in application code — use the `LocaleConfig` accessor instead.

---

## Profile Structure

Each profile file returns a PHP array with the following keys:

```php
<?php
return [
    'name'                => 'Nigeria',
    'iso2'                => 'NG',
    'currency_code'       => 'NGN',
    'currency_symbol'     => '₦',
    'currency_name'       => 'Naira',
    'currency_subunit'    => 'Kobo',
    'phone_country_code'  => '+234',
    'timezone'            => 'Africa/Lagos',
    'locale'              => 'en',
    'academic_framework'  => 'ng_basic',
    'data_residency'      => 'NG',

    '_conf_snippet' => <<<'CONF'
define('DEPLOYMENT_COUNTRY',   'NG');
define('CURRENCY_CODE',        'NGN');
define('CURRENCY_SYMBOL',      '₦');
define('CURRENCY_NAME',        'Naira');
define('CURRENCY_SUBUNIT',     'Kobo');
define('PHONE_COUNTRY_CODE',   '+234');
define('DEPLOYMENT_TIMEZONE',  'Africa/Lagos');
define('DEPLOYMENT_LANG',      'en');
define('ACADEMIC_FRAMEWORK',   'ng_basic');
define('DATA_RESIDENCY_COUNTRY','NG');
define('DB_HOST',              'localhost');
define('DB_NAME',              'serp_ng_schoolname');
define('DB_USER',              'root');
define('DB_PASS',              '');
define('APP_CRYPTO_KEY',       'change-this-key');
define('APP_CRYPTO_IV',        'change-this-iv');
CONF,
];
```

The `_conf_snippet` key contains a ready-to-use `deployment.conf.php` block. The [deployment wizard](index.md#the-deployment-wizard) generates this automatically.

---

## Available Profiles

| File | Country | Currency | Timezone | Language |
|------|---------|----------|----------|----------|
| `gh.php` | Ghana | GHS (₵) | Africa/Accra | en |
| `ng.php` | Nigeria | NGN (₦) | Africa/Lagos | en |
| `ci.php` | Côte d'Ivoire | XOF (CFA) | Africa/Abidjan | fr |
| `sn.php` | Senegal | XOF (CFA) | Africa/Dakar | fr |
| `cm.php` | Cameroon | XAF (FCFA) | Africa/Douala | fr |

---

## Academic Frameworks

Each profile references an **academic framework** — a PHP array in `config/frameworks/` that defines the default CA/exam weight split, pass mark, grading scales, and term structure.

| Framework | Used by | Terms | CA Weight | Exam Weight |
|-----------|---------|-------|-----------|-------------|
| `gh_basic` | Ghana | 3 | 50% | 50% |
| `ng_basic` | Nigeria | 3 | 30% | 70% |
| `francophone_basic` | CI, SN, CM | 3 | 40% | 60% |

These are defaults. Each school can override CA/exam weights per class in **Settings → Academic Settings**.

---

## Adding a New Country Profile

1. Create `config/profiles/xx.php` (replace `xx` with the ISO 2-letter code, lowercase)
2. Return an array matching the structure above
3. Create or reuse an academic framework in `config/frameworks/`
4. Reference the framework in the `academic_framework` key
5. Test by visiting `/setup/` on a localhost deployment and selecting the new country

The `CountryProfile::available()` method auto-discovers profiles by scanning `config/profiles/*.php`, so no further registration is needed.

---

## LocaleConfig Accessors

Application code reads locale values through static methods on `LocaleConfig`:

| Method | Returns | Example |
|--------|---------|---------|
| `LocaleConfig::currencyCode()` | ISO currency code | `NGN` |
| `LocaleConfig::currencySymbol()` | Currency symbol | `₦` |
| `LocaleConfig::currencyName()` | Currency name | `Naira` |
| `LocaleConfig::currencySubunit()` | Subunit name | `Kobo` |
| `LocaleConfig::phoneCode()` | Dial code | `+234` |
| `LocaleConfig::timezone()` | Timezone string | `Africa/Lagos` |
| `LocaleConfig::deploymentLang()` | Language code | `en` |
| `LocaleConfig::country()` | ISO 2-letter code | `NG` |

These read from the `define()` constants in `deployment.conf.php`. They never touch the database.
