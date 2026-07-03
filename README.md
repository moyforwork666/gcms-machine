# GCMS 機台參數管理 — Prototype

互動式原型（單檔 React + 拆頁 HTML，無需建置）。直接用瀏覽器開啟 `index.html` 即可操作。

## 線上操作（GitHub Pages）

啟用 GitHub Pages 後，網址為：

```
https://<你的帳號>.github.io/<repo 名稱>/
```

## 本機操作

直接雙擊 `index.html`，或用任意靜態伺服器：

```bash
python3 -m http.server 8080
# 開啟 http://localhost:8080
```

## 內容

- `index.html` — 完整應用（含側邊選單）
- 拆頁檔：`machine.html`、`machine-type.html`、`game-group.html`、`game-theme.html`、`manufacturer.html`、`baccarat.html`、`bingo.html`、`non-sas.html`、`server-game-id.html`、`quick-setup.html`
- `assets/`、`tokens.css`、`colors_and_type.css` — 樣式與圖片資源

資料透過瀏覽器 localStorage 儲存，支援新增／編輯／匯入匯出與表單驗證。
