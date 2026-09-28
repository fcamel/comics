# 達拉崩吧漫畫閱讀器

靜態網站，直接開啟 `index.html` 即可閱讀 `dalabengba/P01.png` 至 `P42.png`。支援單頁與連續閱讀、預設／適合寬度／適合高度三種顯示方式、頁面一覽、鍵盤方向鍵、手機左右滑動，以及在同一裝置記住閱讀進度與顯示偏好。網址中的 `#p=12` 可以直接開啟第 12 頁。

## 用 GitHub Pages 手動發佈

1. 將此 Git 儲存庫推送到 GitHub。
2. 在儲存庫的 **Settings → Pages → Build and deployment** 中，將 **Source** 設為 **GitHub Actions**。
3. 到 **Actions → Deploy GitHub Pages → Run workflow**，選擇 `main` 並執行。只有手動執行才會發佈；一般推送不會觸發部署。

Workflow 會組裝靜態網站，只上傳首頁、樣式與程式、圖示、42 張漫畫及對應縮圖。網站無需安裝套件或建置；在專案型 Pages 網址下，相對路徑也能正常載入圖片。
