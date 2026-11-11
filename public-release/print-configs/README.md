# Custom Bambu Studio print configurations
# Bambu Studio 自訂列印設定

**The updated ZIP contains 13 `.3mf` projects: eight original projects, two earlier H2C additions, and three stronger intake-pocket projects.**

**更新後 ZIP 包含 13 個 `.3mf` 專案：原始八個、先前兩個 H2C 專案，以及三個新版加厚吃球口口袋專案。**

The original eight projects are preserved snapshots; added H2C/P2S files preserve the supplied projects unchanged. The projects contain plate layouts and printer, nozzle, filament, and process settings. Pick the file that matches your hardware and filament; review the slice before printing. Geometry selection does not imply every printer/material profile has completed a separate test print.

這些是本次公開發佈所收錄的團隊自訂專案快照，包含列印盤配置、印表機、噴嘴、耗材與製程設定。請選擇符合設備與耗材的檔案，並在列印前檢查切片結果。收錄已確認的零件模型，不代表每一種印表機與耗材設定都已個別完成試印。

| Part / 零件 | Included configurations / 收錄設定 |
|---|---|
| Motor stand / 馬達支架 | P2S, 0.4 SF, Bambu PETG Basic |
| Bottom board / 底板 | P2S and X2D, 0.8 HF, JP PETG |
| Ball intake top / 吃求口（之後提供）—上片 | P2S, 0.6 HF and 0.8 HF, JP PETG |
| Ball intake bottom / 吃求口（之後提供）—下片 | P2S and X2D, 0.8 HF, JP PETG |
| Standard battery box / 電池匣 | P2S, 0.8 HF, JP PETG; 12 standing copies |

SF = standard-flow nozzle; HF = high-flow nozzle. All included projects use Textured PEI.

SF＝標準流量噴嘴；HF＝高流量噴嘴。收錄的專案均使用紋理 PEI 列印板。

Open in Bambu Studio, check the plate and filament, slice, and send. Saving edited projects can reset embedded overrides; keep the release copy for reference.

以 Bambu Studio 開啟，確認列印板與耗材後切片並傳送列印。儲存修改後的專案可能重設內嵌覆寫設定；請保留本次發佈的檔案作為參考。

Ongoing team configurations: [KY](https://github.com/Kowls0419/WRG-MASS-PRINTING/tree/main/KY), [JL](https://github.com/Kowls0419/WRG-MASS-PRINTING/tree/main/JL), [TC](https://github.com/Kowls0419/WRG-MASS-PRINTING/tree/main/TC).

持續更新的團隊設定：[KY](https://github.com/Kowls0419/WRG-MASS-PRINTING/tree/main/KY)、[JL](https://github.com/Kowls0419/WRG-MASS-PRINTING/tree/main/JL)、[TC](https://github.com/Kowls0419/WRG-MASS-PRINTING/tree/main/TC)。

## H2C additions / H2C 新增檔案 — 2026-10-31

- [FinalSumo.3mf](H2C/FinalSumo.3mf) — Sumo / 相撲機器人
- [new board.3mf](H2C/new%20board.3mf) — New bottom board / 新版底板

Original supplied H2C 0.4 mm PETG projects, unchanged; available as individual release Assets and in the updated ZIP.

保留原始 H2C 0.4 mm PETG 專案內容；可於發佈頁個別下載，亦包含於更新後 ZIP。

[H2C folder, previews and settings / H2C 專案、預覽與設定](https://github.com/Kowls0419/WRG-MASS-PRINTING/tree/main/H2C)

### Supplied print projects / 提供的列印專案

All three projects preserve the supplied settings and geometry byte for byte: 0.2 mm layers, four walls, 5/3 top/bottom shells, 15% infill. Check the selected hardware and filament in Studio before printing.

三個專案完整保留原始設定與模型：0.2 mm 層高、四道牆、上／下殼層 5／3 層、15% 填充。列印前請在 Studio 確認所選設備與耗材。

| Printer / 印表機 | Part / 零件 | Nozzle / 噴嘴 | Filament / 耗材 | Parts per plate / 每盤零件數 | Project / 專案 |
|---|---|---|---|---|---|
| H2C | 5 mm bottom / 5 mm 底層 | 0.4 SF | Red Bambu PETG Basic / 紅色 Bambu PETG Basic | 1 | [h2c-intake-pocket-bottom-5mm-red.3mf](H2C/h2c-intake-pocket-bottom-5mm-red.3mf) |
| H2C | 3 mm mid / 3 mm 中層 | 0.4 SF | Black Bambu PETG Basic / 黑色 Bambu PETG Basic | 1 | [h2c-intake-pocket-mid-3mm-black.3mf](H2C/h2c-intake-pocket-mid-3mm-black.3mf) |
| P2S | 3 mm mid / 3 mm 中層 | 0.4 HF | Black Generic PETG / 黑色 Generic PETG | 4 | [p2s-intake-pocket-mid-3mm-black.3mf](P2S/p2s-intake-pocket-mid-3mm-black.3mf) |
