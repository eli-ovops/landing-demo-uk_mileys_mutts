# Independent LOCAL_PREVIEW_PACKAGE acceptance — 2026-09-03

Role: independent package reviewer; mechanical, read-only review. Actual model runtime was not independently readable and is therefore `UNKNOWN`. No source, ZIP, Owner manifest/report, deployment/upload package, source-transfer package, external service, send, login, or payment action was changed or performed.

## Decision

```text
LOCAL_PREVIEW_PACKAGE = FAIL — FIX P1
P0 = 0
P1 = 1
CLOUDFLARE_UPLOAD_PACKAGE = NOT CREATED / NOT REVIEWED AS A DEPLOYABLE PACKAGE
SOURCE_TRANSFER_PACKAGE = NOT CREATED / NOT REVIEWED
DEPLOYMENT / UPLOAD / SEND = NOT PERFORMED
```

## Archive identity and structural checks

- ZIP: `/Volumes/EXTERNAL/海外落地页/client_uk_mileys_mutts/demo_20260902/deliverables/mileys-mutts-local-preview-package-20260903.zip`
- Size: `6,183,894` bytes.
- SHA-256 independently calculated twice and identical:
  - `shasum -a 256`: `d4b318bfbb5e04cb82ad88d3d0d673da6a797bf411f53c6f6dd2c0f6df6de67e`
  - `openssl dgst -sha256`: `d4b318bfbb5e04cb82ad88d3d0d673da6a797bf411f53c6f6dd2c0f6df6de67e`
- `unzip -t` completed with no compression errors. ZIP central directory has six entries, no archive comment, all unencrypted, Unix regular-file permissions `100644`, and zero-length per-entry extra fields and comments.
- Actual entries are exactly: `index.html`, `styles.css`, `script.js`, `assets/concept-spaniel-hero.png`, `assets/concept-terrier-care.png`, `assets/concept-schnauzer-rest.png`. `assets/` is an implied parent directory, not a nested package root.
- No symlink, absolute or `..` path, hidden path, `.DS_Store`, `._*`, `__MACOSX`, docs, evidence, manifest/report, PAX, AppleDouble or resource-fork entry was found. Every archive header reports `extra field: 0 bytes`; therefore no xattr is embedded in ZIP entry metadata.

## Content lock

The six unpacked files exactly match `CONTENT_MANIFEST_20260903.tsv` by relative path, size and SHA-256. They also equal the currently independently accepted source allowlist:

| Path | SHA-256 |
| --- | --- |
| `index.html` | `7b3589114c7612575985d86515964c2f60e0502d73a7c142dd108f37eebad406` |
| `styles.css` | `1d97195fd595c7abcf888724226393a8c286b46c866e88998e42fdc5f756ca1a` |
| `script.js` | `2ebd3fd436e0624c697bdc068c13681b8e624cc21a64cbd60cacd992a2c30afb` |
| `assets/concept-spaniel-hero.png` | `f3c0fde394fb069c024cfc0f5d571df42342efd88345295b8a0e8665e1f790a4` |
| `assets/concept-terrier-care.png` | `263f000fccbdb90a55d3df7f90ef003bc25596fd49a0776e1a91e28ce85d5db5` |
| `assets/concept-schnauzer-rest.png` | `8d7989bb4ed63a2e57eb08cc2b9065aee4886a38260299a2105821dca6d3c872` |

This is content-equivalent to the accepted local page: no silent visual, text, image, layout, CTA, or script change was found.

## Isolated unpack-root runtime

The actual ZIP was unpacked to fresh `/var/tmp/mileys-package-review.E0iiYZ` and served from that unpack root only. Reviewer browser evidence:

- `reviewer-package-unpacked-desktop-full-20260903.png`: `1440/1440/1440`, document height `2354`; 3/3 images complete; exact three `mailto:[REDACTED_EMAIL]` and one `tel:+447928254056`; header CTA 44px/focusable; zero console and page errors.
- `reviewer-package-unpacked-mobile-full-20260903.png`: `390/390/390`, document height `3852`; the same three complete images, contact targets and header CTA; zero console and page errors.

Normal-JS desktop establishes all four chapter reveals. Mobile has the same content/overflow/contact result; its chapter reveal remains progressive and does not hide static content. This targeted package check intentionally does not replace the already completed full visual acceptance.

## Required P1 — provenance attribute propagates on actual unpack

| Severity | Observed fact | Why it fails this package gate | Minimum sufficient repair |
| --- | --- | --- | --- |
| P1 | The ZIP container itself has `com.apple.provenance: 01 02`. Although archive headers contain no extra fields/xattrs, immediately after actual `unzip` the unpack root, `assets/` directory, and all six unpacked files each have the same `com.apple.provenance: 01 02` attribute. | This is not an embedded ZIP-entry metadata defect; it is macOS filesystem/container-attribute propagation. But it **does** follow this package through real extraction, so under the requested rule and macOS static-package requirement to exclude/avoid `xattr` / `com.apple.*`, it cannot be treated as a payload-clean PASS. | Produce a fresh archive whose container xattrs are demonstrably absent in the intended delivery context, then independently inspect: (1) container `xattr -l`, (2) `zipinfo -v` extra fields, and (3) a fresh unpack tree `xattr -lr`. All must be clean before re-review. Do not change any page payload to repair this. |

The Owner report correctly notes the header/payload distinction, but its conclusion that the host/container provenance lies outside the package is insufficient here: independent extraction proves actual propagation. This is a local preview package P1 only; it does not change the prior page-quality or content-lock conclusion.

## Disk and use boundary

The ZIP is approximately 5.9MB and the package evidence is small; the reported volume headroom makes the project’s limited 100MB/85%/20GiB hygiene threshold inapplicable. No deletion occurred. This review does not create or approve any Cloudflare package, deployment, public URL, source-transfer package, upload, outreach, or sending action.
