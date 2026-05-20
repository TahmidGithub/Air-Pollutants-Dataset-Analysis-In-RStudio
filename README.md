# Air Pollutants Dataset Analysis

An interactive data analytics dashboard built in R, exploring trends and patterns in air pollutant data across Portsmouth. Created as part of my Software Engineering degree at the University of Portsmouth.

## 📊 Live Dashboard

**[👉 View the interactive dashboard here](https://tahmidgithub.github.io/Air-Pollutants-Dataset-Analysis-In-RStudio/)**

## 🛠️ Built With

- **R** & **RStudio**
- **flexdashboard** — interactive dashboard framework
- **R Markdown** — reproducible analysis
- **plotly**, **ggplot2**, **dplyr**, **tidyr** — data wrangling and visualisation

## 📁 Project Structure

- `flexdashboard.Rmd` — main R Markdown source for the dashboard
- `flexdashboard.html` — knitted interactive output (served via GitHub Pages)
- `visualisation 1.R` – `visualisation 5.R` — individual visualisation scripts
- `iDAV CW Datasets/` — source air pollutant datasets
- `Report and Review.pdf` — full written report and analysis review
- `CW1.Rproj` — RStudio project file

## 🚀 Running Locally

1. Clone the repository
2. Open `CW1.Rproj` in RStudio
3. Open `flexdashboard.Rmd` and click **Knit** to regenerate the dashboard

## 📌 About

End-to-end data analytics project in R — from raw CSV datasets through cleaning, aggregation, and an interactive reporting dashboard. The analysis explores four air pollutants (**PM10**, **Nitric Oxide**, **Nitrogen Oxides as Nitrogen Dioxide**, and **Nitrogen Dioxide**) across 2018–2023, with a focus on specific dates of interest, monthly averages within 2020, and long-term yearly trends.

### 🔍 Approach

- Built individual data frames for each year from raw CSVs, then combined them into a single `POARTOTAL` master dataset.
- Renamed verbose CSV column names (e.g. `PM.sub.10..sub..particulate.matter..Hourly.measured`) into clean references like `PM10`.
- Filtered for specific dates of interest into a `TOTAL_DATE` data frame, removing `NA` values from the PM10 column to ensure clean visualisations.
- Created `POAR2020_filtered` and `monthly_avg_2020` to produce monthly pollutant averages across 2020.
- Created `POARTOTALYEARS` and `yearly_avg` to produce yearly averages across 2018–2023.

### 📈 Visualisations

1. **PM10 across specific dates** — Plotly scatter graph chosen for clear trend visibility and easy date comparison.
2. **Nitric Oxide across specific dates** — ggplot2 `facet_wrap` for side-by-side trend identification.
3. **Nitrogen Oxides as Nitrogen Dioxide across specific dates** — Box plots showing median, min/max, and overall distribution.
4. **2020 monthly averages of all pollutants** — Heatmap for easy comparison of relative concentration across months and pollutants.
5. **Yearly averages of all pollutants (2018–2023)** — Bar chart for clear comparison of pollutant levels across years.

### 💡 Key Findings

- **PM10 levels** were consistently between 10–25 concentration units across most observed dates, suggesting these are normal baseline levels for the area. The date **26-03-2020** stood out with a peak of nearly 50 PM10 — the highest in the sample.
- **Nitric Oxide** followed a similar trend to PM10, generally varying between 10–25 concentration units.
- **Nitrogen Oxides as Nitrogen Dioxide** showed notably higher concentrations than the other pollutants, peaking at **173** on 29-11-2021.
- In the **2020 monthly heatmap**, Nitrogen Oxides as Nitrogen Dioxide was the dominant pollutant year-round, reaching an average of **59** in January. The lowest monthly average was Nitric Oxide in April at **2.97**.
- The **yearly averages (2018–2023)** confirmed the long-term trend: Nitrogen Oxides as Nitrogen Dioxide consistently had the highest average concentration, followed by Nitrogen Dioxide, PM10, and finally Nitric Oxide — a useful baseline for understanding which pollutants may pose greater environmental concern.

For the full written report, see [`Report and Review.pdf`](./Report%20and%20Review.pdf).
