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

## Open questions to resolve before building
- Who is the intended user of this tool — your internal team doing the audit, or the client self-assessing?
- Does this need to integrate with any real client data, or is it self-reported input for now (like the growth quiz)?
- Should scoring weights be fixed, or adjustable per client/category?
