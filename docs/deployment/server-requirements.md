# Server Requirements

SchoolERP (sERP) runs on a standard LAMP stack. No exotic extensions or proprietary software is required.

---

## Minimum Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| **PHP** | 7.4 | 8.2+ |
| **MySQL** | 8.0 | 8.0+ |
| **Apache** | 2.4 | 2.4 |
| **RAM** | 1 GB | 2 GB+ |
| **Disk** | 10 GB | 20 GB+ (grows with file attachments) |
| **OS** | Ubuntu 20.04 LTS | Ubuntu 22.04 LTS |

---

## Required PHP Extensions

| Extension | Purpose |
|-----------|---------|
| `pdo_mysql` | Database connectivity |
| `mbstring` | Multi-byte string handling |
| `openssl` | Cryptographic functions |
| `gd` | Image processing (report headers, logos) |
| `zip` | Data export/import |
| `curl` | SMS gateway API calls |
| `json` | API response handling |

Check installed extensions with:

```bash
php -m | grep -E 'pdo_mysql|mbstring|openssl|gd|zip|curl|json'
```

---

## Apache Configuration

`mod_rewrite` must be enabled and `AllowOverride All` must be set on the webroot to allow `.htaccess` rules for clean URL routing.

```apache
<Directory /var/www/html/serp>
    AllowOverride All
    Options -Indexes +FollowSymLinks
    Require all granted
</Directory>
```

Enable mod_rewrite if not already active:

```bash
sudo a2enmod rewrite
sudo systemctl reload apache2
```

---

## MySQL Configuration

Recommended `my.cnf` additions for a school deployment:

```ini
[mysqld]
innodb_buffer_pool_size = 256M
max_allowed_packet = 64M
character-set-server = utf8mb4
collation-server = utf8mb4_unicode_ci
```

Create the database and user:

```sql
CREATE DATABASE serp_schoolname CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'serp_user'@'localhost' IDENTIFIED BY 'strong-password';
GRANT ALL PRIVILEGES ON serp_schoolname.* TO 'serp_user'@'localhost';
FLUSH PRIVILEGES;
```

---

## HTTPS

HTTPS is required. Use [Let's Encrypt](https://letsencrypt.org) (free) or a purchased SSL certificate.

```bash
sudo apt install certbot python3-certbot-apache
sudo certbot --apache -d yourschool.schoolerpghana.com
```

---

## File Permissions

The web server user (`www-data` on Ubuntu) needs write access to:

```
uploads/          ← student and staff photos, attachments
cache/            ← generated report PDFs (if applicable)
```

```bash
sudo chown -R www-data:www-data /var/www/html/serp/uploads
sudo chmod -R 755 /var/www/html/serp/uploads
```

---

## Nigerian Hosting Providers

For Nigeria deployments under NDPR data residency requirements, consider:

- **Rack Centre** (Lagos) — Tier III carrier-neutral data centre
- **MainOne** (Lagos) — cloud and co-location
- **Galaxy Backbone** — government-affiliated DC, suitable for public/government schools
- Standard VPS providers with Nigerian PoPs (DigitalOcean, Linode, AWS af-south-1 for proximity)
