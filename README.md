## Mô tả dự án

Dự án phân tích chế độ thị trường (market regimes) của Bitcoin và các altcoin, nghiên cứu hiệu ứng lan tỏa (spillover effects) giữa các tài sản, và phát triển chiến lược giao dịch dựa trên phân tích này.


## Cấu trúc thư mục
```
├── config/                    # File cấu hình
│   └── universe_top20.yaml   # Danh sách 20 cryptocurrency
├── data/
│   ├── raw/                  # Dữ liệu giá gốc (OHLCV) từ Binance
│   └── processed/            # Dữ liệu đã xử lý
│       ├── log_returns_1d.csv
│       ├── btc_regimes.csv
│       └── altcoins_*.csv
├── notebooks/                # Jupyter notebooks phân tích
│   ├── 1_Data_Collection.ipynb
│   ├── 2_Regime_Detection_MSM.ipynb
│   ├── 3_Spillover_Analysis.ipynb
│   └── 4_Backtesting_Strategy.ipynb
└── results/                  # Kết quả và biểu đồ
```

## Quy trình phân tích

### 1. Thu thập dữ liệu

Notebook: 1_Data_Collection.ipynb
Thu thập dữ liệu giá 1 ngày của 20 cryptocurrency từ Binance
Tính log returns và căn chỉnh dữ liệu

### 2. Phát hiện chế độ thị trường

Notebook: 2_Regime_Detection_MSM.ipynb
Sử dụng Markov Switching Model (MSM) để phân loại Bull/Bear markets
Phân tích Bitcoin làm tài sản tham chiếu

### 3. Phân tích spillover

Notebook: 3_Spillover_Analysis.ipynb
Tính toán beta, correlation giữa altcoins và BTC
So sánh thống kê trong các chế độ thị trường khác nhau

### 4. Backtesting chiến lược

Notebook: 4_Backtesting_Strategy.ipynb
Kiểm tra hiệu quả chiến lược giao dịch
Tính toán cumulative returns, drawdown, Sharpe ratio

### Cài đặt
bashpip install -r requirements.txt

###  Sử dụng
Chạy các notebook theo thứ tự từ 1 đến 4. Kết quả phân tích và biểu đồ sẽ được lưu trong thư mục results/.
