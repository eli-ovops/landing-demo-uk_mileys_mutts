# Miley's Mutts — Independent Direction A Acceptance

Date: 2026-09-03 (Asia/Shanghai)  
Reviewer scope: independent, local-only, read-only review of the delivered Direction A files and a separately run local browser session. This record does not authorise deployment, public-link allocation, package creation, outreach, or sending.

## Decision

`CLIENT-SHOWABLE DEMO = FAIL — FIX P0/P1`

This is not a direction-level visual failure: the core composition, visual system and responsive page are viable. It is blocked by two P0 hard-gate failures below. The ten-item score is also below the threshold because the factual and no-JavaScript accessibility gates are not satisfied.

## Independent material inspected

- `index.html`, `styles.css`, `script.js`
- `PRE_CODE_DECISION.md`, including the authoritative 18-item closure and Direction A motion contract
- `docs/CUSTOMER_PUBLIC_INTELLIGENCE.md`, `docs/ASSET_INVENTORY.csv`, and `docs/QA_SELF_CHECK.md`
- Local browser URL: `http://127.0.0.1:4175/`; no login, form submission, external navigation or external write occurred.

## P0 — must fix

1. **No-JavaScript motion contract is false.**
   - Selector: `#hero::after` in `styles.css`.
   - Required contract: PRE-CODE says no-JavaScript must be complete **and static**; the only ambient drift is capability-gated progressive enhancement.
   - Independent result: JavaScript disabled at both 1440x900 and 390x844 left every `.motion-ready` visible (`opacity: 1`, `transform: none`), but `getComputedStyle(#hero, '::after')` returned `animationName: drift`, `animationPlayState: running`, with a changing transform. The CSS `@media (prefers-reduced-motion:no-preference)` starts this animation independently of JavaScript.
   - Fix requirement: make the ambient rule static by default and start it only after the same JavaScript capability gate used for `.motion-ready`; preserve static visible content for JavaScript-disabled and reduced-motion users.

2. **Research-to-Demo disposition and review attribution are incomplete/mislocated.**
   - Required contract: the 18-item closure in `PRE_CODE_DECISION.md` specifies F-008 through F-011 as actual customer-visible treatments with author/full date and named selectors; review statements must remain individually attributable.
   - `#room` has no planned `#room-owner-words` target and surfaces Kellie only. F-008 also requires Lorraine, 21 April 2026, as a separately attributable environment observation.
   - `#owner-noticed .mosaic` presents Liv, Gemma, Lorraine and Andrea Ryan only. It omits Kate, 14 April 2026 (F-009) and Rob Georgeson, 10 April 2026 (F-010), despite those being committed in the final disposition plan.
   - `#individual-visits article:nth-of-type(3)` labels a French Bulldog/19 February but does not identify Andrea Darley, whose review supplies that wash-and-pamper account. It then mentions Gemma's Labrador/nail-trim context without Gemma's 12 February 2026 date. This combines two review contexts without the required author/full-date attribution.
   - Fix requirement: either present every committed F-008 through F-011 account in the exact, individually attributed placement promised by PRE-CODE, or revise the authoritative disposition matrix and intelligence/asset ledger before implementation with a concrete, safe exclusion. Do not turn the omitted accounts into an aggregate claim, menu, guarantee or rating.

## P1 — should fix before repeat acceptance

1. **Header enquiry affordance is undersized on touch viewport.**
   - Selector: `header .cta`.
   - Independent 390px result: rendered height `24.8px`, with `min-height: auto`; other enquiry buttons are `49.8px` and telephone is `44px`.
   - Fix requirement: give the header enquiry link a clearly usable touch/focus target (at least 44px high, without weakening the header hierarchy) and retest keyboard focus visibility.

## Passed independent checks

| Gate | Result | Evidence |
| --- | --- | --- |
| Local/static boundary | PASS | Only three local concept images, local CSS/JS and mailto/tel links; no external scripts, form, booking, tracking or deployment action. |
| Desktop normal JS | PASS except P0 content/motion findings | 1440px viewport, `scrollWidth=1425` (scrollbar-adjusted; no horizontal overflow), full height 4974px, 3/3 images complete with positive natural widths, no console warnings/errors. |
| Mobile normal JS | PASS except P0 content/motion findings | 390px viewport, `scrollWidth=375` (scrollbar-adjusted; no horizontal overflow), full height 5892px, 3/3 images complete, no console warnings/errors. |
| Reduced motion | PASS | At desktop and mobile `matchMedia('(prefers-reduced-motion: reduce)')=true`; all `.motion-ready` elements remained `opacity:1` / `transform:none`, all animation names were `none`, and `#hero::after` had `animationName:none`. |
| Normal progressive reveal | PASS | After actual page scrolling, all six `.motion-ready` elements acquired `.motion-in`; no source `scroll` listener exists and entry animation is transform/opacity-only. |
| No-JS content visibility | PASS | At desktop and mobile, all six targets were `opacity:1` / `transform:none`; all 3 images complete. Ambient static requirement nevertheless fails as P0. |
| IDs, links and resources | PASS | Source has eight unique page IDs (`main` plus Hero through contact); three mailto links exactly target `[REDACTED_EMAIL]`; telephone target is `tel:+447928254056`; three local images loaded. |
| Internal-text/dynamic-claim gate | PASS | No customer-visible governance/UNKNOWN/HOLD/PASS/FAIL/AI/rights/research text, dynamic Trustpilot metrics, Emmi/teeth, price perception, NVQ, hours or insurance wording. No external media and no claim that concept images are premises, staff, customer dogs or results. |
| CTA and anti-template scan | PASS with P1 touch exception | Enquiry wording is consistently `Make an enquiry`; no em/en dash, numbered section labels, fake booking widget, star/rating, marquee, repeated eyebrow label, or generic review wall. Seven planned section families are materially expressed; the staggered visit modules and mixed proof mosaic avoid equal-card repetition. |

## Browser evidence produced by this reviewer

- `evidence/reviewer-direction-a-normal-desktop-full-20260903.png` — normal JS, 1440x900 viewport, full page.
- `evidence/reviewer-direction-a-normal-mobile-full-20260903.png` — normal JS, 390x844 viewport, full page.
- `evidence/reviewer-direction-a-nojs-desktop-full-20260903.png` and `evidence/reviewer-direction-a-nojs-mobile-full-20260903.png` — JavaScript-disabled full pages.
- `evidence/reviewer-direction-a-reduce-desktop-full-20260903.png` and `evidence/reviewer-direction-a-reduce-mobile-full-20260903.png` — `prefers-reduced-motion: reduce` full pages.

## Visual assessment

| Criterion | Score / 10 | Independent observation |
| --- | ---: | --- |
| 5-second business recognition | 8.8 | Business, Preston, one-to-one grooming and enquiry are clear in Hero. |
| Customer facts and specificity | 6.0 | Strong bounded base facts, but committed F-008–F-011 accounts are incompletely and sometimes ambiguously attributed. |
| Hero composition and first impression | 8.5 | Strong green/coral split, specific dog-care tone and a legible direct action. |
| Information hierarchy and long-page rhythm | 8.1 | Seven sections change rhythm naturally; the visit sequence remains editorial rather than a review export. |
| Typography and readability | 8.0 | Strong headline scale and hierarchy; small uppercase evidence labels remain readable at tested sizes. |
| Colour, material and overall coherence | 8.5 | Forest is dominant, coral is evidence-led, citron stays limited to action/focus. |
| Image quality and full-page visual narrative | 8.4 | All three concept images load and have distinct Hero/care/quiet-close roles. |
| Content completeness and Bottom 40% commercial progression | 8.2 | The lower page adds proof, quiet reassurance, address and direct enquiry; factual omissions prevent full credit. |
| 390px mobile completion | 7.7 | No overflow, deliberate stacking and crops, usable main CTA; header touch target is too small. |
| Motion reasonableness, accessibility and CTA completeness | 6.0 | Reduce Motion is correct and real observer reveals occur; no-JS ambient animation violates the written static fallback. |

**Average: 7.82 / 10.** Required acceptance threshold is every item >=7 and average >=8.0, plus all hard gates PASS. It is not met.

## Required evidence for re-review

1. Fresh normal/no-JS/reduced-motion screenshots at desktop and 390px after the ambient gate and all fact-attribution changes.
2. Runtime values showing no-JS `#hero::after` is static (`animationName: none` or equivalent non-animated state), while normal capability-enabled mode still demonstrates a real, bounded reveal/drift.
3. DOM/source trace from every F-001..F-011 and C/X item to exactly one disposition, including the complete author/date strings required for all displayed review accounts.
4. 390px keyboard/focus and touch-target measurement for `header .cta`, alongside zero overflow, loaded-image and console evidence.

## Non-blocking residual risk

All business claims remain public-profile/review bounded and should be revalidated if reused later. This acceptance remains strictly local-only, with no approval for deployment, sending, or customer-system action.

---

## Final independent re-review — 2026-09-03

**This section supersedes every acceptance conclusion above.** It was produced from a new local-browser run against the repaired files, not from Owner QA evidence.

### Final decision

`CLIENT-SHOWABLE DEMO = FAIL — FIX P0/P1`

**P0: none.** The two preceding P0 findings are closed:

- With JavaScript disabled at both 1440x900 and 390x844, the document root has no `motion-enabled` class; `#hero::after` has `content: none`, `animationName: none`, and `transform: none`. The sole `.motion-ready` Hero target remains fully visible (`opacity: 1`, `transform: none`).
- With `prefers-reduced-motion: reduce` at both viewports, the media query matched, root motion was not enabled, the pseudo-element had `content: none` / `animationName: none` / `transform: none`, and the visible content stayed static.
- Normal mode independently demonstrated a real bounded enhancement: root class `motion-enabled`, Hero `.motion-ready.motion-in`, and running transform-only `drift` on `#hero::after`; source contains no scroll listener. Header CTA now measures 44px high at 390px and receives a visible 3px citron `:focus-visible` outline.
- `#room-owner-words` now contains Lorraine, 21 April 2026, alongside Kellie, 18 April 2026. Outcome proof visibly carries Kate 14 April, Liv 16 April and Gemma 12 February. Return/referral proof visibly carries Lorraine 21 April, Andrea Ryan 15 April and Rob Georgeson 10 April. Individual-visit accounts are now separate cards for Grace/Cooper 10 April, Andrea Darley/French Bulldog 19 February, and Gemma/Labrador 12 February; they are framed as customer accounts, not a menu or guarantee.

**P1 — must fix before a new independent acceptance:**

1. **The proof mosaic is now a review wall, contrary to the locked anti-template condition.**
   - Selector: `#owner-noticed .mosaic > blockquote`.
   - Independent visual evidence: desktop renders six same-size, same-dark-background quote cells in a regular 2x3 grid; 390px collapses them into six same-style consecutive cards. The PRE-CODE requires an outcome mosaic with mixed quote scale/rule lines and explicitly forbids a review-wall treatment.
   - Fix requirement: retain the exact authors/dates and factual boundaries, but recompose this section as an editorial outcome mosaic with materially varied hierarchy/scale and non-repetitive evidence treatments. Do not hide or aggregate the newly restored accounts, turn them into ratings, or reuse an equal-card grid at mobile.

### Final independent runtime evidence

| Mode | 1440x900 | 390x844 | Result |
| --- | --- | --- | --- |
| Normal JavaScript | width 1440, scrollWidth 1425, full height 4826; 3/3 images complete; root `motion-enabled`; Hero reveal and drift active | width 390, scrollWidth 375, full height 5934; 3/3 images complete; header CTA 44px and visible keyboard focus | PASS |
| JavaScript disabled | width 1440, scrollWidth 1425, full height 4826; pseudo-element absent/static; content visible | width 390, scrollWidth 375, full height 5934; pseudo-element absent/static; content visible | PASS |
| Reduced motion | width 1440, scrollWidth 1425, full height 4826; media query true; pseudo-element absent/static | width 390, scrollWidth 375, full height 5934; media query true; pseudo-element absent/static | PASS |

Scrollbar-adjusted `scrollWidth` is below the corresponding `innerWidth` in every state, so no horizontal overflow occurred. All local images had positive natural widths. No console warnings/errors or `Runtime.exceptionThrown` page errors were observed. Source/DOM checks found unique source IDs, all mailto links targeting `[REDACTED_EMAIL]`, the `tel:+447928254056` link, no empty anchors, and no client-visible internal/governance text, dynamic Trustpilot figures, teeth/Emmi, price perception, NVQ, hours, insurance, external media or external scripts.

### Final reviewer screenshots

- `evidence/reviewer-final-normal-desktop-full-20260903.png`
- `evidence/reviewer-final-normal-mobile-full-20260903.png`
- `evidence/reviewer-final-nojs-desktop-full-20260903.png`
- `evidence/reviewer-final-nojs-mobile-full-20260903.png`
- `evidence/reviewer-final-reduce-desktop-full-20260903.png`
- `evidence/reviewer-final-reduce-mobile-full-20260903.png`

### Final visual score

| Criterion | Score / 10 |
| --- | ---: |
| 5-second business recognition | 8.8 |
| Customer facts and specificity | 8.7 |
| Hero composition and first impression | 8.5 |
| Information hierarchy and long-page rhythm | 7.2 |
| Typography and readability | 8.0 |
| Colour, material and overall coherence | 8.5 |
| Image quality and full-page visual narrative | 8.4 |
| Content completeness and Bottom 40% commercial progression | 8.5 |
| 390px mobile completion | 7.8 |
| Motion reasonableness, accessibility and CTA completeness | 8.3 |

**Average: 8.27 / 10.** Every score is >=7 and all fact/accessibility/runtime gates now pass, but the review-wall P1 keeps the hard anti-template gate open. The page remains strictly local-only: not deployed and not sent.

---

## Final mosaic re-review — 2026-09-03

**This section supersedes every earlier conclusion in this record.** It was generated through a fresh independent local-browser run after the mosaic revision.

## Decision

`CLIENT-SHOWABLE DEMO = PASS`

No P0 or P1 remains.

## Independent acceptance evidence

### Editorial mosaic and content boundary

- `#owner-noticed .mosaic` is materially diversified on desktop: Kate is a coral, 40px Georgia featured field spanning two rows; Liv is a white secondary outcome; Gemma is a transparent ruled secondary outcome; Lorraine, Andrea Ryan and Rob Georgeson are three compact, full-width editorial return/referral rows. Browser-computed geometry and materials differ for all intended groups; it is not a 2x3 equal-card grid.
- At 390px, Kate and Liv retain distinct featured/white-secondary treatments; Gemma plus the three return/referral statements are compact transparent ruled rows, rather than six same-style cards. Full page screenshots confirm the hierarchy remains visually legible and the content is not a review wall.
- All required customer words retain author and full date: Lorraine/Kellie in the room; Kate/Liv/Gemma outcomes; Lorraine/Andrea Ryan/Rob Georgeson return/referral; and Grace/Cooper, Andrea Darley/French Bulldog, Gemma/Labrador as separate visit accounts. The page continues to label these as individual customer words, not promises; it does not state an official menu, guarantee, rating or availability claim.

### Runtime matrix

| Mode | Desktop 1440x900 | Mobile 390x844 | Result |
| --- | --- | --- | --- |
| Normal JavaScript | width 1440, scrollWidth 1425, full height 4880; root `motion-enabled`; Hero `.motion-ready.motion-in`; transform-only `drift` active | width 390, scrollWidth 375, full height 5637; header CTA 44px; focus outline 3px citron | PASS |
| JavaScript disabled | width 1440, scrollWidth 1425, full height 4880; root class empty; Hero pseudo-element `content:none`, `animationName:none`, `transform:none`; content visible | width 390, scrollWidth 375, full height 5637; same static/visible contract | PASS |
| Reduced motion | width 1440, scrollWidth 1425, full height 4880; media query true; pseudo-element absent/static and animations none | width 390, scrollWidth 375, full height 5637; same static/visible contract | PASS |

All three local images completed with positive natural widths in every mode. The scrollbar-adjusted scrollWidth is below innerWidth in all six states, so no horizontal overflow occurred. Normal-mode console had zero warnings/errors; CDP runtime reported zero `Runtime.exceptionThrown` page errors. Source/DOM checks found one unique occurrence of every page ID, all three enquiry links targeting `mailto:[REDACTED_EMAIL]`, the public `tel:+447928254056` link, no empty anchors, no external scripts/media, and no customer-visible internal/governance, dynamic Trustpilot, Emmi/teeth, price, NVQ, hours or insurance claims.

### Reviewer screenshots

- `/Volumes/EXTERNAL/海外落地页/client_uk_mileys_mutts/demo_20260902/evidence/reviewer-final-mosaic-desktop-full-20260903.png`
- `/Volumes/EXTERNAL/海外落地页/client_uk_mileys_mutts/demo_20260902/evidence/reviewer-final-mosaic-mobile-full-20260903.png`

### Final visual score

| Criterion | Score / 10 |
| --- | ---: |
| 5-second business recognition | 8.9 |
| Customer facts and specificity | 9.0 |
| Hero composition and first impression | 8.5 |
| Information hierarchy and long-page rhythm | 8.6 |
| Typography and readability | 8.3 |
| Colour, material and overall coherence | 8.6 |
| Image quality and full-page visual narrative | 8.4 |
| Content completeness and Bottom 40% commercial progression | 8.6 |
| 390px mobile completion | 8.2 |
| Motion reasonableness, accessibility and CTA completeness | 8.5 |

**Average: 8.56 / 10.** Every item is >=7, the average is >=8.0, and all fact, provenance, accessibility, animation, overflow, console, client-visible-text and anti-template hard gates pass.

## Non-blocking risks and boundary

Public business-profile and review facts can change, so they require a fresh source check before a later reuse, deployment or outreach. This is a local-only acceptance of the static concept page: it does not authorise deployment, a public link, packaging, email or sending.
