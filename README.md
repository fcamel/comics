# 達拉崩吧漫畫閱讀器

靜態網站，直接開啟 `index.html` 即可閱讀 `dalabengba/P01.png` 至 `P42.png`。支援單頁與連續閱讀、預設／適合寬度／適合高度三種顯示方式、頁面一覽、鍵盤方向鍵、手機左右滑動，以及在同一裝置記住閱讀進度與顯示偏好。網址中的 `#p=12` 可以直接開啟第 12 頁。

## 用 GitHub Pages 發佈

將此目錄推送到 GitHub 儲存庫，於 **Settings → Pages → Build and deployment** 選擇 **Deploy from a branch**，指定發佈分支及 **/(root)**。網站無需安裝套件或建置；在專案型 Pages 網址下，相對路徑也能正常載入圖片。

`dalabengba/` 是從原始資料夾完整複製的素材。閱讀器只使用其中的 42 張主線漫畫；`reality/` 等其他檔案也會隨根目錄一起發佈。
