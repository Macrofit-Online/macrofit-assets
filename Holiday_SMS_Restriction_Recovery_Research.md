# Holiday Head Start SMS Restriction Recovery Research

**Date checked:** October 20, 2026

## What the Day 1 report shows

The Day 1 Holiday Head Start SMS action attempted 77 contacts. The action reported 24.68% delivered and 75.32% failed, which equals **19 delivered** and **58 failed** contacts. The individual error displayed was:

> Your account has reached today's opt-out/error limit. Please review your messages and try again after 2026-10-20 09:05:12 America/New_York.

This is an **account-level sending restriction**, not evidence that the Day 1 message wording itself was rejected. The stated retry time has passed as of the diagnosis time.

## Restriction History verification

HighLevel Restriction History confirms that the Holiday Head Start lock was triggered by **delivery errors**, not recipient opt-outs:

- **Holiday Head Start — October 19, 2026:** warning at a 37.93% error rate, then temporary restriction at a **51.28% error rate** after **39 sent, 20 errors, 0 opt-outs**.
- **Summer Lock In — July 13, 2026:** warning at a 38.46% error rate, then temporary restriction at a **46.51% error rate** after **43 sent, 20 errors, 1 opt-out**.

The repeat pattern strongly indicates that the account-level restriction is reached at **20 delivery errors** in these campaign batches. It does **not** establish that the message copy caused the individual errors. The remaining root-cause task is to review the first 20 individual, pre-restriction failures for their carrier/number-level error codes, then audit sender/A2P status and number quality before another bulk SMS.

## HighLevel’s documented behavior

HighLevel identifies temporary SMS restrictions caused by high opt-out rates or high delivery-error rates. Its stated lockout thresholds are approximately **3% opt-outs** or **10% delivery errors**, after which SMS sending is locked for 24 hours. The Restriction History log identifies the specific reason and metrics.

HighLevel also states that a workflow can reach an SMS action while SMS is restricted, the SMS can fail, and **failed SMS actions are not automatically retried** after the restriction ends. Recovery therefore requires identifying the failed contacts, correcting the root cause, and deliberately resending or re-enrolling only the appropriate contacts.

## Safe recovery sequence

1. Open **Settings → Phone System → Advanced Settings → Restriction History** and record the exact restriction type, metrics, start/end time, and relevant error code(s).
2. Do not send a second bulk SMS until the restriction is clearly lifted and the root cause has been reviewed.
3. Review the Day 1 SMS failure list and isolate the 58 failed recipients; exclude anyone with SMS DND/STOP, invalid/non-mobile numbers, or an individual carrier failure.
4. Send one test text to a known valid, opted-in mobile number. Confirm delivery before any batch recovery.
5. Re-send the Day 1 SMS only to the eligible failed cohort. Do not resend to the 19 already delivered contacts.
6. Confirm sender identification and STOP/opt-out language are configured under **Settings → Phone System → Advanced Settings → SMS Compliance**.
7. Monitor the next workflow SMS action and check its Statistics/Execution Logs immediately after send time.

## Prevention rule for future drip messages

Before every scheduled broadcast-sized workflow SMS:

- Confirm the account is not restricted in Restriction History.
- Validate a test contact and test message.
- Confirm the actual account time zone and the scheduled Central Time equivalent.
- Use an eligible SMS cohort only: valid mobile numbers, affirmative consent, no SMS DND, and no known failed/filtered contacts.
- Build an email fallback for time-sensitive challenge messages.
- Review delivery statistics immediately after the send rather than assuming an action queued in the workflow will auto-retry.

## Sources

- HighLevel, [Track SMS Restriction History](https://help.gohighlevel.com/support/solutions/articles/155000003568-track-sms-restriction-history)
- HighLevel, [LC Phone Messaging Policy](https://help.gohighlevel.com/support/solutions/articles/48001213941-lc-phone-messaging-policy)
- HighLevel, [Troubleshooting SMS Delivery Issues](https://help.gohighlevel.com/support/solutions/articles/48000981696-troubleshooting-sms-delivery-issues)
