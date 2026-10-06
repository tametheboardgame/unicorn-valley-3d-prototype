# Mobile Target

## Baseline Device

Primary minimum target:

- Samsung Galaxy Tab S8 and newer.
- Tab S8 reference hardware: Snapdragon 8 Gen 1, 8 GB RAM, 2560 x 1600 display.
- Android tablet is the primary deployment platform for the prototype.

The Tab S8 is the performance floor. Newer Tab S-series devices may receive higher visual-quality profiles but must not become the baseline requirement.

## Performance Targets

Hard minimum:

- Stable 30 FPS during normal exploration on the Galaxy Tab S8.
- No sustained thermal behaviour that makes the game unpleasant to use.
- No routine out-of-memory crashes or asset-streaming stalls.

Aspirational:

- 45/60 FPS modes on newer or higher-performance tablets.
- Higher-quality shadows, foliage density, effects and render scale on newer devices.

## Rendering Strategy

Initial production target:

- Unreal Engine 5.8.
- Android Vulkan.
- Mobile renderer.
- Start with Mobile Deferred shading for the visual prototype, subject to profiling on the Tab S8.
- Mobile HDR enabled where required by the chosen post-processing approach.
- Texture streaming, conventional LODs/HLODs, occlusion and cull-distance controls used from the beginning.

The shipping visual baseline must not depend on:

- Nanite.
- Virtual Shadow Maps.
- hardware ray tracing.
- desktop-only rendering features.
- Lumen.

Unreal 5.8 exposes experimental desktop-renderer/Lumen support for some high-end Android Vulkan SM5 devices, including Adreno 7xx-class hardware. This may be tested as a future optional high-end quality mode, but it is not part of the Tab S8 baseline and must not drive asset or lighting design.

## Lighting Strategy

The baseline should favour a controlled stylised lighting model:

- baked or precomputed indirect lighting where appropriate;
- one strong directional/sun light;
- carefully limited dynamic lights;
- reflection captures and image-based lighting;
- lightweight ambient occlusion;
- deliberately authored colour grading;
- mobile-compatible shadows.

The goal is visual richness through art direction rather than brute-force desktop rendering.

## Resolution and Scalability

The Tab S8 native display is 2560 x 1600, but the game should not assume native-resolution rendering.

The project should support dynamic or profile-based render scaling so that visual quality can be traded for performance without changing gameplay or UI layout.

Quality profiles should eventually include:

1. Tablet Baseline — Galaxy Tab S8.
2. Tablet High — newer Tab S-series devices.
3. Development PC — maximum-quality authoring and visual inspection.

## Input

The game should be touch-first.

The prototype must eventually support:

- virtual movement controls;
- camera drag;
- contextual interaction controls;
- touch-friendly UI hit targets.

Keyboard/mouse and controller input may remain available for development but are secondary.

## Device Testing Rule

A feature is not considered complete merely because it performs correctly in the Unreal Editor.

Representative Android builds must be installed and profiled on the Galaxy Tab S8 throughout development, beginning during the greybox phase.

## Android Toolchain

Use the current Unreal Engine Android toolchain and target API level supported by Unreal 5.8.

For any future Google Play distribution, maintain the currently required Android target SDK rather than postponing store compliance until the end of development.
