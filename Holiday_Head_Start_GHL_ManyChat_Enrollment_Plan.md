# Holiday Head Start Challenge: GoHighLevel and ManyChat Enrollment Plan

**Campaign:** Holiday Head Start Challenge  
**Tagline:** Results Before Resolutions  
**Challenge dates:** Monday, October 19 through Sunday, November 29, 2026  
**Primary audience:** Current paid MacroFit members  
**All campaign dates and message times:** Central Time

## Recommended enrollment model

The cleanest approach is to make **GoHighLevel the single system of record for challenge registration**. The public MacroFit landing page at `macrofitprogram.com/holiday-head-start` will host the branded campaign explanation and embed the official GoHighLevel registration form. GoHighLevel will hold the participant status, consent records, tags, workflow entry, and reporting. ManyChat will operate as a short, helpful direct-message guide: it gives interested people the details they need, answers the first membership question, and sends them to the official registration page when they are ready.

This avoids duplicate lists, keeps all consent captured in one form, prevents people who merely download the public companion app from entering member-only communications, and gives MacroFit one dependable participant segment before the first pre-launch message is sent. HighLevel supports visual landing pages, opt-ins, contact capture, tags, and behavior-based workflows in one environment.[3]

> **Operating rule:** A public app download alone does not add a person to the Holiday Head Start communication workflow. A person must intentionally register, and member-only challenge communication must remain limited to paid members who pass the membership check.

## Enrollment approaches to choose from

| Approach | How it works | Tradeoffs | Cost | Setup complexity |
|---|---|---|---|---|
| **Landing-page-first — recommended** | A GoHighLevel page is the only registration method. ManyChat gives campaign information and then opens the page with a tracked link after a person messages a keyword. | Safest consent trail, cleanest reporting, and least integration risk. It introduces one extra tap from Instagram or Messenger. | Uses the existing GoHighLevel and ManyChat accounts. | Low |
| **Dual-entry enrollment** | The GoHighLevel page remains available, while ManyChat also collects registration data and creates or updates the GHL contact. | Removes one tap but adds consent, duplicate-record, integration, and testing complexity. | Existing tools, plus any required ManyChat paid feature or integration cost. | Medium |

**Recommendation:** Use the **landing-page-first model**. A member who comments on a post or sends a direct message receives helpful, concise challenge information in ManyChat. The conversation’s primary action is **Save My Spot**, which opens the official GHL page with a source-tracked link. GHL is then the only place where a person intentionally enrolls and is allowed into the member challenge workflow.

ManyChat’s External Request action can connect a conversation to another system via HTTPS, but it is only available on certain paid plans.[2] We do **not** need that integration for the recommended launch. A simple tracked landing-page link is more reliable for the first version and still shows that the registration originated in ManyChat.

## The enrollment journey

### 1. The GoHighLevel landing page

The public MacroFit page is the campaign’s canonical registration URL. It embeds the GoHighLevel form in the same sub-account that holds MacroFit contacts and workflows, so campaign registration data and automation remain in one place. Use that public URL in email, text, the Facebook group, Instagram bio, organic posts, and ManyChat.

The page should lead with the campaign name, the **Results Before Resolutions** tagline, and the October 19–November 29 challenge window. It should plainly say that the challenge is designed for current paid MacroFit members. A short benefit section should describe what participants receive once the final content plan is approved, such as the companion app, challenge prompts, accountability, community participation, and scheduled support.

The registration form should request only what is needed to identify the member and deliver messages:

- First name
- Email address
- Mobile number, if challenge SMS is part of the launch plan
- A required confirmation: “I am a current MacroFit member.”
- A separate, unchecked SMS consent field with the approved MacroFit disclosure language, if texting is used
- Optional source capture or hidden UTM fields for page, email, group, Instagram, and paid traffic attribution

The principal button should use a direct action such as **Save My Spot** or **Join Holiday Head Start**. The form confirmation should send the person to a dedicated thank-you page rather than simply displaying an inline success message.

### 2. The thank-you page

The thank-you page should confirm that the registration was received and tell members what happens next. Until the Holiday app is ready, it should not promise an immediate download. It can say that app-install information and challenge details will arrive before the October 19 start date.

The page should include a brief “what to do now” sequence: watch for the confirmation email, check that text messages are permitted if they opted in, and join the member community using the approved member-only link. It should also give a clear support contact for a member whose registration is not recognized.

A person who selects that they are **not** a current paid member should not be added to the paid-member challenge path. They should be sent to the direct conversion CTA: **Build My MacroFit Plan** → <https://macrofit.com/signup>. No challenge workflow should begin from an app download or from that redirect alone.

### 3. The ManyChat information and landing-page path

ManyChat should use the same branching structure that performed well for the Summer campaign. Start with Instagram direct messages, then duplicate the flow for Facebook Messenger if that remains an active campaign channel. The recommended trigger is a simple campaign keyword, **CHALLENGE**. A person can send the word in a DM, comment it on an approved Instagram post, or tap a story link that opens the conversation.

The first meaningful choice is **“Are you a current MacroFit member?”** The conversation is intentionally separate for the two audiences:

1. **Current MacroFitter path:** explain that Holiday Head Start is a 42-day, member-first accountability experience running October 19 through November 29. Share the approved benefits: the companion app, daily or weekly challenge support, scheduled encouragement, and community accountability. Then present a clear **Save My Spot** button that opens the tracked GHL registration page.
2. **Not-yet-a-member path:** respond warmly rather than treating the person as ineligible. Explain that the full Holiday Head Start member experience is reserved for paid MacroFitters, invite them to begin with a personalized nutrition plan, and route them to the focused prospect conversion page rather than direct checkout: **Explore MacroFit** → `https://macrofitprogram.com/holiday-head-start/join?utm_source=manychat&utm_medium=instagram-dm&utm_campaign=holiday-head-start-2026&utm_content=non-member-learn`. A high-intent second button, **See Member Options**, deep-links to the `#membership` section on that page. The saved message shows `HHS15` for $15 off the first month; verify that the code is active in checkout before activating the automation. Do not add this branch to the paid-member challenge workflow.
3. **Questions path:** offer short answers to the approved campaign FAQ, including the dates, the 42-day format, who it is for, what participants receive, and where the companion app fits. The final action returns current members to **Save My Spot** and non-members to **Build My MacroFit Plan**.

This means ManyChat does exactly what it did last time: it qualifies the person conversationally, gives the right information to each audience, and then routes them to the appropriate destination. GHL remains the sole challenge-registration destination for current members.

The ManyChat button should use the official landing-page URL with a source parameter such as `utm_source=manychat`, `utm_medium=instagram-dm`, and `utm_campaign=holiday-head-start-2026`. GHL can store those values in hidden fields or capture them in page analytics. Because the form is completed in GHL, the standard member check, email/SMS consent, confirmation, tags, and pre-launch workflow all behave exactly the same regardless of where a person first learned about the challenge.

### Duplicate-and-update implementation checklist

The Summer flow should be duplicated rather than rebuilt. Its two-branch conversation pattern is already familiar to the audience and is the right starting structure. Before publishing the duplicate, update the following items:

1. Rename the flow **Holiday Head Start Challenge — Interest** and leave the Summer version unchanged.
2. Change the trigger keyword and post-comment automation to **CHALLENGE** only for Holiday campaign posts.
3. Replace every Summer Lock In name, date, deadline, reward, and app reference with **Holiday Head Start Challenge**, **Results Before Resolutions**, and **October 19–November 29, 2026**.
4. Preserve the question that separates **current MacroFitters** from **not-yet-members**.
5. On the current-member branch, remove any old phone/email collection steps that were only needed for the former ManyChat registration. Replace the final action with **Save My Spot**, linking to the tracked GHL landing page.
6. On the not-yet-member branch, remove old first-name, phone, email, and direct-checkout cards. Replace them with a concise MacroFit sales bridge, the approved `HHS15` first-month offer (after checkout activation is confirmed), and two tracked buttons: **Explore MacroFit** and **See Member Options**, both pointing to the dedicated prospect conversion page.
7. Replace all old Lock In tags with Holiday-specific ManyChat-only tracking tags if desired. Use `HHS 2026 | Interest | Not a Member` for this branch. These tags indicate interest or source; they must not trigger member-only GHL communication or imply SMS consent.
8. Test both branches on a real mobile device, including each button, the landing-page source parameters, the GHL form submission, and the non-member signup link.

## GoHighLevel data design

### Contact fields

Use a small, standardized set of fields so that registration data remains usable after the challenge:

| Field | Purpose |
|---|---|
| Holiday Head Start 2026 registration status | Tracks Registered or Not a Member according to the selected form answer. |
| Holiday Head Start source | Captures GHL landing page, ManyChat/Instagram DM, Facebook Messenger, email, Facebook group, or another approved source. |
| Holiday Head Start SMS consent | Stores the response used for challenge text eligibility. |
| Membership verification result | Reserved for a future billing-based audit; it is not used by the initial Summer-style form-answer branch. |
| Registration timestamp | Records when the person intentionally registered. |

### Tags

Tags should be specific enough to report on the campaign but simple enough that the team can recognize them quickly:

- `HHS-2026-Registered`
- `HHS-2026-Not-a-Member`
- `HHS-2026-Source-Landing-Page`
- `HHS-2026-Source-ManyChat`
- `HHS-2026-SMS-Opted-In`

The initial workflow deliberately uses the member's form answer, **“Yes, I’m doing MacroFit now,”** as the branch gate. Existing membership or payment-status data can be added later as an audit layer, but it is not required for the current draft.

## GoHighLevel workflow structure

The workflow should be built as a short registration-and-verification workflow, separate from the actual challenge-content workflow. This separation keeps the enrollment process stable even if message content changes later.

| Workflow | Entry trigger | Core actions | Exit condition |
|---|---|---|
| **HHS 2026 — Registration and Verification** | Holiday Head Start landing-page form submission | Branch on the current-member form answer; apply a participant tag to the Yes branch and a non-member tag to the No branch. | Contact reaches `HHS-2026-Registered` or `HHS-2026-Not-a-Member`. |
| **HHS 2026 — Member Pre-Launch** | `HHS-2026-Registered` tag | Send only the approved registration confirmation, app-install instructions, and pre-launch reminders. | Ends at the October 19 activation time. |
| **HHS 2026 — Challenge Content** | `HHS-2026-Registered` tag plus the scheduled Central Time campaign start | Deliver approved email and SMS messages for active participants only. | Ends after November 29 and moves people to the approved post-challenge experience. |

The first workflow should branch as follows:

1. **Current MacroFitter answer:** add `HHS-2026-Registered`. This one tag is the member's Holiday Head Start participant tag.
2. **No or any other answer:** add `HHS-2026-Not-a-Member`. Do not apply the participant tag or enroll the contact in member-only communication. The landing page's direct **Build My MacroFit Plan** link remains the appropriate conversion path.

All time-delayed messages must be set and checked in **Central Time**. The workflow must be tested with both a future registration and a late registration to confirm that it never backfills or sends past-dated messages.

### Selected initial gate and draft workflow configuration

For this campaign, the user-selected initial eligibility signal is the registration-form answer **“Yes, I’m doing MacroFit now.”** This mirrors the Summer-style branch and is sufficient for the initial draft; the form answer is not a substitute for a future billing-based audit if that becomes available. Because the selected Yes branch itself is the registration event for current members, use a single participant tag—`HHS-2026-Registered`—rather than a separate `Registration-Requested` intermediate tag.

Build the following workflow as a **draft only**. It must not be published or allowed to send Holiday content until all email/SMS dates and the registration confirmation are approved:

| Step | Configuration |
|---|---|
| Workflow name | `HHS 2026 — Registration and Verification` |
| Entry trigger | **Form Submitted** → `Holiday Head Start 2026 Registration` (form ID `DGxYECQSEkBQEkicldtI`) |
| Branch condition | **Are you currently a Macrofit member?** equals **Yes, I’m doing Macrofit now** |
| Yes branch | Add `HHS-2026-Registered`; retain UTM/source fields for reporting; leave the participant in draft workflow status pending the approved confirmation message. |
| No branch | Add `HHS-2026-Not-a-Member`; do **not** apply a participant tag or enroll the contact in member-only communication. The public landing page already presents **Build My MacroFit Plan** as the appropriate destination. |
| Immediate messaging | None until the confirmation copy, sender identity, and launch schedule are approved. |
| Workflow status | **Draft.** Do not publish before a two-path test contact confirms the correct tags and zero member messaging for the No branch. |

### New-purchaser conversion handoff — live September 24, 2026

The prospect conversion page does **not** collect Holiday Head Start registration before a purchase. It sends a prospect to MacroFit enrollment first. A dedicated, published purchase bridge now recognizes the relevant paid MacroFit invoice, adds a Holiday-specific purchaser tag in GoHighLevel, and sends the invitation without relying on the general MacroFitter onboarding workflow.

| Component | Live configuration |
|---|---|
| Zapier bridge | **MacroFit Paid Invoice to GHL — Draft** is published as version `v1`. It uses **Stripe: New Invoice**, followed by **Filter by Zapier**. The filter requires `Lines Price Product` to exactly match `prod_V4xmMW8GTPYspe`, preventing unrelated paid invoices from entering this path. |
| GoHighLevel contact update | LeadConnector **Add/Update Contact** uses the Stripe customer email, sets **Mark as Lead** to `false`, adds `hhs-2026-new-purchaser`, and records source `Stripe Paid Purchase`. |
| Dedicated invitation tag | `hhs-2026-new-purchaser` was created in GHL with the description “Stripe-paid MacroFit purchaser; triggers the Holiday Head Start invitation.” |
| Invitation workflow | **`HHS 2026 — New Purchaser Invitation`** is published. It triggers when `hhs-2026-new-purchaser` is added, waits 15 minutes, then sends the approved purchaser invitation email. |
| Email | `holiday-head-start-new-member-invitation.html` is sent with subject **“You’re a MacroFitter—now save your Holiday Head Start spot.”** Its CTA is `https://macrofitprogram.com/holiday-head-start?utm_source=ghl&utm_medium=new-member-email&utm_campaign=holiday-head-start-2026`. |
| Registration outcome | The member completes the short Holiday form, selects **Yes, I’m doing MacroFit now**, and receives `HHS-2026-Registered`. Only then should challenge-specific emails or opted-in texts begin. |

This creates a clean, auditable path: **prospect page → paid invoice for the filtered MacroFit product → `hhs-2026-new-purchaser` → 15-minute wait → Holiday invitation → Holiday registration form → `HHS-2026-Registered`**. It does not activate, depend on, or change the separate general MacroFitter onboarding workflow.

> **Validation note:** The Zapier product filter passed its built-in test. The LeadConnector contact-action test was intentionally skipped because the available Stripe sample record was a real customer email; verify the first real qualifying purchase in Zapier Runs and the matching GHL contact before relying on it as evidence of end-to-end delivery.

## Tracking and reporting

The campaign should report the complete path from discovery to registration. The source tags and hidden page parameters will make it possible to compare landing-page registrations with ManyChat registrations.

The dashboard or saved GHL smart lists should show at least:

- Registrations by source
- Registered participants
- Contacts identifying as not current members
- SMS-consented participants
- Landing-page conversion rate
- ManyChat conversation-to-registration rate
- Duplicate-contact exceptions
- App-install clicks once the Holiday companion app is live

## Build order

1. **Audit last summer’s assets.** Locate the prior GHL funnel, form, thank-you page, contact tags, and workflow. We will clone what still works rather than rebuild the structure from scratch.
2. **Confirm eligibility data.** Identify the exact GHL record that proves active paid membership and decide how manual exceptions are handled.
3. **Build the GHL page and form.** Create the landing page, thank-you page, fields, consent language, source tags, and workflow shell.
4. **Build the membership gate.** Test verified member, unverified member, duplicate contact, and non-member paths using test contacts.
5. **Build the ManyChat information flow.** Set up the keyword entry, current-member versus not-yet-member split, short audience-specific messages, FAQ replies, a source-tracked GHL landing-page button for members, and the MacroFit signup button for non-members.
6. **Create the pre-launch messages.** Add only the approved registration confirmation and reminder messages; keep the content sequence separate until its schedule is final.
7. **Run end-to-end QA.** Test every entry point on mobile, validate source attribution and tag application, check SMS consent behavior, validate Central Time waits, and confirm that a public-app visitor cannot enter the member workflow without intentional registration and verification.
8. **Publish and monitor.** Publish the landing page, activate ManyChat after the page-link and source-attribution test passes, and monitor the `Needs Review` list daily during enrollment.

## Implementation status — September 23, 2026

The planned public landing page and core GoHighLevel assets have been created without changing the completed Summer Lock In campaign:

| Asset | Current state | Required next action |
|---|---|---|
| Canonical registration page | Public MacroFit route built at `macrofitprogram.com/holiday-head-start`; it contains the approved dates, member-first positioning, direct non-member CTA, a branded registration section, and UTM forwarding into the form. | Complete an end-to-end paid-purchase test and confirm the correct registration result. |
| GHL member funnel | `Holiday Head Start 2026 MEMBERS` was cloned from `Summer Lock In 2026 MEMBERS`. | Treat it as a preserved GHL staging copy; the public MacroFit page is the canonical campaign URL. |
| GHL registration form | `Holiday Head Start 2026 Registration` was cloned from the Summer Challenge form. Its form ID is `DGxYECQSEkBQEkicldtI`. The non-marketing SMS disclosure and confirmation/thank-you language now name Holiday Head Start Challenge. | Continue registration-path QA with member and non-member contacts. |
| Current cloned form fields | First name, last name, required phone, required email, a required current-member Yes/No question, non-marketing SMS consent, and marketing SMS consent. | Keep consent checkboxes unchecked; confirm whether phone remains required. Do not add form submitters to the participant path until paid membership is verified. |
| New-purchaser Holiday handoff | The branded purchaser invitation email is attached to the published `HHS 2026 — New Purchaser Invitation` workflow. Zapier v1 applies `hhs-2026-new-purchaser` only after the configured Stripe product filter passes, then the workflow waits 15 minutes before sending the registration link. | Verify the first live matching purchase in Zapier Runs and GHL contact history; this new path remains independent from the general MacroFitter onboarding workflow. |
| ManyChat non-member branch | The revised message, `Explore MacroFit` button, and `See Member Options` deep link are saved in the stopped **Holiday Head Start Challenge** automation. Both URLs preserve source tracking; the second is configured with `#membership`. | Confirm `HHS15` is active in checkout, add the optional ManyChat-only interest tag if desired, test Instagram and Facebook Messenger on mobile, then activate only when the campaign is ready. |

The public page forwards only `utm_source`, `utm_medium`, `utm_campaign`, `utm_content`, and `utm_term` to the embedded form. For the first ManyChat member button, use `https://macrofitprogram.com/holiday-head-start?utm_source=manychat&utm_medium=instagram-dm&utm_campaign=holiday-head-start-2026`.

## Decisions needed before build begins

The following four decisions determine the exact setup:

1. **Membership proof:** What existing GHL tag, pipeline stage, subscription field, or payment record reliably identifies a current paid MacroFit member?
2. **ManyChat channel:** Should the first live entry point be Instagram only, or should we launch Facebook Messenger at the same time?
3. **Texting:** Should challenge SMS be part of this enrollment flow? If yes, we need the exact approved consent language and the sending number/sub-account confirmation.
4. **Exception path:** When a person says they are paid but cannot be matched automatically, should the workflow create a manual-support task, send them to a form, or route them to a team member by text/email?

## Account access required for implementation

GoHighLevel browser access is connected and the Holiday form/funnel copies now exist in the MacroFit sub-account. ManyChat remains to be opened when the duplicated Holiday information flow is ready for its copy and destination-link update. The Summer Lock In form, funnel, and finished automation remain unchanged.

## References

[1]: https://help.gohighlevel.com/support/solutions/articles/48001158874-manychat-to-highlevel-integration "Manychat to HighLevel Integration"
[2]: https://help.manychat.com/hc/en-us/articles/14281285374364-Dev-Tools-External-request "Dev Tools: External request"
[3]: https://www.gohighlevel.com/no-code-website-builder "GoHighLevel No-Code Website Builder"
