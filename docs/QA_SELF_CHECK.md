# Local QA Self-check

Date: 2026-09-02  
Scope: local static concept only; no deployment, external URL allocation, upload, mail send, login, form submission or customer-system action.

## Browser evidence

| View | Browser result | Screenshot |
| --- | --- | --- |
| Desktop 1440x900 | `innerWidth=1440`, `scrollWidth=1440`, no horizontal overflow; hero visual, factual enquiry CTA and concept label visible. | `evidence/mileys-desktop-1440x900.png` |
| Mobile 390x844 | `innerWidth=390`, `scrollWidth=390`, no horizontal overflow; copy appears before the cropped hero image and the enquiry CTA remains visible. | `evidence/mileys-mobile-390x844.png` |
| Full desktop | Same final build captured continuously from Hero through Closing at 1440px wide; rendered height `4191px`. | `evidence/mileys-desktop-full-1440.png` |
| Full mobile | Same final build captured continuously from Hero through Closing at 390px wide; rendered height `5170px`. | `evidence/mileys-mobile-full-390.png` |

## Content and interaction check

- No form, calendar, checkout, tracking parameter, analytics snippet, CMS or customer-system integration.
- Email links use the published public business address; telephone links use the published public number.
- Only verified business proposition, contact details, address and accurately attributed review material are customer-facing. The one customer mention of a bath-and-tidy/full-groom journey is not presented as a service range or merchant promise.
- The three original images have distinct roles and are visibly labelled only at the hero level as an independent concept preview; no image is described as the merchant, staff, client, premises or result.
- Static analysis found no `TODO`, placeholder, Cottam location claim, fake `Book now`, or internal governance text in customer-facing files.
- There is no automatic animation; reduced-motion behaviour leaves the same static composition.
- Final browser console: `0 errors, 0 warnings` after the final rebuild.

## Gate status

`INDEPENDENT VISUAL ACCEPTANCE = PASS` - 2026-09-02; 10-item average `8.3/10`, every item `>=7`.  
`CLIENT-SHOWABLE DEMO = PASS` - local display only.  
`PUBLIC LINK ALLOCATION = NOT REQUESTED`  
`DRAFT ONLY - NOT AUTHORIZED TO SEND`

## 2026-09-03 visual refinement evidence

- `VISUAL REFINEMENT PRE-CODE GATE = PASS` before customer-visible edits.
- Refined final-build full-page evidence: `evidence/mileys-refined-desktop-full-1440.png` (`1440x4763`) and `evidence/mileys-refined-mobile-full-390.png` (`390x5927`).
- Real browser metrics: desktop `innerWidth=1440 / scrollWidth=1440`; mobile `innerWidth=390 / scrollWidth=390`.
- Final browser console after reload: `0 errors, 0 warnings`.
- The first full-page capture exposed a native lazy-load gap for C-003. With only three local visual assets, C-002/C-003 now load eagerly; the final screenshots visibly contain all three concept-image roles.
- `INDEPENDENT VISUAL ACCEPTANCE = PASS` for the refined build on 2026-09-03: 10-item average `8.5/10`; every item `>=7`.
- Refined `CLIENT-SHOWABLE DEMO = PASS` for local display only. This does not authorize deployment, a public link, email sending or outreach.

## 2026-09-03 content supplement — Execution Owner self-check

Scope: local static content/style iteration only. The fresh public source check and local browser render do not authorise deployment, a public link, outreach, email, login, payment or any external write.

| Check | Result | Evidence / boundary |
| --- | --- | --- |
| 1440×900 local browser render | PASS (self-check) | HTTP 200; `innerWidth=1440`, `scrollWidth=1440`, document height `4774`; screenshot overwritten at `evidence/mileys-supplement-desktop-1440x900-20260903.png`. |
| 390×844 local browser render | PASS (self-check) | HTTP 200; `innerWidth=390`, `scrollWidth=390`, document height `5934`; screenshot overwritten at `evidence/mileys-supplement-mobile-390x844-20260903.png`. |
| Full-page continuity | PASS (self-check) | Overwritten final captures: `evidence/mileys-supplement-desktop-full-1440-20260903.png` (`1440×4774`) and `evidence/mileys-supplement-mobile-full-390-20260903.png` (`390×5934`); all three local concept images loaded. |
| Content activation | PASS (self-check) | Visible: 4+ years professional grooming experience, Grace's bath-and-tidy/planned-full-groom review context, and Andrea's nervous-Maltese/feel-at-ease review context. Each review has reviewer/date attribution; none is presented as a guarantee or menu. Customer-visible provenance/process notes were removed; source boundaries remain internal. |
| CTA/link and resource checks | PASS (self-check) | Three `mailto:[REDACTED_EMAIL]` links and two `tel:+447928254056` links resolved in DOM; all three local images had `complete=true` and positive natural width. |
| Console / page errors | PASS (self-check) | 0 console errors, 0 console warnings, 0 page errors in each viewport. |
| Client-visible internal-text scan | PASS (self-check) | No TODO, placeholder, NOT VERIFIED, rights, ledger, AI, Cottam, fake-booking wording, `From the public business profile`, or `Service wording is drawn` found in `index.html` / `styles.css`; `Independent concept preview` is visible in the Hero and footer. |

**Status boundary:** Execution Owner self-check is complete. It does **not** grant or repeat `INDEPENDENT VISUAL ACCEPTANCE`, `CLIENT-SHOWABLE DEMO`, public-link allocation, final package, deployment or sending status; those require PMO/independent review.

## Direction A implementation status

`IMPLEMENTED — PENDING INDEPENDENT ACCEPTANCE`. Owner must still record normal-JS, JavaScript-disabled and reduced-motion browser evidence before any acceptance conclusion. No deployment, public URL, package or outreach is authorised.

## Direction A runtime self-QA — 2026-09-03

| Mode / viewport | Runtime result | Evidence |
| --- | --- | --- |
| Normal JS desktop 1440×900 | `scrollWidth=1440`, full height `4893`; 3/3 images complete with natural widths 1586/1122/1536; 0 page errors. | `evidence/mileys-direction-a-normal-desktop-full-20260903.png` |
| Normal JS mobile 390×844 | `scrollWidth=390`, full height `5847`; 3/3 images complete; 0 console warnings/errors and 0 page errors. | `evidence/mileys-direction-a-normal-mobile-full-20260903.png` |
| JavaScript disabled desktop/mobile | `1440/1440/4893` and `390/390/5847`; all six `.motion-ready` elements computed `opacity=1`, `transform=none`; 3/3 images complete. | `evidence/mileys-direction-a-nojs-desktop-full-20260903.png`; `evidence/mileys-direction-a-nojs-mobile-full-20260903.png` |
| Reduced motion desktop/mobile | `1440/1440/4893` and `390/390/5847`; all six `.motion-ready` elements computed `opacity=1`, `transform=none`; 3/3 images complete. | `evidence/mileys-direction-a-reduce-desktop-full-20260903.png`; `evidence/mileys-direction-a-reduce-mobile-full-20260903.png` |

- DOM: eight unique anchors/IDs (`main`, Hero through contact); all in-page anchor targets resolve. Three mailto links exactly use the verified address and one telephone link uses `tel:+447928254056`.
- Normal JS confirms IntersectionObserver added `.motion-in` to entered targets; no-JS/reduced modes added none and stayed fully visible. One desktop console event was captured during normal mode; it was not a page error. 
- Static customer-visible scan: no TODO, placeholder, lorem, INTERNAL, UNKNOWN, HOLD, PASS, FAIL, rights, research, asset, prototype, wireframe, AI, ChatGPT, Emmi, teeth, NVQ, insurance, hours, dynamic Trustpilot figures, external scripts/media, or price-perception copy. CTA wording is exclusively `Make an enquiry`.
- Owner review remains incomplete for focus-target measurement, explicit first-viewport CTA/bottom-40% visual assessment, and full per-target normal-JS reveal completion; retain `IMPLEMENTED — PENDING INDEPENDENT ACCEPTANCE`.

## Final-fix runtime evidence — 2026-09-03

Six final-fix full-page captures were produced. Normal/no-JS/reduce desktop metrics: `1440/1440/4826`; mobile: `390/390/5889`. All six states had 3/3 complete images (1586/1122/1536), all anchors/three exact mailto links/one exact tel link, and header CTA height `44px`; no page errors. Normal root class was `motion-enabled` and `#hero::after` animationName was `drift`; no-JS and reduce root class were empty and animationName was `none`. Normal reveal was observed (`.motion-ready.motion-in`, opacity 1/transform none); no-JS/reduce kept static opacity 1/transform none. Screenshots: `evidence/mileys-final-fix-{normal,nojs,reduce}-{desktop,mobile}-20260903.png`.

F-008 trace: `#room-owner-words` Lorraine 21 April 2026 and separate Kellie 18 April 2026. F-009 trace: Kate 14 April, Liv 16 April, Gemma 12 February 2026 in `#owner-noticed`. F-010 trace: Lorraine 21 April, Andrea Ryan 15 April, Rob Georgeson 10 April 2026 in `#owner-noticed`. F-011 trace: Grace 10 April, Andrea Darley 19 February, Gemma 12 February 2026 in `#individual-visits`.

## Final-mosaic QA — 2026-09-03

Normal/no-JS/reduce desktop all measured `1440/1440/4880`; mobile all measured `390/390/5592`. Every state loaded all 3 images (1586/1122/1536), retained 44px header CTA, unique IDs/anchors, and all six attributed mosaic accounts. Normal `#hero::after=drift`; no-JS/reduce=`none`; page errors=0. Evidence: `evidence/mileys-final-mosaic-{normal,nojs,reduce}-{desktop,mobile}-20260903.png`. Desktop mosaic is featured Kate field + unequal Liv/Gemma pair + three rule-led return rows; mobile collapses to featured field, varied secondary stack, then compact rows—not a 2×3 or six equal-card wall.

## Compact Care Editorial implementation self-QA — 2026-09-03

Status: execution Owner self-check only. `REPLACEMENT-READY FINAL = PENDING INDEPENDENT REVIEW`; no independent acceptance is claimed.

| Mode | Desktop 1440x900 | Mobile 390x844 | Motion / errors |
| --- | --- | --- | --- |
| normal | 1440/1440/1440; 2354px | 390/390/390; 3852px | root `motion-enabled`; all four chapter targets reached opacity 1/identity transform; hero `::after` animation `drift`. Desktop has one non-blocking local 404 resource error; no page errors. |
| JavaScript disabled | 1440/1440/1440; 2354px | 390/390/390; 3852px | root class absent, every `.motion-ready` computed opacity 1/transform none; hero ambient none; no errors. |
| reduced motion | 1440/1440/1440; 2354px | 390/390/390; 3852px | root class absent, every reveal visible/static; hero ambient none; no errors. |

Final dense evidence: `evidence/mileys-dense-{normal,nojs,reduce}-{desktop,mobile}-20260903.png` (six files). Every run: scrollWidth equals viewport width; all three images complete with natural dimensions 1586x992, 1122x1402 and 1536x1024; all enquiry CTAs resolve to `mailto:[REDACTED_EMAIL]`, telephone resolves to `tel:+447928254056`, and CTA heights are 44px header / 45px page buttons.

Final section boxes (top/height px): desktop `#hero 82/584`, `#experience-ribbon 666/73`, `#care 740/662`, `#owner-noticed 1402/469`, `#practical-close 1871/430`; mobile `#hero 82/692`, ribbon `774/150`, care `924/1257`, noticed `2181/725`, close `2906/873`. The new four-chapter structure removes isolated `#room`, `#individual-visits`, `#quiet-close` and `#contact` poster slabs. It is 51.8% shorter than prior desktop 4880px and 31.7% shorter than the conservative mobile 5637px baseline, outside the planning target because chapter consolidation eliminated more nonfunctional space than forecast; no font size or verified account was removed.

Visual check: desktop retains a continuous hero → proof rail → image-anchored care → editorial outcome → practical close progression. Mobile has no review wall or blank outcome gap after the transform-only motion correction. Reviewer must independently judge whether the unexpectedly stronger height reduction remains commercially appropriate.

## Favicon postfix self-QA — 2026-09-03

`index.html` now declares an inline data-SVG favicon: a neutral forest square with a citron horizontal rule. It is a browser utility mark only, has no network request, is not an official logo and uses no customer or concept-content image.

Postfix evidence: `evidence/mileys-dense-postfix-{normal,nojs,reduce}-{desktop,mobile}-20260903.png`. In all six actual browser runs at `http://127.0.0.1:4175/`, console errors = 0 and page errors = 0; no favicon response was requested because the declared data URI is self-contained, therefore there was no `/favicon.ico` 404. Desktop remained 1440/1440/1440 at 2354px and mobile 390/390/390 at 3852px. All three images remained complete at their registered dimensions; all CTA labels/hrefs and 44px header CTA remained unchanged. Normal retains `motion-enabled` and `drift`; no-JS/reduce retain visible/static reveal targets and no ambient.

Execution Owner status: `IMPLEMENTED — PENDING INDEPENDENT RE-ACCEPTANCE`. Remaining P0/P1 are not self-awarded; independent review must validate the postfix evidence.
