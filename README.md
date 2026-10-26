# Git基礎使用

## 沒有Git的作法

1. 先註冊一個**github**帳號 然後按上面的**fork鍵** 複製一個git到自己的帳號 那個fork會是你的，會跟我的git分開
2. 通常github會自動進到你fork的git，按Go to file旁的加號按鈕 > Uploal file
3. 先把html檔命名成index.html，把html檔拖到裡面，然後按Commit Changes
4. 自動回到Git主畫面後 就可以按上面的Settings > Pages
5. Soure 選 Deploy form a branch，Branch選不是None的，旁邊資料夾選Root
## 完成! 回Git主畫面 然後按Deployments下面的github-pages 就能進入

## 有 Git 的作法

1. 先註冊一個 **GitHub** 帳號，然後按上面的 **Fork** 按鈕，將專案複製到自己的帳號。這樣就會有一份屬於自己的 Git 儲存庫，與原本的專案分開。

2. 在自己的電腦安裝 Git，然後打開終端機，執行以下指令，將你的 Fork 複製到電腦：

   ```bash
   git clone https://github.com/你的帳號/你的儲存庫名稱.git
   ```

3. 進入專案資料夾：

   ```bash
   cd 你的儲存庫名稱
   ```

4. 將 HTML 檔案放進專案資料夾，並命名為 `index.html`。如果已經有其他檔案，也可以一起放進去。

5. 使用 Git 將檔案加入版本控制：

   ```bash
   git add .
   ```

6. 提交變更，留下這次修改的紀錄：

   ```bash
   git commit -m "新增網站首頁"
   ```

7. 將修改推送到 GitHub：

   ```bash
   git push
   ```

8. 回到 GitHub 自己的儲存庫，進入 **Settings > Pages**。

9. 在 **Build and deployment** 裡，Source 選擇 **Deploy from a branch**，Branch 選擇 `main`（或實際存放網站的分支），資料夾選擇 `/ (root)`，然後按 **Save**。

10. 等待 GitHub Pages 部署完成。之後每次修改網站，只需要重新執行以下指令，就能更新網站：

    ```bash
    git add .
    git commit -m "更新網站"
    git push
    ```

## 完成！

回到 GitHub 儲存庫主畫面，在 **Deployments** 下方找到 `github-pages`，即可查看部署狀態並進入網站。

網站網址通常會是：

`https://你的帳號.github.io/你的儲存庫名稱/`

如果儲存庫名稱是 `你的帳號.github.io`，網址則會是：

`https://你的帳號.github.io/`

之後只要修改 HTML、執行 Git 提交並推送，GitHub Pages 就會自動重新部署，不必每次都手動上傳檔案。

