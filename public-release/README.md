# 2026 WRG KCIS-XG Public Release

Open-source 3D-printable parts from the WRG KCIS-XG team, released under the [MIT License](LICENSE).

WRG KCIS-XG 團隊的開源 3D 列印零件，採用 [MIT 授權條款](LICENSE)公開。

This special release is a fixed snapshot of the five selected current designs. The team continues printing and modifying its working projects separately; this release does not require updates for every printing change.

本次特別發佈是五種目前選定設計的固定快照。團隊仍持續列印並修改工作專案，無須為每次列印調整更新本次發佈。

## Parts / 零件

Each STL contains one part. Dimensions are in millimetres.

每個 STL 檔案包含一個零件，尺寸單位為毫米。

| Part / 零件 | Dimensions / 尺寸 (mm) | STL | STEP |
|---|---|---|---|
| Motor stand / 馬達支架 | 37 × 37 × 38 | [STL](stl/motor-stand.stl) | [STEP](step/motor-stand.step) |
| Bottom board / 底板 | 150 × 158 × 4 | [STL](stl/bottom-board.stl) | [STEP](step/bottom-board.step) |
| Funnel top / 漏斗上片 | 225 × 70 × 2 | [STL](stl/funnel-top.stl) | [STEP](step/funnel-top.step) |
| Funnel bottom / 漏斗下片 | 225 × 85.7 × 2 | [STL](stl/funnel-bottom.stl) | [STEP](step/funnel-bottom.step) |
| Standard battery box / 標準版電池盒 | 64 × 115 × 34 | [STL](stl/battery-box-standard.stl) | [STEP](step/battery-box-standard.step) |

The standard battery box is the verified 115 mm version, called “BatTop Standard” in the print projects.

標準版電池盒採用已確認的 115 mm 版本，在列印專案中稱為「BatTop Standard」。

## Custom print configurations / 自訂列印設定

[Open the custom .3mf folder](print-configs/) for Bambu Studio plate layouts and printer/material settings. These are separate from the single-part model files. Use the configuration matching your printer, nozzle, plate, and filament.

[開啟自訂 .3mf 設定資料夾](print-configs/)，取得 Bambu Studio 列印盤配置與印表機／耗材設定。設定檔與單一零件模型分開存放；請選擇符合印表機、噴嘴、列印板及耗材的設定。

## STEP conversion / STEP 轉換

The STEP files are valid closed solids converted from the STL meshes with OpenCascade. Coplanar faces are merged. Curves retain mesh facets; original sketches, dimensions, and parametric feature history are not recovered. For printing, use the STL or a suitable .3mf project.

STEP 檔案由 STL 網格透過 OpenCascade 轉換為有效的封閉實體，並合併共平面面片。曲面仍保留網格面片，未還原原始草圖、尺寸約束或參數化建模歷程。列印時請使用 STL 或適用的 .3mf 專案。

All five STEP files are re-imported and checked for solid validity, dimensions, and volume against the STL. See [validation.json](validation.json) and [sources.json](sources.json) for validation results and source checksums.

五個 STEP 檔案均重新匯入，並與 STL 比對實體有效性、尺寸與體積。驗證結果與來源校驗值請參閱 [validation.json](validation.json) 及 [sources.json](sources.json)。

Conversion tooling: [OpenCascade topology documentation](https://dev.opencascade.org/sites/default/files/pdf/Topology.pdf).

轉換工具參考：[OpenCascade 拓撲文件](https://dev.opencascade.org/sites/default/files/pdf/Topology.pdf)。

## Download and reuse / 下載與使用

Download the public release assets from [2026 WRG KCIS-XG Public Release](https://github.com/Kowls0419/WRG-MASS-PRINTING/releases/tag/2026-wrg-kcis-xg-public). The complete archive includes both model formats, custom print projects, documentation, and the MIT license.

請從 [2026 WRG KCIS-XG Public Release](https://github.com/Kowls0419/WRG-MASS-PRINTING/releases/tag/2026-wrg-kcis-xg-public)下載發佈附件。完整壓縮檔包含兩種模型格式、自訂列印專案、說明文件與 MIT 授權條款。

You may use, modify, and share these files under MIT; include the copyright notice and license when redistributing.

您可依 MIT 授權使用、修改及分享這些檔案；再次散佈時請保留著作權聲明與授權條款。
