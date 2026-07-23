# Biometric Attendance

!!! note
    Available since **sERP v2.1**.

sERP can capture student and staff attendance automatically from biometric devices — fingerprint, facial recognition, or card-based terminals — alongside the manual entry described in [Students → Attendance](students.md#attendance) and [HR → Staff Attendance & Leave](hr.md#staff-attendance-leave). Access biometric administration from **Biometric** in the main navigation menu.

!!! tip
    Manually-recorded attendance always takes precedence. If a class or staff member's attendance for a given date has already been recorded manually, biometric capture will not overwrite it.

---

## Integration Options

There are three ways to connect a device, and a school can use any combination of them:

**Direct Device Push** — the device sends attendance records straight to sERP as they happen, if it has its own internet connectivity and supports a configurable push destination. Gives near real-time updates.

**Local Relay Agent** — a small program runs on a computer within the school's network, communicates with the device locally, and periodically forwards records to sERP. Recommended when the device isn't (or shouldn't be) directly exposed to the internet.

**CSV / Excel Import** — punch records exported from the device as a spreadsheet can be uploaded and imported manually (see [CSV Import](#csv-import) below). This uses the same processing pipeline as the live options.

---

## Managing Devices

1. Go to **Biometric → Devices**
2. Click **Register Device** and complete: device name, type (Fingerprint, Face, Card, or Other), whether it's used for students, staff, or both, its location, and integration mode
3. Click **Register Device** — a one-time **Device Key** and **Secret** are shown

!!! warning
    The device secret is shown only once and cannot be retrieved again. If it's lost, use **Rotate Secret** on that device to generate a new one — the device or relay agent will then need to be reconfigured.

Use the power icon next to a device to disable it (rejecting further punches) without deleting its history, or re-enable it later.

---

## Mapping Device Users

A biometric device identifies people by its own internal user ID, which won't match a student's or staff member's ID in sERP.

1. Go to **Biometric → Mapping**
2. For each unmapped device user ID listed, choose **Student** or **Staff** and enter the corresponding sERP ID
3. Click **Map**

Once mapped, any punches already received for that device user ID are resolved automatically — no need to wait for new punches.

---

## Settings

Go to **Settings → Biometric Attendance** to configure:

- **Enable biometric attendance** — master on/off switch
- **Automatically resolve punches into attendance records** — when on, an automated process (running roughly hourly) turns received punches into attendance and staff attendance records
- **Staff late-arrival cutoff time** — a staff member whose first punch of the day is after this time is marked *Late* instead of *Present*
- **Notify staff by SMS when marked late** — sends an SMS to a staff member's registered mobile number when biometric capture marks them late

---

## CSV Import

1. Go to **Biometric → Import CSV**
2. Choose which device to attribute the punches to (or leave as **CSV Import (generic)**), and select your file (.xlsx, .xls, .csv, or .ods)
3. Click **Next: Map Columns**, then match **External User ID**, **Punch Date/Time**, and optionally **Type** (In/Out) to the corresponding columns
4. Click **Run Import**

The results screen shows how many rows imported successfully and how many failed, with a downloadable CSV of failed rows and the reason for each (e.g. a missing user ID or an unrecognised date format). Imported punches are processed by the same automatic resolution described in [Settings](#settings) above.
