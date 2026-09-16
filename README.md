# TreeForge AOSP Manifest

Slim Android 15 AOSP manifest for TreeForge development on the
Google Pixel Tablet (`tangorpro`).

## Baseline

- Android 15
- AOSP `android-15.0.0_r36`
- Device: `tangorpro`
- SoC: `gs201`
- Default sync jobs: 6
- Recommended clone depth: 1

## Checkout

After this repository is published, initialize with the actual
TreeForgeAOSP manifest repository URL:

    repo init -u ACTUAL_MANIFEST_REPOSITORY_URL -b development --depth=1

Then:

    repo sync

The manifest defaults to six sync jobs.

## Provenance

- `upstream/android-15.0.0_r36-default.xml`
  preserves the Google r36 baseline manifest.
- `overlays/90-treeforge-slim.xml`
  preserves the TreeForge slimming overlay.
- `default.xml`
  is the resolved TreeForge tangorpro manifest.
