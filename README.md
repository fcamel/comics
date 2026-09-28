# 達拉崩吧漫畫閱讀器

靜態網站，直接開啟 `index.html` 即可閱讀 `dalabengba/P01.webp` 至 `P42.webp`。支援單頁與連續閱讀、預設／適合寬度／適合高度三種顯示方式、頁面一覽、鍵盤方向鍵、手機左右滑動，以及在同一裝置記住閱讀進度與顯示偏好。網址中的 `#p=12` 可以直接開啟第 12 頁。

## 檔案結構

```text
.
├── index.html                       網站首頁與第一頁圖片
├── styles.css                       閱讀器樣式
├── reader.js                        翻頁、閱讀模式與圖片路徑
├── favicon.svg                      網站圖示
├── .nojekyll                        避免 GitHub Pages 使用 Jekyll 處理網站
├── dalabengba/
│   ├── P01.png … P42.png            漫畫原稿
│   └── P01.webp … P42.webp          網站實際載入的漫畫頁面
├── thumbnails/
│   ├── P01.jpg … P42.jpg            縮圖原稿
│   └── P01.webp … P42.webp          「頁面一覽」實際載入的縮圖
└── .github/workflows/deploy-pages.yml  手動部署 GitHub Pages
```

## 圖檔用法

- 每頁使用兩位數編號，從 `P01` 到 `P42`。`dalabengba/P13.webp` 是第 13 頁；`thumbnails/P13.webp` 是同一頁在「頁面一覽」中的縮圖。
- 網站只載入 `.webp`：`index.html` 預載並顯示第 1 頁，`reader.js` 依頁碼載入其餘漫畫與縮圖。PNG、JPEG 原稿留在儲存庫，供日後重新轉檔。
- 替換某頁時，請更新對應的 WebP 漫畫和縮圖；若也更新原稿，使用相同的 `PXX` 檔名。只替換 PNG 或 JPEG 不會改變網站畫面。
- GitHub Pages workflow 只複製 42 頁漫畫及其 42 張 WebP 縮圖，不會上傳 PNG、JPEG 原稿。推送更新後仍須手動執行 workflow，網站才會更新。
- 目前頁數固定為 42。增減頁數時，也要更新 `reader.js` 的 `TOTAL_PAGES`、`index.html` 顯示的總頁數及部署 workflow 的頁碼範圍。

## 用 GitHub Pages 手動發佈

1. 將此 Git 儲存庫推送到 GitHub。
2. 在儲存庫的 **Settings → Pages → Build and deployment** 中，將 **Source** 設為 **GitHub Actions**。
3. 到 **Actions → Deploy GitHub Pages → Run workflow**，選擇 `main` 並執行。只有手動執行才會發佈；一般推送不會觸發部署。

Workflow 會組裝靜態網站，只上傳首頁、樣式與程式、圖示、42 張 WebP 漫畫及對應縮圖。網站無需安裝套件或建置；在專案型 Pages 網址下，相對路徑也能正常載入圖片。
