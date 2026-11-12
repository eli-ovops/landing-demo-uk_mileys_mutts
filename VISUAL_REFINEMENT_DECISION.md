# Visual Refinement Decision - Miley's Mutts

Status: `VISUAL REFINEMENT PRE-CODE GATE = PENDING INDEPENDENT REVIEW`  
Date: 2026-09-02  
Scope: authorized local static Concept Demo refinement only. No deployment, upload, public URL, email send, customer login, booking or data capture.

## Flow and skill record

- `ask-matt`: this is a bounded enhancement of an existing one-page static concept, so its recommended route is direct implementation in the current context rather than a multi-session specification flow.
- `ui-ux-pro-max`: ran `independent dog groomer local service editorial calm premium` with variance 7, motion 3 and density 4. It recommended a storytelling/social-proof page and surfaced Aurora UI as a generic style option. Aurora, its pink accent and automatic gradient movement are deliberately rejected: they would read as SaaS, weaken business specificity and risk contrast failure.
- `HyperFrames by HeyGen`: `NOT USED - static deliverable / no video authorization`. It was assessed under its entry workflow, whose applicable outputs are video/motion compositions. No video, render or movement deliverable is requested here, and no local HyperFrames runtime is installed. No package, runtime or generated motion asset will be added merely as decoration. The static page remains its own reduced-motion fallback.

## Refined design read

**Quiet care, bright confidence**: retain the verified 1-to-1/home-salon proposition, but move the visual experience from a dark editorial brochure into a lighter, friendlier local-business introduction. `SOUL 9 / SPECTACLE 3 / DENSITY 5 / MOTION 2`.

The redesign uses a warm chalk ground, evergreen text, a restrained citron action colour and short coral proof accents. It avoids the current holding page's night-sky visual language because it is a GoDaddy placeholder, not verified customer brand material. It also avoids beige/brass salon cliches, paw-print decoration, generic booking widgets, cards in equal rows and decorative animation.

## Material visual changes

| Existing weakness | Change | Business purpose | Boundary |
| --- | --- | --- | --- |
| Dark hero dominates the first impression | Use a light, image-led hero with an airy factual side panel and a more visible direct enquiry route | Feels accessible to local dog owners while retaining distinctiveness | C-001 stays original concept only |
| Page rhythm relies heavily on dark blocks | Alternate chalk, evergreen and soft botanical surfaces; give each proof moment a different shape | Makes the full page more welcoming and less like a repeated editorial template | No invented brand palette or logo |
| Proof is visually small | Make review-derived proof the second visual anchor, with exact attribution and no service-menu conversion | Brings real customer relevance ahead of decorative styling | F-004/F-005 remain third-party customer statements |
| Mobile sections stack but lose variety | Pair meaningful images with concise content, preserve 44px contact targets and give each block an intentional full-width rhythm | Improves scanability at 390px | No hidden desktop-only facts |

## Full-page visual storyboard

| Section | Fact/asset mapping | Composition | Desktop/mobile behaviour |
| --- | --- | --- | --- |
| Hero | F-001, F-002, C-001 | Chalk copy field, tall portrait-like dog image and small direct email action | Desktop asymmetric 5/7 split; mobile content first then 4:5 image |
| Reassurance | F-004 | Coral date marker and large customer statement | Horizontal editorial band; mobile wraps without truncation |
| The approach | F-001, C-002 | Dark evergreen panel offset by bright care image | Two columns; mobile image then factual copy |
| Owner notes | F-004/F-005/F-006 | Three unequal shapes and surface values rather than repeated cards | Deliberate single-column cascade |
| Customer words | F-005, C-003 | Oversized quotation beside resting-dog image | Quote first on mobile; no image repeats |
| Closing | F-002, F-003 | Citron contact rail on evergreen surface | Full-width 44px email/telephone controls |

## File, selector and implementation mapping

The existing customer-visible files will be modified only after this amendment passes review. The old dark editorial direction is replaced section by section; no unrelated file is in scope.

| Storyboard section | Current selector / CSS area | Planned replacement | `ui-ux-pro-max` effect |
| --- | --- | --- | --- |
| Hero | `index.html .hero`, `.hero-copy`, `.hero-image-wrap`; `styles.css .hero`, `.hero-copy`, `.hero-image-wrap`, `h1` | Convert the dark 50/50 block into a chalk content field plus a taller right-side image and a clearer email action | Storytelling page pattern, one above-fold CTA, 1440/390 responsive composition, readable line length |
| Reassurance | `.proof-bar`, `.proof-quote`; `styles.css .proof-bar` | Turn the thin green band into a coral date-led proof marker with an attributed short quote | Social proof immediately follows hero; contrast and no colour-only meaning |
| Approach | `.care`, `.care-visual`, `.care-copy`; `styles.css .care*` | Use a deep evergreen factual panel against a brighter, independently cropped C-002 image | Diverse surface rhythm; 16px mobile body and reserved image aspect ratio |
| Owner notes | `.mentions`, `.mention-grid`, `.mention`; `styles.css .mentions`, `.mention*` | Replace same-feeling panels with three unequal modules and distinct chalk/evergreen/coral surfaces | Asymmetric variance, 8px rhythm, single-column 390px cascade and no equal-card template |
| Customer words | `.words`, `.words-quote`, `.words-image`; `styles.css .words*` | Create one oversized review anchor balanced by C-003 without repeating crops | Long-form measure, meaningful image alt, quote-first mobile hierarchy |
| Closing | `.contact`, `.contact-content`, `.contact-action`; `styles.css .contact*` | Add a citron contact rail on evergreen and make contact links visibly pressable without moving layout | One primary enquiry path, >=44px targets, visible focus/pressed state, semantic mailto/tel |
| Global / mobile | `:root`, `.skip-link`, `a`, `@media (max-width:760px)`, `@media (prefers-reduced-motion:reduce)` | Replace raw old palette tokens with semantic chalk/evergreen/citron/coral tokens; retain skip link and add explicit focus/press styles | Semantic tokens, contrast check, mobile-first 390px gate, reduced motion respected |

## UI-UX design-system traceability

| Decision-system output | Accepted/rejected | Concrete implementation receipt |
| --- | --- | --- |
| Storytelling-driven + social proof | Accepted | `.hero` -> `.proof-bar` -> `.care` sequence; F-004 is placed before the visual approach section. |
| Above-fold CTA | Accepted | `.hero-copy .button` remains the sole filled primary CTA and links to the public email. |
| Variance 7 / density 4 | Accepted with business-specific constraint | `.mention-grid` becomes deliberately unequal, while `.section-shell` retains spacious but not luxury-empty rhythm. |
| Motion 3 | Tightened to motion 2 | No automatic animation or video. `a` may receive only 150-250ms opacity/colour press feedback; reduced-motion removes transitions. |
| Aurora UI / pink / luminous mesh | Rejected | No gradients, pink SaaS accent or decorative movement. `:root` moves instead to chalk/evergreen/citron/coral surface tokens. |
| Typography Lora/Raleway | Rejected | Existing readable editorial serif/sans pairing is retained; selector changes apply scale/measure, not a generic wellness font swap. |

## UX, accessibility and performance acceptance criteria

- One primary enquiry CTA above the fold; repeated actions are semantic `mailto:` / `tel:` links only.
- Visible keyboard focus, 44px minimum contact action targets, a skip link, sensible heading order, meaningful image alt text, no horizontal scroll at 390px.
- Keep all body text at or above 16px on mobile and reserve image aspect ratios. The page has only three local concept images; C-002/C-003 load eagerly so a complete local preview and its evidence cannot render incomplete before a scroll event.
- No automatic animation. Hover/press feedback, if used, is limited to opacity/colour within 150-250ms and respects reduced motion.
- Customer-visible copy may not say Cottam, official image, staff, salon, actual customer dog, booking availability or full service menu unless independently verified.

## Pre-code reviewer request

Independently assess whether this refinement preserves the existing fact/asset boundaries while materially improving visual specificity and purchase appeal. Verify it does not use the GoDaddy star background as customer branding, does not add gratuitous motion/video, and has enough concrete mapping to begin edits to customer-visible HTML/CSS.
