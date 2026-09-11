# AUDIO FORGE AI Build Contract

## Authority
Ø current instruction > this contract > approved PRD/architecture/DSP/security/release specs > ADRs > scoped ticket/acceptance criteria > project memory > supporting corpus > implementation behavior.

## Non-negotiables
1. Build the complete V1→V3 end-state as one architecture; versions are capability gates, not rewrites.
2. Generated products are real source-controlled software projects and remain exportable/editable outside AUDIO FORGE.
3. Model-agnostic; ØMEGA Local is a preferred native model/runtime path, not a hard dependency.
4. JUCE is initial first-class backend, not an irreversible lock-in.
5. Never execute unvalidated model-generated code directly on the realtime audio thread.
6. Audio-thread code must avoid unbounded work, blocking I/O, locks, avoidable allocation and nondeterministic external dependencies.
7. DSP correctness/performance uses deterministic tests/measurements plus listening review; AI judgment alone cannot pass hard gates.
8. Plugin state/preset migrations are versioned and backward compatibility is tested.
9. Plugin formats/hosts/OS/toolchains/signing/licensing providers are adapters/configuration where practical.
10. Generated plugins may implement their own licensing independently from AUDIO FORGE's licensing.
11. Signing/notarization/license secrets never ship in generated source or repository history.
12. Commercial/monetization architecture is preserved even when provider/legal/distribution configuration is required before activation.
13. Material product/DSP architecture changes escalate to Ø; agents do not silently simplify creative intent.
14. Every release maps requirements to build/test/host/audio/installer/licensing evidence.
15. User-provided samples/assets must retain source/license metadata; AUDIO FORGE does not assume rights it cannot establish.

## XYRA Audio Loop
`REQUIREMENT → PLAN → IMPLEMENT → BUILD → VALIDATE → MEASURE/LISTEN → HOST TEST → REVIEW → ATTACK → FIX → REVALIDATE → EVIDENCE → PACKAGE → RELEASE`.
