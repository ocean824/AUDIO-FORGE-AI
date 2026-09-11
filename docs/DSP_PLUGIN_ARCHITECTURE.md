# DSP / Plugin Architecture

## Layers
`ProductSpec → DSPGraph/ParameterSchema/StateSchema → Backend IR → Framework Generator → Plugin Format Adapter → Toolchain → Artifact`.

Keep product semantics above JUCE-specific implementation so future backends remain possible.

## DSP graph
Nodes have stable type/version/ports/parameters/state. Edges distinguish audio, MIDI/event, modulation/control and sidechain/routing. Graph compiler validates cycles, channel compatibility, rate domains and required latency/tail declarations.

## Realtime contract
Audio callback must not perform blocking filesystem/network/license calls, unbounded model inference, mutex waits, UI work or avoidable heap allocation. Heavy work is prepared off-thread and atomically/safely exchanged. Parameter changes are smoothed where required. Denormal handling and deterministic reset/state behavior are tested.

## Parameters
Stable IDs never depend on display names/order. Store normalized + domain conversion metadata, units, ranges, skew/steps, automatable/discrete flags, MIDI mapping and version migration. Removing/reusing IDs requires explicit migration.

## State/presets
Versioned state schema. Host project state and preset files share canonical migration services. Missing sample/content references degrade visibly and recoverably.

## Voice architecture
Instrument projects support configurable voice allocator, polyphony, stealing, mono/legato, unison, MPE/channel expression, tuning and per-voice/global modulation.

## Sample engine
Streaming/preload policy, zones, round robin, velocity, groups/chokes, loop/crossfade, slicing, waveform metadata, pitch/time adapters, content IDs/hashes and portable library manifests.

## UI separation
UI never owns DSP truth. Controls bind to stable parameters/actions. Video/visual layers must respect GPU/CPU budgets and cannot destabilize audio thread.

## Formats
VST3/AU/standalone first. CLAP/AUv3 adapters designed where relevant. AAX isolated behind adapter/provider requirements.

## Generated repository
Recommended generated project:
`src/dsp`, `src/plugin`, `src/ui`, `assets`, `content`, `presets`, `tests`, `cmake`, `packaging`, `docs`, `LICENSE_CONFIG`, version/migration manifests. Generated source includes no builder/signing secrets.
