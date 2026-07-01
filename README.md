# 鄭凱文 Kevin Cheng · 數位名片

手機優先、卡片化的個人數位名片單頁。設計流程：Apple Wallet 上的 QR Code → 掃描 → 開啟此網頁。

**線上網址（已部署 GitHub Pages）：** https://imnivek.github.io/namecard/
**GitHub Repo：** https://github.com/imnivek/namecard

## 檔案結構

```
數位名片/
├── index.html          ← 主頁面（CSS / JS 全內嵌，單檔即可運作）
├── assets/
│   ├── profile.jpg      ← 形象照
│   ├── wechat-qr.jpg    ← 微信 QR（ID: taiwan-kevin）
│   ├── logo-404table.png
│   ├── logo-vibecoding.png
│   ├── logo-25hrs.png
│   └── logo-7g.png
└── README.md
```

## 頁面內容

1. **Hero** — 形象照、鄭凱文 / Kevin Cheng、404方桌 共同創辦人、三個定位標籤、一句話簡介、學經歷 credential，含「聯絡 / 加好友」「看創業品牌」兩顆 CTA。
2. **Positioning** — 「不是教 AI 概念的人，是用 AI 把產品跑出市場的人。」
3. **十年硬數字** — 9 間 / 6x / 200% / 5x / 20+ / 600+ / 100+ / 80+。
4. **創業品牌與作品（四大主打卡片）**，每張附可點連結：
   - 404 方桌 — 官網、Camp SR、Camp JR
   - Vibe Coding Taipei — Open Space、Threads
   - 25HRS 第廿五時 — 官網
   - 7G 奇雞先生 — 命相館官網
5. **五大專業模組** — 可點開展開的手風琴（連續創業 / AI 落地 / 跨國增長 / 沉浸式策展 / 教育底蘊）。
6. **十年職涯軌跡** — 2010 → 2026 時間軸。
7. **為什麼是我** — 三個信任支點。
8. **聯絡與社群** — 微信 QR、Instagram、Threads、Open Space、Email。
9. **Footer** — 「儲存聯絡人 vCard」按鈕（一鍵下載 .vcf 存進手機通訊錄）。

## 本機預覽

因為使用了本機圖片，直接雙擊 `index.html` 部分瀏覽器會擋圖，建議用本機伺服器：

```bash
cd 數位名片
python -m http.server 8000
# 開啟 http://localhost:8000
```

## 上線（讓 Apple Wallet QR 指向它）

任選一個免費靜態託管，把整個資料夾上傳，取得公開網址後，再把該網址填進 Apple Wallet 名片的 QR：

- **GitHub Pages**（你 404table 官網已在用 `imnivek.github.io`，最順）
  1. 新建一個 repo（例如 `namecard`），把整個資料夾內容 push 上去
  2. Settings → Pages → 選 branch `main` / root
  3. 網址會是 `https://imnivek.github.io/namecard/`
- **Cloudflare Pages / Netlify / Vercel** — 拖曳整個資料夾即可部署，會給一個 `*.pages.dev` 網址
- **Zeabur** — 你社群在推的工具，靜態站也可直接部署

### 產生 Apple Wallet QR
拿到公開網址後，用任一 QR 產生器把網址做成 QR，加入 Apple Wallet 的自訂卡片（或用支援「網址型」的電子名片 App）。QR 內容 = 你的公開網址。

## 之後要改內容

- **文字 / 連結**：直接編輯 `index.html`（品牌卡在 `<section id="brands">`、社群在 `<section id="contact">`）。
- **換圖**：換掉 `assets/` 內對應檔案，維持同檔名即可，不用改 HTML。
- **改 vCard 資訊**：在 `index.html` 底部 `<script>` 內的 `vcard` 陣列調整（目前 Email、微信 ID、官網、IG 皆已填入）。

## 備註
- 目前 Email 為 `imnivek@gmail.com`（mailto 連結與 vCard 皆已同步）。
- 視覺沿用 404方桌創辦人簡報的設計語言：炭黑 `#1A1815` × 珊瑚橘 `#E8834E` × 米色 `#F1EDE6`，字體 Noto Sans TC / Inter / JetBrains Mono。
