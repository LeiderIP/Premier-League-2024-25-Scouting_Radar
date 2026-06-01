# Premier League 2024/25 — Scouting Radar Chart

Interactive radar chart for player scouting and head-to-head comparison, built from StatsBomb event data.

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python) ![Canvas](https://img.shields.io/badge/Viz-Canvas%20%2B%20JS-orange?style=flat-square) ![Data](https://img.shields.io/badge/Data-StatsBomb-red?style=flat-square)

---

## Live Demo

**[Open Scouting Radar](https://leiderip.github.io/Premier-League-2024-25-Scouting_Radar/Scouting_Radar.html)**

---

## Features

- 6 position groups with tailored metrics: Forward, Winger, Midfielder, Defensive Mid, Centre Back, Full Back
- Per-90 normalised metrics — fair comparison regardless of minutes played
- Within-position percentiles — each axis ranks the player vs same-position peers
- Head-to-head overlay — compare any two players on the same radar
- Team badges — read-only club tags update automatically on player selection
- Hover tooltips — exact value and percentile on each dot
- Dual player cards with position and season minutes
- Stats table with percentile bars for both players
- Dark / Light theme toggle

---

## Metrics by Position

| Position | Metrics |
|---|---|
| Forward | Goals p90, xG p90, Shots p90, Shot Accuracy %, Key Passes p90, Dribbles Won %, Box Touches p90, Progressive Carries |
| Winger | Goals p90, xG p90, Key Passes p90, Dribbles Won %, Crosses p90, Progressive Carries, Pressures p90, Box Touches p90 |
| Midfielder | Pass %, Key Passes p90, Progressive Passes p90, Dribbles Won %, Pressures p90, Ball Recoveries p90, Carry Distance p90, G+A p90 |
| Defensive Mid | Pass %, Progressive Passes p90, Pressures p90, Tackles Won %, Interceptions p90, Recoveries p90, Aerial Duels Won %, Carry Distance p90 |
| Centre Back | Pass %, Progressive Passes p90, Tackles Won %, Interceptions p90, Clearances p90, Aerial Duels Won %, Recoveries p90, Pressures p90 |
| Full Back | Pass %, Key Passes p90, Crosses p90, Tackles Won %, Interceptions p90, Pressures p90, Dribbles Won %, Progressive Carries |

---

## Portfolio

| Project | Link |
|---|---|
| Title Race | [Live](https://leiderip.github.io/Premier-League-2024-25-Title-race/pl_position_race.html) |
| xG Race Explorer | [Live](https://leiderip.github.io/Premier-League-2024-25-xG-Title-race-/xG_Race_Explorer.html) |
| Season Shot Map | [Live](https://leiderip.github.io/Premier-League-2024-25-Shot-Map/Shot_Map.html) |
| Top Scorers vs xG | [Live](https://leiderip.github.io/Premier-League-2024-25-Top-Scorers-xG/Top_Scorers_xG.html) |
| Player Heatmap | [Live](https://leiderip.github.io/Premier-League-2024-25-Player-Heatmap/Player_Heatmap.html) |
| Scouting Radar | This project |

---

*Data © StatsBomb. MSc Applied Performance Analysis — University of Essex. MIT licensed.*
