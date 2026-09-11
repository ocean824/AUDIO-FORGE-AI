# AUDIO FORGE System Architecture

```text
Web/Desktop UI + CLI/API/MCP
          |
 Product/Agent Orchestrator
          |
+---------+---------+----------+----------+
| Product | DSP     | UI       | Content  |
| Spec    | Graph   | Studio   | Presets  |
+---------+---------+----------+----------+
          |
     Backend IR / Generator
          |
 JUCE Adapter + Future Backends
          |
 Plugin Format / Toolchain Matrix
          |
 Sandbox Build Workers
          |
 Validator + Host Lab + Audio Gauntlet
          |
 Release / Installer / Licensing Factory
```

## Platform services
PostgreSQL canonical metadata; object/artifact storage for audio/assets/builds; queue/jobs; cache; audit/evidence; secrets vault; model gateway; feature flags/entitlements; observability.

## Desktop vs cloud
Desktop app is valuable for local audio devices, DAWs, plugins, sample libraries and listening. Heavy builds/tests/model workloads can dispatch to isolated local/remote workers. macOS AU/sign/notarize tests require appropriate macOS workers; Windows targets require Windows workers. Compute remains provider-neutral.

## ØMEGA
Generic agent/runtime/model routing can consume the versioned ØMEGA SDK. AUDIO FORGE owns audio-product domain logic and deterministic DSP/build/test systems.

## XIO/SONARA
Expose versioned API/CLI/MCP capabilities: create project, update ProductSpec, generate module, build, validate, run Gauntlet, package/release, inspect status/artifacts. Consequential release/sign/license actions obey approvals.
