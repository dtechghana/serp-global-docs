# User Management

sERP supports three types of user accounts: **staff**, **student**, and **guardian** (parent). Each account is linked to an existing record in the system and inherits a default permission set based on its role.

---

## Adding a User Account

1. Go to **Admin → Manage Users**
2. Click **Add New User (+)**
3. Select the **User Type**:

    === "Staff"
        - Select **Staff** as the user type
        - In **Link User to Staff**, search for and select the staff member
        - The staff member must already have a record under **HR → Staff**

    === "Student"
        - Select **Student** as the user type
        - In **Link User to Student ID**, enter the student's sERP ID
        - Grants access to the student portal

    === "Guardian"
        - Select **Guardian** as the user type
        - In **Link User to Student(s)**, enter one or more student IDs (comma-separated)
        - Grants access to the parent portal for all linked students

4. Enter a **Username** and **Password**
5. Click **Add User**

!!! tip
    After creating the account, you can adjust individual permissions by editing the user record. The default permission set is based on the user type but can be overridden per user.

---

## Editing a User

1. Go to **Admin → Manage Users**
2. Click the edit (✏️) icon in the **Actions** column for the user
3. Update details in the **User Details** panel
4. Manage granular permissions in the **User Access Restriction** panel
5. Click **Modify User**

---

## Deleting a User

1. Go to **Admin → Manage Users**
2. Click the delete (**×**) icon for the user
3. Confirm the deletion

!!! warning
    Deleting a user account is permanent. The linked staff/student/guardian record is not deleted — only the login account.

---

## Changing Your Password

1. From the top navigation, click your **username**
2. Select **Change Password**
3. Enter your current password and your new password (twice)
4. Click **Change Password**

---

## Role-Based Permissions

| User Type | Default Access |
|-----------|----------------|
| Admin | Full access to all modules |
| Staff (Teaching) | Academic grading, attendance, assignments, lesson plans |
| Staff (Finance) | Billing, collections, receipts, financial reports |
| Staff (HR) | Staff records, payroll, leave management |
| Student | Student portal only — timetable, assignments, results |
| Guardian | Parent portal only — fee balance, results, attendance, messages |

!!! note
    Permissions are additive. An admin can grant additional access to any user beyond their default role, or restrict specific sections.

---

## Multi-Factor Authentication (MFA)

MFA is available for admin accounts. When enabled, the user must enter a one-time code (sent by SMS or email) in addition to their password.

To enable MFA for an account:

1. Edit the user record (**Admin → Manage Users → Edit**)
2. Toggle **Enable MFA** to on
3. Save the user record

The user will be prompted to verify their phone number or email address on next login.
