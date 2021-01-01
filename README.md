# stock-website

## 限時一個禮拜的分組趣味性質模擬賽

從 mock api 獲取資料並按照規定格式渲染

## 期間實現功能: 
  - 搜尋股票代號欄位，並即時顯示搜尋結果
  - 依照年份重新排序資料
  - loading 畫面
  - 動態抽換 DOM (Single Page Application)
  - 數字加上千分位符號，負數顯示為 紅色 小括號
  - 按照年表欄位層級對欄位縮排
  - 頁面重載時能維持在上一次瀏覽的頁面
  - 預設 2330 當進入網站的顯示資料

### Source

年表欄位層級
- https://5fbd1e2b3f8f90001638cc76.mockapi.io/layer
- 說明
    - order
        - 1 表示該欄位為第一層
        - 2 表示該欄位為第二層，欄位需縮排
    - parent
        - value 表示該欄位所屬父層

```json=
[
  {
    "id": 8,
    "table_name": "balance_sheets",//所屬表格為「資產負債表」
    "column_name": "other_current_assets",//該欄位名稱為「其他流動資產」
    "parent": "current_assets",//該欄位所屬父層為「流動資產」
    "order": 2 //該欄位為第二層級
  },
  {
    "id": 9,
    "table_name": "balance_sheets",//所屬表格為「資產負債表」
    "column_name": "current_assets",//該欄位名稱為「流動資產」
    "parent": "first", //該欄位沒有父層
    "order": 1 //該欄位為第一層級
  }
]
```

- 年表
  - https://5fbd1e2b3f8f90001638cc76.mockapi.io/reportYear2330
  - https://5fbf2d965923c90016e6ba2d.mockapi.io/reportYear3043
- 財務比例分析
  - https://5fbd1e2b3f8f90001638cc76.mockapi.io/reportRatioYear2330
  - https://5fbf2d965923c90016e6ba2d.mockapi.io/reportRatioYear3043
- 資產分析圖
  - https://5fbd1e2b3f8f90001638cc76.mockapi.io/chartAssetYear2330
  - https://5fbf2d965923c90016e6ba2d.mockapi.io/chartAssetYear3043
