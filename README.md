# ARIA v9.5 — The Resilience Monitor

## Week 14 Homework

---

## 1. 專案簡介

本作業將 ARIA 系統升級至 **v9.5 — The Resilience Monitor**，將觀測範圍延伸至 2000–2026 年，並進行下列分析：

1. 太魯閣／秀林地區的年度 NDVI 長期趨勢。
2. 像素級 Greening、Browning 與 Stable 空間分布。
3. 桃園台地埤塘消失、新增水體與 MNDWI 驗證。
4. 2024 年花蓮地震後的植被恢復比率與韌性分類。
5. NDVI、MNDWI、NBR 多指標趨勢儀表板。
6. 太魯閣 2000–2026 年 NDVI 年度動畫 GIF。

1~4 為四個核心 Task，5、6為 Bonus 1、Bonus 2。

---

## 2. 研究區

### 太魯閣／秀林研究區

```python
TAROKO_BBOX = [
    121.34526379253053,
    24.046021742135874,
    121.85149217685861,
    24.35767637905926
]
```

### 桃園台地研究區

```python
TAOYUAN_BBOX = [
    120.94,
    24.83,
    121.35,
    25.08
]

TAOYUAN_URBAN_BBOX = [
    121.00,
    24.88,
    121.28,
    25.05
]
```

## 3. Notebook 執行流程

| 分析階段    | 主要內容                     |
| ------- | ------------------------ |
| 環境設定    | 安裝套件、匯入函式庫、初始化 GEE       |
| 共用前處理   | Landsat 波段調和、表面反射率校正、雲遮罩 |
| Task 1  | 年度 NDVI 中值合成與長期趨勢圖       |
| Task 2  | 像素級線性趨勢、分類統計與 GeoTIFF 匯出 |
| Task 3  | 桃園 MNDWI、水體頻率、埤塘變遷與驗證    |
| Task 4  | 植被恢復比率、韌性分類與 GeoTIFF 匯出  |
| Bonus 1 | NDVI、MNDWI、NBR 多指標儀表板    |
| Bonus 2 | 2000–2026 年 NDVI 動畫 GIF  |


## 4. 輸出檔案

| 檔案名稱                                     | 用途                        |
| ---------------------------------------- | ------------------------- |
| `taroko_annual_ndvi_trend_2000_2026.png` | Task 1 年度 NDVI 趨勢圖        |
| `taoyuan_pond_change_summary.csv`        | Task 3 桃園埤塘變遷統計           |
| `taroko_resilience_summary.csv`          | Task 4 植被韌性分類統計           |
| `taroko_multi_index_annual_summary.csv`  | Bonus 1 多指標年度統計           |
| `taroko_multi_index_dashboard.png`       | Bonus 1 多指標儀表板            |
| `taroko_ndvi_test_frame_2024.png`        | Bonus 2 動畫測試影格            |
| `taroko_ndvi_2000_2026_timelapse.gif`    | Bonus 2 年度 NDVI 動畫        |
| `gee_geotiff_export_screenshot.png`      | Google Drive GeoTIFF 匯出證明 |

```
