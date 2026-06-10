# GHL Workflow: New MacroFitter Onboarding

## Overview
This workflow fires when the `macrofitter` tag is added to a contact in GHL.
Zapier triggers this by adding the tag when a new Stripe "Macrofit Premium One-time payment" invoice is paid.

**Workflow Name:** New MacroFitter Onboarding
**Trigger:** Contact Tag → Tag added → macrofitter

---

## Workflow Steps

---

### STEP 1 — Send SMS (Immediate)
**Action Name:** Welcome SMS - Day 1
**Delay:** None (fires immediately)

**Message:**
```
Hey {{contact.first_name}}! You just made a really good decision! Welcome to Macrofit! Your next step is logging into the app and entering your baseline data — that information is necessary to build your personalized plan. Try to get that done a few days before your start date so everything is ready to go on Day 1. The app is available in both the App Store and Google Play — and you can always access your account on www.macrofit.com.
```

---

### STEP 2 — Send Email (Immediate)
**Action Name:** Welcome Email - Day 1
**Delay:** None (fires immediately after SMS)

**Subject:** Welcome to Your Journey with MacroFit

**Body:**
```
Hi {{contact.first_name}},

Welcome to MacroFit! We're so glad you're here.

Here's what happens next:

1. BUILD YOUR WEEK 1 MEAL PLAN
Log into the MacroFit app and build your first week of meals. This is the most important step — don't skip it. Your plan is already waiting for you.

2. GROCERY SHOP
Use the grocery list generated from your meal plan. Everything is already calculated for you.

3. MEAL PREP
Set aside a few hours before your start date to prep. The more you prep, the easier your week will be.

A few things to know about Week 1:
- Week 1 has the MOST food you'll ever eat in the program. It's intentionally higher to ease you in.
- You don't have to be perfect. Aim to follow your plan most of the time.
- Workouts are optional but encouraged — 3 resistance-based sessions per week if you can.
- Steps goal: 8,000–10,000/day. Start where you are and build up.

What makes MacroFit different:
✓ Flexible meal planning — you choose what you eat
✓ Macro Points system — no calorie counting
✓ Calorie cycling — your intake adjusts week to week
✓ On-the-go restaurant options built in
✓ We do the planning. You just follow it.

You're not paying for recipes. You're paying so "What should I eat?" isn't a question you have to answer anymore.

Let's go,
Chelsea
MacroFit
```

---

### STEP 3 — Wait
**Action Name:** Wait 1 Day
**Delay:** 1 day

---

### STEP 4 — Send Email (Day 2)
**Action Name:** How It Works Email - Day 2
**Subject:** Here's exactly how MacroFit works

**Body:**
```
Hi {{contact.first_name}},

Now that you're getting settled in, here's a quick breakdown of how the MacroFit system works so nothing feels confusing.

THE MACRO POINTS SYSTEM
Think of Macro Points like a weekly budget. Each week, you have a set number of points to spend on meals and snacks. You pick from the meal plan options — each one has a point value — and you stay within your budget.

That's it. No weighing food. No tracking macros manually. We've done that math for you.

HOW TO USE YOUR PLAN
- Select your meals for the week from the app
- Your grocery list generates automatically
- Use Alternative meals, Single Serving options, or On-the-Go (OTG) restaurant options when life happens

THE 6-MONTH CYCLE
MacroFit runs on a 24-week cycle:
- Weeks 1–16: Calorie cycling (gradually decreasing to create a fat loss deficit)
- Weeks 17–24: Reverse diet (gradually increasing back up to protect your metabolism)

Your Macro Points are adjusted weekly based on your check-in. This is why consistency with your weekly check-in matters — it's how we know what to do next.

WHAT TO EXPECT WEEK 1
Week 1 is the most food you'll eat in the entire program. It's designed that way on purpose. We want you to feel satisfied and not deprived as you get started.

Any questions? Just reply to this email or text us.

Chelsea
MacroFit
```

---

### STEP 5 — Wait
**Action Name:** Wait 1 Day
**Delay:** 1 day

---

### STEP 6 — Send Email (Day 3)
**Action Name:** Family Meals Email - Day 3
**Subject:** Cooking MacroFit for the whole family

**Body:**
```
Hi {{contact.first_name}},

One of the most common questions we get: "Can I cook MacroFit meals for my whole family?"

Yes — and here's how.

THE KEY: WEIGH YOUR PORTION SEPARATELY
MacroFit meals are built around 7 servings per recipe. When you cook, make the full recipe for your family — but weigh or measure your portion before serving.

Your Macro Points budget is personalized to YOU. Your husband, your kids — they have different caloric needs. So you eat the same food, just your specific portion.

PRACTICAL TIPS:
- Double recipes when feeding a crowd — just keep your portion the same
- Prep your portion first, then serve the rest family-style
- OTG (On-the-Go) options are great for nights when everyone wants something different

You don't have to cook two separate meals. You just have to know your portion.

Chelsea
MacroFit
```

---

### STEP 7 — Wait
**Action Name:** Wait Until Start Date
**Delay:** Wait until {{contact.start_date}} (NOTE: Update this once start date field is set up via Zapier/Stripe metadata. For now, use a 4-day wait as placeholder.)
**Placeholder Delay:** 4 days

---

### STEP 8 — Send SMS (Start Date - Day 0)
**Action Name:** Start Day SMS
**Subject:** N/A (SMS)

**Message:**
```
Today's the day, {{contact.first_name}}! Your MacroFit plan officially starts now. You've got everything you need — just open the app and follow your plan. We're rooting for you. Reply anytime if you need us!
```

---

### STEP 9 — Send Email (Start Date - Day 0)
**Action Name:** Launch Day Email
**Subject:** Today's the Day

**Body:**
```
Hi {{contact.first_name}},

Today is Day 1.

Your meal plan is ready. Your grocery list is done. Your prep is (hopefully) handled.

Now you just show up.

Here's the only thing that matters this week: follow your plan most of the time. Not perfectly. Most of the time.

You're not paying for discipline. You're paying so discipline isn't required.

The system does the heavy lifting. Your job is to trust it and keep going.

We'll check in with you soon.

Chelsea
MacroFit
```

---

### STEP 10 — Wait
**Action Name:** Wait 7 Days
**Delay:** 7 days

---

### STEP 11 — Send Email (Week 2)
**Action Name:** Expectations Email - Week 2
**Subject:** What to expect (and what not to)

**Body:**
```
Hi {{contact.first_name}},

You're one week in. Let's talk about what you should — and shouldn't — expect.

WHAT MACROFIT IS:
A fat loss program. Not a weight loss program.

These are different things.

Fat loss = losing body fat while preserving muscle.
Weight loss = losing any combination of fat, muscle, and water.

The scale measures weight. It doesn't tell you what kind of weight.

WHAT GOOD PROGRESS LOOKS LIKE:
- 0.5–1 lb per week is excellent fat loss
- Some weeks the scale won't move — that doesn't mean nothing is happening
- You might lose inches before you lose pounds
- Energy, sleep, and how your clothes fit matter more than the number

THE 24-WEEK REALITY:
MacroFit is a 24-week program. Real, lasting fat loss takes time. Anyone promising dramatic results in 2 weeks is selling you something that won't last.

If you're doing the work, the results will come. Stay in the system.

Chelsea
MacroFit
```

---

### STEP 12 — Wait
**Action Name:** Wait 7 Days
**Delay:** 7 days

---

### STEP 13 — Send Email (Week 3)
**Action Name:** Adherence Email - Week 3
**Subject:** The one number that predicts your results

**Body:**
```
Hi {{contact.first_name}},

There's one number in the MacroFit app that predicts your results better than anything else.

Your adherence score.

Adherence measures how closely you followed your plan each week. The scale goes from 1–10.

Here's the honest truth:
- Adherence 8–10: You will see results. Consistently.
- Adherence 5–7: You'll see some progress, but it'll be slower than it should be.
- Adherence 1–4: The program can't work if you're not following it.

This isn't a judgment. It's math.

MacroFit creates a calorie deficit by design — but only if you follow the plan. If your adherence is a 4, that's why you're not seeing results. Not because the program doesn't work.

The good news: adherence is completely within your control.

Aim for 8 or above this week.

Chelsea
MacroFit
```

---

### STEP 14 — Wait
**Action Name:** Wait 21 Days
**Delay:** 21 days (brings us to approximately Week 6)

---

### STEP 15 — Send Email (Week 6)
**Action Name:** Retention Email - Week 6
**Subject:** You're not paying for discipline

**Body:**
```
Hi {{contact.first_name}},

Quick check-in.

You're about 6 weeks in, which means you've probably noticed something:

This doesn't require the same daily heroics as past diets.

That's not an accident.

MacroFit isn't designed to test your willpower.
It's designed to remove the need for willpower.

We decide the portions.
We adjust your intake.
We absorb the imperfect days.

Your only job is to show up most of the time.

That's why this works when everything else hasn't.

You're not paying for discipline.
You're paying so you don't need discipline.

Keep going,
Chelsea

P.S. If last week felt "off," that's normal. Nothing needs fixing. Just submit your check-in like always.
```

---

### STEP 16 — Wait
**Action Name:** Wait 14 Days
**Delay:** 14 days (brings us to approximately Week 8)

---

### STEP 17 — Send Email (Week 8)
**Action Name:** Retention Email - Week 8
**Subject:** Structure beats motivation

**Body:**
```
Hi {{contact.first_name}},

Maybe you weren't "feeling it."
Maybe life got busy and meals felt like an afterthought.

And yet… you still made progress.

That's the entire point of MacroFit.

Motivation is unreliable. Systems are not.

When you have structure, low-motivation weeks don't derail you.
You don't restart from zero.
You don't spiral into "screw it" mode.

You just keep going.

That's not willpower. That's design.

Most diets require you to be ON all the time.
MacroFit works because you don't have to be.

So if this week felt boring or uninspired?
That probably means it's working.

Chelsea

P.S. Your body doesn't care if you were motivated. It cares if you were consistent. You were.
```

---

### STEP 18 — Wait
**Action Name:** Wait 14 Days
**Delay:** 14 days (brings us to approximately Week 10)

---

### STEP 19 — Send Email (Week 10)
**Action Name:** Retention Email - Week 10
**Subject:** If it feels boring, it's probably working

**Body:**
```
Hi {{contact.first_name}},

Real talk:

Sustainable fat loss doesn't feel dramatic.

It doesn't feel urgent.
It doesn't feel Instagram-worthy.

It feels... kind of boring.

And that's exactly why it works.

The stuff that feels exciting? That's usually the stuff that doesn't last.

MacroFit isn't designed to give you weekly dopamine hits from the scale.
It's designed to keep you moving forward even when progress feels quiet.

Because here's what we know after 4,500+ clients:

The people who get the best results aren't the ones who had perfect weeks.
They're the ones who stayed in the system long enough for boring to turn into results.

You're in week 10.
You're doing the boring work.
That's the work that compounds.

Keep going.

Chelsea

P.S. If the scale hasn't moved in a week or two, don't panic. We adjust for that. Just keep showing up.
```

---

### STEP 20 — Wait
**Action Name:** Wait 14 Days
**Delay:** 14 days (brings us to approximately Week 12)

---

### STEP 21 — Send Email (Week 12)
**Action Name:** Retention Email - Week 12
**Subject:** You don't cancel the thing that's finally working

**Body:**
```
Hi {{contact.first_name}},

You're 3 months in.

And if I had to guess, you're probably thinking one of two things:

1. "I've got this now. Maybe I don't need MacroFit anymore."

or

2. "This feels too easy. Am I even trying hard enough?"

Let me address both.

---

If you're thinking you've "got this":

That feeling? That's the system working.

You don't feel like you need MacroFit anymore because MacroFit is doing the heavy lifting.

Most people quit right when the structure starts carrying the weight.

And then 6 weeks later, they're back at square one — winging it, second-guessing every meal, stuck in the same cycle they broke free from.

You don't cancel the thing that makes it easy once it finally feels easy.

---

If you're thinking this feels "too easy":

That's because you're used to diets that require constant mental effort.

MacroFit doesn't.

You're not supposed to white-knuckle your way through this.
You're supposed to stop thinking about food all the time.

That's the entire point.

You're not paying for struggle. You're paying so struggle isn't required.

---

Here's the truth:

Life is going to get harder before it gets easier.

Busy seasons. Travel. Stress. Chaos.

MacroFit exists for those weeks.
The ones that aren't Instagram-worthy.

Chelsea
```

---

### STEP 22 — Send SMS (Week 12)
**Action Name:** Referral SMS - Week 12
**Delay:** None (same day as Week 12 email)

**Message:**
```
Hey {{contact.first_name}}! Did you know MacroFit has a referral program? Refer a friend and they get $30 off their first month — and you get $20 off per month they stay enrolled. Up to 5 friends = potentially free membership. Find it in the app under Settings → Rewards and Referrals.
```

---

### STEP 23 — End Workflow

---

## Summary Timeline

| Step | Timing | Type | Name |
|---|---|---|---|
| 1 | Immediately | SMS | Welcome SMS |
| 2 | Immediately | Email | Welcome Email |
| 3 | +1 day | Wait | — |
| 4 | Day 2 | Email | How It Works |
| 5 | +1 day | Wait | — |
| 6 | Day 3 | Email | Family Meals |
| 7 | +4 days (placeholder) | Wait | Until Start Date |
| 8 | Start Date | SMS | Start Day SMS |
| 9 | Start Date | Email | Launch Day Email |
| 10 | +7 days | Wait | — |
| 11 | Week 2 | Email | Expectations |
| 12 | +7 days | Wait | — |
| 13 | Week 3 | Email | Adherence |
| 14 | +21 days | Wait | — |
| 15 | Week 6 | Email | You're not paying for discipline |
| 16 | +14 days | Wait | — |
| 17 | Week 8 | Email | Structure beats motivation |
| 18 | +14 days | Wait | — |
| 19 | Week 10 | Email | If it feels boring |
| 20 | +14 days | Wait | — |
| 21 | Week 12 | Email | You don't cancel |
| 22 | Week 12 | SMS | Referral |
| 23 | — | End | — |

---

## Notes for Future Updates
- **Step 7 (Wait Until Start Date):** Once Zapier passes the `start_date` from Stripe metadata to GHL as a custom contact field, update this wait step to "Wait Until {{contact.start_date}}" instead of the 4-day placeholder.
- **Resubscriber workflow:** Build separately — shorter sequence, warmer tone, skips basic how-it-works emails.
- **Summer Lock In workflow:** Build separately with fixed dates (June 29–Aug 9, 2026).
