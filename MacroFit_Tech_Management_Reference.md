# MacroFit Tech Management Reference

**Last Updated:** June 10, 2026
**Purpose:** Central reference for all technical infrastructure, integrations, and pending developer tasks across the MacroFit platform.

---

## 1. Current Platform Architecture

### macrofit.com (Member Platform)
- **Stack:** Custom-built PHP 7.2 on CodeIgniter Framework
- **Database:** MySQL
- **Frontend:** HTML5, CSS, Bootstrap, jQuery, JavaScript
- **Member dashboard URL:** `macrofit.com/customer/dashboard`
- **Signup URL:** `macrofit.com/signup`
- **Payments:** Stripe (existing integration)
- **Analytics:** Google Analytics (already installed)
- **Facebook Pixel:** Not installed — **pending**
- **Stripe Metadata:** Not configured — **pending**

### macrofitprogram.com (Marketing Site — Current)
- **Stack:** React 19 + Tailwind CSS 4 + shadcn/ui
- **Hosting:** Manus (managed hosting)
- **Domain:** macrofitprogram.com
- **Editable by:** Chelsea via Manus (no developer required for content changes)
- **Status:** Live and published

### join.macrofitprogram.com (GHL Funnel Pages)
- **Platform:** GoHighLevel (GHL)
- **Current pages:** Summer Lock In 2026 opt-in funnel
- **Note:** Consent checkboxes in legal text still reference "Summer Shred 2026" — needs to be updated to "Summer Lock In 2026"

---

## 2. Planned Architecture Migration

### Goal
Move the member platform backend to `app.macrofit.com` and use `www.macrofit.com` for the new marketing site.

### Target State
| Domain | Purpose | Stack |
|---|---|---|
| `www.macrofit.com` | Marketing site (homepage, pricing, about) | React / Manus |
| `app.macrofit.com` | Member platform (login, dashboard, meal plans) | PHP / CodeIgniter |
| `join.macrofitprogram.com` | GHL funnel pages | GoHighLevel |

### Developer Tasks Required
1. **Move backend to app.macrofit.com** — DNS update, update all internal links from `macrofit.com/customer/*` → `app.macrofit.com/customer/*`
2. **Point www.macrofit.com to Manus** — DNS CNAME update to Manus hosting
3. **Set up CI/CD pipeline** — so publishing from Manus automatically deploys to www.macrofit.com
4. **Update all GHL workflows** — find and replace any links referencing `macrofit.com/signup` → `app.macrofit.com/signup`
5. **Update email templates** — same find-and-replace for signup/login links in all GHL email sequences

---

## 3. Pending Developer Tasks — macrofit.com

### Task 1: Facebook Pixel Installation
**Priority:** High
**Estimated dev time:** 1 hour

**What to do:**
- Add the Meta Pixel base code to the `<head>` section of the main PHP layout file (the template that wraps every page)
- Add a Purchase event on the payment confirmation / thank-you page
- Add a Lead event on the signup form submission

**What Chelsea needs to provide:**
- Facebook Pixel ID (found in Meta Business Suite → Events Manager → your Pixel → Settings)

**Ad account context:** The Pixel should be from the MacroFit Program ad account (not a personal ad account).

---

### Task 2: Stripe Metadata + Invoice Update
**Priority:** High
**Estimated dev time:** 2–4 hours

**What to do:**

**A. Add metadata to the Stripe subscription object** (in the PHP code that creates the subscription):
```php
'metadata' => [
    'start_date'    => $start_date,       // e.g. "2026-06-23"
    'plan_type'     => $plan_type,        // "monthly", "3-month", or "6-month"
    'user_id'       => $user->id,         // MacroFit internal user ID
    'referral_code' => $referral_code,    // if applicable, otherwise null
]
```

**B. Update the Stripe invoice description** so the customer's receipt is clear:
```
"MacroFit Monthly Membership — Starting [start_date]"
```

**Why this matters:**
- Allows filtering subscribers by cohort/round in Stripe
- Makes customer support lookups instant
- Enables revenue reporting by plan type and start date

---

### Task 3: Stripe Tiered Pricing (Future — Not Yet Live)
**Priority:** Medium — implement when pricing tiers go live
**Estimated dev time:** 4–8 hours

**Planned pricing structure:**
| Plan | Price | Billing |
|---|---|---|
| Monthly | $109/month | Billed monthly |
| 3-Month Commitment | $89/month | Billed monthly |
| 6-Month Commitment | $74/month | Billed monthly |

**Current price:** $99/month (single tier)

**What to do when ready:**
- Create three Stripe Products/Prices in the Stripe dashboard
- Update the signup flow to present the three options
- Pass `plan_type` in metadata as noted above

---

## 4. Marketing Site — macrofitprogram.com (Manus)

### What's Built
- Full homepage with all sections (hero, stats, who it's for, how it works, adaptive system explainer, comparison table, FAQ, pricing, testimonials, community CTA)
- Summer Lock In landing page
- Conversion optimizations: urgency bar, dynamic spots remaining, sticky mobile CTA, pricing section

### Dynamic Urgency Logic
The site automatically calculates the next available Monday start date (minimum 8 days out) and displays a dynamic "spots remaining" count:

| Days Until Start | Spots Shown |
|---|---|
| 15+ days | 18 spots remaining |
| 12–14 days | 12 spots remaining |
| 9–11 days | 7 spots remaining |
| 8 days | Only 3 spots remaining |

This resets automatically each week — no manual updates needed.

### Pending Mobile Fixes (Minor)
- Feature pills in hero section overflow on small screens — need to wrap to multiple lines
- Comparison table needs horizontal scroll or simplified mobile layout on small screens

### How to Edit
Chelsea can request changes through Manus. No developer required for:
- Copy changes (headlines, body text, CTAs)
- Pricing updates
- Adding/removing sections
- New campaign pages

---

## 5. GoHighLevel (GHL) — Onboarding Workflow

### Existing Messages (Already in Workflow)
| # | Type | Timing | Content |
|---|------|---------|---------|
| — | System email | Immediately post-purchase | Platform welcome, baseline data, app download |
| 2 | SMS | Shortly after purchase | "Hey it's Chelsea — check your email, read the series" |
| 3 | SMS | Early on | Referral program ($30 off for friend, $20/month back for you) |
| 5 | SMS | ~4 days before start | Download the app, build meal plan, grocery shop |
| 7 | SMS | Day before start (Sunday) | Meal Prep Sunday — it's time to prep! |
| 11 | SMS | Week 3 | Scale check-in pep talk |

### New Messages (Built — Ready to Add to GHL)
| # | Type | Timing | Content | File |
|---|------|---------|---------|------|
| 1 | SMS | Immediately post-purchase | "You just made a really good decision! Welcome to MacroFit!" | Copy only |
| 4 | Email | ~5 days before start | 6-month cycle explainer | `email_02_6month_cycle.html` |
| 6 | Email | ~4 days before start | Cooking for your family | `email_03_cooking_for_family.html` |

### Emails Still to Build
| # | Type | Timing | Content |
|---|------|---------|---------|
| 8 | Email | ~3 days before start | Full how-it-works breakdown |
| 9 | Email | Start day | Launch day |
| 10 | Email | Week 1–2 | Fat loss vs. weight loss expectations |
| 11 | Email | Week 2 | Adherence |

### GHL Email Settings (Recommended)
- **Track clicks:** ON
- **UTM tracking:** ON
- **Add tags:** ON

### Note on Consent Text
The legal consent checkbox on the Summer Lock In GHL funnel page still reads "Summer Shred 2026" — needs to be updated to "Summer Lock In 2026."

---

## 6. Key Credentials Needed (Chelsea to Locate)

| Item | Where to Find | Used For |
|---|---|---|
| Facebook Pixel ID | Meta Business Suite → Events Manager → Pixels → Settings | Developer Task 1 |
| Stripe API keys | Stripe Dashboard → Developers → API Keys | Developer Task 2 |
| GA4 Measurement ID | Google Analytics → Admin → Data Streams | Confirm already on macrofit.com |

---

## 7. Recommended Next Actions

**Immediate (this week):**
1. Provide Facebook Pixel ID to developer — 1 hour to install
2. Developer adds Stripe metadata + invoice start date
3. Continue building GHL email sequence (Emails 4–7)

**Short-term (next 2–4 weeks):**
4. Developer migrates backend to app.macrofit.com
5. www.macrofit.com pointed to Manus marketing site
6. CI/CD pipeline set up
7. All GHL links updated from macrofit.com/signup → app.macrofit.com/signup

**Medium-term:**
8. Stripe tiered pricing implemented when ready to launch new pricing
9. Before/after transformation photos updated with member names and results
10. Mobile fixes applied to comparison table and hero pills
