# move and model

中醫 × AI × 跨域實驗場——個人品牌網站,收納 TCM Playground 三個工具。

## 本機跑起來

```bash
npm install
npm run dev
```

打開 http://localhost:4321

## 部署到 Vercel

1. 把這個資料夾 push 到你的 GitHub repo
2. 到 vercel.com 用 GitHub 帳號登入,選擇這個 repo,一路預設值 Deploy 即可
   (Astro 是 Vercel 官方支援的框架,不需要額外設定)
3. 之後每次 push 到 GitHub,Vercel 會自動重新部署

## 之後想改字體

打開 `src/styles/global.css`,改這兩行:

```css
--font-voice: 'Fraunces', 'Noto Serif TC', serif;   /* 標題/wordmark 用的字體 */
--font-body: 'Work Sans', 'Noto Sans TC', sans-serif; /* 內文用的字體 */
```

同時到 `src/layouts/Layout.astro` 裡,把 Google Fonts 的 `<link>` 換成新字體的網址
(去 fonts.google.com 選字體,它會給你對應的 `<link>` 程式碼,整段貼上去即可)。

## 之後想改顏色

同樣在 `src/styles/global.css` 最上面的色彩變數區塊,改十六進位色碼即可,
全站所有頁面會自動套用,不用逐頁修改。

## 目錄結構

```
src/
  layouts/Layout.astro       # 共用外框(導覽列、頁尾、字體引入)
  components/
    MeshMotif.astro          # logo 網格線稿母題,可重複使用
    ToolCard.astro           # 作品卡片
  pages/
    index.astro              # 首頁
    about.astro               # 關於我
    contact.astro             # 聯繫
    playground/
      index.astro             # 作品總覽
      acupuncture.astro        # AI 針灸學習(佔位頁,待開發)
      exam-prep.astro          # 國考刷題系統(佔位頁,待開發)
      notes-to-quiz.astro      # 講義拆解工具(佔位頁,待開發)
```

三個工具目前是佔位頁面,之後做好功能後直接把內容寫進對應的 `.astro` 檔案即可,
不用動架構跟導覽邏輯。
