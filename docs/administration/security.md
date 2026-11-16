# Security Features

sERP includes multi-factor authentication at login, automated database backups, and encryption of sensitive personal data at rest.

---

## Multi-Factor Authentication (MFA)

Every account is required to complete two-factor authentication (2FA) at login, with the exception of a small set of top-level accounts described below. After entering the correct username and password, a 6-digit One-Time Password (OTP) is sent to the account's registered mobile number via SMS.

### MFA Login Process

1. Enter your username and password on the login page and click **Login**
2. sERP verifies your credentials. Unless your account is exempt (see below), you are redirected to the OTP verification page
3. Check your registered mobile number for the SMS containing your 6-digit OTP
4. Enter the OTP on the verification screen
5. Click **Verify OTP** to complete login

!!! note
    OTPs expire after **5 minutes**. If the OTP expires before you enter it, return to the login page and log in again to receive a fresh OTP.

### Which Accounts Are Exempt

A small number of top-level accounts always log in with username and password only, and are never prompted for an OTP: the school's own **Super Admin** account, plus the vendor's **System Administrator** account.

Every other account — including all other staff, teacher, student, and parent accounts — is required to complete MFA.

### Configuring a Mobile Number for MFA

An account must have a mobile number registered in order to receive OTP codes. This is managed from the **Change Password** page.

1. Log in to the account
2. From the welcome menu, click **Change Password**
3. In the **MFA Phone Number** pane, enter or update the mobile number
4. Click **Save Phone**

!!! warning
    If no mobile number is configured for an account that requires MFA, the OTP is displayed on-screen as a temporary fallback. This is intended for development and initial setup only. Always ensure a valid mobile number is configured before going live.

### Turning MFA Off School-Wide

The school's **Super Admin** account can turn MFA off for the whole school, from **Settings → SMS Settings**, under **Enforce two-factor authentication at login?**.

!!! note
    Turning this off means any account with no phone number on file can still log in with username and password alone — useful while you're still populating phone numbers for a new rollout. Turn it back on once every account has a valid phone number. The exempt top-level accounts themselves are never affected either way, whether this is on or off.

---

## Automated Database Backups

See [Backups & Data Export](backups.md) for details on scheduled database backups.

---

## Data Encryption at Rest

Sensitive personal data is encrypted before it is stored in the database, rather than kept as plain text. This protects the information even if the underlying database is ever accessed directly, outside of the application.

### What Is Encrypted

- Student and guardian contact details (phone numbers, addresses, email addresses)
- Student health records (blood type, allergies, medical conditions, vaccination history, emergency contacts)
- Student disciplinary records

!!! note
    Encryption is applied automatically whenever this data is saved or updated. There is nothing for school staff to configure — records are encrypted transparently and decrypted for display to authorised users within the application.

### Password Storage

User passwords are stored using the bcrypt hashing algorithm, a one-way hash that cannot be reversed to recover the original password. Accounts created under the previous hashing scheme are upgraded automatically, without disruption, the next time that user logs in.
