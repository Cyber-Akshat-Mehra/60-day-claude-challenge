Prompt:-


Act as a Senior Data Analyst, Environmental Researcher, UX Designer, and Frontend Dashboard Developer.

Create a Claude Artifact called:
🌍 Personal Environmental Health Analyzer

DATA RULES

If a dataset is provided, use it. If no dataset is provided, automatically search the web for the latest AQI and water-quality data for the user's current city/location. If location is unavailable, ask for the city name first. Use the most recent available data, cite sources, clean the data, handle missing values, and validate quality before analysis.

ANALYSIS

Generate: cleanest city, most polluted city, highest AQI city, lowest AQI city, average AQI, number of cities analyzed, trends, anomalies, most surprising observation, executive summary.

INTERACTIVE DASHBOARD

Create a fully interactive Claude Artifact with:

📊 Key Metrics: average AQI, highest AQI city, lowest AQI city, number of cities analyzed, environmental health score.

📈 Visualizations: AQI comparison chart, PM2.5 comparison chart, PM10 comparison chart, city ranking chart, AQI distribution chart.

🎛 Interactive Filters: city selector, AQI range filter, pollutant selector, health-risk filter, date filter (if available), city comparison mode.

📋 City Detail Cards: AQI, PM2.5, PM10, air-quality category, health score, water-quality score.

🚦 AQI Categories: Good (Green), Satisfactory (Light Green), Moderate (Yellow), Poor (Orange), Very Poor (Red), Severe (Dark Red).

ENVIRONMENTAL HEALTH ANALYSIS

For the selected city explain AQI impact on lungs, sleep, energy levels, exercise performance, long-term health, and water-quality impact on hair fall, hair dryness, scalp health, skin dryness, acne, and sensitive skin.

Use risk indicators: 🟢 Low, 🟡 Moderate, 🔴 High.

PERSONAL REPORT CARD

Generate an Environmental Health Score (0–100) with breakdowns for Air Quality Score, Water Quality Score, and Overall Environmental Score.

Assign grades for Air Quality (A–F), Water Quality (A–F), Hair Risk, and Skin Risk.

INSIGHTS PANEL

Include: top 3 cleanest cities, top 3 most polluted cities, biggest anomaly, most surprising observation, recommended actions.

PERSONALIZED RECOMMENDATIONS

Provide: daily actions, indoor air improvements, outdoor activity guidance, hair-care recommendations, skin-care recommendations, water-quality improvement suggestions.

DESIGN

Modern, professional, mobile responsive, dark theme, smooth animations, premium UI, clean typography, dashboard-style layout, highly visual, colourful, LinkedIn-shareable.

OUTPUT

Generate a complete downloadable HTML application that is fully responsive and ready to save as index.html.

IMPORTANT

Do not provide code snippets. Create a complete interactive Claude Artifact with working charts, filters, cards, insights, report cards, and dashboards that users can interact with directly.





Result :-

Good, the JS is syntactically valid. Let me also sanity-check the numeric calculations and do a quick visual check with a headless browser if available.Scores look sensible and consistent with the categories. Now let's copy the final file to outputs and present it.No dataset was provided, so I pulled live AQI data for 10 major Indian cities today (CPCB, AQI.in, AQICN) and built the full dashboard around it — save as `index.html` and it works standalone, dark theme, fully interactive.

A few honest notes on the data, all documented in the app's "Data Quality & Methodology" panel:
- **AQI**: real, sourced live snapshots (15 Jul 2026).
- **PM2.5/PM10**: not uniformly published per-city, so derived from AQI via CPCB sub-index breakpoints — flagged as derived, not raw readings.
- **Water Quality**: uses CPCB/NITI Aayog state-level composite scores as a city proxy (Delhi and Jaipur have direct citations; others are estimated and marked with `*`).
- It's a static snapshot, not a live feed — the numbers won't auto-refresh, by design, since this is a downloadable file.

What's in it: 6 key metrics, 5 charts (AQI/PM2.5/PM10 comparison, ranking, distribution), city/AQI-range/pollutant/risk filters, 10 city cards, a two-city comparison mode, a per-city health-impact breakdown (lungs/sleep/energy/exercise/long-term + hair/skin), an Environmental Health Report Card with A–F grades, an insights panel (the anomaly and gap-detection are computed live from the data, not scripted), personalized recommendations, an executive summary, and a "copy shareable summary" button for LinkedIn.

Since it's monsoon season, current AQI readings are on the cleaner end (Good–Moderate) — worth re-running this in winter, when north Indian cities typically spike much higher.


And the file is provided in Personal Environmental Health Analyzer folder
