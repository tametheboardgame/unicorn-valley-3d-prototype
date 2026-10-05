# Unicorn Valley 3D Prototype Vision

## Purpose

Build a tablet-first 3D vertical slice of Unicorn Valley to determine whether the existing game can be recreated as a visually high-quality stylised 3D experience by a one-person creator working heavily with AI-assisted development, without requiring a conventional game-development team or significant budget.

This is an experimental companion project, not a replacement for the existing Unicorn Valley game. Development of the current game continues independently.

## Core Question

Can Unicorn Valley become a polished, expressive 3D game with the visual appeal and movement feel of a high-end stylised commercial title while remaining practical to build, maintain and run on a tablet?

The prototype exists to answer that question with working software rather than assumptions.

## Prototype Target

The first vertical slice will focus on a small but recognisable section of Sunbeam Village.

It should ultimately demonstrate:

- Nova as a fully controllable 3D character.
- Third-person exploration with walk, trot and gallop movement.
- A recognisable Sunbeam Village layout and visual identity.
- High-quality stylised terrain, paths, foliage, rocks, buildings, water and environmental effects.
- Several ambient NPC unicorns.
- At least one dialogue interaction.
- At least one enterable building or equivalent interior transition.
- At least one small gameplay activity or mini-game.
- Music and environmental audio.
- A packaged build running on the target tablet.

## Visual Ambition

The target is not photorealism.

The intended look is a premium stylised fantasy world with:

- strong art direction and colour;
- readable, expressive characters;
- polished animation;
- attractive lighting;
- lush but performance-conscious environments;
- convincing water, foliage, particles and atmospheric effects;
- an overall presentation that feels substantially more expensive than the size of the development team would suggest.

The PC development build may use higher quality settings, but the world and asset pipeline must be designed around tablet constraints from the beginning.

## Primary Success Criterion

The prototype succeeds technically when:

> Nova can explore and gallop around a recognisable and attractive 3D section of Sunbeam Village on the agreed target tablet at a stable 30 FPS or better.

30 FPS is the initial hard performance floor. Higher frame rates are desirable where hardware permits.

## Wider Success Criteria

The experiment is considered successful if all of the following are true:

- The tablet can run the representative vertical slice at acceptable performance and visual quality.
- Nova looks and moves well enough to carry the visual identity of the game.
- The environment can achieve the intended premium stylised look without unsustainable asset complexity.
- The project can be developed effectively through a Git-centred, AI-assisted workflow.
- Routine changes to layout, gameplay and content do not require excessive manual editor work.
- Assets and systems can be reused across future regions rather than rebuilt for every scene.
- Build size, storage use and development hardware requirements remain practical.
- The development effort required for a new region appears achievable for a one-person project with AI assistance.
- The 3D version demonstrably adds enough experience and appeal to justify its additional complexity over the existing 2D game.

## Hard Scope Boundaries

The prototype is not intended to recreate the whole current game.

The initial vertical slice is limited to:

- one section of Sunbeam Village;
- Nova;
- a small number of NPCs;
- a small selection of representative buildings and environmental assets;
- one interaction/dialogue example;
- one interior example;
- one small gameplay activity.

The following are explicitly out of scope until the prototype passes its decision gate:

- rebuilding Rainbow Meadow;
- rebuilding Crystal Brook;
- recreating all existing quests;
- recreating every mini-game;
- migrating the full inventory/progression system;
- building the entire world;
- multiplayer;
- live-service systems;
- large-scale procedural open-world generation;
- purchasing large asset libraries or expensive development hardware solely for this prototype.

## Development Principles

- Tablet first.
- Build ugly before building beautiful.
- Test on real target hardware early and repeatedly.
- Prefer reusable systems and modular asset kits.
- Prefer C++, data-driven definitions and Git-friendly formats where practical.
- Use Blueprints where they genuinely improve the Unreal workflow, not by default.
- Keep generated/cache/build artefacts out of source control.
- Do not commit large asset libraries simply because they were downloaded.
- Keep the existing Unicorn Valley game as the design and gameplay reference.
- Do not allow the prototype to stall development of the existing game.
- Every major visual increase must justify its performance cost.

## Decision Gate

Once the vertical slice is complete, development pauses for an explicit assessment.

The questions are:

1. Does it look sufficiently better than the existing presentation to justify 3D?
2. Does it run acceptably on the target tablet?
3. Is Nova visually and mechanically convincing?
4. Can the workflow be maintained by one person working with AI assistance?
5. Is producing additional regions likely to be practical?
6. Are the hardware, storage and asset requirements acceptable?
7. Is the additional development complexity producing enough value?

Only after that review should the project expand beyond the prototype area.

A successful prototype does not automatically mean the whole game will be rebuilt. It means there is enough evidence to make that decision intelligently.
