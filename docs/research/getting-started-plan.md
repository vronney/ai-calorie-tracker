# CAL AI Rebuild — Initial Steps to Get Started

This is the **practical first-start plan** for week 1–2.

## 1) Lock scope and success criteria (Day 1)
- Define MVP scope: manual entry, barcode scan, daily macros dashboard, weekly trend.
- Define target UX metric: meal log in < 20 seconds.
- Define data quality metric: >= 90% user-accepted logs without edits for barcode flows.
- Define launch platform: start with web PWA first, then native wrapper if needed.

## 2) Create product spec + user flows (Day 1–2)
Document these flows with wireframes:
- Onboarding + goal setup
- Log meal via barcode
- Log meal manually
- Edit meal macros/portion
- Daily summary + weekly trend

Deliverable: `docs/product/mvp-spec.md` (or equivalent).

## 3) Stand up the monorepo and toolchain (Day 2)
- Create Next.js app with TypeScript and App Router.
- Add Tailwind + shadcn/ui for UI primitives.
- Add Storybook for component development.
- Add TanStack Query + Zustand baseline setup.
- Add lint/format/husky pre-commit standards.

Deliverable: a clean bootstrapped repo with CI passing.

## 4) Provision infrastructure (Day 2–3)
- PostgreSQL database (managed preferred).
- Object storage bucket for meal images.
- Okta tenant/app integration for auth.
- Environment config strategy (`.env.local`, secrets in CI/CD).

Deliverable: dev/staging environments with working login.

## 5) Design data model + migrations (Day 3)
Create first schema and migration set for:
- `users`, `goals`
- `meal_entries`, `meal_entry_items`
- `food_items`, `branded_foods`
- `images`, `daily_rollups`

Deliverable: reproducible migrations and seed data.

## 6) Build vertical slice #1: manual logging (Day 4–5)
- Create add-meal form and quick-add macros.
- Persist to DB.
- Show daily totals and macro progress.
- Track event telemetry for “time-to-log.”

Deliverable: end-to-end manual logging flow in staging.

## 7) Build vertical slice #2: barcode logging (Week 2)
- Add barcode scan UI + API endpoint.
- Resolve food by barcode from branded food table.
- Add correction/edit UI when match is wrong.
- Store corrections for future ranking.

Deliverable: reliable packaged-food logging path.

## 8) Add analytics baseline (Week 2)
- Daily calories/macros
- 7-day trend chart
- Adherence % vs goals

Deliverable: dashboard that supports retention loop.

## 9) Ship guardrails from day one
- Clear pricing before full signup/paywall.
- Explicit confidence/source indicators for AI-generated nutrition.
- Audit log for edits and data provenance.

## 10) Define “ready for AI photo logging” gate
Only start photo AI after:
- Manual + barcode flows are stable
- Correction UX is fast
- Baseline retention is measured

Then introduce camera pipeline with human-editable itemization.

---

## Suggested first tickets (copy/paste into tracker)
1. Initialize Next.js + Tailwind + shadcn + Storybook.
2. Configure Postgres connection and migration tool.
3. Implement Okta auth with protected routes.
4. Build `CreateMealEntry` API + form UI.
5. Build daily macro summary cards.
6. Add barcode scan endpoint and lookup table.
7. Add correction modal for serving size + macros.
8. Add weekly trends chart.
9. Add telemetry events for log completion latency.
10. Add seed script for test foods + branded barcodes.


## Premortem companion
For failure-mode planning and mitigations, see: `docs/research/premortem-no-signups-6-months.md`.
