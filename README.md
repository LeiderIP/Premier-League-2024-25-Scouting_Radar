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

## Data Pipeline

| Step | Description |
|---|---|
| Event extraction | Reads all 380 match CSVs; extracts passes, shots, duels, carries, pressures, recoveries |
| Minutes played | Derived from substitution events; players with < 90 min total are excluded |
| Per-90 normalisation | All counting stats divided by minutes played × 90 |
| Percentage metrics | Completion %, dribble success %, shot accuracy computed from raw counts |
| Percentile ranking | Each metric ranked within its position group using `rank(pct=True)` |
| JSON embed | All player data serialised and embedded directly in the HTML |

---

## Key Technical Decisions

| Challenge | Solution |
|---|---|
| Freeze-frame duplicates | `drop_duplicates('id')` before counting any event type |
| Numeric columns as strings | `pd.to_numeric(..., errors='coerce')` applied to minute, second, pass_length |
| Radar hover detection | Dot positions stored globally after draw; `mousemove` checks distance to each dot |
| Canvas scaling on retina | Mouse coordinates scaled by `canvas.width / rect.width` |
| Position classification | Regex-based mapping from StatsBomb position names to 6 groups |

---

## How to Run

1. Mount Google Drive and set `PROJECT_FOLDER` to your match CSV directory
2. Run **Cell 1** — processes all 380 matches (~5 min) and exports the HTML
3. Run **Cell 2** — uploads to GitHub (requires a Personal Access Token with `repo` scope)
4. Enable GitHub Pages: **Settings → Pages → Branch: main → Save**

> The 380 match CSVs are not included due to file size. Data available from [StatsBomb Open Data](https://github.com/statsbomb/open-data).

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

Built as part of a data analytics portfolio during an MSc in Applied Performance Analysis at the **University of Essex**. Demonstrates end-to-end sports data work: event ingestion, domain-specific metric derivation, statistical normalisation, and interactive visualisation — all within a single reproducible notebook.

---

*Data © StatsBomb. Project code MIT licensed.*
