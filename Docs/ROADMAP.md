# Roadmap

## Status

Pre-production and technical preparation.

The existing Unicorn Valley game remains the active main project. This repository is an experimental 3D prototype and should not block or replace normal development.

## UV3D-P0 — Technical Foundation

Goal: establish a reproducible Unreal development environment and source-control architecture.

Planned outcomes:

- Confirm development workstation specification and permitted configuration.
- Confirm target tablet specification.
- Install and configure the agreed Unreal Engine version.
- Configure C++ development tooling.
- Configure Android development/deployment tooling.
- Configure Git LFS and final Unreal ignore rules.
- Establish project folder and naming conventions.
- Create the initial Unreal C++ project.
- Produce a minimal packaged Android build.
- Verify deployment to the target tablet.
- Record baseline performance and build size.

Exit gate: a minimal Unreal project builds, packages and launches successfully on the target tablet.

## UV3D-P1 — Greybox Sunbeam

Goal: prove scale, navigation and world composition before art production.

Planned outcomes:

- Third-person camera.
- Placeholder Nova character.
- Walk, trot and gallop controls.
- Small greybox section of Sunbeam Village.
- Fountain/plaza.
- Representative paths.
- Placeholder Bakery, Story House, Twinkle & Thread and cottages.
- Hard world boundaries and basic collision.
- Basic NPC placeholders.
- Early tablet build and performance test.

Exit gate: Nova can move reliably around a recognisable greybox Sunbeam Village on the target tablet at the required performance floor.

## UV3D-P2 — Nova Character

Goal: prove that the main character can reach the required visual and animation quality.

Planned outcomes:

- Finalised Nova 3D character specification.
- Reusable base unicorn architecture.
- Production-quality Nova model appropriate for tablet.
- Rig and animation system.
- Idle, walk, trot, gallop, turn and stop animations.
- Initial expressive animation/facial system.
- Tablet-appropriate material and texture solution.

Exit gate: Nova looks and feels sufficiently polished to justify continuing the 3D experiment.

## UV3D-P3 — Sunbeam Visual Pass

Goal: turn the greybox into a representative premium stylised environment.

Planned outcomes:

- Modular terrain and path treatment.
- Reusable rock/cliff kit.
- Reusable foliage kit.
- Flowers and environmental dressing.
- Building exterior style.
- Fountain/water treatment.
- Lighting and atmosphere.
- Wind and environmental movement.
- Performance-conscious particle effects.
- Quality scalability between tablet and development PC.

Exit gate: representative screenshots and an on-device build demonstrate the intended visual direction without dropping below the agreed performance floor.

## UV3D-P4 — Living World

Goal: prove that the environment supports actual Unicorn Valley gameplay rather than functioning only as a visual demo.

Planned outcomes:

- Several NPC unicorns.
- Ambient NPC movement.
- Interaction prompts.
- One dialogue sequence.
- One enterable building or representative interior transition.
- Basic game-state persistence where required.
- Music and ambient audio.

Exit gate: the prototype feels like a small playable section of Unicorn Valley rather than a technology demo.

## UV3D-P5 — Vertical Slice

Goal: produce the complete decision-making prototype.

Planned outcomes:

- One small gameplay activity or mini-game.
- UI and interaction polish.
- Animation polish.
- Visual optimisation.
- Tablet profiling and optimisation.
- Packaged release-style build.
- Final build-size and hardware assessment.
- Workflow assessment.
- Comparison against the existing game.

Exit gate: complete the project decision gate defined in Docs/VISION.md.

## Expansion Rule

No additional region is started until UV3D-P5 is complete and the prototype has passed an explicit go/no-go review.

In particular, Rainbow Meadow, Crystal Brook and the wider world remain out of scope during the prototype programme.
