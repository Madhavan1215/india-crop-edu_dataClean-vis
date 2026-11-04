# India Crop Production: Exploratory Data Analysis

An exploratory analysis of district-level crop production in India (1997–2014): which states grow the most, how land use changed over time, and how yields differ between regions. Built with pandas, matplotlib and seaborn.

## Dataset

- **Source:** Ministry of Agriculture & Farmers Welfare, Government of India (originally published on [data.gov.in](https://data.gov.in/))
- **Copy used:** [Crop Production in India on Kaggle](https://www.kaggle.com/datasets/abhinand05/crop-production-in-india) (`data/crop_production.csv`, about 15 MB)
- **Columns:** state, district, year, season, crop, area (hectares), production (tonnes)

## Findings

1. **Rice leaders:** West Bengal and Uttar Pradesh together produced about 477 million tonnes of rice between 1997 and 2014, roughly 30% of all rice production in this dataset.
2. **Trend:** Rice area grew from about 30.7 million hectares in 1997 to 39.1 million in 2014, a rise of roughly 27%.
3. **Seasons:** Kharif crops cover about 1.5 times as much land as Rabi crops (1.40 vs 0.95 billion hectare-years).
4. **Wheat yield:** Among the eight states with the most wheat records, median yield is highest in Uttar Pradesh (2.78 t/ha) and lowest in Assam (1.18 t/ha), more than double.
5. **Tamil Nadu:** Rice covers about 1.9 million hectares per year, over three times as much as the next crop, groundnut (about 0.6 million).

## Data cleaning

- Standardised column names and stripped extra whitespace from text columns
- Dropped rows with missing or zero production or area, and duplicate rows
- Added a yield column (production ÷ area)
- Removed aggregate rows such as "Total foodgrain" from the Tamil Nadu chart, since they double-count other crops
- Never summed production across different crops, because units differ (for example coconut)

## How to run

Requires [uv](https://docs.astral.sh/uv/).

```bash
git clone https://github.com/Madhavan1215/india-crop-edu_dataClean-vis.git
cd india-crop-edu_dataClean-vis
uv sync
uv run jupyter lab
```

Then open `notebooks/eda.ipynb` and choose **Kernel → Restart Kernel and Run All Cells**.

## Next idea

Predict crop yield from state, season and year, as a first machine learning model.