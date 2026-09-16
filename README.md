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

    REPO_ALLOW_SHALLOW=1 repo init \
        -u https://github.com/TreeForgeAOSP/treeforge_aosp_manifest.git \
        -b development \
        --depth=1 \
        --no-clone-bundle

Then:

    REPO_ALLOW_SHALLOW=1 repo sync --no-clone-bundle

The manifest defaults to six sync jobs.

`REPO_ALLOW_SHALLOW=1` and `--no-clone-bundle` are part of the
TreeForge shallow-checkout policy. They were validated against Repo
2.67 and prevent large full-history project object stores from being
materialized during a depth-1 checkout.

## Provenance

- `upstream/android-15.0.0_r36-default.xml`
  preserves the Google r36 baseline manifest.
- `overlays/90-treeforge-slim.xml`
  preserves the TreeForge slimming overlay.
- `default.xml`
  is the resolved TreeForge tangorpro manifest.
