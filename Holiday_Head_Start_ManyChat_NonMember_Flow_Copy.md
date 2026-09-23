# Holiday Head Start Challenge: ManyChat Non-Member Flow

**Purpose:** Turn an Instagram or Facebook Messenger conversation from a not-yet-member into a qualified visit to the dedicated MacroFit conversion page. This is not a Holiday Head Start registration path. The full challenge is reserved for active MacroFit members.

**Campaign:** Holiday Head Start Challenge  
**Tagline:** Results Before Resolutions  
**Challenge dates:** October 19–November 29, 2026  
**All dates and campaign messaging:** Central Time

## What changes from the current Summer flow

The existing non-member branch asks for a first name, phone number, and email address, then offers a Summer Lock In code and directs the person to a generic MacroFit checkout. Replace that entire sequence. A non-member should not have to submit contact details in ManyChat before she understands MacroFit, and the branch should not imply that a Holiday challenge spot is available before membership.

Remove the following steps from the **No, I’m interested** branch:

1. The first-name capture message.
2. The phone-number capture message.
3. The email capture message.
4. The Summer Lock In offer/code message.
5. The old `Lockin Interest Nonmember` action.

Do **not** collect a phone number or imply future text outreach in this branch. Challenge and marketing SMS consent must be captured separately and explicitly in GoHighLevel.

## Recommended visual flow

```text
"No, I’m interested" selected
        ↓
Optional action: Add ManyChat-only interest tag
        ↓
Message: warm Holiday / MacroFit sales bridge + HHS15 offer
        ↓
Button: Explore MacroFit     → prospect page
Button: See Member Options   → pricing section of prospect page
        ↓
End
```

The existing **Yes, I’m a member** branch remains separate. It continues to send current MacroFitters to the member registration route; it must not be merged into this prospect branch.

## Exact ManyChat setup

### 1. Replace the old action

**Location:** Immediately after the person selects **“No, I’m interested.”**

| Setting | Value |
|---|---|
| Action | **Add Tag** |
| ManyChat tag | `HHS 2026 | Interest | Not a Member` |
| Purpose | Internal ManyChat reporting only: count people who expressed Holiday Head Start interest but were not current MacroFitters. |
| Important restriction | Do **not** use this tag to trigger GoHighLevel challenge email, SMS, or registration workflows. Do not sync it as a paid-member tag. |

### 2. Replace the four contact-collection/code cards with one message

**Card name:** `HHS Non-Member — MacroFit Plan Bridge`

> This is actually a really good time to start. You do not have to wait for January to get started on your goals.  
>  
> MacroFit gives you a personalized plan, flexible meals, grocery lists, restaurant options, and support that fits real life. When you become a MacroFitter, Holiday Head Start is included for you.  
>  
> **Use code HHS15 for $15 off your first month when you join.**  
>  
> Get your plan in place now, and once you are officially a member, we will send you the quick link to save your Holiday Head Start spot.

Use only the two buttons below. Do not use a countdown or imply that challenge access is available before the person becomes a member. **Before activation, verify that `HHS15` is active in the MacroFit checkout system and applies $15 off the first month.**

| Button label | Destination | Purpose |
|---|---|---|
| **Explore MacroFit** | `https://macrofitprogram.com/holiday-head-start/join?utm_source=manychat&utm_medium=instagram-dm&utm_campaign=holiday-head-start-2026&utm_content=non-member-learn` | Opens the full focused MacroFit conversion page, including benefits, member proof, and the transparent Holiday handoff. |
| **See Membership Options** | `https://macrofitprogram.com/holiday-head-start/join?utm_source=manychat&utm_medium=instagram-dm&utm_campaign=holiday-head-start-2026&utm_content=non-member-ready#membership` | Sends a high-intent person directly to the pricing section of the same conversion page. |

For the Facebook Messenger version, keep the message unchanged and replace only `utm_medium=instagram-dm` with `utm_medium=facebook-messenger`.

### 3. End the ManyChat branch after the button click

Do not request an email or mobile number after either button. The prospect page and MacroFit checkout are the appropriate next experience. Once a payment is completed, the existing Stripe → Zapier → GoHighLevel `macrofitter` tag path identifies the active member. The separate new-member Holiday invitation workflow can then send the short challenge registration link when that workflow is approved and activated.

## Experience the prospect sees after the click

1. The focused **Holiday Head Start prospect page** explains that the challenge is an included member benefit, not a separate purchase.
2. The page provides MacroFit proof, benefits, and the 6-month, 3-month, and monthly membership choices.
3. The member completes MacroFit enrollment.
4. Stripe → Zapier applies the existing `macrofitter` tag in GoHighLevel.
5. When approved for launch, the separate **HHS 2026 — New Member Invitation** workflow waits 15 minutes and sends the short Holiday registration link.
6. Only after the member submits that form and selects the member answer does GoHighLevel apply `HHS-2026-Registered` and permit Holiday-only communication.

## QA checklist

Test both channels on a real phone before publishing.

| Test | Expected outcome |
|---|---|
| Instagram DM non-member selection | Adds `HHS 2026 | Interest | Not a Member` in ManyChat only; does not create Holiday challenge enrollment in GHL. |
| **Explore MacroFit** | Opens `/holiday-head-start/join` with the exact Instagram UTM parameters. |
| **See Membership Options** | Opens the same page at `#membership` with `utm_content=non-member-ready`. |
| Facebook Messenger version | Same copy and behavior, with `utm_medium=facebook-messenger`. |
| Existing member selection | Still routes only to the current-member registration experience, not the prospect page. |
| Purchase after click | Uses the existing Stripe → Zapier → GHL `macrofitter` process; no Holiday email sends until the invitation workflow is deliberately published. |

## Guardrails

- No Summer Lock In wording, dates, promo codes, or tags remain in the Holiday flow.
- Do not label a prospect “registered” or “enrolled” merely because she opened the page or chose a button.
- Do not auto-add a non-member to the paid-member Holiday list.
- Do not activate the new-member invitation workflow until the core onboarding email sequence and the end-to-end Stripe/Zapier/GHL test are approved.
- Keep the current-member path and non-member path visibly separate in ManyChat.
- As of September 23, 2026, the revised message and the two buttons are saved in the **stopped** Holiday Head Start Challenge automation. The existing comment trigger remains off; do not activate it until the checkout code and both mobile paths pass QA.
