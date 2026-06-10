# ManyChat Flow Script — Summer Lock In Challenge
## Keyword Trigger: LOCKIN

**Platform:** Build as two separate flows — one for Instagram, one for Facebook  
**Trigger:** User comments or DMs the word **LOCKIN** (set as a keyword trigger, case-insensitive)  
**Goal:** Collect name, phone, and email → ask if they're a current MacroFit member → push contact to GHL with the correct tag → deliver appropriate confirmation message  

---

## Flow Architecture Overview

```
LOCKIN keyword trigger
        ↓
  [Message 1] — Opener + name ask
        ↓
  [Message 2] — Phone ask
        ↓
  [Message 3] — Email ask
        ↓
  [Message 4] — Member or not? (Quick Reply buttons)
        ↓
    ┌───────────────────────────────┐
    │                               │
[YES — Member]               [NO — Not a Member]
    │                               │
[Message 5A]                  [Message 5B]
Confirmation +                Intro + coupon
hype message                  LOCKIN20
    │                               │
Push to GHL                   Push to GHL
Tag: Summer Lock In           Tag: Summer Lock In
- Member                      - Non-Member
```

---

## Step-by-Step Flow Script

---

### TRIGGER

**Keyword(s):** LOCKIN, lockin, lock in, Lock In  
**Where:** Comment reply + DM trigger  
**Timing:** Send immediately upon trigger

---

### MESSAGE 1 — Opener

> Hey! 👋 You're on the list for the **MacroFit Summer Lock In Challenge** — I just need a few quick things from you so I can make sure you get all the details the moment enrollment opens.
>
> First — what's your **first name**?

**Input type:** Free text (save to custom field: `first_name`)

---

### MESSAGE 2 — Phone

> Nice to meet you, {{first_name}}! 🙌
>
> What's the best **phone number** to reach you at? (We'll text you the moment the challenge drops — before it's announced anywhere else.)

**Input type:** Phone number (save to custom field: `phone`)  
**Validation:** Enable phone number validation in ManyChat

---

### MESSAGE 3 — Email

> Perfect. And what's your **email address**?

**Input type:** Email (save to custom field: `email`)  
**Validation:** Enable email validation in ManyChat

---

### MESSAGE 4 — Member Check

> Last one — are you currently a **MacroFit member**?

**Quick Reply Buttons:**
- ✅ Yes, I'm a member
- 🆕 No, not yet

*(Do not use free text here — force a button selection so the branch is clean)*

---

### BRANCH A — Current Member

**Condition:** User tapped "Yes, I'm a member"

#### MESSAGE 5A — Member Confirmation

> You're in, {{first_name}}! 🎉
>
> The **Summer Lock In Challenge** kicks off **June 29th** — 42 days of structure, weekly challenges, live check-ins with Chelsea, community accountability, and a chance to win a **$50 gift card** just for showing up consistently.
>
> Since you're already a MacroFit member, everything runs right inside the app you already use. No extra setup needed.
>
> We'll text and email you **before** enrollment opens to anyone else. Keep an eye on your messages — spots are limited. 🔒
>
> See you on June 29th! 💪

**Action after message:**
- Add tag in ManyChat: `Summer Lock In - Member`
- Trigger GHL webhook or Zapier integration → push contact with tag `Summer Lock In - Member`

---

### BRANCH B — Non-Member

**Condition:** User tapped "No, not yet"

#### MESSAGE 5B — Non-Member Intro + Coupon

> No worries at all — this is actually the perfect time to start. 🙌
>
> Here's how MacroFit works: you get a **personalized meal plan built around real food** — spaghetti, cheeseburger bowls, tacos, all of it. A grocery list is automatically generated. You spend about **1.5 hours prepping on Sunday** and you're set for the entire week. No calorie counting. No guesswork.
>
> MacroFit is **month-to-month** — no contracts, cancel anytime. And the Summer Lock In Challenge is a bonus layer of accountability and community that runs inside the app starting June 29th.
>
> To join the challenge, you'll need to be a MacroFit member first. But here's the thing — **we want you in**, so we're giving you a special code:
>
> 🎟️ **Use code LOCKIN20 for $20 off your first month** (just $79 to start)
>
> 👉 Sign up at **macrofitprogram.com** and use code **LOCKIN20** at checkout.
>
> Once you're a member, you're automatically eligible for the challenge. We'll text you with all the details before June 29th. 🔒

**Action after message:**
- Add tag in ManyChat: `Summer Lock In - Non-Member`
- Trigger GHL webhook or Zapier integration → push contact with tag `Summer Lock In - Non-Member`

---

### MESSAGE 6 — Universal Follow-Up (Both Branches, send 24 hours later)

> Hey {{first_name}} — just a quick reminder that the **MacroFit Summer Lock In Challenge** opens **June 29th** and spots are limited. 🔒
>
> If you have any questions before then, just reply here and I'll get back to you. Can't wait to see what you accomplish in 42 days. 💪

**Timing:** Send 24 hours after Message 5A or 5B  
**Condition:** Only send if user has not already clicked a link or replied

---

## ManyChat Setup Checklist

| Step | Action |
|---|---|
| Custom Fields | Create: `first_name`, `phone`, `email` |
| Tags | Create: `Summer Lock In - Member`, `Summer Lock In - Non-Member` |
| Keyword Trigger | Set LOCKIN (and variants) as a keyword in both IG and FB flows |
| Comment Trigger | Enable "Comment to DM" — when someone comments LOCKIN on any post, auto-DM them with Message 1 |
| Phone Validation | Enable in ManyChat settings for the phone input step |
| Email Validation | Enable in ManyChat settings for the email input step |
| GHL Integration | Set up via ManyChat's native GHL integration OR Zapier webhook (see GHL Setup Guide) |
| Test Flow | Run through both branches manually before going live |

---

## Copy Notes

- Keep every message short and conversational — this is a DM, not an email
- Use the person's first name ({{first_name}}) in messages after it's collected to keep it personal
- Do not use all-caps or aggressive urgency language — warm, encouraging tone throughout
- The non-member branch should feel like an invitation, not a sales pitch
- Emoji use is intentional and light — do not add more than what's written here

---

*Built for MacroFit Summer Lock In Challenge 2026 — Instagram + Facebook DM flows*
