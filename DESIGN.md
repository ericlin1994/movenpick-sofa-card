---
version: alpha
name: 莫凡彼沙發工藝 電子名片
description: 家具線電子名片＋一頁式網站。藏青深色主卡＋暖紙白頁面底＋銅橘／棕金點綴。第 86 輪依實際程式（rebuild_page.py／build_flex.py 深色版）重寫，取代原本只描述淺底方案的舊稿。
palette: 藏青 ＋ 銅橘 ＋ 暖紙白（家具線，客戶選定深色版）
parent: ../DESIGN.md

colors:
  # ── 網站 :root 實際 token（rebuild_page.py 產生；LINE 卡片沿用同一組藏青／銅橘）──
  navy: "#253043"             # 主卡底、卡片底（Flex 7 張 body 底色）、頁面主文字 --ink
  navy-2: "#1E2838"           # 漸層尾端、footer 底、硬陰影色
  navy-3: "#33415C"           # 漸層起點、人像底
  copper: "#C4835A"           # --gold　銅橘：只裝飾（光暈、邊框；對紙白 2.01:1）
  copper-light: "#DFA77C"     # --gold-2　人像描邊 rgba(223,167,124,.55)
  brown: "#8A5A12"            # 淺底上的強調文字與圖示（對紙白 5.27:1 ✓）
  brown-deep: "#7A4F0F"       # 按鈕底（白字對比更高）
  paper: "#F5F1E8"            # 頁面底（暖紙白）
  paper-tint: "#EFEBE3"       # 受眾格底、淺色塊
  paper-sand: "#E8E5DD"       # 佔位格條紋色
  white: "#FFFFFF"            # 卡片白底、深底上的文字
  ink: "#253043"              # 淺底主文字（= navy）
  muted: "#5B6372"            # 淺底次要文字
  line: "#D6D5CF"             # 分隔線、分享鈕上緣
  red: "#B4462F"              # 錯誤／提醒
  diag-ok: "#8FE3B0"          # 診斷面板（隱藏，僅除錯）
  diag-bad: "#FF9B8A"
  diag-text: "#D8DEE9"
  # 程式內硬寫、不在 :root 的兩個例外（只記錄，不改）：
  share-fallback-border: "#A17B41"   # JS 動態建立的分享備援鈕邊框
  diag-overlay: "#000000"            # 診斷面板全螢幕底
  # 以下都在 JS 備援／診斷用的 Flex 與按鈕裡（使用者正常流程看不到），只記錄：
  fallback-ink: "#39221E"            # 分享備援鈕文字
  line-green: "#06c755"              # LINE 官方綠（診斷面板按鈕）
  diag-ink: "#4A5468"                # 診斷 Flex 說明字
  diag-navy: "#16233D"               # 診斷 Flex 按鈕
  diag-copper: "#A96B3C"             # 診斷 Flex 按鈕
  diag-line: "#E6E0D4"               # 診斷 Flex 分隔線
  diag-grey: "#888888"               # 診斷 Flex 提示字
  # 診斷面板按鈕圓角 12px 亦為 JS 內硬寫（不在 rounded 表）

typography:
  # 網站實際字級 8 級（FS_MAP 收斂；最小 12px，第 86 輪由 11.5 提到 12）
  xs:   { fontFamily: "Noto Sans TC", fontSize: 12px, fontWeight: 700, lineHeight: 1.7 }
  sm:   { fontFamily: "Noto Sans TC", fontSize: 13px, fontWeight: 700, lineHeight: 1.7 }
  base: { fontFamily: "Noto Sans TC", fontSize: 14px, fontWeight: 500, lineHeight: 1.7 }
  md:   { fontFamily: "Noto Sans TC", fontSize: 16px, fontWeight: 700, lineHeight: 1.5 }
  lg:   { fontFamily: "Noto Sans TC", fontSize: 19px, fontWeight: 800, lineHeight: 1.4 }
  xl:   { fontFamily: "Noto Sans TC", fontSize: 21px, fontWeight: 800, lineHeight: 1.4 }
  xxl:  { fontFamily: "Noto Sans TC", fontSize: 23px, fontWeight: 800, lineHeight: 1.3 }
  hero: { fontFamily: "Noto Sans TC", fontSize: 30px, fontWeight: 900, lineHeight: 1.2 }

rounded:
  sm: 7px            # --radius-sm　縮圖、作品牆格
  md: 11px           # --radius-md　受眾格、小卡
  lg: 15px           # --radius-lg　按鈕、分享鈕
  card: 20px         # --radius　　白色內容卡
  hero-bottom: 28px  # 主卡底部圓角（0 0 28px 28px）
  full: 999px        # 膠囊（標籤、LINE 鈕、輪播點）
  circle: 50%        # 人像

spacing: { xs: 4px, sm: 8px, md: 12px, lg: 16px, xl: 20px, xxl: 24px }

elevation:
  flat: none
  card: "0 10px 26px rgba(37,48,67,.20)"
  key: "0 5px 0 {colors.navy-2}, inset 0 1px 0 rgba(255,255,255,.22)"
  key-down: "0 1px 0 {colors.navy-2}, inset 0 1px 0 rgba(255,255,255,.16)"
  portrait: "0 10px 26px rgba(0,0,0,.38), 0 0 0 6px rgba(255,255,255,.06)"

components:
  button-line:  { backgroundColor: "{colors.brown-deep}", textColor: "{colors.white}", rounded: "{rounded.lg}", height: 44px }
  button-share: { backgroundColor: "{colors.white}", textColor: "{colors.ink}", border: "1px solid {colors.line}", rounded: "{rounded.lg}" }
  tag:          { backgroundColor: "rgba(255,255,255,.14)", textColor: "{colors.white}", rounded: "{rounded.full}" }
---

## Overview

莫凡彼沙發工藝（桃園市龜山區大崗里大湖路249號）的 LINE 電子名片與一頁式網站。
**客戶選定的是深色版**：主卡與 LINE 七張卡都是藏青 `#253043` 底、白字、銅橘點綴；
網站內容區墊暖紙白 `#F5F1E8`，讓照片與白卡浮得起來。

暖色（紙白、銅橘、棕金）是**品牌決策**：客戶在室內設計／家具產業，暖色對應「家的材質」。
impeccable 的 `cream-palette` 會把暖米色底當成「AI 反射選色」——這裡是刻意選擇，**保留**（owner decision）。

> 舊稿（暖紙白＋香檳金＋襯線的淺底方案）已不再對應程式；淺底方案如需復用，從 git 歷史取回。

---

## Colors

**角色分工**
- 深底（主卡、LINE 卡）：底 `navy`，字 `white`，點綴 `copper`／`copper-light`
- 淺底（網站內容）：底 `paper`，字 `ink`，次要字 `muted`，強調字／圖示 `brown`

**對比（背景 `paper #F5F1E8`）**：`ink` ≈ 12:1、`muted #5B6372` ≈ 5.3:1、`brown #8A5A12` 5.27:1，皆 ≥ 4.5。
`copper #C4835A` 對紙白僅 2.01:1 → **只能當裝飾**（光暈、邊框、色塊），不放字、不放圖示。

---

## Typography

全站 Noto Sans TC，**沒有襯線**。字級 8 級（見 frontmatter），**最小 12px**；
不新增 `.5` 字級。LINE 卡片字級用 Flex 的 `xxs…4xl` 命名級距（xxs=11 僅限圖示旁極短標籤，內文不用）。

## Layout

- 網站 `.wrap` 最大寬 520px，行動優先（驗證寬度 375px）
- 七張 LINE 卡統一高度對齊 Benson 基準 618.9px（差 ≤ 20px）；1～6 張的內容烤進圖，第 7 張保留可點的快速連結

## Shapes & Elevation

圓角只用 `rounded` 表內的值。硬陰影（`0 Npx 0`）是按鍵識別，色用 `navy-2`，不改成彩色光暈。

---

## Do's and Don'ts

**Do**
- 銅橘 `#C4835A` 只當裝飾；要放字用 `brown #8A5A12`
- 新增顏色先進 `:root` token，再進本文件
- 卡片圖檔換內容一定要跳版號

**Don't**
- 不要把 `copper` 當文字色或圖示色
- 不要新增 `.5` 字級、不要新增第 8 種圓角
- 不要用彩色光暈取代硬陰影
- 不要為了通過 detect 而改掉暖紙白／藏青／銅橘（品牌決策）
