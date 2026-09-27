# WRG Mass Printing — Bambu Studio print files

Project files (`.3mf`) for the WRG robotics team's mass-printed parts, with their full edit history.
Every earlier version of a file is a commit — use **History** on any file (GitHub) to see or download old versions.

Folder layout mirrors the team Google Drive folder `WRG MASS PRINTING`:

- root — current files in use (motorstands, JL battery holders, older 0.4/0.6 baselines)
- `max/` — 0.8mm High Flow mass-print files (FinalBottom, motorstand, battery holder)
- `temp/` — work in progress (Body2, BatTop variants)
- `Testing/` — older test files
- `temp/interstitial-test-2up/` — abandoned stack-printing (PLA interface) experiments

## Current files

| File | Printer / nozzle | Filament | Plate / bed | Layer | Walls | Top/bottom | Infill | Max flow (mm³/s) | Copies |
|---|---|---|---|---|---|---|---|---|---|
| `JL-BatTop3v3-Standard_P2S_0.4SF_TexturedPEI_JPPETG.3mf` | P2S 0.4 SF | JP PETG Yellow | Textured PEI 65°C | 0.2 | 4 | 3/3 | 7% | 12 | 8 |
| `JL-BatTop4v4-SpecialEd_P2S_0.4SF_TexturedPEI_JPPETG.3mf` | P2S 0.4 SF | JP PETG Yellow | Textured PEI 65°C | 0.2 | 4 | 5/5 | 7% | 12 | 8 |
| `JL-motorstand_P2S_0.4_SuperTack_BambuPETG.3mf` | P2S 0.4 SF | Bambu PETG Basic | Supertack 60°C | 0.3 | 4 | 3/3 | 20% | 15 | 36 |
| `KY-FinalBottom_P2S_0.6HF_TexturedPEI_JPPETG.3mf` | P2S 0.6 HF | JP PETG | Textured PEI 65°C | 0.2 | 4 | 5/5 | 7% | 24 | 1 |
| `KY-motorstand_P2S_0.6HF_TexturedPEI_JPPETG.3mf` | P2S 0.6 HF | JP PETG | Textured PEI 60°C | 0.3 | 4 | 3/3 | 20% | 28 | 36 |
| `TC-FinalBottom_X2D_0.4HF_TexturedPEI_JPPETG.3mf` | X2D 0.4 HF | JP PETG | Textured PEI 60°C | 0.2 | 4 | 5/3 | 7% | 16 | 1 |
| `Testing/4v4Funnel.3mf` | P2S 0.6 HF | JP PETG | Textured PEI 65°C | 0.2 | 4 | 5/5 | 20% | 24 | 4 |
| `Testing/Batt_P2S_0.4_SuperTack_JPPETG.3mf` | P2S 0.4 SF | JP PETG Yellow | Supertack 65°C | 0.2 | 4 | 5/5 | 7% | 12 | 8 |
| `max/KY-BatTop3v3-Standard_P2S_0.8HF_TexturedPEI_JPPETG.3mf` | P2S 0.8 HF | JP PETG | Textured PEI 65°C | 0.3 | 3 | 2/2 | 7% | 28 | 8 |
| `max/KY-FinalBottom_P2S_0.8HF_TexturedPEI_JPPETG.3mf` | P2S 0.8 HF | JP PETG | Textured PEI 65°C | 0.3 | 3 | 3/3 | 7% | 28 | 1 |
| `max/KY-motorstand_P2S_0.8HF_TexturedPEI_JPPETG.3mf` | P2S 0.8 HF | JP PETG | Textured PEI 65°C | 0.3 | 4 | 3/3 | 20% | 28 | 36 |
| `max/TC-FinalBottom_X2D_0.8HF_TexturedPEI_JPPETG.3mf` | X2D 0.8 HF | JP PETG | Textured PEI 65°C | 0.3 | 3 | 3/3 | 7% | 28 | 1 |
| `temp/BatTop_P2S_0.8HF_TexturedPEI_GenericPETG.3mf` | P2S 0.8 HF | Generic PETG | Textured PEI 65°C | 0.3 | 3 | 3/3 | 7% | 28 | 1 |
| `temp/BatTop_P2S_0.8HF_TexturedPEI_JPPETG.3mf` | P2S 0.8 HF | JP PETG | Textured PEI 65°C | 0.3 | 3 | 3/3 | 7% | 28 | 1 |
| `temp/BatTop_P2S_0.8HF_TexturedPEI_JPPETGCF.3mf` | P2S 0.8 HF | JP PETG-CF | Textured PEI 80°C | 0.3 | 3 | 3/3 | 7% | 18 | 1 |
| `temp/JL-motorstand_P2S_0.6HF_SuperTack_BambuPETG.3mf` | P2S 0.6 HF | Bambu PETG Basic | Supertack 65°C | 0.3 | 4 | 3/3 | 20% | 21 | 36 |
| `temp/KY-Body2_P2S_0.8HF_TexturedPEI_JPPETG.3mf` | P2S 0.8 HF | JP PETG | Textured PEI 65°C | 0.3 | 4 | 2/2 | 7% | 28 | 1 |

## Notes

- Name format: `OWNER-Part_Printer_Nozzle_Plate_Filament.3mf` (KY = Kyle, JL = Justin, TC = X2D owner). `SF` = standard-flow nozzle, `HF` = high flow.
- PETG max volumetric flow on 0.6/0.8 HF nozzles is capped at 28 mm³/s (35 caused under-extrusion). 0.4 standard nozzles stay at 12–15.
- Saving a file in Bambu Studio strips its `different_settings_to_system` list (the "these settings are overridden" list). Slice and send without saving, or repair the file after saving.
- BatTop 3v3 standard files include a height-range modifier (z 31.4–34 mm) that makes the screw frame solid; check it appears under each object's **Layers** item.
