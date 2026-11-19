# Transport Management

!!! note
    Available since **sERP v2**.

sERP's Transport module manages a school's vehicle fleet, drivers, routes, and the students assigned to each — with boarding safety and billing built in rather than run as separate systems. Access it from **Transport** in the main navigation menu.

Transport roles are granted per user the same way as any other module: **Access Dashboard**, **Fleet & Driver Management**, **Route & Stop Planning / Student Allocation**, **Boarding Check-in**, **Fee Collection**, and **Reports** can be assigned independently — so, for example, gate staff can be given check-in access without any administrative visibility into the rest of the module.

---

## Vehicles & Drivers

1. Go to **Transport → Vehicles**, click **Add Vehicle**, and complete the form: registration number, make/model, seating capacity, fuel type, and roadworthy/insurance expiry dates.
2. Go to **Transport → Drivers**, click **Add Driver**, and select the staff member it corresponds to (see [HR & Payroll](hr.md)), with license number, class, and expiry.
3. Assign a driver to a vehicle from the drivers list. Each vehicle has one active driver at a time — reassigning closes out the previous assignment and keeps a full history rather than overwriting it.

## Routes, Stops & Student Allocation

1. Go to **Transport → Routes**, click **Add Route**, then add **Stops** to it with a scheduled time each.
2. Go to **Transport → Student Allocations** to assign a student to a route, stop, vehicle, and fee zone.

**Manifest** — **Transport → Manifest** shows a live, per-vehicle roster of every allocated student, generated directly from current allocations, with nothing to separately prepare.

!!! tip
    The **Exempt from Fee?** option on a student's allocation keeps them on the route — still appearing on manifests and check-in — but bills them at zero instead of their zone's amount. Use this for a scholarship case rather than un-allocating the student.

## Fee Zones & Billing

Go to **Transport → Fee Zones** to define the distance/zone-based fee tiers offered on the Student Allocations screen, each with its own amount in the deployment's local currency.

Transport fees are billed through the same Finance module as tuition, not a parallel system — see [Fees, Finance & Accounting](finance.md). A student's zone fee becomes an individual-student fee the moment they're allocated, and transport payments use the same payment flow, receipts, and reports as any other fee, so they appear in the Debtors List and Payment History alongside everything else.

## Boarding Check-in & Alerts

Students board and alight either manually from **Transport → Check-in**, or automatically via RFID/NFC (see below) — both write to the same check-in record, so a vehicle's history is complete regardless of method.

**Departed / Delayed broadcasts** — buttons on the Check-in screen (also available from the paired tablet's Driver Console app) send an immediate SMS to every allocated student's parent on that vehicle, independent of individual check-ins.

!!! tip
    Parent/admin SMS alerts for Transport must be switched on at **Settings → SMS Settings → Transport Alerts** — off by default, the same convention as every other SMS alert type.

## RFID/NFC Check-in & Live GPS Tracking

RFID/NFC boarding and live GPS tracking both run through one standardized device per vehicle: a ruggedized Android tablet (NFC + GPS + LTE) mounted in the vehicle, running the companion **Driver Console** app. NFC is the same 13.56MHz contactless technology as a transit or payment card, so this covers RFID check-in without any separate specialized reader hardware.

1. Go to **Transport → Devices**, click **Register Device**, name it, and select the vehicle it's mounted in.
2. A one-time **Device Key** and **Secret** are shown — pair the Driver Console app on that tablet with them, either by scanning the QR code shown or entering them manually.

!!! warning
    The device secret is shown only once and cannot be retrieved again. If it's lost, rotate it from the devices list and reconfigure the Driver Console app with the new value.

Go to **Transport → Student NFC Cards** to link a physical card's UID to a student. Click into the **Card UID** field and tap the card against a USB NFC reader in keyboard-wedge mode to fill it in automatically (no driver needed), or type the UID in by hand if one isn't available. A student has one active card at a time, and assigning a new one automatically revokes the previous one.

**Transport → Live Map** shows each vehicle's most recent GPS position, reported automatically by its paired tablet whenever its Driver Console app has a route in progress.

### The Driver Console App

The Driver Console is a separate, dedicated app for the tablet mounted in each vehicle — not a role within a parent/student-facing app, and not something a driver logs into with a personal account. Once paired to a registered device, it authenticates as that device, not a user. It provides continuous NFC scanning that queues and syncs automatically (including after a connectivity gap), a Start/End Route toggle that also triggers the Departed broadcast and GPS reporting, a Bus Delayed button, and screen pinning so the tablet stays on the app while mounted.

The app is sideloaded rather than distributed through an app store, since it only ever runs on school-owned, mounted tablets.
