# UI / Skin / Visual System

AUDIO FORGE must allow generated plugins to look unlike the builder and unlike one another.

## Canonical UI model
`Window → Scenes/Pages → Containers → Components → Bindings → States → Animations → Assets`.

## Components
Knobs, sliders, switches, buttons, XY pads, keyboards, pads, waveform/spectrum/scope, meters, graphs, envelopes, sequencers, browsers, menus, text, images, custom canvases and plugin-specific components.

## Customization
- free/constraint/grid layout modes;
- responsive/resizable layouts;
- arbitrary typography/branding;
- vector/raster assets;
- component skins;
- light/dark/multiple themes;
- user-selectable skins where product enables them;
- custom control filmstrips/atlases;
- animation timeline/state transitions;
- audio/MIDI/parameter-reactive visuals;
- video loops/backgrounds with lifecycle/performance controls;
- shader/custom-render adapters where supported;
- accessibility labels/keyboard focus/contrast/scaling.

## AI workflows
Prompt-to-layout, image/sketch-to-layout proposal, brand-kit application, iterative natural-language edits, component generation, asset replacement and responsive QA. AI may propose original designs from references but must not blindly reproduce third-party protected visual assets.

## Performance
UI render performance is separately budgeted from audio. Video/GPU visual failures must degrade gracefully without affecting DSP. Host resize/open/close/recreate/HiDPI/multi-monitor behavior is tested.
