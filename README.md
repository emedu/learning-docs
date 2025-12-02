# Learning Docs 專案

這個專案用來記錄所有學習資料、討論內容、執行計畫和報告,方便未來查閱和 AI 交接。

## 📁 專案結構

```
learning-docs/
├── docs/
│   ├── learning/          # 學習教學資料
│   ├── discussions/       # 討論記錄
│   ├── plans/            # 執行計畫
│   └── reports/          # 執行報告
└── README.md
```

## 📚 文件說明

### learning/ - 學習資料
存放各種技術教學和指南:
- `git-github-guide.md` - Git 和 GitHub 完整整合指南
- `terminal-tutorial.md` - Windows 終端機使用教學

### discussions/ - 討論記錄
記錄與 AI 的討論內容,方便回顧和交接

### plans/ - 執行計畫
存放專案執行計畫和設計文件

### reports/ - 執行報告
記錄專案進度和完成報告

## 🎯 使用方式

1. **查閱學習資料**: 到 `docs/learning/` 找相關教學
2. **回顧討論**: 到 `docs/discussions/` 查看歷史對話
3. **了解計畫**: 到 `docs/plans/` 查看執行計畫
4. **追蹤進度**: 到 `docs/reports/` 查看報告

## 🔄 同步到 GitHub

這個專案會同步到 GitHub,確保:
- ✅ 資料備份到雲端
- ✅ 可以在不同裝置存取
- ✅ 有完整的版本控制
- ✅ 方便 AI 交接時讀取

## 📝 維護原則

1. **定期更新**: 每次學習新內容或討論後,記得更新文件
2. **清楚命名**: 檔案名稱要清楚描述內容
3. **日期標記**: 討論記錄加上日期,例如 `2025-12-02-workflow-summary.md`
4. **分類整理**: 把文件放到正確的資料夾中

## 🚀 快速開始

### 初始化 Git 並推送到 GitHub
```powershell
# 進入專案資料夾
cd D:\projects\learning-docs

# 初始化 Git
git init

# 加入所有檔案
git add .

# 提交變更
git commit -m "Initial commit: Setup learning docs project"

# 使用 GitHub CLI 建立倉庫並推送
gh repo create learning-docs --public --source=. --push
```

### 日常更新流程
```powershell
# 1. 修改或新增文件
# 2. 加入變更
git add .

# 3. 提交變更
git commit -m "Add new tutorial or update discussion"

# 4. 推送到 GitHub
git push
```

## 📌 注意事項

- 這個專案主要是**個人學習記錄**,可以設為 Public 或 Private
- 如果包含敏感資訊,建議設為 **Private**
- 定期備份到 GitHub,避免資料遺失
