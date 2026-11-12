# Xattr diagnostic — Phase 1–3

Scope: task-scoped disposable controls only. The real local-preview ZIP was not rebuilt, replaced, deleted or modified.

## Phase 1: reproduction and environment

Exact volume check:

```text
stat -f 'filesystem=%T mount=%m' .
filesystem=/ mount=1788425539
mount | rg '/Volumes/EXTERNAL'
/dev/disk7s1 on /Volumes/EXTERNAL (apfs, local, nodev, nosuid, journaled, noowners)
```

The current ZIP, a newly created empty diagnostic control, a metadata-suppressing `cp -X /usr/bin/true` copy, and current `index.html`, `styles.css` and `script.js` each reported exactly `com.apple.provenance: 01 02`; each `xattr -l` call exited 0. A new plain file in a fresh `/tmp` extraction destination reported the same value.

On disposable control `control.bTKRZ9`, documented built-ins were tested:

```text
xattr -d com.apple.provenance control.bTKRZ9  => exit=0
xattr -l control.bTKRZ9                       => com.apple.provenance: 01 02; exit=0
sleep 1; xattr -l control.bTKRZ9              => com.apple.provenance: 01 02; exit=0
xattr -c control.bTKRZ9                       => exit=0
xattr -l control.bTKRZ9                       => com.apple.provenance: 01 02; exit=0
```

No sudo, protection bypass, service/configuration change or broad scan was used.

## Phase 2: archive boundary comparison

Local help was read for `zip`, `unzip`, `ditto` and `xattr`. Relevant supported flags were `zip -X` (exclude extra file attributes), `COPYFILE_DISABLE=1`, and `ditto --norsrc --noextattr --noqtn --noacl`.

A disposable one-file `zip -X` archive was created from `tiny-source.VofK23`. `zipinfo -v` reported `length of extra field: 0 bytes`, `extended local header: no`, no archive comment and a one-entry central directory. `COPYFILE_DISABLE=1 unzip -qq` extracted it into a fresh `/tmp` directory. The extracted file and every created parent directory immediately had `com.apple.provenance: 01 02`; a plain `mktemp` file created beside it had the same xattr. Thus the metadata is not carried by the tested archive entry or its headers.

An earlier disposable template attempt (`tiny.XXXXXX.zip`) was malformed because the local `mktemp` invocation did not expand a non-terminal X template; it was not used for any conclusion. The successful `tiny-source.VofK23.zip` control above is the sole archive evidence.

## Phase 3: hypothesis and safe-generator discovery

**Hypothesis:** this APFS/Codex execution environment injects or virtualises `com.apple.provenance` on newly created filesystem objects, including files created by copy, ZIP extraction and plain creation. The real ZIP's container xattr is therefore environment-side; it is not embedded by `zip -X` and cannot be cleared through the documented `xattr` APIs in this context.

`command -v docker` and `command -v podman` returned no executable. Consequently no already-installed, local-image, network-disabled container generator exists to test. No pull, image build, daemon change or network use occurred.

## Result

No existing safe compliant generation path met all required conditions: container xattr empty, ZIP extra fields 0, and fresh unpack xattrs empty. Phase 4 is blocked. Retain the functionally valid current ZIP unchanged; do not waive this condition or attempt a protection bypass.

Minimal manual option: an authorised human can recreate and inspect the same explicit six-file, `zip -X` package from a macOS environment that does not auto-attach `com.apple.provenance`, then independently verify empty container and fresh-unpack xattrs before replacing any archive.
