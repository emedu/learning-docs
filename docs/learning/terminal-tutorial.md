# Windows 終端機使用教學

## 📖 什麼是終端機？

終端機 (Terminal) 是一個文字介面的工具,可以讓您用指令來操作電腦,而不是用滑鼠點擊。在 Windows 中,主要有兩種終端機:
- **PowerShell** (推薦,功能較強大)
- **命令提示字元 (CMD)** (傳統,功能較少)

---

## 🚀 方法 1: 使用 Windows Terminal (最推薦)

### 開啟方式:
1. 按下鍵盤 `Win + X` (或在開始按鈕上按右鍵)
2. 選擇 **"Windows Terminal"** 或 **"Windows PowerShell"**

### 或者:
1. 按下 `Win + R` 打開執行視窗
2. 輸入 `wt` 或 `powershell`
3. 按 Enter

### 或者 (最簡單):
1. 在開始選單搜尋列輸入 **"PowerShell"**
2. 點擊 **"Windows PowerShell"**

---

## 🎯 方法 2: 在資料夾中直接開啟終端機

這個方法最方便,可以直接在您的專案資料夾開啟終端機!

### 步驟:
1. 打開檔案總管 (File Explorer)
2. 進入您的專案資料夾,例如 `D:\projects\emedu-audio-tools`
3. 在資料夾空白處 **按住 Shift + 按右鍵**
4. 選擇 **"在這裡開啟 PowerShell 視窗"** 或 **"Open PowerShell window here"**

這樣終端機就會直接在該資料夾開啟,不需要再用 `cd` 指令切換目錄!

---

## 📝 基本終端機指令教學

### 1. 查看目前位置
```powershell
pwd
# 顯示目前所在的資料夾路徑
```

### 2. 列出資料夾內容
```powershell
ls
# 或
dir
# 顯示目前資料夾中的所有檔案和子資料夾
```

### 3. 切換資料夾
```powershell
# 進入某個資料夾
cd D:\projects

# 進入子資料夾
cd emedu-audio-tools

# 返回上一層
cd ..

# 返回上兩層
cd ..\..
```

### 4. 清除畫面
```powershell
clear
# 或
cls
# 清除終端機畫面上的內容
```

---

## 🔧 GitHub CLI 常用指令

開啟終端機後,您可以直接使用這些指令:

### 1. 檢查 GitHub CLI 版本
```powershell
gh --version
```
**預期輸出**: `gh version 2.83.1 (2025-11-13)`

### 2. 查看登入狀態
```powershell
gh auth status
```
**預期輸出**: 
```
✓ Logged in to github.com account emedu
```

### 3. 查看您的倉庫列表
```powershell
gh repo list
```

### 4. 查看說明文件
```powershell
gh --help
# 或查看特定指令的說明
gh repo --help
gh repo create --help
```

---

## 🎓 實際操作練習

### 練習 1: 開啟終端機並確認位置
```powershell
# 1. 開啟 PowerShell
# 2. 輸入以下指令查看目前位置
pwd

# 3. 切換到專案資料夾
cd D:\projects
```

### 練習 2: 測試 GitHub CLI
```powershell
# 1. 確認 gh 指令可用
gh --version

# 2. 查看登入狀態
gh auth status

# 3. 列出您的倉庫
gh repo list
```

### 練習 3: 為專案建立 GitHub 倉庫
```powershell
# 1. 進入專案資料夾
cd D:\projects\emedu-audio-tools

# 2. 初始化 Git (如果還沒有)
git init

# 3. 加入所有檔案
git add .

# 4. 提交變更
git commit -m "Initial commit"

# 5. 使用 gh 建立倉庫並推送
gh repo create emedu-audio-tools --public --source=. --push
```

---

## 💡 常見問題

### Q: 如果輸入 `gh` 顯示找不到指令怎麼辦?
**A**: 
1. 關閉終端機視窗
2. 重新開啟一個新的終端機視窗
3. 再試一次 `gh --version`

如果還是不行,可能需要重新啟動電腦讓 PATH 環境變數生效。

### Q: 如何複製終端機中的文字?
**A**: 
- 用滑鼠選取文字後,按 `Ctrl + C` 或直接按右鍵即可複製
- 貼上則是按 `Ctrl + V` 或按右鍵選擇貼上

### Q: 如何關閉終端機?
**A**: 
- 輸入 `exit` 然後按 Enter
- 或直接點擊視窗右上角的 X

### Q: 終端機中的路徑分隔符號?
**A**: 
- Windows 可以使用 `\` 或 `/` 都可以
- 例如: `D:\projects` 或 `D:/projects` 都正確

---

## 🎯 下一步學習

1. **練習基本指令**: 多使用 `cd`, `ls`, `pwd` 來熟悉終端機
2. **學習 Git 指令**: `git status`, `git add`, `git commit`, `git push`
3. **探索 GitHub CLI**: 試試 `gh repo`, `gh pr`, `gh issue` 等指令
4. **自訂終端機**: 可以安裝 Windows Terminal 並自訂主題和字型

---

## 📚 快速參考卡

| 功能 | 指令 |
|------|------|
| 查看目前位置 | `pwd` |
| 列出檔案 | `ls` 或 `dir` |
| 切換資料夾 | `cd 路徑` |
| 返回上一層 | `cd ..` |
| 清除畫面 | `clear` 或 `cls` |
| 查看 Git 狀態 | `git status` |
| 查看 GitHub 登入狀態 | `gh auth status` |
| 列出倉庫 | `gh repo list` |
| 建立倉庫 | `gh repo create` |
| 關閉終端機 | `exit` |

---

## ✨ 小技巧

1. **Tab 自動完成**: 輸入指令或路徑時,按 `Tab` 鍵可以自動完成
2. **上下鍵**: 按 `↑` 和 `↓` 可以查看之前輸入過的指令
3. **Ctrl + C**: 取消目前正在執行的指令
4. **右鍵貼上**: 在終端機中按右鍵可以快速貼上剪貼簿內容

---

**準備好了嗎?** 現在就開啟您的第一個終端機視窗,試試看這些指令吧! 🚀
