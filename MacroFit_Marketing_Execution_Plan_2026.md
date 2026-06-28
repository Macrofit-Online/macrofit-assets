# MacroFit Marketing Execution Plan: Awareness & Sales Roadmap

**Prepared by:** Manus AI (Acting Marketing Director)  
**Prepared for:** Chelsea Brynn, MacroFit  
**Date:** June 28, 2026  

---

## 1. Executive Summary & Strategic Positioning

MacroFit is positioned not as a conventional, punishment-driven fitness brand, but as an **adaptive, behavior-change nutrition system** that simplifies food decisions and responds to real life.[1] The core differentiator is that MacroFit answers the question most nutrition apps do not: *"What should I do next?"*[2] 

To drive awareness and sales, our marketing execution will shift from feature-led messaging (macros, meal plans, recipes) to decision-support messaging (start, check in, adjust, continue).[2] Our campaigns will target four distinct personas (Alex, Dan, Michelle, and Chris) by addressing their specific pain points: decision fatigue, health urgency, changing life stages, and tracking inefficiency.[1]

---

## 2. Funnel & Landing Page Optimization

The current funnel structure includes the main marketing site (`macrofitprogram.com`) and GoHighLevel (GHL) funnel pages (`join.macrofitprogram.com`).[3] To maximize conversions, we will execute the following updates:

### Immediate Sales Page Updates
| Action Item | Strategic Purpose | Priority |
|---|---|---|
| **Update Hero Copy** | Shift from generic fitness messaging to: *"Nutrition guidance that adjusts with you. MacroFit helps you know what to do next with your food, week after week."*[2] | High |
| **Add "Why 24+ Weeks" Section** | Frame the 24-week commitment as a minimum runway for sustainable change (dieting, reversing, stabilizing), not an expiration date.[2] | High |
| **Add Comparison Matrix** | Visually contrast MacroFit (adaptive system) against static meal PDFs, macro calculators, and tracking apps.[2] | High |
| **Mobile UX Fixes** | Wrap feature pills in the hero section and add horizontal scrolling to the comparison table on small screens.[3] | Medium |

### Tech & Tracking Requirements
To properly measure funnel performance, the following developer tasks must be completed:
1. **Facebook Pixel Installation:** Add the base code to the PHP layout and configure Purchase/Lead events.[3]
2. **Stripe Metadata Configuration:** Pass `plan_type` and `start_date` to Stripe for cohort tracking.[3]
3. **GHL Legal Text Update:** Change the consent checkbox on the funnel page from "Summer Shred 2026" to "Summer Lock In 2026."[3]

---

## 3. Organic Content Strategy

Organic social media is our primary engine for building trust, lowering pressure, and demonstrating real-life fit. Content will be categorized into seven pillars, with a heavy emphasis on mindset shifts and practical relief.[1]

### Content Pillars & Execution
| Content Pillar | Execution Strategy | Persona Focus |
|---|---|---|
| **Make It Easier** | Showcase grocery lists, "cook once/eat twice" prep, and backup freezer meals. Emphasize that the mental load is handled. | Alex, Chris |
| **Real-Life Nutrition** | Normalize off-plan meals, vacations, and eating out. Show how MacroFit adapts to busy Tuesdays. | Michelle, Dan |
| **Mindset Shifts** | Reframe slow progress. Teach that consistency beats perfection and that users don't need to "earn" their food. | All Personas |
| **Community/Humor** | Use light, relatable humor (e.g., "The air fryer deserves employee of the month"). Normalize imperfect weeks.[1] | Alex, Social Audience |

### The "What Happens Next" Series
We will launch a recurring content series explaining the logic behind MacroFit's weekly adjustments. This makes the invisible value of the adaptive system visible to prospects:
*   *Why holding steady is sometimes the best adjustment.*
*   *Why your macros increased (Reverse Dieting explained).*
*   *How the plan adapts to breastfeeding and hormonal changes.*[2]

---

## 4. Paid Advertising Strategy

Paid ads will move away from generic "lose weight" hooks and instead target the specific emotional triggers of our four personas.[1]

### Campaign Angles by Persona
| Target Persona | Core Messaging Angle | Example Ad Hook |
|---|---|---|
| **Alex (Reluctant Planner)** | Mental-load relief, family-friendly meals, grocery lists done for you. | *"Healthy eating shouldn’t add another job to your day. The planning is handled."* |
| **Dan (Breaking Point)** | Health control, clarity, realistic sustainability without extreme fitness culture. | *"You don’t have to become a fitness person to take your health seriously."* |
| **Michelle (Adapting Body)** | Adapting to changing hormones/life stages, consistency without burnout. | *"If what used to work no longer fits your life, your plan should adapt with you."* |
| **Chris (Efficiency Seeker)** | Macro structure without manual tracking, reduced cognitive load. | *"Macro structure without the mental Tetris. Stay consistent without obsessing."* |

### Ad Creative Guidelines
*   **Avoid:** Manipulative before/after photos, body shaming, "summer body" rhetoric, and extreme fitness imagery.[1]
*   **Use:** Authentic testimonials highlighting ease, real-food examples, screenshots of the grocery list feature, and relatable lifestyle imagery.

---

## 5. Email Marketing & Onboarding Sequence

Email is critical for nurturing leads and reinforcing the value of the adaptive system post-purchase.[2] We will optimize the GoHighLevel sequences to improve retention and conversion.

### Pre-Purchase Nurture
*   **Abandoned Checkout:** Remind prospects they are investing in guided decision support, not just a static macro calculation.[2]
*   **Objection Handling:** Address the 24-week commitment, price vs. cheap apps, and how the system handles plateaus.[2]

### Post-Purchase Onboarding (GHL)
We will implement the planned GHL email sequence to set correct expectations:[3]
1.  **Welcome Email:** *"Your starting Macro Points are only the beginning. Your check-ins determine what happens next."*[2]
2.  **Day -5:** The 6-month cycle explainer (dieting, reversing, maintaining).[3]
3.  **Day -4:** Cooking for your family without making separate meals.[3]
4.  **Day -3:** Full "how it works" breakdown (Start, Follow, Check In, Adjust, Continue).
5.  **Week 1-2:** Fat loss vs. weight loss expectations.

### Weekly Check-In Reinforcement
To improve retention, we will implement post-check-in explanation copy inside the app/emails to explain *why* macros changed (or didn't change), reinforcing the value of the adaptive system.[2]

---

## 6. Testimonial & Social Proof Strategy

We will move beyond standard weight-loss testimonials and categorize social proof to align with our core messaging pillars.[1]

*   **Ease & Time-Saving:** Feature quotes about the grocery list and done-for-you planning (e.g., *"I'm able to enjoy my weeknights instead of being stuck in the kitchen."*).
*   **Real-Life Fit:** Highlight members who eat "fun" foods (e.g., *"If people can eat Little Debbie cakes and still lose weight... what a program!"*).
*   **Health Outcomes:** Use powerful stories of improved blood work and condition management (e.g., PCOS, breast cancer recovery), ensuring sensitivity and permission.
*   **Life Transitions:** Feature postpartum success stories to appeal to the Michelle persona.

---

## 7. Immediate Next Steps for the Marketing Director

To kick off this execution plan, I recommend we prioritize the following this week:
1.  **Developer Handoff:** Provide the Facebook Pixel ID and Stripe requirements to the dev team to ensure tracking is in place before scaling ads.[3]
2.  **Sales Page Updates:** Submit the copy updates (Hero, 24-Week section, Comparison Matrix) to Manus for the `macrofitprogram.com` site.[3]
3.  **GHL Sequence Completion:** Finalize and activate the remaining onboarding emails (Days -3, 0, and Weeks 1-2) in GoHighLevel.[3]
4.  **Content Batching:** Outline the first 4 weeks of organic social content based on the "What Happens Next" series and the persona-specific angles.[1]

---

**References:**
[1] MacroFit Marketing Content Strategy Reference (`MacroFit_Marketing_Content_Strategy_Reference.md`)
[2] MacroFit Adaptive Value Messaging Strategy (`MacroFit Adaptive Value Messaging Strategy.md`)
[3] MacroFit Tech Management Reference (`MacroFit Tech Management Reference.md`)
