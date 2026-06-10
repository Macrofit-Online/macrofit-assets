# ManyChat Flow Script — Summer Lock In Challenge
## Keyword Trigger: LOCKIN

**Platform:** Build as two separate flows — one for Instagram, one for Facebook  
**Trigger:** User comments or DMs the word **LOCKIN** (set as a keyword trigger, case-insensitive)  
**Goal:** Hype their interest → ask if they're a current member → branch to appropriate experience → collect contact info → push to GHL

> ⚠️ **Platform Difference — Important:**  
> **Facebook Messenger** does not allow data collection in the first automated message. The opener (Message 1) is compliant for both platforms since it contains no data collection — it just hypes them and asks for a button tap.  
> **Instagram** and **Facebook** can use the same Message 1. The flows are otherwise identical.

---

## Flow Architecture Overview

```
LOCKIN keyword trigger
        ↓
  [Message 1] — Rah rah opener, no data collected
        ↓
  [Button tap] — "Yes, I want in! 🙌"
        ↓
  [Message 2] — "Are you currently a MacroFit member?"
        ↓
    ┌───────────────────────────────┐
    │                               │
[YES — Member]               [NO — Not yet]
    │                               │
[Message 3A]                  [Message 3B]
Hype + you're                 LOCKIN20 code
already in!                   drop + sign up
    │                               │
[Message 4A]                  [Message 4B]
Collect name                  Collect name
phone, email                  phone, email
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
**Note:** Works for both Instagram and Facebook — no platform difference at this step

---

### MESSAGE 1 — Rah Rah Opener *(both platforms)*

> Omg yesss!! 🙌 I'm SO glad you're interested in the Summer Lock In Challenge — this is going to be one of my favorite things I've ever done with this community.
>
> 42 days. Weekly challenges. Live check-ins with me. Real accountability. And a chance to win a **$50 gift card** just for showing up.
>
> Tap below and let's get you set up! 👇

**Button:** `Yes, I want in! 🙌`

**Note:** No data collection in this message. Compliant for Facebook. Gets the user engaged before branching.

---

### MESSAGE 2 — Member Check *(send immediately after button tap)*

> Quick question before I send you the details — are you currently a MacroFit member?

**Quick Reply Buttons:**
- ✅ Yes, I'm a member!
- 🆕 Not yet, but I want to be!

*(Force button selection — do not allow free text here)*

---

## BRANCH A — Current Member

**Condition:** User tapped "Yes, I'm a member!"

---

### MESSAGE 3A — Member Hype

> Yay!! 🎉 Okay so here's the thing — you're already doing the hard part. You're already showing up, already building the habit. The Summer Lock In Challenge is just going to make it even better.
>
> Starting **June 29th**, we're doing 42 days together — weekly challenges, live check-ins with me, and a community of people all pushing toward the same goal. Everything runs right inside the app you already use.
>
> I'll make sure you're the first to know when enrollment opens. I just need a couple quick things from you! 👇

---

### MESSAGE 4A — Collect Name (Member)

> What's your **first name**?

**Input type:** Free text (save to custom field: `first_name`)

---

### MESSAGE 5A — Collect Phone (Member)

> Love it, {{first_name}}! 🙌 What's the best **phone number** to reach you at?

**Input type:** Phone number (save to custom field: `phone`)  
**Validation:** Enable phone number validation

---

### MESSAGE 6A — Collect Email (Member)

> Perfect! And your **email address**?

**Input type:** Email (save to custom field: `email`)  
**Validation:** Enable email validation

---

### MESSAGE 7A — Member Confirmation

> You're all set, {{first_name}}!! 🔒 I'll text you personally before enrollment opens to anyone else — spots are limited and I want to make sure you get one.
>
> Cannot wait to do this with you!! 💪

**Actions after this message:**
- Add ManyChat tag: `Summer Lock In - Member`
- Trigger Zapier → push contact (name, phone, email) to GHL with tag `Summer Lock In - Member`

---

## BRANCH B — Not Yet a Member

**Condition:** User tapped "Not yet, but I want to be!"

---

### MESSAGE 3B — Non-Member + Code Drop

> Okay, this is literally the perfect time to start. 🙌
>
> MacroFit is a **month-to-month membership** (no contracts, cancel anytime). Every week you get a personalized meal plan built around real food — spaghetti, cheeseburger bowls, tacos. Your grocery list is automatically generated. You prep for about 1.5 hours on Sunday and you're set for the whole week. No calorie counting, no guesswork, no sad diet food.
>
> And right now, you can join and jump straight into the Summer Lock In Challenge on **June 29th** — 42 days of structure, accountability, weekly challenges, and live check-ins with me.
>
> Here's your exclusive code:
>
> 🎟️ **LOCKIN20** — $20 off your first month (just $79 to start)
>
> 👉 Sign up at **macrofitprogram.com** and use **LOCKIN20** at checkout.
>
> Once you're in, I'll make sure you have everything you need for June 29th. Let me grab your info so I can follow up! 👇

---

### MESSAGE 4B — Collect Name (Non-Member)

> What's your **first name**?

**Input type:** Free text (save to custom field: `first_name`)

---

### MESSAGE 5B — Collect Phone (Non-Member)

> So excited, {{first_name}}! 🙌 What's the best **phone number** to reach you at?

**Input type:** Phone number (save to custom field: `phone`)  
**Validation:** Enable phone number validation

---

### MESSAGE 6B — Collect Email (Non-Member)

> Perfect! And your **email**?

**Input type:** Email (save to custom field: `email`)  
**Validation:** Enable email validation

---

### MESSAGE 7B — Non-Member Confirmation

> You're all set, {{first_name}}! 🔒 Don't forget — use code **LOCKIN20** at macrofitprogram.com to get $20 off your first month.
>
> Once you sign up, I'll text you everything you need before June 29th. I really hope you join us — this group is going to be so good. 💪

**Actions after this message:**
- Add ManyChat tag: `Summer Lock In - Non-Member`
- Trigger Zapier → push contact (name, phone, email) to GHL with tag `Summer Lock In - Non-Member`

---

## Follow-Up Message (Both Branches — send 24 hours later)

> Hey {{first_name}}! Just checking in — do you have any questions about the Summer Lock In Challenge before June 29th? I'm literally right here if you want to chat. 😊
>
> Spots are limited so I want to make sure you're locked in!

**Timing:** 24 hours after Message 7A or 7B  
**Condition:** Only send if user has not replied or clicked a link since last message

---

## ManyChat Build Checklist

### Before You Build
- [ ] Create custom fields: `first_name`, `phone`, `email`
- [ ] Create tags: `Summer Lock In - Member`, `Summer Lock In - Non-Member`
- [ ] Connect Zapier (or native GHL integration) to push contacts on tag assignment

### Flow Setup
- [ ] Set keyword trigger: LOCKIN (add variations: lockin, lock in, Lock In)
- [ ] Enable both comment reply and DM as trigger sources
- [ ] Build Message 1 with button — no user input collected
- [ ] Build Message 2 with two Quick Reply buttons (no free text)
- [ ] Build Branch A (member) and Branch B (non-member) as separate paths
- [ ] Set each data collection step to save to the correct custom field
- [ ] Enable phone and email validation on those steps
- [ ] Add tag assignment actions after Message 7A and 7B
- [ ] Add Zapier trigger action after tag assignment
- [ ] Set 24-hour follow-up with send condition (only if no reply)

### Testing
- [ ] Test full flow as a member (tap "Yes, I'm a member!")
- [ ] Test full flow as a non-member (tap "Not yet, but I want to be!")
- [ ] Verify contacts appear in GHL with correct tags after each test
- [ ] Verify Zapier zap fires and maps fields correctly
- [ ] Test on both Instagram and Facebook separately

---

## Zapier Setup (ManyChat → GHL)

**Trigger:** ManyChat — New Tag Added to Subscriber  
**Filter:** Tag name contains "Summer Lock In"  
**Action:** GHL — Create or Update Contact  

**Field mapping:**
| ManyChat Field | GHL Field |
|---|---|
| `first_name` | First Name |
| `phone` | Phone |
| `email` | Email |
| Tag name | Tag (apply matching tag in GHL) |

**Two zaps needed:**
1. Tag = `Summer Lock In - Member` → GHL tag `Summer Lock In - Member`
2. Tag = `Summer Lock In - Non-Member` → GHL tag `Summer Lock In - Non-Member`
