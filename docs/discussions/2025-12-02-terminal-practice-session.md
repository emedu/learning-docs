# 終端機實戰練習討論記錄

**日期**: 2025-12-02  
**時間**: 23:17 - 00:00  
**主題**: PowerShell、GitHub CLI 和 Git 實戰練習

---

## 📋 討論摘要

本次對話是一次完整的終端機實戰練習課程，從基礎的 PowerShell 操作到完整的 Git 工作流程，涵蓋了日常開發中最常用的指令和操作。

---

## 🎯 練習目標

1. 熟悉 PowerShell 基本操作
2. 學會使用 GitHub CLI (`gh`) 指令
3. 掌握 Git 日常操作流程
4. 完成完整的 Git 工作流程實踐

---

## 📝 詳細練習過程

### 練習 1: PowerShell 基本操作

#### 1.1 查看目前位置
```powershell
pwd
```
**結果**: `C:\Users\jjhon`

**學習重點**:
- `pwd` = Print Working Directory
- 顯示目前所在的資料夾路徑

#### 1.2 列出檔案
```powershell
ls
```
**結果**: 顯示了所有資料夾和檔案

**學習重點**:
- Mode 欄位的意義：
  - `d-----` = 普通資料夾
  - `dar---` = 封存的唯讀資料夾
  - `dar--l` = 唯讀資料夾 + 連結點
  - `-a----` = 普通檔案

**問題與解答**:
- **Q**: `dar---` 和 `dar--l` 是什麼意思？
- **A**: 
  - `d` = Directory（資料夾）
  - `a` = Archive（封存）
  - `r` = Read-only（唯讀）
  - `l` = ReparsePoint（連結點）

#### 1.3 切換資料夾
```powershell
cd D:\projects
```
**結果**: 成功切換到專案資料夾

#### 1.4 查看專案內容
```powershell
ls
```
**結果**: 看到了 `emedu-audio-tools`、`learning-docs`、`預約系統開發示範` 等專案

#### 1.5 進入子資料夾
```powershell
cd learning-docs
ls
```
**結果**: 看到 `docs` 資料夾和 `README.md` 檔案

#### 1.6 返回上一層
```powershell
cd ..
```
**結果**: 回到 `D:\projects`

---

### 練習 2: GitHub CLI 基本指令

#### 2.1 檢查版本
```powershell
gh --version
```
**結果**: `gh version 2.83.1 (2025-11-13)`

#### 2.2 查看登入狀態
```powershell
gh auth status
```
**結果**:
```
github.com
✓ Logged in to github.com account emedu (keyring)
- Active account: true
- Git operations protocol: https
- Token: gho_****************************
- Token scopes: 'gist','read:org','repo','workflow'
```

**學習重點**:
- **keyring**: 密碼儲存在 Windows 憑證管理員中
- **Token scopes**: 權限範圍
  - `gist`: 建立和管理程式碼片段
  - `read:org`: 查看組織資訊
  - `repo`: 建立、修改、刪除倉庫
  - `workflow`: 管理 GitHub Actions

#### 2.3 列出倉庫
```powershell
gh repo list
```
**結果**: 顯示了 4 個倉庫（後來刪除了 test 倉庫，剩 3 個）
- `learning-docs` (public)
- `imay-ai-training-app` (private)
- `emedu-audio-tools` (private)
- ~~`test` (public)~~ - 已刪除

**額外學習**:
- 討論了如何刪除倉庫
- 使用 `gh repo delete` 指令

---

### 練習 3: Git 基本操作

#### 3.1 查看 Git 狀態
```powershell
cd D:\projects\learning-docs
git status
```
**結果**:
```
On branch main
Your branch is up to date with 'origin/main'.
nothing to commit, working tree clean
```

**學習重點**:
- 在 `main` 分支上
- 本地和 GitHub 同步
- 沒有未提交的變更

#### 3.2 查看提交歷史
```powershell
git log --oneline -5
```
**結果**:
```
68dae7d (HEAD -> main, origin/main) Add project setup report
33b0963 Initial commit: Setup learning docs project with Git/GitHub guides and discussion logs
```

**學習重點**:
- **68dae7d**: 提交 ID
- **(HEAD -> main, origin/main)**: 分支標記
  - HEAD = 目前位置
  - main = 本地分支
  - origin/main = GitHub 分支
- **提交訊息**: 說明這次做了什麼

#### 3.3 查看遠端倉庫
```powershell
git remote -v
```
**結果**:
```
origin  https://github.com/emedu/learning-docs.git (fetch)
origin  https://github.com/emedu/learning-docs.git (push)
```

**問題與解答**:
- **Q**: fetch 和 push 有什麼不一樣？
- **A**:
  - **Push** 📤: 本地 → GitHub（上傳）
  - **Fetch** 📥: GitHub → 本地（下載）

#### 3.4 查看分支
```powershell
git branch
```
**結果**:
```
* main
```

**學習重點**:
- `*` 表示目前在這個分支上
- 分支就像平行宇宙，可以同時開發多個功能

---

### 練習 4: 完整的 Git 工作流程

#### 步驟 1: 建立測試檔案
```powershell
echo "# 終端機練習測試" > practice-test.md
ls
```
**結果**: 成功建立 `practice-test.md` (24 bytes)

#### 步驟 2: 查看 Git 狀態
```powershell
git status
```
**結果**:
```
Untracked files:
  practice-test.md
```
**學習重點**: Git 發現了新檔案，但還沒追蹤

#### 步驟 3: 加入暫存區
```powershell
git add practice-test.md
git status
```
**結果**:
```
Changes to be committed:
  new file:   practice-test.md
```
**學習重點**: 檔案變成綠色，準備提交

#### 步驟 4: 提交變更
```powershell
git commit -m "Add practice test file for terminal tutorial"
```
**結果**:
```
[main 08fc4e2] Add practice test file for terminal tutorial
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 practice-test.md
```

#### 步驟 5: 推送到 GitHub
```powershell
git push
```
**結果**:
```
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 16 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 353 bytes | 353.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/emedu/learning-docs.git
   68dae7d..08fc4e2  main -> main
```

**詳細解釋**:
- **Enumerating objects**: 計算需要上傳的物件
- **Delta compression**: 使用壓縮減少資料量
- **Writing objects**: 上傳 353 bytes
- **68dae7d..08fc4e2**: 從舊版本更新到新版本
- **main -> main**: 本地推送到遠端

#### 步驟 6: 在瀏覽器驗證
```powershell
gh repo view --web
```
**結果**: 成功在 GitHub 上看到 `practice-test.md` 檔案

#### 步驟 7: 清理測試檔案
```powershell
rm practice-test.md
git add practice-test.md
git commit -m "Remove practice test file"
git push
```
**結果**: 成功刪除並推送，GitHub 上的檔案也消失了

---

## 🎓 重要概念總結

### Git 工作流程
```
1. 建立/修改檔案
2. git add .           # 加入暫存區
3. git commit -m "..." # 提交變更
4. git push            # 推送到 GitHub
```

### Git 三個區域
```
工作目錄 → 暫存區 → Git 倉庫 → GitHub
(修改)    (add)   (commit)  (push)
```

### 分支概念
```
main 分支:    A --- B --- C --- D
                    \
feature 分支:        E --- F
```

---

## ✅ 完成的練習項目

- [x] 成功開啟 PowerShell
- [x] 執行 `pwd` 和 `ls` 指令
- [x] 切換到 `D:\projects` 資料夾
- [x] 執行 `gh --version` 確認 GitHub CLI
- [x] 執行 `gh auth status` 確認登入
- [x] 執行 `gh repo list` 查看倉庫
- [x] 刪除 test 倉庫
- [x] 執行 `git status` 查看 Git 狀態
- [x] 執行 `git log` 查看歷史
- [x] 執行 `git remote -v` 查看遠端倉庫
- [x] 執行 `git branch` 查看分支
- [x] 建立測試檔案並提交
- [x] 推送到 GitHub
- [x] 在瀏覽器確認變更
- [x] 清理測試檔案

---

## 💡 關鍵學習點

### PowerShell
- `pwd`: 查看目前位置
- `ls`: 列出檔案
- `cd`: 切換目錄
- `cd ..`: 返回上一層

### GitHub CLI
- `gh --version`: 查看版本
- `gh auth status`: 查看登入狀態
- `gh repo list`: 列出倉庫
- `gh repo view --web`: 在瀏覽器開啟倉庫

### Git
- `git status`: 查看狀態
- `git log --oneline -5`: 查看歷史
- `git remote -v`: 查看遠端倉庫
- `git branch`: 查看分支
- `git add`: 加入暫存區
- `git commit -m "..."`: 提交變更
- `git push`: 推送到 GitHub

---

## 🎯 下一步建議

### 短期
1. 在 `emedu-audio-tools` 專案中實際應用這些指令
2. 練習更多的 Git 操作
3. 熟悉日常開發流程

### 中期
1. 學習 Git 分支操作（branch, merge）
2. 了解如何解決衝突
3. 探索 GitHub Pull Requests

### 長期
1. 學習 GitHub Actions 自動化
2. 建立完整的開發工作流程
3. 掌握進階 Git 技巧

---

## 📚 相關文件

- [Git 和 GitHub 整合指南](../learning/git-github-guide.md)
- [Windows 終端機使用教學](../learning/terminal-tutorial.md)
- [終端機實戰練習指南](../../.gemini/antigravity/brain/be30540e-93b5-44b9-b313-1e78a966c90e/terminal_practice_guide.md)

---

**練習完成時間**: 2025-12-02 23:59  
**總練習時長**: 約 42 分鐘  
**完成度**: 100% ✅
