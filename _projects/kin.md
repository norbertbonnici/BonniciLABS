---
title: Kin
ref: KIN-05
category: APPLICATION
status: COMING TO THE APP STORE
state: dev
order: 4.5
summary: A private family log from pregnancy to a child's third birthday. One-tap logging, patterns at a glance, reports for the doctor, and sharing with a co-parent over iCloud, with no accounts, no ads and no tracking.
tags: swiftui · core data · cloudkit · healthkit · widgetkit · watchos
progress: 95
progress_label: RELEASE
stack: [Swift, SwiftUI, Core Data, CloudKit, HealthKit]
platform: iPhone · iPad · Apple Watch
year: 2026
icon: /assets/img/projects/kin.png
icon_alt: "Kin icon — a parent cradling a baby inside the letter K"
meta_left: "data: yours"
description: "Kin is a private family log for pregnancy and a child's first three years, for iPhone, iPad and Apple Watch."
---

## The idea

The first years of a child's life produce a lot of small facts: when the last feed was, how long the nap lasted, what the doctor asked about at the last check-up. Kin makes those facts quick to record and easy to find again, and it keeps them inside the family.

Kin follows the child's stage. Expecting parents get the pregnancy screens, which switch to the newborn ones at birth. From twelve months, the toddler trackers appear.

<div class="shots" role="list">
  <figure role="listitem"><img src="/assets/img/projects/kin/01-today.jpg" alt="Today screen with one-tap Feed, Wake and Diaper buttons and today's totals" loading="lazy" width="540" height="1173"></figure>
  <figure role="listitem"><img src="/assets/img/projects/kin/02-timeline.jpg" alt="Timeline listing today's sleep, nappies, feeds and medication" loading="lazy" width="540" height="1173"></figure>
  <figure role="listitem"><img src="/assets/img/projects/kin/03-pregnancy.jpg" alt="Pregnancy Today screen at 22 weeks with days to go and a weekly summary" loading="lazy" width="540" height="1173"></figure>
  <figure role="listitem"><img src="/assets/img/projects/kin/04-week-by-week.jpg" alt="Week by week guide showing the baby's size at week 22" loading="lazy" width="540" height="1173"></figure>
  <figure role="listitem"><img src="/assets/img/projects/kin/05-growth.jpg" alt="Growth chart of weight over time against WHO reference bands" loading="lazy" width="540" height="1173"></figure>
  <figure role="listitem"><img src="/assets/img/projects/kin/06-sleep.jpg" alt="Sleep insights with the usual nap window and two weeks of sleep" loading="lazy" width="540" height="1173"></figure>
  <figure role="listitem"><img src="/assets/img/projects/kin/07-summary.jpg" alt="Weekly summary describing the week in plain sentences" loading="lazy" width="540" height="1173"></figure>
  <figure role="listitem"><img src="/assets/img/projects/kin/08-doctor-report.jpg" alt="Doctor report screen for creating a PDF of the last 90 days" loading="lazy" width="540" height="1173"></figure>
  <figure role="listitem"><img src="/assets/img/projects/kin/09-family.jpg" alt="Family screen with two caregivers and an iCloud invite button" loading="lazy" width="540" height="1173"></figure>
  <figure role="listitem"><img src="/assets/img/projects/kin/10-toddler.jpg" alt="Toddler Today screen with Meal, Potty, Behaviour, Activity and Daycare buttons" loading="lazy" width="540" height="1173"></figure>
</div>

## What it does

- **Pregnancy:** a week-by-week guide, symptoms, appointments, medications, weight and blood pressure, ultrasound scans with INTERGROWTH-21st reference bands, a contraction timer, a hospital-bag checklist and a birth plan.
- **Newborn and infant:** one-tap logging for feeds, sleep and nappies, growth charts with WHO reference bands read at corrected age for babies born early, vaccinations, medications, allergies and milestones.
- **Toddler:** meals, potty training, behaviour notes, activities and a daily daycare handover.
- **Patterns:** a Today screen, a timeline of everything, nap windows learned from the child's own logs, and a weekly summary in plain words.
- **Appointments:** a PDF report for the doctor or midwife, with selectable text, growth charts and reference bands.
- **Family:** invite a co-parent over iCloud. You both log from your own Apple Accounts, and an activity log shows who changed what.
- **Wrist and Lock Screen:** widgets and an Apple Watch app log a feed, nap or nappy without opening the app.

## Inform, never diagnose

Kin describes what a family logged and shows public reference data next to it. It never judges a child's progress, and it never offers a diagnosis. The weekly summary is written by a deterministic engine on the device, and a safety gate checks its wording on every build. Wherever reference data appears, Kin points parents to their midwife, doctor or health visitor.

## Private by design

There is no Kin server. Everything stays on the family's devices and in their own private iCloud, which the developer cannot read. There are no accounts, no analytics, no advertising and no third-party SDKs. Face ID can lock the app and hide the widgets, and parents can export everything or erase it at any time.

<p class="case-links"><a href="/projects/kin/privacy/">→ privacy policy</a> &nbsp; <a href="/projects/kin/support/">→ support</a></p>
