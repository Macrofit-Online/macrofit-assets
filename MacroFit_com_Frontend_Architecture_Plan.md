# macrofit.com Frontend Architecture & Collaboration Plan

**Status:** Planning — pending dev team setup
**Last updated:** June 30, 2026

---

## Overview

The goal is to give Chelsea full creative and marketing control over `macrofit.com` — building landing pages, campaigns, and features with Manus — while the dev team maintains full control over the secure backend at `app.macrofit.com`. These two domains operate independently with no risk of one affecting the other.

---

## Domain Split

| Domain | Owner | Purpose |
|---|---|---|
| `macrofit.com` | Chelsea + Manus | Marketing site — landing pages, campaigns, Lock In App, calculator, etc. |
| `app.macrofit.com` | Dev team | Secure app — user login, member portal, subscriptions, data |

---

## Recommended Tech Stack

**Vercel + GitHub + Next.js**

- **GitHub** — single source of truth for all code; Manus pushes branches, team reviews and merges
- **Vercel** — auto-deploys every branch as a unique preview URL; production only deploys on merge to `main`
- **Next.js (React)** — industry-standard framework for marketing sites; familiar to most dev teams, flexible for future dynamic features, native Vercel integration

---

## Collaboration Workflow

```
Manus builds → pushes to GitHub branch
       ↓
Vercel auto-generates a preview URL (staging)
e.g. macrofit-git-feature-xyz.vercel.app
       ↓
Chelsea + dev team review the preview link
       ↓
Approve → merge to main → Vercel deploys to macrofit.com
```

Chelsea approves and merges. The dev team reviews PRs and controls what reaches production. Manus never pushes directly to `main`.

---

## Staging vs. Production

| Environment | How it works |
|---|---|
| **Preview (staging)** | Every branch or PR gets a unique URL automatically — share with team to review before merging |
| **Production** | Only deploys when `main` branch is merged — `macrofit.com` stays stable |

Optional: point `staging.macrofit.com` at the `staging` branch for a permanent staging URL.

---

## One-Time Setup (Dev Team Action Items)

1. **Create GitHub repo** — e.g. `macrofit-org/macrofit-site` (or under Chelsea's account)
2. **Connect repo to Vercel** — free at vercel.com; link the GitHub repo
3. **Point `macrofit.com` DNS to Vercel** — add CNAME record in domain registrar (Vercel provides step-by-step instructions)
4. **Set branch protection on `main`** — require PR review before anything reaches production
5. **Share repo URL with Manus** — Manus pushes feature branches; Chelsea or dev team merges to deploy

---

## What Manus Builds

The `macrofit.com` site is a **static marketing frontend** — no database, no server to manage. All secure functionality (user accounts, payments, member data) lives on `app.macrofit.com` under the dev team's control.

Manus builds:
- Landing pages and campaign pages
- The Lock In App and future challenge apps
- The Macro Points calculator and other lead-gen tools
- Seasonal promotions and content pages

---

## Decision Needed

Before setup begins, confirm the preferred framework with the dev team:

| Option | Best for |
|---|---|
| **Next.js (React)** | Recommended — flexible, scalable, native Vercel support, familiar to most dev teams |
| **Astro** | Fastest static output, great for content-heavy pages |
| **Plain HTML/CSS/JS** | Maximum simplicity, no build step, easiest for any team member to edit |

**Recommendation: Next.js on Vercel** — most common, most flexible, easiest to grow with.
