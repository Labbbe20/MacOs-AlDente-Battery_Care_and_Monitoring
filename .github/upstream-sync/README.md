# Upstream Synchronization

This fork keeps the application source as close to upstream as possible. Local automation is limited to `.github/workflows/sync-upstream.yml` and the state files in this directory.

The workflow:

- Merges `AppHouseKitchen/AlDente-Battery_Care_and_Monitoring` `master` into this fork's `master` on a schedule and on manual runs.
- Force-syncs upstream tags into the fork.
- Mirrors the most recent upstream GitHub releases and their release assets into this fork.
- Runs a best-effort macOS build from the public source when upstream source changes or when the workflow is run manually.

The upstream README currently states that current AlDente releases are closed-source. Without AppHouseKitchen's private source, Apple Developer signing certificate, provisioning setup, and notarization credentials, this fork cannot reproduce the official signed and notarized DMG byte-for-byte.

Mirrored release DMGs are copied from the upstream GitHub releases. The CI build artifact is unsigned, not notarized, and intended only as a transparency check that the public source can still be built where possible.
