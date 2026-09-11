# Licensing / Installer / Release Architecture

## Separate licensing planes

### Builder plane
AUDIO FORGE accounts, subscriptions, usage/compute entitlements, teams, projects and commercial tiers.

### Generated product plane
Each plugin chooses a licensing profile independent of builder billing.

Supported abstractions:
- free/unlicensed;
- time-limited trial;
- perpetual license;
- subscription;
- machine/seat activation;
- account entitlement;
- license key;
- offline challenge/response;
- grace period;
- bundles/product families;
- paid/free update eligibility.

License provider/server is adapter-based. Generated plugin receives only required public/product configuration and secure runtime tokens—not AUDIO FORGE master secrets.

## Audio safety
License checks are asynchronous/non-realtime. Network outage cannot block the audio callback. Policy defines grace/degraded behavior.

## Release pipeline
`VERSION → MIGRATION TEST → BUILD MATRIX → VALIDATE → HOST MATRIX → AUDIO GAUNTLET → SIGN → NOTARIZE → INSTALLER → INSTALL/UPGRADE TEST → MANIFEST/CHECKSUM → RELEASE CHANNEL`.

## Packaging
Windows installer/uninstaller and macOS package/uninstall guidance first. Install correct plugin/content locations, standalone app where enabled, presets/content, documentation and updater components where configured.

## Signing
Signing/notarization executed by protected service/worker with scoped secrets. Generated repos reference signing configuration but never contain private certificates/passwords/tokens.

## Updates
Stable/beta/custom channels; manifest; version compatibility; download integrity; staged rollout/rollback; release notes; optional in-plugin updater where host/platform practice permits.

## Customer operations
Optional creator portal/API for license issuance/revocation, activations, downloads, entitlements, customer support audit and analytics with privacy controls.
