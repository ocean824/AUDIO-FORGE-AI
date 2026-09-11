# Security Baseline

AUDIO FORGE executes generated native code and manages signing/licensing secrets, so build isolation is a core security boundary.

- sandbox generated builds/tests;
- least-privilege worker credentials;
- no signing/notarization/license master secrets in generated repos;
- scoped secret broker;
- dependency/source integrity checks;
- SAST/dependency/secret scanning;
- restrict worker network/filesystem access;
- malware/asset scanning where appropriate;
- verify downloaded toolchains/dependencies;
- signed/checksummed release artifacts;
- audit consequential build/release/license actions;
- human/policy approval for production signing/publishing/revocation;
- prompt-injection/untrusted-reference isolation;
- user sample/assets treated as untrusted files;
- generated code cannot silently add telemetry/network behavior outside ProductSpec;
- licensing network code cannot execute on realtime audio thread;
- reproducible/traceable toolchain manifests;
- backups and artifact retention/recovery;
- kill/cancel for autonomous agent/build runs.

Adversarial testing is limited to authorized local/sandbox/staging environments and generated products.