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

Initialize the checkout with shallow project history while keeping
the manifest repository itself unshallowed:

    REPO_ALLOW_SHALLOW=1 repo init \
        -u https://github.com/TreeForgeAOSP/treeforge_aosp_manifest.git \
        -b development \
        --depth=1 \
        --manifest-depth=0 \
        --no-clone-bundle

Then synchronize:

    REPO_ALLOW_SHALLOW=1 repo sync \
        --no-clone-bundle

The manifest defaults to six parallel sync jobs through `sync-j="6"`.

### Shallow checkout policy

The following are part of the validated TreeForge checkout policy:

- `REPO_ALLOW_SHALLOW=1`
- `--depth=1`
- `--manifest-depth=0`
- `--no-clone-bundle`

`--depth=1` keeps AOSP project repositories shallow.

`--manifest-depth=0` keeps the small TreeForge manifest repository
unshallowed so future manifest updates can be fetched and rebased
normally.

This configuration was fresh-checkout validated with all 1002
manifest projects shallow and zero missing or non-shallow projects.


## Provenance

- `upstream/android-15.0.0_r36-default.xml`
  preserves the Google r36 baseline manifest.
- `overlays/90-treeforge-slim.xml`
  preserves the TreeForge slimming overlay.
- `default.xml`
  is the resolved TreeForge tangorpro manifest.
