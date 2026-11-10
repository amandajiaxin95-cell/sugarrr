# 暫停蔗一刻｜帝國製糖廠影展專題網站

行銷系甲二組影展專題「暫停蔗一刻」的介紹網站。主題是帝國製糖廠臺中營業所，內容依本組企劃書與影展短片整理。

- 作者：吳佳芯（D1446035）
- 課程：Project 1（115-1 行銷系）
- 製作方式：Vibe Coding，用 AI（Claude）依照指令產生程式碼，再檢查、預覽與修改

## 網站連結

- GitHub：（https://github.com/amandajiaxin95-cell/sugarrr）
- InfinityFree：(https://jiaxin.site.je/)
- Vercel：（https://xxxx.vercel.app/)

## 我使用的 Vibe Coding 指令

以下是製作這個網站時，給 AI 的主要指令，依使用順序排列。

### 1. 先寫出 CSS 設計

我先請 AI 依照帝國糖廠的主題寫一份 CSS，設定了色彩變數：磚紅色對應日治紅磚建築，湖水藍灰呼應星泉湖。CSS 裡也做好了導覽列、側邊欄、Grid 卡片、16:9 影片容器和 RWD 規則。

### 2. 找出畫面沒有樣式的原因

> 他的不知道是什麼問題，打開後沒有顯示格式和顏色，所以也上傳不了。

AI 檢查後發現 CSS 本身沒有問題，原因出在 HTML 載入 CSS 的路徑，或是資料夾擺放的位置。

### 3. 重新製作完整網站

> 可以幫忙再做一個新的嗎？像剛剛的那樣，因為我們一群人實在是搞不清楚。HTML 也刪掉了，可能要全部重來。我有給你企劃書和照片、影片了，如果 CSS 可以用就不用換新的了。

AI 讀了企劃書，整理出糖廠歷史、建築特色、短片故事、競爭者比較與組員分工，做成五個分頁。原本的 CSS 設計全部保留，只依作業要求拆成四個檔案。

## 網站結構

```text
├── index.html        首頁（landing page）：封面、專題介紹、四張分頁卡片、市場定位
├── story.html        糖廠故事：場域概述、歷史年表、建築特色、建築照片
├── film.html         影展短片：故事大綱、YouTube 短片、關鍵畫面、廣告精神
├── visit.html        漫遊指南：建議路線、場域比較表、Google 地圖
├── team.html         製作團隊：組員分工、目標客群、資料來源
├── README.md         本說明檔
├── css/
│   ├── base.css        色彩變數、重設、內文排版
│   ├── layout.css      導覽列、側邊欄 + 主內容雙欄版面、頁尾
│   ├── components.css  封面、按鈕、卡片、影片、Grid、表格、地圖
│   └── responsive.css  RWD：平板與手機的 @media 規則
└── images/
    └── cover.jpg       營業所照片（來源：臺中觀光旅遊網）
```

## 作業要求對照

| 要求 | 做法 |
| --- | --- |
| 導覽列、側邊欄、分頁 | 五個分頁共用頂部導覽列，目前頁面以 `.active` 標示；每頁都有側邊欄（本頁目錄、參觀資訊、關鍵字） |
| SEO | 每頁有自己的 `title`、`description`、`keywords`、Open Graph，並使用 header、nav、main、section、aside、footer 等語意標籤 |
| Grid System | `.grid-system` 用 `grid-template-columns: repeat(auto-fit, minmax(240px, 1fr))` 自動排列卡片 |
| RWD | 900px 以下側邊欄移到上方、目錄變成標籤；600px 以下卡片變一欄、導覽列換行；影片維持 16:9 |
| CSS 切割 | 分成 base、layout、components、responsive 四個檔案，都放在 `css` 資料夾 |
| 圖片放 images | 照片放在 `images/cover.jpg`；HTML 用 `images/cover.jpg`，CSS 用 `../images/cover.jpg` |

## 路徑小筆記

- HTML 的路徑從 HTML 所在的資料夾出發，所以寫 `css/base.css`、`images/cover.jpg`
- CSS 的 `url()` 從 css 資料夾出發，所以要先用 `../` 回到上一層，寫成 `url('../images/cover.jpg')`

## 資料來源

- 文化部文化資產局：帝國製糖廠臺中營業所暨附屬設施
- 臺中觀光旅遊網：帝國製糖廠臺中營業所
- 臺中市文化資產處：帝國製糖廠臺中營業所暨附屬設施
- 本組企劃書「暫停蔗一刻」
- YouTube：影展短片「暫停蔗一刻」
