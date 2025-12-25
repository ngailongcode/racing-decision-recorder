# 賽馬決策記錄器

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python Version](https://img.shields.io/badge/python-3.8+-green.svg)

## 📋 專案簡介

**賽馬決策記錄器** 是一個用於記錄和分析賽馬決策過程的應用程式。該工具幫助使用者系統地記錄每場比賽的決策邏輯、投注結果和績效分析，以便持續改進投注策略。

## ✨ 主要功能

- 📝 **決策記錄** - 記錄每場比賽的分析過程和決策理由
- 📊 **績效追蹤** - 追蹤投注結果和勝率統計
- 💰 **資金管理** - 監控投注資金和投資回報率（ROI）
- 📈 **數據分析** - 生成詳細的績效報告和趨勢分析
- 🔍 **決策評論** - 回顧過去的決策，尋找改進空間

## 🚀 快速開始

### 系統需求

- Python 3.8 或更高版本
- pip 套件管理器
- 至少 2GB 的可用磁碟空間

### 安裝步驟

1. **克隆倉庫**
   ```bash
   git clone https://github.com/ngailongcode/racing-decision-recorder.git
   cd racing-decision-recorder
   ```

2. **建立虛擬環境（推薦）**
   ```bash
   python -m venv venv
   ```

3. **啟動虛擬環境**
   
   - 在 Windows 上：
   ```bash
   venv\Scripts\activate
   ```
   
   - 在 macOS/Linux 上：
   ```bash
   source venv/bin/activate
   ```

4. **安裝依賴包**
   ```bash
   pip install -r requirements.txt
   ```

5. **執行應用程式**
   ```bash
   python main.py
   ```

## 📁 專案結構

```
racing-decision-recorder/
├── README.md                 # 專案文檔
├── requirements.txt          # Python 依賴包
├── main.py                   # 應用程式入口點
├── config.py                 # 設定檔
├── src/
│   ├── __init__.py
│   ├── recorder.py           # 核心記錄功能
│   ├── analyzer.py           # 數據分析模組
│   └── database.py           # 數據庫操作
├── tests/
│   ├── __init__.py
│   ├── test_recorder.py      # 記錄器測試
│   └── test_analyzer.py      # 分析器測試
└── data/
    └── records.db            # 本地數據庫檔案
```

## 💻 使用示例

### 記錄新的決策

```python
from src.recorder import DecisionRecorder

recorder = DecisionRecorder()

# 記錄比賽決策
recorder.record_decision(
    race_id="2025-12-25-001",
    horse_name="飛馬王",
    odds=3.5,
    stake=100,
    reasoning="基於速度表現和最近表現",
    result="Win"  # Win, Place, Show, Loss
)
```

### 查看績效分析

```python
from src.analyzer import PerformanceAnalyzer

analyzer = PerformanceAnalyzer()

# 獲取績效統計
stats = analyzer.get_statistics()
print(f"勝率: {stats['win_rate']:.2%}")
print(f"總投報率 (ROI): {stats['roi']:.2%}")
print(f"淨利潤: ${stats['net_profit']:.2f}")
```

## ⚙️ 設定

編輯 `config.py` 以自訂應用程式設定：

```python
# 數據庫設定
DATABASE_PATH = "data/records.db"

# 貨幣設定
CURRENCY = "USD"
INITIAL_BANKROLL = 1000

# 日誌設定
LOG_LEVEL = "INFO"
LOG_FILE = "logs/app.log"
```

## 📊 數據導出

該應用程式支援將記錄導出為多種格式：

- **CSV** - 用於 Excel 和其他電子表格應用程式
- **JSON** - 用於進一步的數據處理
- **PDF** - 用於列印和分享

```bash
python main.py export --format csv --output reports/decisions.csv
python main.py export --format json --output reports/decisions.json
python main.py export --format pdf --output reports/report.pdf
```

## 🧪 測試

執行單元測試以確保應用程式的完整性：

```bash
# 執行所有測試
pytest

# 執行特定測試檔案
pytest tests/test_recorder.py

# 帶有覆蓋率報告的測試
pytest --cov=src
```

## 📝 API 文檔

### DecisionRecorder 類

主要類別，用於管理決策記錄。

**方法：**
- `record_decision(race_id, horse_name, odds, stake, reasoning, result)` - 記錄新決策
- `get_all_records()` - 獲取所有記錄
- `delete_record(record_id)` - 刪除特定記錄

### PerformanceAnalyzer 類

用於分析賽馬投注績效。

**方法：**
- `get_statistics()` - 獲取統計數據
- `get_monthly_report(month)` - 獲取月度報告
- `get_trend_analysis()` - 獲取趨勢分析

## 🐛 故障排除

### 問題：無法連接到數據庫
**解決方案：** 確保 `data/` 目錄存在，並且具有寫入權限。

### 問題：匯入錯誤
**解決方案：** 重新安裝依賴包並確保正確使用了虛擬環境。
```bash
pip install --upgrade -r requirements.txt
```

### 問題：性能緩慢
**解決方案：** 嘗試優化數據庫，或考慮檔案備份和清理舊記錄。

## 🤝 貢獻

歡迎貢獻！請遵循以下步驟：

1. Fork 本倉庫
2. 建立功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 開啟 Pull Request

## 📄 許可證

此專案採用 MIT 許可證。詳見 [LICENSE](LICENSE) 檔案。

## 📧 聯絡方式

- **作者：** ngailongcode
- **GitHub：** [https://github.com/ngailongcode](https://github.com/ngailongcode)
- **問題反饋：** [提交 Issue](https://github.com/ngailongcode/racing-decision-recorder/issues)

## 🙏 致謝

感謝所有為此專案做出貢獻的人員和支援者。

---

**免責聲明：** 本應用程式僅供教育和記錄用途。使用者應自行承擔所有投注決策的責任和財務風險。

**最後更新：** 2025-12-25
