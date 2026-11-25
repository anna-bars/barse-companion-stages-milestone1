# Companion Stages — Fox, Bear & Dragon (Stage 1 + Stage 2 + Stage 3)

Live Rive demo + integration reference. Design follows the Elephant Mood
Tracker demo (violet stage, black docs panel, Space Grotesk / JetBrains Mono).

## What's new in this version

- **Milestone 1 art**: updated Fox / Bear / Dragon `.riv` files for all 3 stages (scroll item, Idle/Talk improvements, item polish)
- **Size control**: 100% · 80% · 75% · 50% · 25% · 15% (scales the companion around its centre; resets to 100% when the stage changes, kept when switching companion)
- **Stage selector** (Stage 1 / Stage 2 / Stage 3)
- **Stage 3 files** for Fox, Bear and Dragon, same state machine schema as Stages 1 and 2
- **Stage 2 files** for Fox, Bear and Dragon, same state machine schema as Stage 1
- Updated integration documentation (in the page and below)

## Files

| Stage | File | Artboard | State machine |
|---|---|---|---|
| 1 | `src/assets/stage1/ART_Fox.riv` | `ART_Fox` | `Fox Controller` |
| 1 | `src/assets/stage1/ART_Bear.riv` | `ART_Bear` | `Bear Controller` |
| 1 | `src/assets/stage1/ART_Dragon.riv` | `ART_Dragon` | `Dragon Controller` |
| 2 | `src/assets/stage2/ART_Fox_Stage2.riv` | `STAGE2_ART_Fox` | `Fox Controller` |
| 2 | `src/assets/stage2/ART_Bear_Stage2.riv` | `STAGE2_ART_Bear` | `Bear Controller` |
| 2 | `src/assets/stage2/ART_Dragon_Stage2.riv` | `STAGE2_ART_Dragon` | `Dragon Controller` |
| 3 | `src/assets/stage3/ART_Fox_Stage3.riv` | `STAGE3_ART_Fox` | `Fox Controller` |
| 3 | `src/assets/stage3/ART_Bear_Stage3.riv` | `STAGE3_ART_Bear` | `Bear Controller` |
| 3 | `src/assets/stage3/ART_Dragon_Stage3.riv` | `STAGE3_ART_Dragon` | `Dragon Controller` |

## Inputs (identical in every stage)

| Input | Type | Notes |
|---|---|---|
| `isTalking` | boolean | true → Talking loop, false → Idle |
| `Celebrate` | trigger | one-shot Celebrating |
| `Blink` | trigger | one-shot Blink on its own layer |
| `CompassTapped` / `MirrorTapped` | Rive events | item interaction targets |

Events are scoped per character controller. Listen on the instance that is on screen.

## Size

The artwork is exported at 100%. For smaller display, scale the canvas/view around its centre
(`transform: scale(size / 100)` on web, `transform: [{ scale }]` in React Native). Steps: 100, 80, 75, 50, 25, 15.

## Run it

```bash
npm install
npm run dev
```

## Build / deploy

```bash
npm run build
```

Works on Vercel as a Vite project (build command `npm run build`, output `dist`).
