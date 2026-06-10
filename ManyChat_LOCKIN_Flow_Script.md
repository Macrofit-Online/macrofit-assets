# ManyChat Flow Script — Summer Lock In Challenge
## Keyword Trigger: LOCKIN

**Platform:** Build as two separate flows — one for Instagram, one for Facebook  
**Trigger:** User comments or DMs the word **LOCKIN** (set as a keyword trigger, case-insensitive)  
**Goal:** Collect name, phone, and email → ask if they're a current MacroFit member → push contact to GHL with the correct tag → deliver appropriate confirmation message  

> ⚠️ **Platform Difference — Important:**  
> **Facebook Messenger** does not allow data collection in the first automated message. The first message must be a simple, non-collecting opener that gets the user to tap a button or reply before you can ask for any information. The flow below notes where each platform diverges.  
> **Instagram** does not have this restriction — data collection can begin in Message 1.

---

## Flow Architecture Overview

**Instagram Flow:**
```
LOCKIN keyword trigger
        ↓
  [Message 1] — Opener + name ask  ← data collection starts here
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

**Facebook Flow (add Message 0 before data collection):**
```
LOCKIN keyword trigger
        ↓
  [Message 0] — Compliant opener, button tap required  ← Facebook only
        ↓
  [Message 1] — Name ask  ← data collection starts here
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

### MESSAGE 0 — Facebook Compliant Opener *(Facebook flow only — skip for Instagram)*

> Hey!! I'm so excited you're interested in the Summer Lock In Challenge 🙌 Tap below and I'll send you all the details!

**Button:** `Yes, send me the details! →`  
**Note:** This message contains no data collection. It exists solely to get the user to tap a button, which opens the 24-hour messaging window required by Facebook's Messenger policy. Data collection begins in Message 1 after they tap.

---

### MESSAGE 1 — Name Ask *(Instagram: send immediately after trigger | Facebook: send after button tap in Message 0)*

> Hey!! I'm SO excited you're interested in the Summer Lock In Challenge 🙌 This is going to be such a good one.
>
> I just need a couple quick things from you so I can make sure you get all the details first — before I announce it anywhere else.
>
> What's your **first name**?

**Input type:** Free text (save to custom field: `first_name`)

---

### MESSAGE 2 — Phone

> Love it, {{first_name}}! 🙌
>
> What's the best **phone number** to reach you at? I'll personally text you the moment enrollment opens — you'll get access before anyone else.

**Input type:** Phone number (save to custom field: `phone`)  
**Validation:** Enable phone number validation in ManyChat

---

### MESSAGE 3 — Email

> Perfect! And what's your **email**? I'll send you all the details there too so you have everything in one place.

**Input type:** Email (save to custom field: `email`)  
**Validation:** Enable email validation in ManyChat

---

### MESSAGE 4 — Member Check

> Last thing — are you currently a MacroFit member? I want to make sure I send you the right info! 😊

**Quick Reply Buttons:**
- ✅ Yes, I'm a member
- 🆕 Not yet!

*(Do not use free text here — force a button selection so the branch is clean)*

---

### BRANCH A — Current Member

**Condition:** User tapped "Yes, I'm a member"

#### MESSAGE 5A — Member Confirmation

> Yay, {{first_name}}!! I'm so glad you're in 🎉
>
> The Summer Lock In Challenge starts **June 29th** — 42 days of weekly challenges, live check-ins with me, community accountability, and a chance to win a **$50 gift card** just for showing up. It's going to be so good.
>
> Since you're already a member, everything runs right inside the app — nothing new to set up. You're already doing the work, this just adds the structure and the fun. 🙌
>
> I'll text you personally before enrollment opens to anyone else. Keep an eye on your messages — spots are limited and I want to make sure you get one. 🔒
>
> Cannot wait to do this with you!! 💪

**Action after message:**
- Add tag in ManyChat: `Summer Lock In - Member`
- Trigger GHL webhook or Zapier integration → push contact with tag `Summer Lock In - Member`

---

### BRANCH B — Non-Member

**Condition:** User tapped "No, not yet"

#### MESSAGE 5B — Non-Member Intro + Coupon

> Okay {{first_name}}, honestly — this could not be better timing. 🙌
>
> MacroFit is a month-to-month membership (no contracts, cancel anytime) where you get a personalized meal plan every week built around **real food** — like spaghetti, cheeseburger bowls, tacos. Your grocery list is automatically generated. You prep for about 1.5 hours on Sunday and you're set for the whole week. No calorie counting, no guesswork, no sad diet food.
>
> The Summer Lock In Challenge is a 42-day bonus layer of accountability, weekly challenges, and live check-ins with me that runs inside the app starting June 29th. I designed it specifically to help people build real momentum in their first 6 weeks.
>
> To join, you just need to be a MacroFit member first — and I want to make it easy for you:
>
> 🎟️ **Use code LOCKIN20 for $20 off your first month** — just $79 to start
>
> 👉 **macrofitprogram.com** → use code **LOCKIN20** at checkout
>
> Once you're in, I'll text you everything you need before June 29th. I really hope you join us — this group is going to be so good 🔒

**Action after message:**
- Add tag in ManyChat: `Summer Lock In - Non-Member`
- Trigger GHL webhook or Zapier integration → push contact with tag `Summer Lock In - Non-Member`

---

### MESSAGE 6 — Universal Follow-Up (Both Branches, send 24 hours later)

> Hey {{first_name}}! Just wanted to check in — do you have any questions about the Summer Lock In Challenge before June 29th? I'm literally right here if you want to chat about it. 😊
>
> Spots are limited so I want to make sure you're locked in. Reply anytime!

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
