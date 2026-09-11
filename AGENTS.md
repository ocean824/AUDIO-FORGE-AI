# AUDIO FORGE Agent Operating Contract

AUDIO FORGE is developed with XYRA and may itself use ØMEGA/XIO-style agent orchestration.

## Required roles
- ORCHESTRATOR
- PRODUCT PLANNER
- AUDIO/DSP ARCHITECT
- DSP IMPLEMENTER
- UI/VISUAL DESIGNER
- SAMPLE/CONTENT ENGINEER
- PRESET/SOUND DESIGNER
- BUILD/TOOLCHAIN ENGINEER
- TEST ENGINEER
- REALTIME-SAFETY REVIEWER
- HOST/DAW COMPATIBILITY REVIEWER
- SECURITY/LICENSING REVIEWER
- ADVERSARY
- RELEASE ENGINEER

Roles are logical; default model/provider/reasoning can be configured globally and overridden by project/Epic/ticket/run. Spawned agents receive role charter + XYRA stage + governing docs + minimal context manifest + tool/secret permissions + required evidence.

## Isolation
Generated code builds/tests in sandboxed workers. Plugin-host/DAW automation must be isolated from production secrets and user projects. Parallel implementation uses scoped branches/worktrees.

## Independent review
Material DSP/plugin code cannot be approved solely by the authoring agent. Realtime safety, host compatibility, licensing/security and release packaging require independent review contexts.

## Context
Use `docs/CONTEXT_INDEX.md`; do not load the full specification corpus for every ticket.

## Completion evidence
Requirement IDs; source changes; DSP graph/schema changes; test results; plugin validation; host matrix; audio fixtures/measurements; CPU/memory; installer/signing/notarization status; licensing tests; known limitations; release artifacts/checksums; PR/commit references.
