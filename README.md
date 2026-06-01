# Premier League 2024/25 — Scouting Radar Chart

Interactive radar chart for player scouting and head-to-head comparison across the full 2024/25 Premier League season, built entirely from StatsBomb event-level data.

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python) ![Canvas](https://img.shields.io/badge/Viz-Canvas%20%2B%20JS-orange?style=flat-square) ![Data](https://img.shields.io/badge/Data-StatsBomb-red?style=flat-square) ![Colab](https://img.shields.io/badge/Platform-Google%20Colab-orange?style=flat-square&logo=google-colab)

---

## Live Demo

**[Open Scouting Radar](https://leiderip.github.io/Premier-League-2024-25-Scouting_Radar/Scouting_Radar.html)**

---

## Overview

This tool processes all 380 Premier League 2024/25 match CSVs from StatsBomb, aggregates player actions across the full season, normalises everything to **per-90 minutes**, and computes **within-position percentiles** so every metric is compared fairly against players in the same role.

The radar chart renders entirely in the browser using HTML Canvas — no server, no external chart library, no dependencies beyond the embedded JSON data.

---

## Features

- **6 position groups** — Forward, Winger, Midfielder, Defensive Mid, Centre Back, Full Back
- **8 tailored metrics per position** — relevant stats for each role, not a generic template
- **Per-90 normalisation** — fairly compares players regardless of minutes played
- **Within-position percentiles** — each axis represents rank among same-position players
- **Head-to-head overlay** — compare any two players on the same radar simultaneously
- **Team badges** — read-only club tags update automatically when a player is selected
- **Hover tooltips** — hover any dot to see exact value and percentile for that metric
- **Dual player cards** — full name, position, and season minutes for both players
- **Stats table** — exact values + percentile bars side by side for every metric
- **Dark / Light theme toggle**

---

## Metrics by Position

| Position | Metrics |
|---|---|
| **Forward** | Goals p90, xG p90, Shots p90, Shot Accuracy %, Key Passes p90, Dribbles Won %, Box Touches p90, Progressive Carries |
| **Winger** | Goals p90, xG p90, Key Passes p90, Dribbles Won %, Crosses p90, Progressive Carries, Pressures p90, Box Touches p90 |
| **Midfielder** | Pass Completion %, Key Passes p90, Progressive Passes p90, Dribbles Won %, Pressures p90, Ball Recoveries p90, Carry Distance p90, Goals+Assists p90 |
| **Defensive Mid** | Pass Completion %, Progressive Passes p90, Pressures p90, Tackles Won %, Interceptions p90, Ball Recoveries p90, Aerial Duels Won %, Carry Distance p90 |
| **Centre Back** | Pass Completion %, Progressive Passes p90, Tackles Won %, Interceptions p90, Clearances p90, Aerial Duels Won %, Ball Recoveries p90, Pressures p90 |
| **Full Back** | Pass Completion %, Key Passes p90, Crosses p90, Tackles Won %, Interceptions p90, Pressures p90, Dribbles Won %, Progressive Carries |

---

## Portfolio Projects

| Project | Description |
|---|---|
| [Title Race Visualiser](https://leiderip.github.io/Premier-League-2024-25-Title-race/pl_position_race.html) | Animated bump chart — all 20 clubs across 38 matchweeks |
| [xG Race Explorer](https://leiderip.github.io/Premier-League-2024-25-xG-Title-race-/xG_Race_Explorer.html) | Match-by-match xG race chart for all 380 games |
| [Season Shot Map](https://leiderip.github.io/Premier-League-2024-25-Shot-Map/Shot_Map.html) | Full-season shot map per team, filtered by outcome |
| [Top Scorers vs xG](https://leiderip.github.io/Premier-League-2024-25-Top-Scorers-xG/Top_Scorers_xG.html) | Goals vs expected goals scatter plot for all players |
| [Player Heatmap Explorer](https://leiderip.github.io/Premier-League-2024-25-Player-Heatmap/Player_Heatmap.html) | Touch heatmap — any player, any match, side-by-side comparison |
| **Scouting Radar** | Per-90 percentile radar — position-aware player comparison |

---

## About

*Data © StatsBomb. Project code MIT licensed.*
