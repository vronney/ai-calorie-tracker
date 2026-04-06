# Premortem: 6 Months After Launch, Signups Are Low

Date: April 6, 2026  
Scenario: The app launched, but user signups remain weak after six months.

## Executive summary
If signups are low after six months, the likely failure is **not one bug**. It is usually a compound failure across:
1. weak positioning,
2. low trust,
3. poor first-use experience,
4. unclear pricing,
5. distribution/channel mismatch,
6. slow product learning loops.

---

## What probably went wrong

## 1) We built “another calorie app,” not a must-try alternative
### Failure mode
- Messaging sounded generic: “AI calorie tracking with photo scan.”
- Users already have entrenched alternatives and did not perceive a compelling reason to switch.

### Observable signals
- Low CTR on landing-page hero.
- High bounce rate on homepage.
- Visitors do not reach onboarding.

### Mitigation
- Reposition around one core wedge: **"Fastest trustworthy logging"**.
- Show concrete comparison proof (“log meal in <20 sec with editable confidence”).
- Use social proof and before/after examples on landing page.

## 2) Trust gap: users didn’t believe calorie estimates
### Failure mode
- Photo outputs looked “magic” but were often wrong on mixed meals or portions.
- Correction UX required too many taps.

### Observable signals
- High edit rate after AI scan.
- Drop-off immediately after first scan.
- Support tickets mention “inaccurate” and “not reliable.”

### Mitigation
- Add confidence indicators + source labels (barcode, OCR, estimated).
- Optimize correction flow to under 10 seconds.
- Introduce calibration onboarding (common foods + serving habits).

## 3) Onboarding friction killed intent
### Failure mode
- Too many questions before value delivery.
- Required account/paywall before first successful log.

### Observable signals
- Onboarding completion < 40%.
- First-meal-log completion < 25%.

### Mitigation
- Let users complete one log before account creation.
- Reduce onboarding to 3 essential questions.
- Progressive profiling after first value moment.

## 4) Pricing/paywall strategy reduced conversions
### Failure mode
- Pricing shown too late, causing perceived bait-and-switch.
- No clear free-tier utility.

### Observable signals
- High drop when paywall appears.
- Low trial starts from high-intent sessions.

### Mitigation
- Show pricing transparently on site and in app before account lock.
- Offer meaningful free tier (manual + barcode + daily dashboard).
- Test weekly vs annual framing with clear refund terms.

## 5) Channel strategy failed (great product, wrong traffic)
### Failure mode
- Over-reliance on paid ads with weak creative differentiation.
- No durable channels (SEO, creator partnerships, referrals).

### Observable signals
- CAC too high relative to trial/paid conversion.
- Paid traffic quality low; poor D1 retention from ad cohorts.

### Mitigation
- Build channel mix: SEO program, micro-creators, UGC demos, referral loop.
- Create comparison pages and “switch-from-X” onboarding flows.
- Instrument per-channel activation metrics, not just installs.

## 6) We optimized model quality, not activation metrics
### Failure mode
- Team focused on AI benchmark metrics rather than user-perceived speed/accuracy.

### Observable signals
- Model iterations improve offline scores; signup and activation unchanged.

### Mitigation
- Set product north-star: **first successful log in under 60 seconds**.
- Track “time-to-log,” “edit burden,” and “day-1 repeat log rate.”
- Prioritize UX and reliability over incremental model gains.

## 7) Weak retention loop made acquisition ineffective
### Failure mode
- Users who signed up didn’t return, reducing word-of-mouth and referrals.

### Observable signals
- D1/D7 retention poor.
- Few users reach 7 logged days.

### Mitigation
- Daily streaks tied to meaningful outcomes (protein target, consistency score).
- Weekly review card with clear next action.
- Saved meals and one-tap relog for habit efficiency.

## 8) Technical reliability issues eroded confidence
### Failure mode
- Slow scans, crashes, and edge-case failures in barcode/OCR paths.

### Observable signals
- Elevated crash-free session issues.
- Latency spikes in scan pipeline.

### Mitigation
- SLOs for scan latency and success rates.
- Robust fallbacks: barcode -> OCR -> manual quick add.
- Queue/retry architecture with explicit failure states.

## 9) Privacy and health-data concerns were under-addressed
### Failure mode
- Users unsure what happens to meal photos and data.

### Observable signals
- Drop-off near permission prompts.
- Security/privacy objections in reviews.

### Mitigation
- Plain-language privacy panel in onboarding.
- Granular controls for image retention/deletion.
- Security trust badges and policy summaries.

---

## The likely root-cause chain
The most probable chain is:
1. Generic positioning ->
2. low-quality traffic + weak differentiation ->
3. trust issues on first scan ->
4. onboarding/paywall friction ->
5. low activation ->
6. low retention ->
7. no compounding growth.

---

## 30-day recovery plan

## Week 1: Instrument + diagnose
- Build activation funnel dashboard:
  - LP visit -> CTA click -> onboarding start -> first successful log -> account created -> trial start.
- Add event tracking for:
  - scan latency,
  - scan confidence,
  - correction taps,
  - paywall view and conversion.

## Week 2: Fix activation blockers
- Remove account requirement before first log.
- Reduce onboarding steps.
- Improve correction UX and confidence display.
- Add transparent pricing entry points.

## Week 3: Reposition and relaunch landing page
- New hero with clear wedge and proof.
- Add competitor comparison section.
- Launch 3 creative angles for paid + organic tests.

## Week 4: Channel and lifecycle experiments
- Referral incentive test.
- “7-day protein consistency” email/push lifecycle.
- Creator partnership pilot with tracked promo links.

---

## KPI targets (to know recovery is working)
- Landing page CTA CTR: +30%
- Onboarding completion: >60%
- First successful log: >45% of onboarding starts
- D1 retention: >35%
- D7 retention: >20%
- Trial start rate (from activated users): >15%

---

## Practical takeaway
If signups are weak at month 6, treat this as a **go-to-market + trust + activation** problem first, and an AI-model problem second. Win the first 60 seconds of user experience, then scale channels.
