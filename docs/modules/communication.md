# Communication & SMS

The communication module gives schools a direct channel to parents, students, and staff — through bulk SMS, automated alerts, in-app messaging, and announcements.

---

## SMS Gateway

sERP sends SMS via an integrated SMS gateway (configured per-deployment by the country licensee). Before using any SMS feature, ensure the gateway is configured under **Settings → SMS Settings**.

SMS credits are consumed per message segment (standard 160-character SMS = 1 credit). Long messages use multiple credits.

### Supported networks

sERP SMS delivery works on any GSM network in the deployment country. For Nigeria deployments this includes MTN, Airtel, Glo, and 9mobile.

---

## Bulk SMS

Send a message to any group of recipients in one step.

1. Go to **Communication → Send SMS**
2. Select the **Recipient Group**:
    - All parents
    - All students
    - All staff
    - By class (parents or students)
    - By year group
    - Custom (enter numbers manually)
3. Type your message in the text box (character counter shows credits required)
4. Click **Send SMS**

A delivery report is available under **Communication → SMS Delivery Log**.

---

## Automated SMS Alerts

sERP can send automated SMS messages triggered by system events. These are configured in **Settings → SMS Settings**:

| Alert | Trigger |
|-------|---------|
| **Absence alert** | A student is marked absent in attendance |
| **Fee reminder** | Manually triggered from the Debtors list |
| **Result notification** | Terminal reports are published |
| **Payment confirmation** | A fee payment is recorded |

Toggle each alert on or off independently.

---

## In-App Messaging

Two-way in-app messaging is available between:

- Staff ↔ Staff
- Staff ↔ Parent
- Staff ↔ Student

### Sending an in-app message

1. Go to **Communication → Messages**
2. Click **New Message**
3. Select the recipient(s) by name or role
4. Type your message and click **Send**

Recipients see new messages via the notification badge in the navigation bar and in their portal inbox.

---

## Announcements & Notice Board

Post announcements visible to all or selected user groups:

1. Go to **Communication → Announcements**
2. Click **Post Announcement**
3. Enter a **Title** and **Body**
4. Select the **Audience** (All, Staff only, Parents, Students, or by Class)
5. Set an **Expiry Date** (after which the announcement is archived)
6. Click **Post**

Announcements appear on the dashboard and in the portal notice boards.

---

## Parent–Teacher Conferences

Schedule and manage parent–teacher meetings:

1. Go to **Communication → Parent-Teacher Conferences**
2. Click **Schedule Conference**
3. Select the **Class**, **Teacher**, and available **Time Slots**
4. Send SMS invitations to parents from the same screen
5. Track RSVPs and attendance from the conference record

---

## SMS Usage Report

View SMS credit consumption:

1. Go to **Communication → SMS Reports**
2. Filter by **Date Range**, **Message Type**, or **Staff Sender**
3. The report shows credits used, delivery status, and recipient breakdown
