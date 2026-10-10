# Converter — ESP mounting adapter / ESP 安裝轉接板

Adapter for mounting the ESP to the top of the battery box (電池匣), using Kyle’s supplied `converter.stl`. The model dimensions and hole positions are unchanged: **80 × 74.955 × 2 mm**.

此轉接板用於將 ESP 安裝於電池匣上方，採用 Kyle 提供的 `converter.stl`。模型尺寸與孔位保持原樣：**80 × 74.955 × 2 mm**。

## KY: print one first / KY：先試印一片

**[KY one-copy TEST1](KY-Converter-TEST1_P2S_0.8HF_TexturedPEI_JPPETG.3mf)** — P2S, 0.8 HF, black JP PETG; estimated **21 min / 10.4 g**.

**[KY 單片 TEST1](KY-Converter-TEST1_P2S_0.8HF_TexturedPEI_JPPETG.3mf)**：P2S、0.8 HF、黑色 JP PETG；預估 **21 分鐘／10.4 g**。

[TC five-copy TEST5](TC-Converter-TEST5_X2D_0.8HF_TexturedPEI_JPPETG.3mf) is available for the X2D; estimated 1 h 6 min / 52 g.

另提供 [TC 五片 TEST5](TC-Converter-TEST5_X2D_0.8HF_TexturedPEI_JPPETG.3mf)，適用於 X2D；預估 1 小時 6 分鐘／52 g。

Check that the ESP mounting holes and battery-box mounting holes line up, the screws fit, and the plate sits flat. Confirm the fit before using the mass-production drafts.

請確認 ESP 與電池匣的安裝孔位對齊、螺絲可安裝，且轉接板可平整貼合。確認尺寸合適後，再使用量產草稿。

## Full plates — WIP drafts / 滿盤配置—WIP 草稿

| File / 檔案 | Copies / 數量 | Estimate / 預估 |
|---|---|---|
| [KY mass draft — P2S 0.8 HF](KY-Converter-MASS-DRAFT_P2S_0.8HF_TexturedPEI_JPPETG.3mf) | 9 | 2 h 10 min / 94 g |
| [TC mass draft — X2D 0.8 HF](TC-Converter-MASS-DRAFT_X2D_0.8HF_TexturedPEI_JPPETG.3mf) | 9 | 1 h 55 min / 94 g |

These drafts remain in WIP. After the fit test passes, promote the corresponding mass-production files into KY/TC and publish them in a working print release. The existing special public release is a separate snapshot.

這些檔案暫留 WIP。尺寸試印通過後，再將對應的量產檔案移至 KY／TC，並另行發佈列印工作版本。既有的特別公開發佈仍為獨立快照。

KY’s revised settings keep lightweight 7% infill and slow the final surface after the first print showed infill texture and small gaps. Retest the KY one-piece plate before mass printing.

KY 的首次試印出現填充紋路與表面小孔，因此保留輕量的 7% 填充並降低頂面速度。請先重印 KY 單片測試，再進行量產。

## Print setup / 列印設定

- Flat on Textured PEI at 65°C; black JP PETG. Each printer retains its own hardware settings, temperatures, flow limit, and extruder mapping.
- 0.3 mm layers, 0.2 mm first layer, 3 walls; **3 top shells and 1 bottom shell**, with **7% gyroid infill**.
- Outer walls 80 mm/s with acceleration 1000 mm/s²; top surface **40 mm/s for KY**, 80 mm/s for TC. No supports, brim, or prime tower.
- KY’s one-copy test is centered on the bed. TC’s five-copy test uses two centered rows (3 + 2), with 3 mm gaps, printed by layer.
- Nine-copy plates use a rotated 3×3 grid with 3 mm gaps, printed by layer.

- 平放於 65°C 的紋理 PEI 列印板，使用黑色 JP PETG；各印表機保留自身的硬體、溫度、流量上限與擠出機對應設定。
- 層高 0.3 mm、首層 0.2 mm、3 道牆；**頂部 3 層、底部 1 層**，搭配 **7% Gyroid 填充**。
- 外牆速度 80 mm/s、加速度 1000 mm/s²；頂面速度 **KY 40 mm/s／TC 80 mm/s**。不使用支撐、brim 或擦拭塔。
- KY 單片試印置於列印板中央。TC 五片試印採置中的兩排配置（3 + 2），間距 3 mm，逐層列印。
- 九片滿盤採旋轉的 3×3 配置，間距 3 mm，逐層列印。

Open the matching .3mf in Bambu Studio, check the black filament assignment, slice, and send. Keep the original project copy when saving local changes.

以 Bambu Studio 開啟符合印表機的 .3mf，確認黑色耗材對應後切片並傳送列印。若要另存修改，請保留原始專案作為參考。

Source mesh: [Converter.stl](Converter.stl).

原始網格：[Converter.stl](Converter.stl)。
