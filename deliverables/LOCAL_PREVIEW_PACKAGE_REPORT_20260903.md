# Miley's Mutts local preview package — 2026-09-03

## Purpose and boundary

`LOCAL_PREVIEW_PACKAGE = PASS` is a local-only, content-locked browser-preview archive. It is not a customer source-transfer package, a Cloudflare upload package, a deployment artefact, or permission to send, upload, publish or contact anyone.

`CLOUDFLARE_UPLOAD_PACKAGE = NOT CREATED`  
`SOURCE_TRANSFER_PACKAGE = NOT CREATED`  
`DEPLOYMENT/SEND = NOT AUTHORIZED/NOT PERFORMED`

## Archive and content manifest

Archive: `mileys-mutts-local-preview-package-20260903.zip`  
Size: 6,183,894 bytes  
SHA-256 (`shasum -a 256`): `d4b318bfbb5e04cb82ad88d3d0d673da6a797bf411f53c6f6dd2c0f6df6de67e`  
SHA-256 (`openssl dgst -sha256`): `d4b318bfbb5e04cb82ad88d3d0d673da6a797bf411f53c6f6dd2c0f6df6de67e`

The six-file content manifest is `evidence/package_20260903/CONTENT_MANIFEST_20260903.tsv`. ZIP root has direct `index.html`, `styles.css`, `script.js`, and `assets/`; it contains no internal docs, evidence, PRE_CODE, inventories, hidden files, `.DS_Store`, `._*` or `__MACOSX` paths. `zip -X` was used with fixed staging mtimes and explicit sorted allowlist. The archive embeds no Apple resource-fork entries; the host filesystem continued to expose a system `com.apple.provenance` xattr after an attempted clear, which is outside ZIP headers/content and is recorded rather than concealed.

## Isolated unpack verification

The actual ZIP was unpacked to a fresh temporary directory. Its six relative paths, file counts, sizes and SHA-256 values matched the manifest and the explicit source allowlist. Browser evidence from the unpack root is listed below.

| Viewport | Runtime result from unpack root |
| --- | --- |
| 1440x900 | `inner/client/scroll = 1440/1440/1440`, full height 2354px; 3/3 images complete; three mailto links and tel link correct; header enquiry CTA 44px; 0 console and 0 page errors. |
| 390x844 | `390/390/390`, full height 3852px; 3/3 images complete; same contact routes and 44px header CTA; 0 console and 0 page errors. |

Screenshots: `evidence/package_20260903/mileys-package-unpacked-desktop-1440x900-20260903.png` and `evidence/package_20260903/mileys-package-unpacked-mobile-390x844-20260903.png`. The unpacked DOM has nine unique IDs and the same `motion-enabled` normal-state capability behavior as the locked source.

## Disk hygiene

New archive is 5.9MB and new package evidence is 2.3MB. The volume reports 8% used with about 1.7TiB free, so the 100MB / 85% / 20GiB limited hygiene thresholds were not triggered. No deletion occurred.

## Final status

`LOCAL_PREVIEW_PACKAGE = PASS`  
P0 = 0; P1 = 0 for this mechanical local package check. This conclusion does not create, imply or replace a Cloudflare upload package, a source-transfer package, deployment approval, send approval, or customer asset-transfer eligibility.
