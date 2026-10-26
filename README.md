# Git 與 GitHub Pages 使用教學

Git 是一套分散式版本控制系統，可以用來管理程式碼、追蹤修改紀錄，以及將本機專案推送到 GitHub。

## 一、初次使用Git--各種作業系統安裝 Git

### 1. Windows 10 / 11

![Windows Logo](https://upload.wikimedia.org/wikipedia/commons/5/5f/Windows_logo_-_2012.svg)

使用 PowerShell 或 Windows Terminal 執行：

```powershell
winget install --id Git.Git -e
```

也可以前往官方網站下載安裝程式：

https://git-scm.com/install/windows

### 2. macOS

<img src="https://upload.wikimedia.org/wikipedia/commons/f/fa/Apple_logo_black.svg" width="80">

使用 Homebrew 安裝：

```bash
brew install git
```

或者使用 Apple Command Line Tools：

```bash
xcode-select --install
```

Homebrew 官方網站：https://brew.sh/

### 3. Ubuntu / Debian / Linux Mint

![Ubuntu Logo](https://assets.ubuntu.com/v1/29985a98-ubuntu-logo32.png)

```bash
sudo apt update
sudo apt install git
```

### 4. Arch Linux / Manjaro

![Arch Linux Logo](https://archlinux.org/static/logos/archlinux-logo-dark-90dpi.png)

```bash
sudo pacman -S git
```

### 5. Fedora / RHEL / Rocky Linux / AlmaLinux

![Fedora Logo](https://fedoraproject.org/w/uploads/2/2d/Fedora_logo.svg)

Fedora：

```bash
sudo dnf install git
```

RHEL、Rocky Linux、AlmaLinux 也可以使用 `dnf` 安裝，實際可用版本取決於已啟用的軟體來源。

### 6. openSUSE

![openSUSE Logo](https://en.opensuse.org/images/6/69/Button-filled-colour.png)

```bash
sudo zypper install git
```

### 7. FreeBSD

![FreeBSD Logo](https://www.freebsd.org/images/logo-symbol.png)

```bash
sudo pkg install git
```

### 8. Alpine Linux

![Alpine Linux Logo](https://alpinelinux.org/alpinelinux-logo.svg)

```bash
sudo apk add git
```

### 9. 驗證安裝

安裝完成後，開啟終端機並執行：

```bash
git --version
```

如果顯示 Git 的版本資訊，就代表安裝成功。

接著設定使用者名稱與電子郵件：

```bash
git config --global user.name "你的名稱"
git config --global user.email "你的電子郵件"
```

### 10. 開始使用 Git

進入你的網站專案資料夾：

```bash
cd 你的專案資料夾
```

初始化 Git：

```bash
git init
```

加入檔案並建立第一次提交：

```bash
git add .
git commit -m "Initial commit"
```

之後即可將本機專案連接到 GitHub，推送程式碼並透過 GitHub Pages 部署網站。

### 官方資源

- [Git 官方網站](https://git-scm.com/)
- [Git 官方安裝指南](https://git-scm.com/install)
- [GitHub](https://github.com/)
- [GitHub Pages 文件](https://docs.github.com/pages)

---

## 二、上傳pages--沒有 Git 的作法

這種方法只需要瀏覽器，不必安裝 Git，也不必使用終端機。

1. 先註冊一個 **GitHub** 帳號，然後按上面的 **Fork** 按鈕，將原始專案複製到自己的帳號。這份 Fork 會是你自己的儲存庫，與原始專案分開。

2. GitHub 通常會自動進入你的 Fork。在 **Go to file** 旁邊，按下加號按鈕，選擇 **Upload files**。

3. 將 HTML 檔案命名為 `index.html`，再把檔案拖曳到上傳區域，最後按下 **Commit changes**。

4. 回到自己的 GitHub 儲存庫，進入 **Settings > Pages**。

5. 在 **Build and deployment** 中，將 Source 設為 **Deploy from a branch**。接著選擇有檔案的分支，例如 `main`，資料夾選擇 `/ (root)`，最後按下 **Save**。

### 完成！

回到 GitHub 儲存庫主畫面，在 **Deployments** 下方找到 `github-pages`，即可查看部署狀態並進入網站。

---

## 三、上傳pages--有 Git 的作法

使用 Git 可以在自己的電腦修改網站，再將修改推送到 GitHub，不必每次都透過網頁手動上傳。

### 1. Fork 原始專案

先註冊一個 **GitHub** 帳號，然後按下原始專案上方的 **Fork** 按鈕，將專案複製到自己的帳號。

### 2. 將專案下載到電腦

確認已安裝 Git，然後打開終端機，執行：

```bash
git clone https://github.com/你的帳號/你的儲存庫名稱.git
```

### 3. 進入專案資料夾

```bash
cd 你的儲存庫名稱
```

### 4. 新增網站檔案

將 HTML 檔案放進專案資料夾，並命名為 `index.html`。如果已經有其他檔案，也可以一起放進去。

### 5. 將檔案加入版本控制

```bash
git add .
```

### 6. 提交變更

```bash
git commit -m "新增網站首頁"
```

### 7. 將修改推送到 GitHub

```bash
git push
```

### 8. 設定 GitHub Pages

回到 GitHub 自己的儲存庫，進入 **Settings > Pages**。

在 **Build and deployment** 中設定：

- **Source：** `Deploy from a branch`
- **Branch：** `main`（或實際存放網站的分支）
- **Folder：** `/ (root)`

最後按下 **Save**。

### 9. 更新網站

之後每次修改網站，只需要在專案資料夾執行：

```bash
git add .
git commit -m "更新網站"
git push
```

GitHub Pages 就會自動重新部署，不必每次都手動上傳檔案。

### 完成！

回到 GitHub 儲存庫主畫面，在 **Deployments** 下方找到 `github-pages`，即可查看部署狀態並進入網站。

網站網址通常會是：

```text
https://你的帳號.github.io/你的儲存庫名稱/
```

如果儲存庫名稱是 `你的帳號.github.io`，網址則是：

```text
https://你的帳號.github.io/
```

> **注意：** 如果你 Fork 的原始專案已經設定 GitHub Pages，自己的 Fork 仍然需要另外確認 Pages 設定及部署狀態。若 `git push` 要求驗證，請使用 GitHub 支援的驗證方式，例如 Personal Access Token 或 SSH 金鑰。

