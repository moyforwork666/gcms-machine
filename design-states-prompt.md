# Prompt：請 Claude.ai / design 製作 States

> 用法：把這份 prompt 連同 `index.html`（必要時加上 `tokens.css`、`colors_and_type.css`）一起貼給 Claude design。

---

## 給設計的 Prompt（可直接複製）

我附上一份**機台參數管理（GCMS）後台原型**，單一檔案 `index.html`（React + inline 樣式，搭配 `tokens.css` / `colors_and_type.css` 的設計 token）。這是「功能流程已確認」的互動原型，但**還沒有完整的視覺狀態規格**。

請以這份原型為唯一事實來源，為其中的**元件與畫面產出完整的 States（狀態）規格**。請務必：

1. **沿用既有設計 token**（顏色、字級、圓角、間距），不要自創色票；token 定義在 `tokens.css` 與 `colors_and_type.css`，原型內以 `var(--…)` 取用。
2. 以**元件為單位**整理 States，每個元件列出所有狀態，並標註對應 token、尺寸、間距。
3. 以**畫面/流程為單位**整理關鍵狀態（空、載入中、唯讀、編輯、錯誤、確認彈窗）。
4. 維持現有版面結構與互動行為，只補齊「視覺狀態」，不要新增功能或改流程。

### 一、元件層級 States（請逐一產出）
- **Button**：variant = primary / confirm / cancel / warning / support / light-gray / outline；每個 variant 給 rest / hover / disabled（必要時 focus）。
- **Field（輸入）**：text / select / textarea；rest / focus / read-only / error（含錯誤訊息）。
- **Switch**：on / off / disabled。
- **Checkbox（Check）**：unchecked / checked。
- **Chip**：neutral / primary / success / warning / error。
- **DataTable**：表頭、奇偶列、hover、單選選中列、批次模式 checkbox 欄、空資料狀態。
- **Sidebar / 導覽**：收合（icon-only）/ 展開；父層群組展開/收合；項目 rest / hover / active。
- **Stepper、SubTabs、Tabs**：未完成 / 進行中 / 完成 / 選中。
- **Dialog / Toast**：標題列（一般 vs danger 紅底）、Toast 出現/消失。

### 二、畫面/流程層級 States（請逐一產出）
1. **機台快速建置流程（精靈）**：各步驟「填寫」與「略過」狀態、最後「檢視套用」、「套用後對機台執行重置」勾選 未勾/已勾、勾選後跳出的**批次重置確認**彈窗。
2. **清單 + 右側編輯卡片型頁面**（機台維護、機台類型清單、遊戲類型群組、遊戲主題、製造商、Non-SAS）：清單 view、選取一列後右卡「檢視」、右卡「編輯」、「批次編輯」（欄位勾選）、批次「預覽套用」彈窗、單筆新增、右卡未選取的空狀態。
3. **機台類型 → Game Theme Detail**（drill-in）：主題清單 + 新增/編輯。
4. **賓果維護**：Game Server 清單 + 右側「Game Server Information」檢視/編輯、drill-in「Bingo Machine 詳細」（左側新增機台 + 右側機台表格、空狀態）、Promotion Setting 彈窗（檢視/編輯）、Reset 確認彈窗。
5. **Non-SAS**：清單 + 編輯卡片、Region Setting 彈窗（表格 + 新增/編輯，原資料不可刪）。
6. **百家樂設定（單一店家表單）**：唯讀檢視、編輯中、未儲存（dirty）標示、切換店家。

### 三、交付格式
- 每個元件一張 States 對照表/畫板（state 名稱 + 視覺 + 使用 token + 尺寸/間距）。
- 每個畫面一組關鍵狀態的視覺稿。
- 若輸出到 Figma：請建立可重用的 component variants（用 variant property 表示 state），並對應 token；色彩/字級使用 styles/variables 綁定 token，不要寫死數值。

備註：此原型已驗證**所有頁面皆可由側欄與卡片按鈕點擊到達、無無法觸及的畫面**；若你發現任何狀態在原型中找不到觸發路徑，請先回報再產出。
