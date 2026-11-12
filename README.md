# 倉管盤點 PWA → 用 PWABuilder 包成 APK

PWABuilder 需要一個「網址」才能打包，所以要先把這個資料夾放到網路上（免費即可）。

## 步驟 1：放到網路上（任選一個）
- Netlify Drop：打開 https://app.netlify.com/drop ，把整個資料夾（或解壓後的資料夾）拖進去，就會得到 https://xxx.netlify.app
- GitHub Pages：建 repository，上傳這些檔案，Settings → Pages → Branch 選 main → Save。
- Cloudflare Pages：Create project → Upload assets，上傳資料夾。
網址必須是 https。

## 步驟 2：PWABuilder 打包
1. 打開 https://www.pwabuilder.com ，貼上你的網址，按 Start。
2. 看到 Manifest、Service Worker 都打勾（本資料夾已備好），按 Package for stores。
3. 選 Android → Generate Package。Package ID 可用預設或自訂（例如 com.yourname.warehouse）。
4. 建議把「Signing key」選「New」，下載後的 zip 內含已簽名的 .apk 和 .aab，以及 signing.keystore（請妥善保存，之後更新要用同一把）。
5. 把 .apk 傳到手機安裝（允許安裝未知來源的應用程式）。

## 注意
- 這個 APK 會用 Trusted Web Activity 開啟你的網站，所以網址必須長期有效；改程式就更新網站，App 會跟著更新。
- 資料存在手機本機（瀏覽器儲存空間）。清除 App 資料就會消失，重要資料請另外備份。
- 首次開啟後，到「主檔」最下方填 Gemini API key。
