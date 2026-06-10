# GHL Setup Guide — Summer Lock In Challenge
## ManyChat → GHL Integration

**Purpose:** This guide covers everything you need to set up in GoHighLevel to receive leads from the ManyChat LOCKIN flow, segment them correctly, and send the right follow-up sequence to members vs. non-members.

---

## Overview of the Two Segments

Every lead that comes through the ManyChat LOCKIN flow will arrive in GHL as a contact with one of two tags. Everything downstream — automations, messages, pipelines — is driven by which tag they carry.

| Tag | Who They Are | Goal |
|---|---|---|
| `Summer Lock In - Member` | Already a MacroFit member | Confirm their spot, hype them up, keep them warm until June 29th |
| `Summer Lock In - Non-Member` | Not yet a member | Nurture them into joining MacroFit before June 29th using LOCKIN20 coupon |

---

## Part 1 — GHL Contact Setup

### 1.1 Custom Fields to Map from ManyChat

When ManyChat pushes a contact to GHL, make sure these fields are mapped correctly in your integration (native GHL integration or Zapier):

| ManyChat Field | GHL Field |
|---|---|
| `first_name` | First Name |
| `phone` | Phone |
| `email` | Email |
| ManyChat tag | GHL Tag (see below) |

### 1.2 Tags to Create in GHL

Create the following tags in GHL before setting up automations:

- `Summer Lock In - Member`
- `Summer Lock In - Non-Member`
- `Summer Lock In - Enrolled` *(add manually after June 29th once challenge is live)*

### 1.3 Pipeline (Optional but Recommended)

Create a pipeline called **Summer Lock In 2026** with the following stages:

| Stage | Who |
|---|---|
| Waitlist — Member | Tagged as Member, not yet enrolled |
| Waitlist — Non-Member | Tagged as Non-Member, not yet signed up |
| Enrolled | Confirmed challenge participant |
| Converted (Non-Member) | Non-member who signed up for MacroFit |

---

## Part 2 — Automation 1: Member Sequence

**Trigger:** Contact is tagged `Summer Lock In - Member`  
**Goal:** Keep them warm, build excitement, remind them of the June 29th start date

### Message 1 — Immediate (SMS)

Send within 5 minutes of tag being applied.

> Hey {{contact.first_name}}! You're officially on the waitlist for the MacroFit Summer Lock In Challenge 🎉 We'll text you the moment enrollment opens — before it's announced anywhere else. June 29th is going to be a big one. Stay tuned! 💪
> — MacroFit

### Message 2 — Day 3 (SMS)

> Hey {{contact.first_name}} — just a heads up that the Summer Lock In Challenge fills up fast. We'll be sending your enrollment link soon. In the meantime, keep showing up with your weekly meal plan — that consistency is exactly what makes the challenge work. See you June 29th! 🔒
> — MacroFit

### Message 3 — Day 7 (Email)

**Subject:** Your Summer Lock In spot is almost ready 🔒

> Hey {{contact.first_name}},
>
> The MacroFit Summer Lock In Challenge kicks off June 29th — and you're on the early access list.
>
> Here's what's coming your way:
> - 42 days of structure and accountability inside the MacroFit app
> - Weekly challenges — Do It + Share It every week
> - Live weekly check-ins with Chelsea
> - A private community of women doing the challenge alongside you
> - A chance to win a $50 gift card just for showing up consistently
>
> Since you're already a MacroFit member, everything runs inside the app you already use. No extra setup, no new platform to learn.
>
> We'll send your enrollment link before anyone else gets it. Keep an eye on your texts and inbox around June 27th.
>
> See you on June 29th 💪
>
> — Chelsea & the MacroFit Team

### Message 4 — June 27th (SMS — Enrollment Open)

> 🚨 It's time, {{contact.first_name}}! The Summer Lock In Challenge enrollment is officially OPEN — and you're getting first access. Here's your link: [INSERT ENROLLMENT LINK]. Spots are limited — grab yours now. Challenge starts June 29th! 🔒
> — MacroFit

---

## Part 3 — Automation 2: Non-Member Nurture Sequence

**Trigger:** Contact is tagged `Summer Lock In - Non-Member`  
**Goal:** Educate them on MacroFit, remove objections, drive them to sign up using LOCKIN20 before June 29th

### Message 1 — Immediate (SMS)

Send within 5 minutes of tag being applied.

> Hey {{contact.first_name}}! Thanks for your interest in the MacroFit Summer Lock In Challenge 🙌 To join, you'll need to be a MacroFit member first — and we've got you covered. Use code **LOCKIN20** for $20 off your first month (just $79). Sign up at macrofitprogram.com and you're in. We'll follow up with everything you need to know! 💪
> — MacroFit

### Message 2 — Day 1 (SMS)

> Hey {{contact.first_name}} — quick question: what's the #1 thing that's made eating healthy feel hard for you? Most of our members say it's the planning, the guesswork, and not knowing what to actually eat. That's exactly what MacroFit handles. Real food, built-for-you plan, grocery list done. Month-to-month, cancel anytime. Use **LOCKIN20** at checkout → macrofitprogram.com 🙌
> — MacroFit

### Message 3 — Day 3 (Email)

**Subject:** What actually happens inside MacroFit (real talk)

> Hey {{contact.first_name}},
>
> You showed interest in the Summer Lock In Challenge — so I want to make sure you know exactly what MacroFit is before June 29th.
>
> Here's the honest version:
>
> MacroFit is not a diet. It's not a 30-day program. It's a month-to-month nutrition membership that gives you a personalized meal plan built around real food — spaghetti, cheeseburger bowls, tacos, the stuff your family actually eats.
>
> Every week you get a new plan. A grocery list is automatically generated. You spend about 1.5 hours prepping on Sunday and you're set for the entire week. No calorie counting. No macro tracking. No guesswork.
>
> **Members who stick with it lose real weight.** Katelyn lost 48 lbs. Kadie is down 51 lbs. Sarah lost 22 lbs and 20.5 inches — and she said she never once felt deprived.
>
> The Summer Lock In Challenge is a 42-day bonus layer of accountability, weekly challenges, live check-ins, and community that runs inside the app starting June 29th. It's designed to give you the structure and momentum to actually see results in your first 6 weeks.
>
> **To join the challenge, you need to be a MacroFit member.** And right now, you can start for just $79 your first month using code **LOCKIN20** at checkout.
>
> 👉 macrofitprogram.com — code **LOCKIN20**
>
> Questions? Just reply to this email. I read every one.
>
> — Chelsea

### Message 4 — Day 5 (SMS)

> {{contact.first_name}}, the Summer Lock In Challenge is filling up and June 29th is almost here. If you've been thinking about it — this is the sign. Use **LOCKIN20** for $20 off your first month at macrofitprogram.com. Real food. Real results. Month-to-month. 🔒
> — MacroFit

### Message 5 — Day 7 (Email)

**Subject:** Last chance to join before the challenge starts 🔒

> Hey {{contact.first_name}},
>
> The MacroFit Summer Lock In Challenge starts June 29th — and I want you in it.
>
> I know starting something new can feel like a big decision. So here's what I want you to know:
>
> MacroFit is month-to-month. No contracts. No long-term commitment. If it's not for you after the first month, you cancel — no questions asked. But if it's anything like what our members experience, you won't want to.
>
> Your first month is **$79** with code **LOCKIN20** (normally $99).
>
> 👉 Sign up at macrofitprogram.com before June 29th and you'll be enrolled in the challenge automatically.
>
> This is the last reminder I'll send before the challenge kicks off. I hope to see you there.
>
> — Chelsea & the MacroFit Team

### Message 6 — June 27th (SMS — Final Push)

> Hey {{contact.first_name}} — 2 days left to join the MacroFit Summer Lock In Challenge. Use **LOCKIN20** for $20 off your first month → macrofitprogram.com. Challenge starts June 29th. Don't miss it 🔒
> — MacroFit

---

## Part 4 — Integration Setup (ManyChat → GHL)

### Option A: Native ManyChat + GHL Integration (Recommended)

ManyChat has a built-in GoHighLevel integration. To set it up:

1. In ManyChat, go to **Settings → Integrations → GoHighLevel**
2. Connect your GHL account
3. In your LOCKIN flow, after each branch (Member / Non-Member), add a **GHL action**:
   - Action: **Create or Update Contact**
   - Map fields: first name, phone, email
   - Add tag: `Summer Lock In - Member` or `Summer Lock In - Non-Member`
4. GHL will create the contact and apply the tag, which triggers your automation

### Option B: Zapier Webhook

If the native integration is unavailable or you prefer Zapier:

1. In ManyChat, add a **Webhook** action at the end of each branch
2. Send the following fields to your Zapier webhook URL: `first_name`, `phone`, `email`, `tag`
3. In Zapier: trigger = Webhook → action = GHL "Create/Update Contact" + "Add Tag"
4. Set up two separate Zaps — one for each tag

---

## Part 5 — Automation Settings Summary

| Automation | Trigger | Messages | Stop Condition |
|---|---|---|---|
| Member Sequence | Tag: `Summer Lock In - Member` | SMS Day 0, SMS Day 3, Email Day 7, SMS June 27 | Contact enrolls (tag: `Summer Lock In - Enrolled`) |
| Non-Member Nurture | Tag: `Summer Lock In - Non-Member` | SMS Day 0, SMS Day 1, Email Day 3, SMS Day 5, Email Day 7, SMS June 27 | Contact signs up for MacroFit (tag: `Summer Lock In - Enrolled` or `Summer Lock In - Member`) |

**Important:** Add a stop condition to both automations so that if a non-member signs up and gets tagged as a member, they exit the non-member sequence and enter the member sequence automatically.

---

## Part 6 — Compliance Notes

All SMS messages sent through GHL must comply with TCPA regulations. Ensure the following:

- Consent was collected in ManyChat (the terms checkbox in the DM flow covers this for the ManyChat side)
- Your GHL account has SMS compliance language configured
- Every SMS includes an opt-out path — GHL handles this automatically with "Reply STOP to unsubscribe" appended to messages when compliance mode is enabled
- Keep records of consent timestamps — ManyChat logs these automatically

---

*Built for MacroFit Summer Lock In Challenge 2026*  
*Prepared by Manus AI for MacroFit Content Strategy*
