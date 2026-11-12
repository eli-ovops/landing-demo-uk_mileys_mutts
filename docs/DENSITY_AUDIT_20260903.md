# Miley's Mutts density audit — 2026-09-03

Scope: read-only local rendering audit triggered by the user's feedback that the page feels too empty. This is planning evidence only; no customer-visible source or screenshot was changed.

## Current owned-site Gate A evidence

Chrome/Playwright, no login, no interaction with the form, settled for 2.5 seconds after `DOMContentLoaded` on 2026-09-03. Both calls ended at `https://mileysmutts.com/` with title `mileysmutts.com` and HTTP 200. The saved evidence is a full-page capture at each named viewport so that the actual `Launching Soon`, generic form and action context are all reviewable in one stable image.

| Viewport | Stable evidence | Visible path and runtime | Access limit / errors |
| --- | --- | --- | --- |
| 1440x900 | `evidence/mileys-current-site-desktop-1440x900-20260903.png` | `inner/client/scroll = 1440/1440/1440`, full height 1634px. `Launching Soon`, generic Contact Us form, reCAPTCHA/cookie controls and GoDaddy/Airo promotion visible. Form action resolves to `https://mileysmutts.com/`, method GET; no submit was taken. | One console `404` resource error; no page error or login/access block. |
| 390x844 | `evidence/mileys-current-site-mobile-390x844-20260903.png` | `inner/client/scroll = 390/390/390`, full height 1410px. Same Launching Soon/contact path visible. Form action resolves to `https://mileysmutts.com/`, method GET; no submit was taken. | No console or page error; no login/access block. |

## Measured rendering

| Viewport | Full document height | Key section boxes (`top / height`, px) |
| --- | ---: | --- |
| 1440x900 | 4880 | `#hero 82/664`; `#experience-ribbon 746/78`; `#room 824/764`; `#individual-visits 1588/1091`; `#owner-noticed 2679/765`; `#quiet-close 3444/764`; `#contact 4208/608` |
| 390x844 | 5592 | `#hero 82/840`; `#experience-ribbon 922/163`; `#room 1085/1007`; `#individual-visits 2092/1047`; `#owner-noticed 3139/1042`; `#quiet-close 4181/833`; `#contact 5014/489` |

The same-run result uses Chrome headless, `innerWidth = clientWidth = scrollWidth` (1440/390) and one local HTTP origin. A prior independent-review run reported the same desktop total (`4880px`) but mobile `5637px` and `#contact` about `534px`. This plan preserves both observations rather than silently normalising them: the 45px mobile difference is treated as viewport/font-rendering variance until independent comparison identifies a source. The proposed target therefore uses the more conservative `5637px` mobile baseline: `4228–4791px` means a 15–25% reduction against the higher observed baseline.

## Finding and planned correction

- `#individual-visits` uses stepped cards that leave a large uninformative desktop flank and become a long same-unit stream on mobile.
- `#quiet-close` and `#contact` each consume poster-scale vertical space although their business tasks can be completed together.
- The first post-hero image rhythm is interrupted by a long, dispersed visits chapter rather than a continuous care narrative.

Selected Direction A, **Compact Care Editorial**, targets a desktop height of 3416–3904px (about 20–30% shorter from the reproducible 4880px baseline) and mobile height of 4228–4791px (about 15–25% shorter from the conservative 5637px review baseline). The testable intention is not “less content”: every retained screen must carry either a verified fact/customer account, a contact action or one of the already-registered concept images. The proposed chapters are compact Hero/proof rail, continuous care chapter, outcome editorial, and a combined practical quiet close.

## Density dials and acceptance meaning

- **finesse `DENSITY 8`**: an implementation target, up from the previously declared-but-unrealised 7. It requires chapter consolidation, reduced nonfunctional vertical space, and richer relations between existing fact, image and action. It does not permit smaller type or removal of accounts.
- **design-taste `VISUAL_DENSITY 6`**: an outcome target from the observed 3–4. Each viewport must show a meaningful fact, customer account, contact action or registered visual carrier, without becoming a review wall.
- **`DESIGN_VARIANCE 7`**: retain the four different chapter families rather than substitute a universal card.
- **`MOTION_INTENSITY 4`**: chapter-level hierarchy/reveal only; no motion fills whitespace.

## Implemented result

The local final implementation measures 2354px at 1440x900 and 3852px at 390x844, compared with 4880px desktop and conservative 5637px mobile baselines. Its four live sections are compact Hero/proof, image-anchored care, outcome editorial and practical close. This exceeds the planned reduction range because the previously independent room, visits, quiet-close and contact slabs now share content-bearing layout. It is retained for independent review rather than declaring the target met by exception.
