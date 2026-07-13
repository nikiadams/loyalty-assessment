# Loyalty Audit Tool — Product Framework

**Purpose:** A tool that assesses how effective a brand's loyalty program is — structurally, experientially, and financially — and produces a clear scorecard + recommendations. Same spirit as the growth quiz: something a client (or your internal team) can walk through without it feeling like homework.

---

## 1. Steps to Evaluate a Program

### Step 1 — Intake & Discovery
Gather the basics before scoring anything.
- What is the program's stated goal? (retention, acquisition, data capture, margin protection)
- Who is the target member? (segments, tiers)
- What's the current structure? (points, tiers, subscription, hybrid)
- What data do they currently have access to?

### Step 2 — Program Structure Analysis
Look at the mechanics themselves.
- Earn structure (how points/rewards are accumulated)
- Burn structure (redemption options, friction to redeem)
- Tiering logic (is it motivating or confusing?)
- Expiration/lapsing rules

### Step 3 — Customer Experience Audit
Walk the program the way a real member would.
- Enrollment friction (how many steps, what data is required)
- Omnichannel presence (app, web, in-store, POS integration)
- Redemption friction (can they actually use what they earn easily?)
- Communication cadence (do members know their status/points?)

### Step 4 — Data & Personalization Review
- Is the program capturing first-party data effectively?
- Is that data being used to personalize offers, or just stored?
- Segmentation depth (basic tiers vs. behavioral micro-segments)

### Step 5 — Financial / ROI Analysis
- Program cost (rewards issued, redeemed, breakage)
- Incremental revenue or retention lift attributable to the program
- Cost per active member vs. value generated

### Step 6 — Competitive Benchmarking
- How does this compare to 3-5 direct competitors' programs?
- What's category-standard vs. differentiated?

### Step 7 — Technology Stack Review
- What platform(s) run the program today?
- Integration health (POS, CRM, app, email/SMS)
- Where are the manual workarounds/duct tape?

### Step 8 — Scoring & Recommendations
- Roll everything into a weighted scorecard
- Identify the 2-3 highest-leverage fixes
- Prioritize by effort vs. impact

---

## 2. Technology to Consider, Per Step

| Step | Tech to Consider |
|---|---|
| Intake & Discovery | Conversational form/quiz UI (LLM-driven, like the growth app) to make intake feel guided, not like a client questionnaire |
| Program Structure Analysis | Structured input forms + a rules-engine or scoring logic (could be a simple weighted rubric, doesn't need to be fancy) |
| CX Audit | Could include a "mystery shopper" style walkthrough script, or even screen-recording/journey-mapping tools if you want to get fancy later |
| Data & Personalization | Light integration/API checks if you get access to their systems; otherwise self-reported audit via structured questions |
| Financial/ROI | Simple calculator logic — inputs (program cost, redemption rate, member counts) → outputs (cost per member, estimated ROI) |
| Competitive Benchmarking | Could pull from a maintained internal database of known programs, or LLM-assisted research summaries per competitor |
| Tech Stack Review | Checklist-based (what platforms, what's integrated) — doesn't need heavy tech, just structured capture |
| Scoring & Output | Dashboard/report generator — this is where you'd want the polished, branded output |

**Note on complexity:** you don't need custom infra for most of this. A well-structured quiz/form (same engine as the growth app) can capture Steps 1, 2, 3, 4, and 7. Step 5 needs a lightweight calculator. Step 8 is really a report-generation layer on top of everything collected. The heaviest lift is just good question design, not backend engineering.

---

## 3. What Makes a Good Loyalty Program (the evaluation criteria)

Use these as your scoring categories — each could be weighted based on client priorities:

- **Value perception** — do members feel the rewards are worth earning, not token gestures?
- **Low friction** — easy to join, easy to earn, easy to redeem
- **Personalization** — offers/rewards feel relevant to the individual, not generic
- **Emotional engagement** — does it build affinity/identity, or is it purely transactional?
- **Tiering that motivates** — clear, achievable progression (not a wall you never reach)
- **Multi-channel accessibility** — works wherever the customer already is
- **Data utilization** — first-party data is actually acted on, not just collected
- **Measurable business impact** — retention, frequency, basket size lift is trackable
- **Brand alignment** — the program feels like the brand, not a bolted-on generic points system (especially relevant for something like Coke — playful, ownable, distinct)
- **Adaptability** — can evolve without a full rebuild every time strategy shifts

---

## 4. Final Output

Recommend a two-layer output:

**A. Scorecard (quantitative)**
- Score per category (from Section 3) on a defined scale
- Overall composite score
- Visual — could be a simple radar/spider chart so strengths/weaknesses are visible at a glance

**B. Narrative Report (qualitative)**
- Executive summary (2-3 sentences: where the program stands)
- Category-by-category findings with the "why" behind each score
- Gap analysis — what's missing vs. what "good" looks like
- Prioritized recommendations — ranked by effort vs. impact, not just a laundry list

**Optional (on-brand, in the spirit of the growth app's playfulness):**
Given the Coke-flavor gamification direction you're already using elsewhere, the audit output could lean into the same theme — e.g., the final scorecard "reveals" as a flavor profile or a branded badge, so it's shareable/fun internally even though the underlying content is a serious business audit. Keeps consistency across both tools if they'll be used together.

---

---

## 5. Detailed Assessment Criteria Library

This is modeled directly on the existing audit format already in use (the Avion iOS review) — each criterion gets an **ID**, **category/subcategory**, a **1-5 score**, a **status** (Found / Partial / Not Found), an **observation**, and a **recommended action**. That format is already working — the goal here is to expand it into a full library so the tool can run a consistent, repeatable review instead of ad hoc screen-by-screen notes.

**Per-criterion template:**
| Field | Description |
|---|---|
| ID | Category prefix + number (e.g., DX-02) |
| Category / Subcategory | High-level area + specific theme |
| Criterion | What "good" looks like, stated as a checkable claim |
| Score | 1-5 scale (1 = absent/poor, 5 = best-in-class) |
| Status | Found / Partial / Not Found |
| What was observed | Evidence from the screen/flow reviewed |
| Recommended action | Specific, actionable fix if score is low |

### DX — Digital Experience / Omnichannel
- **DX-01** Enrollment can be completed in under 2 minutes with minimal required fields
- **DX-02** Multiple earn channels are shown (in-store scan, mobile order, web order) *(existing example)*
- **DX-03** Member can view point balance and tier status without navigating more than 1 screen
- **DX-04** Redemption flow requires no more than 3 taps from browse to confirm
- **DX-05** Program is accessible and consistent across app, web, and in-store POS

### PS — Program Structure (Earn/Burn/Tiering)
- **PS-01** Earn rate is clearly stated and easy to calculate (no hidden multipliers)
- **PS-02** Redemption catalog offers a range of reward values (not just one high threshold)
- **PS-03** Tier thresholds and benefits are visible before the member has to click into a separate page
- **PS-04** Points expiration policy (if any) is clearly disclosed at or near the balance
- **PS-05** Tier progression feels achievable (not a single unreachable top tier)

### PZ — Personalization & Data
- **PZ-01** Offers shown are tailored to member behavior/history, not generic to all users
- **PZ-02** App requests/uses purchase history to personalize recommendations
- **PZ-03** Member profile allows preference-setting (categories, communication channel, etc.)

### CM — Communication & Engagement
- **CM-01** Member is notified of point balance changes in near-real-time
- **CM-02** Push/email notifications are relevant and not purely promotional spam
- **CM-03** Program includes some non-transactional engagement (challenges, bonus events, gamified elements)

### VL — Value Perception & Financial
- **VL-01** Reward value is competitive relative to category benchmarks (cost of points vs. cash value)
- **VL-02** Member can see "progress to next reward" without manual calculation
- **VL-03** Program cost structure is sustainable relative to redemption/breakage rates (internal metric, not customer-facing)

### BA — Brand Alignment
- **BA-01** Visual design, tone, and language feel distinctly on-brand (not a generic templated loyalty UI)
- **BA-02** Program name/theme reinforces brand identity rather than using generic "points/rewards" language
- **BA-03** Any gamification elements (badges, animations, streaks) reflect brand personality

---

### How this plugs into the framework above
- These criteria live mainly inside **Step 3 (CX Audit)** and **Step 2 (Program Structure Analysis)** from Section 1.
- The existing screenshot-based review approach (AI observing a screen against a criterion, scoring it, recommending a fix) is a strong model for **Steps 2, 3, and 4** — anywhere you have an actual UI to review.
- Steps 5 (Financial/ROI) and 6 (Competitive Benchmarking) aren't screen-reviewable — those need their own calculator/research inputs, not this criteria format.
- Recommend keeping the ID/category/score/status structure consistent across *all* criteria so the final output (Section 4) can roll everything into one unified scorecard, regardless of which step it came from.

---

---

## 6. Scoring Rubric Detail (What 1 vs. 3 vs. 5 Looks Like)

General scale, applied consistently across every criterion:

| Score | Meaning |
|---|---|
| **1** | Absent or actively broken — feature doesn't exist, or exists but fails/confuses |
| **2** | Present but poor — technically there, significant friction or gaps |
| **3** | Functional but basic — meets minimum expectation, nothing differentiated |
| **4** | Strong — well executed, minor polish opportunities only |
| **5** | Best-in-class — differentiated, seamless, category-leading |

Below is the specific rubric per criterion.

### DX — Digital Experience / Omnichannel

**DX-01 — Enrollment under 2 minutes, minimal fields**
- 1: Enrollment requires account creation on a separate site, or 6+ fields, or fails to complete
- 2: Completable but requires 5+ fields or multiple screens with unclear progress
- 3: Completable in-app in under 5 minutes with a reasonable number of fields
- 4: Under 2 minutes, minimal fields, clear progress indicator
- 5: Under 1 minute, social/SSO sign-in option, immediate confirmation of enrollment reward

**DX-02 — Multiple earn channels shown**
- 1: No earn channels indicated anywhere in the flow
- 2: One channel mentioned in text only, no visual cues
- 3: Two channels shown with basic icons/labels
- 4: Three or more channels shown with clear iconography
- 5: All relevant channels shown contextually at the point of earning, not just in a help page

**DX-03 — Balance/tier visible in ≤1 screen**
- 1: Requires 3+ taps or a search to find balance/tier
- 2: Requires 2 taps, buried in a menu
- 3: Visible within 1 tap from home
- 4: Visible directly on home/landing screen
- 5: Visible on home screen plus persistent across other screens (e.g., header badge)

**DX-04 — Redemption in ≤3 taps**
- 1: Redemption flow is broken, unclear, or exceeds 6 taps
- 2: 5-6 taps with unclear next steps
- 3: 4-5 taps, functional but not streamlined
- 4: 3 taps, clear CTA at each step
- 5: 1-2 taps, one-click redemption for common rewards

**DX-05 — Cross-channel consistency (app/web/in-store)**
- 1: Program only works in one channel; others show errors or no recognition
- 2: Works in 2 channels but with inconsistent balance/data sync
- 3: Works across channels with occasional sync delay
- 4: Consistent real-time sync across all channels
- 5: Consistent sync plus channel-specific optimizations (e.g., in-store quick-scan, web bulk-redeem)

### PS — Program Structure

**PS-01 — Earn rate clarity**
- 1: Earn rate not disclosed anywhere accessible to the member
- 2: Disclosed only in T&Cs/legal fine print
- 3: Disclosed in an FAQ or help section
- 4: Disclosed near the point of transaction
- 5: Shown in real time as a calculation (e.g., "you'll earn X points on this order")

**PS-02 — Redemption catalog range**
- 1: Single redemption option only
- 2: 2-3 options, all clustered at one price point
- 3: Moderate range (low/mid/high value options)
- 4: Wide range including experiential or partner rewards
- 5: Wide range plus personalized reward suggestions based on member history

**PS-03 — Tier visibility**
- 1: Tier info not available or requires contacting support
- 2: Available only in a separate document/PDF
- 3: Available on a dedicated tiers page, 2+ taps away
- 4: Summarized on the main loyalty screen, full detail 1 tap away
- 5: Fully visible on main screen including "X away from next tier" progress

**PS-04 — Expiration disclosure**
- 1: Points expire with no disclosure anywhere in-app
- 2: Disclosed only in T&Cs
- 3: Disclosed in account settings/FAQ
- 4: Disclosed near balance display
- 5: Active expiration countdown/warning shown to member before points lapse

**PS-05 — Tier achievability**
- 1: Top tier requires unrealistic spend/behavior for target audience
- 2: Large gaps between tiers with little mid-tier incentive
- 3: Reasonable gaps, but no visible path/momentum
- 4: Clear, achievable path with visible progress
- 5: Achievable path plus mechanisms to accelerate (bonus events, challenges)

### PZ — Personalization & Data

**PZ-01 — Tailored offers**
- 1: All members see identical generic offers
- 2: Minimal segmentation (e.g., new vs. existing member only)
- 3: Basic behavioral segmentation (category preference)
- 4: Offers reflect purchase history meaningfully
- 5: Offers dynamically adjust based on recent behavior and predicted preference

**PZ-02 — Purchase history usage**
- 1: No visible use of purchase history anywhere
- 2: History is viewable but not used to inform anything
- 3: History informs basic recommendations
- 4: History actively drives personalized offers/rewards
- 5: History drives offers and is transparently shown to the member ("because you bought X...")

**PZ-03 — Preference-setting**
- 1: No preference controls available
- 2: Limited to communication opt-in/out only
- 3: Category or interest preferences available
- 4: Granular preferences (channel, frequency, category) available
- 5: Preferences directly and visibly shape the member's experience going forward

### CM — Communication & Engagement

**CM-01 — Real-time balance notification**
- 1: No notification of balance changes
- 2: Notification delayed by 24+ hours
- 3: Notification within a few hours
- 4: Near-real-time notification
- 5: Real-time notification plus contextual next-step prompt (e.g., "you can now redeem X")

**CM-02 — Notification relevance**
- 1: Notifications are purely promotional/spam, unrelated to member activity
- 2: Mostly promotional with occasional relevant content
- 3: Mixed — some relevant, some generic
- 4: Mostly relevant to member's own activity/status
- 5: Highly relevant, personalized, and appropriately paced (not overwhelming)

**CM-03 — Non-transactional engagement**
- 1: No engagement mechanics beyond earn/redeem
- 2: One-off engagement feature, rarely updated
- 3: Occasional challenges/bonus events
- 4: Regular, varied engagement mechanics (challenges, streaks, surprise rewards)
- 5: Engagement mechanics are core to the experience and clearly tied to brand identity

### VL — Value Perception & Financial

**VL-01 — Competitive reward value**
- 1: Reward value significantly below category benchmark
- 2: Below benchmark
- 3: At benchmark/parity with competitors
- 4: Above benchmark
- 5: Best-in-category value, clearly differentiated

**VL-02 — Progress-to-reward visibility**
- 1: No indication of progress toward any reward
- 2: Requires manual calculation by the member
- 3: Basic progress bar available
- 4: Clear progress bar with next-reward context
- 5: Progress shown with proactive nudges as member nears a reward

**VL-03 — Program cost sustainability** *(internal/business-facing metric, not customer-facing UI)*
- 1: Breakage/redemption data unavailable or program running at a loss with no plan
- 2: Data available but shows unsustainable trend, no mitigation in place
- 3: Roughly break-even, no optimization effort
- 4: Healthy margin with some optimization in place
- 5: Actively monitored and optimized against clear financial targets

### BA — Brand Alignment

**BA-01 — On-brand visual/tone**
- 1: Generic template UI with no brand personality
- 2: Brand colors/logo present but tone/language feels generic
- 3: Consistent brand visual identity, generic copy/interactions
- 4: Strong brand visual and tonal consistency throughout
- 5: Program feels inseparable from brand identity — couldn't be mistaken for another brand's program

**BA-02 — Brand-reinforcing naming/theme**
- 1: Uses generic "points"/"rewards" language exclusively
- 2: Custom name exists but isn't used consistently
- 3: Custom program name used consistently, limited thematic depth
- 4: Custom name and theme reinforced throughout the experience
- 5: Naming/theme is memorable, ownable, and something members refer to by name

**BA-03 — Gamification reflects brand personality**
- 1: No gamification elements present
- 2: Generic gamification (points/badges) with no brand connection
- 3: Some brand-flavored gamification, inconsistently applied
- 4: Gamification consistently reflects brand personality
- 5: Gamification is distinctive, memorable, and drives organic word-of-mouth (similar to the "Coke flavor" concept discussed for the growth app)

---

---

## 7. New Member Journey & Lifecycle Communications (Follow-Ups / Next Steps)

This is the piece that's often missing from loyalty audits — most focus on the app/program mechanics themselves, but the **join journey** (what happens right after someone signs up) is where a lot of programs quietly lose members before they ever earn anything.

### Journey Stages to Evaluate

**Stage 1 — Welcome (Day 0)**
- Confirmation that enrollment succeeded
- Clear explanation of how the program works (earn/redeem basics)
- Sets expectation for what's coming next (e.g., "watch for your first bonus offer")

**Stage 2 — Early Engagement (Day 1-7)**
- Nudge toward first transaction/first earn if member hasn't acted yet
- Reinforcement of value (what they could redeem, tier preview)
- Introduction to any app features they haven't used yet (e.g., "did you know you can check your balance in-app?")

**Stage 3 — First Milestone**
- Acknowledgment of first earn or first redemption
- Positive reinforcement to build the habit loop

**Stage 4 — Ongoing Lifecycle**
- Tier upgrade congratulations
- Birthday/anniversary acknowledgment
- Point expiration warnings (ties back to PS-04)
- Periodic re-engagement if activity drops

**Stage 5 — Win-Back / Lapsed Member**
- Defined inactivity threshold (e.g., 60/90 days no activity)
- Win-back sequence with incentive to return
- Clear final message if member is at risk of losing points/status

### Channels to Evaluate Across the Journey
- **Email** — typically the most detailed explanation, good for the welcome/education layer
- **SMS/Text** — best for time-sensitive nudges (points about to expire, limited-time bonus) — should be short and used sparingly to avoid fatigue
- **Push notification** — real-time, in-the-moment (balance updates, redemption reminders)
- **In-app messaging** — persistent, non-intrusive reinforcement (banners, home screen callouts)

The strongest programs coordinate across these rather than duplicating the same message on every channel — e.g., email carries the "why," SMS carries the "act now."

### New Assessment Criteria — ON (Onboarding & Lifecycle Communications)

- **ON-01** Welcome message sent within 24 hours of enrollment, clearly explains program value
- **ON-02** Channels are coordinated (not sending the identical message via email + SMS + push simultaneously)
- **ON-03** First-earn or first-redemption nudge exists for members who haven't transacted yet
- **ON-04** Milestone messaging exists (tier upgrades, anniversaries, birthdays)
- **ON-05** Defined win-back sequence exists for lapsed/inactive members
- **ON-06** Point expiration warning is sent proactively before points lapse (not just disclosed passively — ties to PS-04)

### Scoring Rubric — ON

**ON-01 — Welcome message timing/clarity**
- 1: No welcome message sent
- 2: Sent, but generic/delayed (48+ hours) or doesn't explain the program
- 3: Sent within 24 hours, basic explanation of program
- 4: Sent within a few hours, clear and engaging explanation
- 5: Immediate, personalized, sets up a clear next action (e.g., first bonus challenge)

**ON-02 — Channel coordination**
- 1: Same message blasted across all channels simultaneously, no coordination
- 2: Some overlap/duplication, minimal sequencing
- 3: Channels used for distinct purposes but not tightly sequenced
- 4: Well-sequenced, each channel has a clear distinct role
- 5: Fully orchestrated journey — channel, timing, and content all coordinated around member behavior

**ON-03 — First-earn/redemption nudge**
- 1: No nudge exists; members who don't transact are never re-prompted
- 2: Generic reminder exists but isn't tailored to "haven't earned yet" status
- 3: Basic nudge exists for inactive new members
- 4: Nudge includes an incentive (bonus points, small reward) to drive first action
- 5: Nudge is personalized (based on known preferences) and timed intelligently

**ON-04 — Milestone messaging**
- 1: No milestone messaging of any kind
- 2: Only one type exists (e.g., tier upgrade only, nothing else)
- 3: Covers 2 milestone types (e.g., tier + birthday)
- 4: Covers most milestone types with reasonably personalized content
- 5: Comprehensive milestone coverage, each feeling distinct and celebratory rather than templated

**ON-05 — Win-back sequence**
- 1: No win-back sequence exists; lapsed members simply go silent
- 2: A single generic "we miss you" message, no incentive
- 3: Basic sequence with a defined inactivity trigger and one follow-up
- 4: Multi-touch sequence with escalating incentive
- 5: Multi-touch, personalized sequence with clear urgency (e.g., points expiring) and strong incentive to return

**ON-06 — Expiration warning proactivity**
- 1: No warning sent; points simply expire
- 2: Warning sent but too close to expiration to act (e.g., day-of)
- 3: Warning sent with reasonable notice (1-2 weeks)
- 4: Warning sent with enough notice plus a clear CTA to use points
- 5: Multiple staged warnings with an easy one-tap path to redeem before expiration

### Where this fits in the framework
This slots in as its own step between **Step 3 (CX Audit)** and **Step 4 (Data & Personalization)** in Section 1 — call it **Step 3.5 — Lifecycle Communications Audit**. It also feeds the same final scorecard (Section 4) as its own category, alongside DX, PS, PZ, CM, VL, and BA.

---

## Open questions to resolve before building
- Who is the intended user of this tool — your internal team doing the audit, or the client self-assessing?
- Does this need to integrate with any real client data, or is it self-reported input for now (like the growth quiz)?
- Should scoring weights be fixed, or adjustable per client/category?
