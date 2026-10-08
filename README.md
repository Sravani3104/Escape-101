# Escape-101
A 2D stealth-survivor platformer. Due to a virus that was invented in the lab, everyone got infected. You are the only survivor, but how long will that last?

## Play now (no download)

**https://Sravani3104.github.io/Escape-101/**

It runs in any browser, but Chrome or EDGE work best.

## Controls

| Key | Action |
|---|---|
| A / D or ← / → | Walk |
| Shift | Sprint (louder) |
| Space / W | Jump |
| F or click | Swing scalpel |
| E / Up at the exit | Leave the floor |
| Esc / P | Pause |
| M | Mute music |

## How a run works

1. Each floor has a countdown timer. Run out of time or health and you die.
2. Find the **keycard** to unlock the exit.
3. Grabbing the keycard sets off the **alarm**. Every infected person on the floor hunts you.
4. Reach the **exit** before time runs out. Five floors, then you escape.

## What's in the lab

- **Infected:** Walkers (steady), Runners (fast, weak) and Brutes (slow, tanky, hit hard). They notice you by sight and by noise. Sprinting and fighting are loud.
- **Floor holes (pits):** fall in and you die. They appear from floor 2.
- **Spikes:** damage on touch. They appear from floor 3.
- **Steam vents:** pulsing hazards that burn. They appear from floor 4.
- **Darkness:** you only see what is near you.

## The tech (what makes it different each time)

**Cellular automata generate every floor.** I fill each floor with random noise, then smooth it over several passes using a neighbour rule. This makes cave-like lab layouts. A guaranteed-path check makes sure every floor can be completed, then hazards, enemies and the keycard are placed automatically.

**Daily lab.** The seed comes from today's date plus the floor number, so everyone who plays on the same day gets the same lab and can compare runs.

**A Director adjusts difficulty (DDA).** It tracks how you play on each floor: deaths, damage taken, time used and times spotted. It combines these into a frustration score from 0 to 1.
- Doing well makes the next floor harder (more enemies, faster, longer sight lines, more hazards, less time).
- Struggling makes it easier.
- The current difficulty is shown in the corner of the HUD so you can watch it respond.

## Built with

- Unity 6 (2D, WebGL build) and C#
- All art, UI and audio are generated in code (placeholder shapes, IMGUI menus, procedural music and sound effects)
- AI-assisted development with Claude (see the write-up for how)

## Run it locally

1. Open the project in Unity 6.
2. Open the `Menu` scene and press Play.
3. Build Profiles scene order must be: `0 Menu`, `1 Lab`.

## Known limitations

- Placeholder art and sounds
- Browser audio only starts after your first click
- Built as a 4-day prototype, so balance numbers are untuned.
