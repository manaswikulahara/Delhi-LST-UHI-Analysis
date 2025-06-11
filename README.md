# Delhi Land Surface Temperature and Urban Heat Island Analysis (2022–2024)

This repository contains Google Earth Engine (GEE) scripts used to analyze the **Land Surface Temperature (LST)** and **Urban Heat Island (UHI)** effects over **Delhi** using **Landsat 8 Surface Temperature Data** for the years 2022, 2023, and 2024 (May–June).

---

## 📂 Contents

| File | Description |
|------|-------------|
| `1_LST_May_June_2022.js` | Extracts and exports mean LST for May–June 2022 |
| `2_LST_May_June_2023.js` | Extracts and exports mean LST for May–June 2023 |
| `3_LST_May_June_2024.js` | Extracts and exports mean LST for May–June 2024 |
| `4_LST_UHI_Combined_2022_2024.js` | Visualizes and compares LST for all 3 years to assess UHI |
| `README.md` | Documentation and instructions |

---

## 📍 Area of Interest

All scripts use **Delhi** as the area of interest. The boundary is defined by:

- Custom shapefile (`Delhi_ward`) uploaded as an asset, or
- FAO GAUL dataset (`ADM1_NAME = 'Delhi'`)

---

## 📅 Time Range

- **Start Date**: May 1 of each year
- **End Date**: June 30 of each year
- Filtered for cloud-free pixels (`CLOUD_COVER < 10%`)

---

## 🌡️ LST Processing Steps

1. **Filter** Landsat 8 Collection 2 (Level 2) imagery
2. **Mask** clouds and shadows using `QA_PIXEL`
3. **Scale** LST band (`ST_B10`) to Kelvin and convert to Celsius
4. **Mean** LST is computed over the 2-month window
5. **Clipping** to Delhi boundary
6. **Exporting** to Google Drive as GeoTIFFs

---

## 📊 UHI Visualization

- Combined map layers for all three years
- Color-coded using:
  ```js
  palette: ['blue', 'cyan', 'yellow', 'orange', 'red']

