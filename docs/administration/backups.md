# Backups & Data Export

Each school's data is in its own MySQL database. Backups and exports can be managed at both the server level and the application level.

---

## Automated Server Backups

For managed deployments (hosted by PerAnkh Limited or Darrel Technologies Ltd), daily automated backups are taken at the server level and retained for 30 days. Contact your licensee to request a backup restore.

For self-hosted deployments, configure automated MySQL backups using a cron job:

```bash
# Daily mysqldump — runs at 2:00 AM
0 2 * * * mysqldump -u serp_user -p'password' serp_schoolname | gzip > /backups/serp_$(date +\%Y\%m\%d).sql.gz
```

Ensure backups are stored off-server (e.g. S3, Backblaze, or an external drive).

---

## Manual Database Export

To export the full school database from the server:

```bash
mysqldump -u serp_user -p serp_schoolname > serp_schoolname_backup.sql
```

To restore:

```bash
mysql -u serp_user -p serp_schoolname < serp_schoolname_backup.sql
```

---

## In-Application Data Export

sERP provides export functions within the application for common data sets:

| Data | Location | Format |
|------|----------|--------|
| Student list | Students → Student List → Export | CSV / Excel |
| Academic results | Academic → Terminal Reports → Export | PDF / CSV |
| Fee collection | Finance → Reports → Export | CSV / Excel |
| Payroll run | HR → Payroll → [Month] → Export | CSV / Excel |
| Pension schedule | HR → Payroll → [Month] → Pension Export | CSV |
| SMS delivery log | Communication → SMS Reports → Export | CSV |

---

## Full Data Export on Cancellation

On subscription cancellation, customers are entitled to a full SQL export of their database:

1. Contact your licensee in writing requesting a data export
2. The export is provided within 7 business days in `.sql` format
3. Data is retained for 30 days after the subscription end date, then securely deleted

---

## What Is NOT Backed Up by Default

- Uploaded files in the `uploads/` directory (student/staff photos, attachments) — back these up separately using `rsync` or your hosting provider's file backup

```bash
# Example rsync to a remote backup server
rsync -avz /var/www/html/serp/uploads/ backup-server:/backups/serp-uploads/
```

---

## Disaster Recovery

For managed deployments:

1. Contact your licensee with a description of the issue
2. Provide the last known date when the system was functioning correctly
3. The support team will restore from the nearest clean backup

Recovery time objective (RTO) and recovery point objective (RPO) depend on the service tier. Ask your licensee for SLA details.
