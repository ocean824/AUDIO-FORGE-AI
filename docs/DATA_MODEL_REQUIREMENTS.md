# Data Model + Requirement Registry

## Core entities
`User, Organization, PluginProject, ProductSpec, Requirement, DSPGraph, DSPNode, ParameterDefinition, StateSchema, Migration, UIProject, UIComponent, Skin, VisualAsset, ContentLibrary, SampleAsset, SampleMapping, PresetBank, Preset, BackendProfile, FormatTarget, ToolchainProfile, BuildMatrix, BuildRun, Artifact, HostProfile, ValidationRun, AudioFixture, AudioMeasurement, TestRun, Finding, GauntletRun, Evidence, LicenseProfile, LicenseProduct, InstallerProfile, Release, ReleaseChannel, UpdateManifest, AgentProfile, ModelProfile, AgentExecution, AuditEvent`.

## Requirements
- `AF-REQ-001` Natural-language/reference brief becomes versioned ProductSpec.
- `AF-REQ-002` Project supports synth/sampler/rompler/drum/effect/MIDI/generative families.
- `AF-REQ-003` DSP graph compiles to exportable production source.
- `AF-REQ-004` JUCE first-class but backend/format/toolchain adapters remain replaceable.
- `AF-REQ-005` Stable parameter/state schemas and migrations preserve host/preset compatibility.
- `AF-REQ-006` UI supports arbitrary skins/layout/assets/animation/video/audio-reactive visuals.
- `AF-REQ-007` Sample/content engine supports commercial library packaging and source metadata.
- `AF-REQ-008` Preset system supports banks/tags/search/macros/migrations/AI generation.
- `AF-REQ-009` Build farm produces versioned Windows/macOS target artifacts.
- `AF-REQ-010` Host Lab verifies declared plugin/DAW compatibility matrix.
- `AF-REQ-011` Audio Gauntlet deterministically checks DSP/realtime/performance requirements.
- `AF-REQ-012` Independent adversarial review is required for material releases.
- `AF-REQ-013` Release Factory produces installers/signing/notarization/update artifacts via protected adapters.
- `AF-REQ-014` Builder licensing and generated-plugin licensing are separate configurable planes.
- `AF-REQ-015` Generated projects remain source-exportable and maintainable outside AUDIO FORGE.
- `AF-REQ-016` API/CLI/MCP supports XIO/SONARA/ØMEGA automation.
- `AF-REQ-017` Model roles/defaults/overrides are configurable; deterministic gates cannot be bypassed by model output.
- `AF-REQ-018` V1/V2/V3 share one end-state architecture.
- `AF-REQ-019` Secrets never enter generated source/repository history.
- `AF-REQ-020` Realtime thread remains independent of network/model/license operations.
