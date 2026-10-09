# Neon Rift 3D: Completed Project Plan

## Goal

Improve the Week 8 Godot C# demo and use separate Git branches to record the
changes clearly. Make the player faster and make the Striker attack more often.

## Planned and completed changes

| Task | Branch | Before | After | Status |
| --- | --- | --- | --- | --- |
| Improve player movement | `feature/player-speed` | 7 units/s | 8.5 units/s | Implemented and merged |
| Increase Striker attack frequency | `feature/striker-fire-rate` | 1.6 s between shots | 1.2 s between shots | Implemented and merged |

The player change is in `Scripts3D/Player3D.cs`. The Striker change is in
`Scripts3D/StrikerEnemy3D.cs`. Comments and the README now match the new values.
The Striker's first shot delay remains 1 second. The target remains 10 kills.

## Branch and merge record

Two feature branches were created from the original demo commit `9a38085`.
Including `main`, the repository has three branches.

1. `d10a954`: change player speed to 8.5 units/s.
2. `8814a3d`: change the Striker shooting interval to 1.2 seconds.
3. `e5ac3d8`: merge `feature/player-speed` into `main`.
4. `43aa160`: merge `feature/striker-fire-rate` into `main`.

Both merges use `--no-ff`, so the merge history keeps the two tasks visible.
There was no merge conflict because the branches changed different files.
The work was prepared with one GitHub account. These branches do not claim
that two different students made the commits.

## Design explanation

Player3D owns the player's movement speed. StrikerEnemy3D owns its shooting
interval, so each change belongs in that class. Both changes affect game
behaviour and balance. Godot's 3D node types, scene geometry, collision setup
and camera do not need to change.

## Verification

The final C# project builds successfully with zero errors. It reports two
existing CS8632 nullable annotation warnings in Player3D and Bullet3D.
The commit graph confirms that both branches start from the original version
and both merge into main. The final source contains both new values.

A full interactive playthrough has not been completed. Before presenting,
open the project in Godot 4.7.2 .NET, build, and run `Scenes3D/Main3D.tscn`.
Use WASD to check movement and mouse aiming/shooting. Reach four kills to
observe Strikers. Check victory at 10 kills and defeat when player HP reaches 0.

## Submission

Submit this completed plan together with the public GitHub repository link.
The repository contains the improved code, both feature branches and the
commit and merge history. Group member details should be added through the
course submission form where required.
