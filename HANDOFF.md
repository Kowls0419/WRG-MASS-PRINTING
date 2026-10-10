# HANDOFF

## Goal
The 2026-09-27 release of `KY/KY-BatTop-Standard_P2S_0.8HF_TexturedPEI_JPPETG.3mf` used the WRONG STL.
Build a WIP test project from the correct mesh `WIP/BatTop for standard.stl`, oriented for best
supported print (quality first, then material), for Kyle to test-print tonight (2026-09-29).

## Done
- Codex built TEST2 (native orientation). Claude reviewed: the native orientation put the battery space's 3,500 mm² ceiling on 24 mm supports. Kyle confirmed the battery sits in the deep 24 mm space, so Claude flipped the mesh 180° about X (vertices x,-y,34-z; build Y 123.25). The file loads in the CLI like TEST1 (exit 239). Bed contact 1313 mm², overhang 4115 mm².
- Committed + pushed to main: TEST2 file, source STL, README WIP row.

## In progress
- 2026-09-30: TEST2 committed (c85f994): flat and upside down, Tree default style, auto brim 5 mm, top Z 0.6, independent support layers off, base spacing 2.5, XY 0.8. Kyle saved in Studio, which wiped the override list; Claude restored it (48 keys). Kyle is considering a VERTICAL orientation (not saved in the file yet). If adopted: outer brim 5 mm, Tree Strong.
- Waiting on Kyle's test print tonight (open in Studio, slice, send without saving).

## Next
1. Kyle test-prints tonight. If good → replace the mesh in the KY 8-copy release file and note the fix in a new release.

## Gotchas
- Released KY file has NO `different_settings_to_system` key (was wiped); restore it from TEST1 when swapping in the new mesh.
- Headless BambuStudio CLI always exits 239 'process not compatible with printer', even for good files; exit 250 = model failed to load.
- Battery sits in the deep 24 mm space → print upside down (native z=34 face on bed).
- Work only on `main` (repo rule). No branches, no PRs.
- Don't re-save in Bambu Studio — it wipes `different_settings_to_system`. Follow `~/.claude/skills/bambu-3mf/SKILL.md`.
- Don't touch `KY/` or the released file until the test print passes.

## Delegated
### Codex: rebuild BatTop Standard test file from correct STL
- **Scope (may write):** new file `WIP/KY-BatTop-Standard-TEST2_P2S_0.8HF_TexturedPEI_JPPETG.3mf`; README.md WIP table (add one row); this HANDOFF.md (append results). Scratch work under `/tmp` or a scratch dir.
- **Off-limits:** everything in `KY/`, `JL/`, `TC/`, `releases/`, other WIP files, git commits/pushes.
- **Settings source:** copy all process/filament/printer settings + override list from `KY/KY-BatTop-Standard_P2S_0.8HF_TexturedPEI_JPPETG.3mf` (Tree Slim, trunk angle 7°/2 walls, top gap 0.5 / XY gap 0.6, 0.3 layer, 3 walls, 3-1 shells, 7% infill, flow 28, 230 °C). 1 copy for the test plate.
- **Done =** file opens in Bambu Studio with the new mesh, oriented and placed on the plate, supports enabled, override list intact; README row added; report the chosen orientation + reasoning here.

### Codex: result
- **Status:** WIP TEST2 built and archive validated; manual test print pending.
- **Files written:** `WIP/KY-BatTop-Standard-TEST2_P2S_0.8HF_TexturedPEI_JPPETG.3mf`, `README.md` (one WIP row), this `HANDOFF.md` entry. Analysis script and preview PNGs are under `/private/tmp/claude-501/-Users-kyle-Library-CloudStorage-GoogleDrive-kyleyang0419-gmail-com--shortcut-targets-by-id-1kxogleB79tXoCQxdjdixNj0m9beZRwHz-To-be-printed----Queue-WRG-MASS-PRINTING/73fddd10-69c3-40d6-854c-1eecf079e7a8/scratchpad/`.
- **Orientation:** STL native orientation, identity rotation; bottom (native -Z) on bed, battery pocket/floor face upward. Applied XY translation `(128, 132.75)` mm and Z translation `0`; plate bounds X `96–160`, Y `78.25–177.75`, Z `0–34` mm. This preserves clean upward-facing pocket/mating surfaces, vertical mounting holes, and a broad 976.7 mm² flat contact face; the overhangs are under the floor/frame rather than on the pocket surface. Tree Slim supports stay enabled.
- **Candidate measurements:** Triangle area with surface angle >45° below horizontal, excluding bed-contact faces: native -Z `4451.3 mm²` (bed contact `976.7 mm²`, projected-area × height proxy `114457 mm³`); inverted +Z `4114.9 mm²` (bed contact `1313.1 mm²`, proxy `45749 mm³`) but pocket floor faces support; side +Y `1158.8 mm²` (bed contact `214.0 mm²`, proxy `96483 mm³`) but makes the part 99.5 mm tall and mounting holes horizontal. Other axis faces: -Y `1336.3`, ±X `5933.0 mm²`; largest additional convex-hull side planes had only `1.4 mm²` flat area and `1365.6–5963.8 mm²` overhang. Proxy is geometric, not sliced support volume.
- **Validation:** Binary STL has 752 unique vertices, 1552 triangles, watertight edge incidence, positive signed volume. ZIP CRC check and XML parse pass. New mesh counts exactly match STL and `mesh_stat`; one build item and one plate instance. All 580 values from the release JSON are unchanged; its missing `different_settings_to_system` was restored exactly from TEST1 (3 elements, 47 print override names). Supports enabled; Tree Slim / 7° / 2 support walls / 0.5 top gap / 0.6 XY gap / 0.3 layer / 3 walls / 3-1 shells / 7% infill / flow 28 / 230°C / 65°C confirmed.
- **Commands:** NumPy STL geometry and convex-hull plane analysis; generated PNG previews (`upright_-Z.png`, `inverted_+Z.png`, `side_+Y.png` plus `_top.png` views); ZIP/XML/JSON/placement validation; BambuStudio CLI `--slice 1` attempted for TEST1 and TEST2.
- **Claude check:** CLI successfully parses TEST2 but refuses slicing both TEST1 and TEST2 with `process not compatible with printer` (exit 239), even with a copied local preset directory, so no trustworthy support/filament estimate is available. Open and slice TEST2 in Studio to verify the profile resolves before Kyle prints; do not save it in Studio because that can erase the override list. The release's own override key was already missing before this task.

### Codex: diff peer's successful TEST2 against repo TEST2 (2026-09-30)
- **Why:** a teammate printed their copy of TEST2 successfully, and the supports came off easily. We want to know exactly what differs from the repo version.
- **Inputs (read-only):** the peer's file is at `<scratchpad>/peer_TEST2.3mf` (copied from Messages); the repo file is `WIP/KY-BatTop-Standard-TEST2_P2S_0.8HF_TexturedPEI_JPPETG.3mf` (commit c85f994).
- **Scope:** READ-ONLY. Don't modify any repo file except appending a `### Codex: result (peer diff)` entry here. No commits.
- **Done =** a list of every differing setting in project_settings (old → peer), the override list in both files, orientation and placement (mesh bbox + build transform), object-level overrides in model_settings.config, plate/brim, and anything else that differs. Also a short verdict on which differences likely explain the easy support removal.
### Claude: result (peer diff) — Codex couldn't run (model config error, then launch blocked by the permission check)
- The peer file is the SAME geometry and orientation (flat, upside down, 34 mm tall), with 2 copies. But it was re-profiled to **P2S 0.4 standard nozzle**, the "0.20mm Standard @BBL P2S" system preset, Generic PETG at 255 °C / 70 °C plate, and an override list of 2 keys. So our 0.8 HF tuning was NOT used.
- Support differences (repo → peer): top Z 0.6→0.2, XY 0.8→0.35, independent layers 0→1, build-plate-only 1→0, expansion 1→0, interface pattern rectilinear→auto, trunk angle 7→5, tree walls 2→auto, line width 0.82→0.42, fan 30-40%→40-90%. Style (default), base spacing (2.5) and interface layers are the same.
- Takeaway: the orientation is validated. The easy removal most likely comes from thin 0.42 support lines + 0.2 layers + high fan, which can't transfer directly to the 0.8 HF file. The peer file is a good base for a 0.4 SF version.
### 2026-09-30 17:21 — Kyle's Studio save of TEST2 (committed after review)
- Orientation: **vertical, standing on its end** (99.5 mm tall; build transform rotated, mesh unchanged).
- Settings: support style default → Tree Hybrid, top Z 0.6 → 0.4, independent support layers off → on, top shells 3 → 2, bottom shells 1 → 2, filament colour yellow. Brim stays auto 5 mm.
- The save DELETED `different_settings_to_system` entirely. Claude restored it (48 keys = old list + the 5 changed keys).
- Watch: top Z 0.4 isn't a multiple of 0.3 and independent layers are on again, so the gap under the tabs may round up (last time it showed as 3 layers).
### 2026-09-30 — seam fix on TEST2
- Visible gap along the aligned Z seam (inside corner, full 99.5 mm height). Set seam_gap 15% → 0%, seam_slope_type none → external (scarf seam on outer walls), seam_slope_conditional 1 → 0 (so the scarf applies to this sharp-cornered part). All 3 added to the override list (now 51).
- If the seam is still visible: next try is pressure advance (currently off, PA 0.02), or painting the seam onto an outside corner.
### 2026-09-30 — JL motorstand 0.4 SF (Bambu PETG Basic black)
- Built `WIP/JL-motorstand_P2S_0.4SF_SuperTack_BambuPETG.3mf` from `JL/JL-motorstand_P2S_0.6HF_SuperTack_BambuPETG.3mf` (source unchanged).
- Printer keys set to real P2S 0.4 standard values (checked against the peer's 0.4 file): nozzle 0.4, volume type Standard, preset "Bambu Lab P2S 0.4 nozzle", inherits "0.20mm Standard @BBL P2S", filament "Bambu PETG Basic @BBL P2S".
- Layer 0.3→0.2, line widths 0.42 (inner/sparse 0.45, first layer 0.5). Walls 4×0.62=2.48 mm → 6 walls ≈2.67 mm. Shells 3×0.3=0.9 mm → 5×0.2=1.0 mm. Flow 21→12 (unverified). Filament retraction 0.4→nil (use printer 0.8). Temps 250/245, SuperTack 65 °C, 20% gyroid, 36 copies unchanged. Override list 37 keys; process_settings_1 updated.
- Headless slice succeeded: 383 g, 49,073 s (~13 h 38 m).
### 2026-09-30 — reorganised + release 2026-09-30 published
- Active folders now: KY/KY-FinalBottom, TC/TC-FinalBottom, JL/JL-motorstand_P2S_0.4SF (commit c122ca7).
- KY-BatTop-Standard + JL-BatTop-Standard moved to WIP/ (wrong mesh). KY 0.6HF motorstand → KY/archive/, JL 0.6HF motorstand → JL/archive/.
- Tag + GitHub release `2026-09-30` published with those 3 files (now "Latest"). Notes: releases/2026-09-30.md.
- Still open: the 2026-09-27 release still carries both wrong-mesh BatTop assets. Ask Kyle before editing or deleting them.
- JL motorstand 0.4 SF switched to Textured PEI 70 °C and renamed `JL-motorstand_P2S_0.4SF_TexturedPEI_BambuPETG.3mf` (a0d8f27). Release asset swapped and notes edited. The tag 2026-09-30 still points at c122ca7.
- JL motorstand 0.4 SF now uses the official profile `Bambu PETG Basic @BBL P2S 0.4 nozzle` (flow 15, retraction 0.4, preheat delta 0), commit a76557d; release asset re-uploaded. Filament profile names on the P2S ALWAYS have the nozzle suffix.
### 2026-10-01 — TEST3: real Standard BatTop mesh
- Kyle: the mesh in `WIP/JL-BatTop-SpecialEd_P2S_0.4SF...` is actually the STANDARD BatTop (60 needed). It's 64×115×34 mm, 2600 tris, 18.0 cm³. TEST2's STL is 64×99.5×34 mm.
- Built `WIP/KY-BatTop-Standard-TEST3_P2S_0.8HF_TexturedPEI_JPPETG.3mf` from TEST2 (all settings, override list of 51), with the SpecialEd mesh rotated 180° about X into TEST2's frame. Same vertical build transform, z=57.5, so it's 115 mm tall at 96–160 × 111–145. Dropped the thumbnails, plate_1.json and TEST2's layer_heights_profile.txt (mesh-specific). The CLI loads it (exit 239, same as TEST2).
- Restored TEST2 from git: Kyle's Studio save had only deleted the override list.
- Open question: is `BatTop for standard.stl` / TEST2 now obsolete?
### 2026-10-02 — Standard vs SpecialEd sorted out
- Kyle verified: TEST3 mesh (64×115×34) = STANDARD; the old TEST2 / `BatTop for standard.stl` mesh (64×99.5×34) = SPECIAL edition. TEST2 was renamed `KY-BatTop-SpecialEd-TEST2_...`.
- TEST3: Kyle's Studio save laid it flat (tabs on bed) with support style Default. Claude restored the override list (51 keys).
- All other WIP files were moved to archive/ (not deleted). WIP now holds only those 2 files.
### 2026-10-03 — TEST3 orientation test
- Kyle put 2 copies on the plate: one flat and upside down, one standing on end. His save deleted the override list and Claude restored it (51). The plate was "by object", which can't work: P2S rod clearance is 32.5 mm, the copies are 34 and 115 mm. Set to "by layer" at Kyle's OK.
- Removed the inherited 32–33.8 mm layer range (1 wall, then solid with 6 walls) from the standing copy. Kept it on the flat copy, where it's the screw-tab top. TEST2 (SpecialEd, standing) still has that range: ASK Kyle about removing it.
- 2026-10-03: removed the old-STL 32–33.8 mm layer-range rules (layer_config_ranges.xml) from TEST2 and TEST3 entirely, at Kyle's request. No active file (KY/JL/TC/WIP) has layer ranges now. Archived old-mesh files still contain them (left as history).
- 2026-10-03: Kyle added plate 2 to TEST3 (3 standing copies, by layer) and is printing it now. Override list restored (51). Commit below.
- 2026-10-03: test print of plate 2 (3 standing) went well and supports came off easily, but the central support was bulky. Chosen orientation = STANDING. Supports changed: style default→tree_slim, expansion 1→0, interface spacing 0.5→0.8, top Z 0.4→0.6, independent support layers 1→0. Kept 2 trunk walls and angle 7 for the tall tab trees.
- 2026-10-03: Kyle felt the supports sat too far from the part, so both gaps were halved: top Z 0.6→0.3 (exactly 1 layer), XY 0.8→0.4.
- 2026-10-03: Kyle added plate 3 (1 standing copy) with an adaptive layer-height profile (0.16–0.56 mm, object 7 only), sliced and printed it, then saved. Override list restored (51). Plates 1–2 have no adaptive profile.
- 2026-10-03: standing side walls swayed when the nozzle passed. Anti-sway set on all speed slots: default accel 5000→2000, outer wall accel 3000→1000, travel accel 6000→2500, travel 600→300, outer wall 180/500→80, inner wall 220/600→120, Z-hop Auto→Spiral Lift. Override list 55.
### 2026-10-04 — Standard BatTop mass-print file
- Kyle skipped a further test. Built `KY/KY-BatTop-Standard_P2S_0.8HF_TexturedPEI_JPPETG.3mf` from TEST3: 12 standing copies (3×4 grid, x 46/128/210, y 38/98/158/218, footprint 14–242 × 21–235 mm, gaps 18 mm × 26 mm), all TEST3 settings (override list 55), by layer, and plate 3's adaptive layer profile copied to all 12 copies (same mesh and orientation). No thumbnails until the first save. The CLI loads it (exit 239 like the tests).
- 60 needed = 5 plates.
### 2026-10-04 — JL BatTop Standard 0.4 SF
- `JL/JL-BatTop-Standard_P2S_0.4SF_TexturedPEI_JPPETG.3mf`: the KY mass-plate geometry (12 standing copies) + the old JL 0.4 SF settings base (3-slot printer arrays, JP PETG Yellow, flow 12, 230/225, retraction 0.8). KY print decisions ported: Tree Slim, expansion 0, base spacing 2.5, XY 0.4, independent layers off, seam fix, anti-sway speeds, Spiral Z-hop. Scaled: top Z 0.3→0.2 (1 layer), interface spacing 0.8→0.4, walls 3×0.82→6×~0.44 (2.67 mm), shells 2×0.3→3×0.2. Nozzle tag High Flow→Standard. Override list 61 (old file had none).
- The adaptive profile was dropped (0.8-nozzle heights). Kyle/Justin need to click Adaptive in Studio. CLI full slice: 330 g, 36 h 17 m, support ~5.8 h.
- 2026-10-04: JL BatTop moved JL/→WIP/ (not released). Release 2026-10-04 published (Latest): KY BatTop Standard (new) + KY bottom + TC bottom + JL motorstand 0.4 SF.
- 2026-10-04: Textured PEI bed temp 65→70 °C (plus first layer) on all 4 BatTop files (KY release, JL WIP, TEST2, TEST3), added to override lists. The 2026-10-04 release asset was replaced.
- 2026-10-04: Kyle reports the 12-copy KY BatTop Standard plate printed successfully. README and release notes updated.

### 2026-10-04 — 4v4 Funnel test files (Top + Bottom)
- Source: `~/Desktop/4v4foronecar.3mf` (Studio 2.08, 0.4 PLA defaults). Plate 1 "2 bottom per bot" = 4× bottom mesh (225×85.7×2, object_6.model); plate 2 "1 top per bot" = 4× top mesh (225×70×2, object_3.model). Need 106 bottoms / 53 tops, 4 per plate (tracker: 27 + 14 plates).
- Built `WIP/KY-FunnelBottom_P2S_0.8HF_TexturedPEI_JPPETG.3mf` (plate 1 only, grey): FinalBottom project_settings verbatim (65 °C, 0.3, 3 walls, 3-3, 7%, no brim, override list 23). CLI exit 239 like all 0.8 HF files, so check the slice in Studio.
- Built `WIP/JL-FunnelTop_P2S_0.6HF_TexturedPEI_JPPETG.3mf` (plate 2 shifted −307.2 mm X onto plate 1, black): archived KY motorstand 0.6 HF JP PETG base + FinalBottom choices (no brim, skirt 1, 7%/25%, 65 °C, fan 30–40, close fan 5), 4 walls. Override list 26. CLI slice OK: 1 h 24 m, 62.5 g, 7 layers.
- Build script: scratchpad `build.py`. Removing objects needs `<assemble_item>` entries removed too, or the load fails (exit 250).
- Next: Justin prints the top (black), Kyle prints the bottom (grey) on 2026-10-05; then move to JL/ and KY/ if good.

### Codex: review the 4v4 Funnel test files (delegated 2026-10-04)
- **Scope:** READ-ONLY review of commit d5c4bee: `WIP/KY-FunnelBottom_P2S_0.8HF_TexturedPEI_JPPETG.3mf`, `WIP/JL-FunnelTop_P2S_0.6HF_TexturedPEI_JPPETG.3mf`, README WIP rows. Only write: append `### Codex: result (funnel review)` here. No commits, no edits to .3mf/README.
- **Check:** geometry/plate integrity vs source `~/Desktop/4v4foronecar.3mf` (right mesh per file, 4 copies, on the 256×256 bed, no dangling objects/assemble items/rels); settings vs donors `KY/KY-FinalBottom_P2S_0.8HF_TexturedPEI_JPPETG.3mf` (KY should be identical except print_settings_id + colour) and `KY/archive/KY-motorstand_P2S_0.6HF_TexturedPEI_JPPETG.3mf` (JL base + FinalBottom choices); `different_settings_to_system` covers every changed key; array lengths valid; README numbers match.
- **Done =** list of real problems (or "none"), with key/file and suggested fix.

### Codex: result (funnel review) — recorded by Claude (Codex had no write access)
- Both files: zip/XML/JSON OK, correct mesh ×4, on bed (≥4.6 mm margin), no dangling refs, settings diffs vs donors as intended, README rows match.
- Flagged: (1) KY override list missed keys that differ from the system "0.40mm Standard @BBL P2S 0.8 nozzle" (7% gyroid, zig-zag, first-layer speeds…), inherited from FinalBottom. (2) 3-entry process arrays vs 2 printer variants: Studio's own output (FinalBottom is the same), left alone. (3) JL filament_settings_id names a 0.4 nozzle profile: it's the custom JP PETG preset from the 0.6 HF motorstand, values embedded, left alone.
- 2026-10-04 Claude fix (Kyle OK'd funnel only, NOT FinalBottom): added 17 keys to the KY funnel override list (23→40), no values changed. JL list was already complete. FinalBottom still has the same gaps, and Kyle said not to change it.
- 2026-10-04: at Kyle's request, released BOTH funnel files before their test print: moved WIP→KY/ and JL/, README rows marked "⚠️ released before test print", new tag + GitHub release `2026-10-04b` (notes releases/2026-10-04b.md). The `2026-10-04` release left untouched.
- Next: test prints 2026-10-05. If good, remove the ⚠️ in README and edit the 2026-10-04b release notes.
- 2026-10-04: Justin got "no preset inside project applied". Cause: the funnel files renamed print_settings_id ("Funnel - P2S 0.xHF - Functional") but had no embedded `Metadata/process_settings_1.config`, so Studio couldn't find that preset. Added one to both files (from=project, inherits the system 0.6/0.8 preset, plus every process key on the override list and brim_type), like the motorstand file has. Release 2026-10-04b assets replaced. Gotcha: any new print_settings_id name NEEDS an embedded process_settings_1.config.
- 2026-10-04: Kyle will also print tops. Built `WIP/KY-FunnelTop_P2S_0.8HF_TexturedPEI_JPPETG.3mf`: JL top geometry + KY-FunnelBottom settings and embedded process preset (override list 40), black. CLI exit 239 (normal for 0.8 HF). Not released.
- 2026-10-04: KY-FunnelTop moved WIP→KY/ and added to release 2026-10-04b (asset + notes updated) at Kyle's request.
### 2026-10-06 — KY BatTop Standard in Bambu PETG Basic Yellow
- `WIP/KY-BatTop-Standard_P2S_0.8HF_TexturedPEI_BambuPETG.3mf` = the released KY JP PETG file with official `Bambu PETG Basic @BBL P2S 0.8 nozzle` values: 250/245 °C, filament retraction 0.4, max flow 21 (the official list has 21/23 per nozzle variant and the slot mapping is unverified, so 21 went on all slots = safe side), fan max 60, close fan first 3 layers, preheat delta 0, density 1.25, GFG00, yellow. Plates 70 °C. Geometry, supports, anti-sway and adaptive profile unchanged. Override list 62. CLI exit 239 (loads).
### 2026-10-06 — TC FunnelBottom (X2D 0.8 HF, grey)
- `TC/TC-FunnelBottom_X2D_0.8HF_TexturedPEI_JPPETG.3mf` = KY-FunnelBottom geometry/plate (4 per plate) + TC-FinalBottom project settings (X2D hardware, JP PETG X2D profile, 6-slot arrays untouched) + an embedded process preset renamed "Funnel - X2D 0.8HF - Functional". Grey #8E9089. ironing_inset 0.21→0.31 (KY). Override list 45. Filament 1 → extruder 1 (0.8 Direct Drive, full 256 bed). The CLI behaves like released TC-FinalBottom. Added to release 2026-10-04b.
### 2026-10-06 — no more orange "modified" values in Studio
- Cause: the embedded `Metadata/process_settings_1.config` presets were missing (4 KY/WIP BatTop + KY FinalBottom) or held only a few keys. TC's also inherited "0.20mm Standard @BBL X2D" (the 0.4-nozzle preset) and had a stale wall_loops 4. So Studio compared the file against the system preset and painted every customised value orange.
- Fix (all 12 files in KY/JL/TC/WIP): rebuilt each preset as from=project, inherits the correct system parent (P2S 0.8 → 0.40mm Standard @BBL P2S 0.8 nozzle, P2S 0.6 → 0.30mm … 0.6 nozzle, P2S 0.4 → 0.20mm Standard @BBL P2S, X2D 0.8 → 0.40mm Standard @BBL X2D 0.8 nozzle), plus EVERY process key whose project value differs from that parent (26–75 keys). Name = print_settings_id. inherits_group[0] set to the same parent where present. The CLI result is identical before/after for every file. Script: scratchpad/fixpreset.py.
- Gotcha: after any settings edit, regenerate the preset or the changed keys turn orange again.
- 2026-10-06: release `2026-10-06` (Latest) = pending prints only: JL-FunnelTop, KY-FunnelTop, KY-FunnelBottom, TC-FunnelBottom, KY-BatTop-Standard.
### 2026-10-06 — TC FunnelBottom: adopted Kyle's clean Studio save
- Kyle did "save preset to project" + save in Studio (copy in ~/Downloads), which turned it fully grey. Studio re-laid it for the real "Bambu Lab X2D 0.8 nozzle" preset: nozzle_diameter 0.8/0.8 (ours said 0.8/0.4), 4-slot variant arrays (not 6), X2D-0.8 default speeds (top surface 200→150, bridge 50→30, gap infill 250→50, accels), a 30-key preset, and an override list of 23. All print-relevant values are unchanged. Adopted as-is, plus 19 safety keys added back to the override list (JP PETG flow 28, plate 65 °C, shells, line widths, layer limits) → 42.
- Lesson: Studio's own "save preset to project" output is the reference for a clean, grey file. TC-FinalBottom has the same 0.8/0.4 + 6-slot leftovers and could get the same treatment.

### Codex: collect all single original STL meshes (2026-10-09)
- **Status:** complete. Kyle explicitly requested all, including archives.
- **Files changed:** new `Original STLs/` (11 current/archived part STLs, 17 experimental connected-shell STLs in `Experimental/`, README.md, sources.json); root README.md collection link; this entry.
- **Commands run:** Python ZIP/XML/STL extraction and NumPy geometry deduplication via `/private/tmp/wrg_extract_stls.py`, `/private/tmp/wrg_finish_stls.py`, `/private/tmp/wrg_verify_stls.py`; binary STL round-trip validation; SHA-256 checks of all 78 original input files.
- **Findings:** all 78 3MF/STL inputs readable (initial Drive timeouts cleared). Six current designs plus five archived revisions; experimental stacks split into single connected shells and deduplicated. Standard and Special Edition names follow verified geometry, not obsolete source labels. Per-file provenance retained in sources.json. Original source files unchanged.
- **Next / Claude check:** none required for collection. These are recovered mesh exports in millimetres, with source mesh orientation/coordinates; print settings and plate placements are not included. Different triangulations remain separate. No commits or pushes.

### Codex: 2026 WRG KCIS-XG Public Release (2026-10-10)
- **Goal:** publish a fixed public release in the existing GitHub repo, MIT licensed, English primary / Traditional Chinese secondary. Kyle explicitly approved MIT and organizing the existing repo.
- **Done:** `public-release/` contains five single-part STLs, five converted STEP solids, eight unchanged current KY/JL/TC .3mf snapshots in `print-configs/`, bilingual README files, MIT license, source manifest and validation.json. Root README links the public collection; release notes are in `releases/2026-wrg-kcis-xg-public.md`. Local ZIP/checksums are in ignored `releases/assets/` (Drive-synced).
- **Validation:** all five STL meshes closed by edge incidence; STEP conversion via OpenCascade 8.0.1 sews triangle faces, makes a solid, merges coplanar faces, then reimports STEP. Each result is valid, one solid, with matching dimensions (0.0001 mm) and volume (relative 1e-6). ZIP CRC, model/config counts, Markdown links and source/config SHA-256 checks pass. Active project files unchanged.
- **Commands:** temporary conversion environment `/private/tmp/wrg-step-venv`; conversion/preparation scripts under `/private/tmp/wrg_*`; geometry, ZIP, hashes and links verified with Python. GitHub repo initially PRIVATE and had no license.
- **Status / Next:** COMPLETE. Release commit `be2b555` pushed to main; GitHub repository is PUBLIC and recognizes MIT. Published tag `2026-wrg-kcis-xg-public` with title `2026 WRG KCIS-XG Public Release`, marked Latest, 12 uploaded assets (complete ZIP, 5 STL, 5 STEP, checksum list). Anonymous public ZIP download verified byte-for-byte against the local archive; ZIP CRC passes. No further work required.
- **Published URL:** https://github.com/Kowls0419/WRG-MASS-PRINTING/releases/tag/2026-wrg-kcis-xg-public
- **Gotchas:** STEP is a faceted mesh-derived solid, not recovered parametric CAD. WIP, Special Edition and experimental parts excluded from the five-design public snapshot. Current geometry selection does not certify every printer/material preset was individually test-printed. No ongoing print-file reorganization or settings edits are needed.
