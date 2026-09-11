# Testing / Host / Audio Gauntlet

## Test pyramid
1. deterministic DSP/unit tests;
2. graph/schema/property tests;
3. plugin wrapper/state tests;
4. validator scans;
5. headless host tests;
6. real DAW/host automation;
7. installer/upgrade tests;
8. listening/adversarial review.

## DSP checks
Impulse, sine/noise/reference fixtures; frequency/phase/gain behavior where specified; silence; NaN/Inf; DC; clipping; denormals; latency; tail; channel routing; oversampling; reset; deterministic seed; automation smoothing; sample-rate/block-size sweeps; CPU/memory/allocations; long soak.

## Instrument checks
Voice stealing, note-on/off, stuck notes, sustain, pitch bend, MPE if enabled, tuning, polyphony, preset/state restore, sample missing/corruption, content streaming, transport sync.

## Host checks
Scan/validate, instantiate, GUI open/close/resize, audio/MIDI, automation write/read, bypass, suspend/resume, save/reopen project, offline bounce, freeze/render, preset recall, multiple instances, format interoperability where expected.

Host matrix is versioned/configurable; no claim of compatibility without evidence for the declared matrix.

## Realtime adversary
Stress small/large blocks, rapid automation, preset switching, sample/library changes, host transport churn, device/sample-rate changes where applicable, memory pressure, repeated construction/destruction and provider/license-server outage. Licensing/network failure must not block realtime audio callback.

## Upgrade matrix
Previous supported plugin versions → current: host state, presets, content IDs, license state and installers. Breaking migration requires explicit product decision and release note.

## Evidence
Store toolchain/OS/host/plugin-format versions, machine profile, logs, audio fixture hashes, measurements, crashes/dumps, screenshots where useful and artifact checksums.
