---
layout: default
title: Sun Down, Prices Up | José Nunes
---

<p class="back-link"><a href="/#projects">&larr; Back to projects</a></p>

<h1 class="page-title">Sun Down, Prices Up: How Wind and Solar Changed Electricity Prices in Portugal</h1>

<p class="page-lead">
Across Europe, wind and solar are changing how electricity prices behave: lower on average, much lower at midday and still high in the evening. This project measures these effects with hourly data for Portugal since 2019: how much each extra point of wind and solar lowers the wholesale price, how much value solar loses as more of it is built, and how much the gap between cheap and expensive hours is worth to a battery. These questions are at the centre of the EU debate on electricity market design and on investment in storage. A live app, the Portugal Electricity Tracker, is updated automatically every day and shows tomorrow's prices, where today's electricity came from and how much a battery would earn.
</p>

<div class="project-links page-links">
  <a href="https://portugal-electricity-tracker.streamlit.app/" target="_blank" rel="noopener"><i class="fa-solid fa-up-right-from-square"></i> Open the live app</a>
  <a href="https://github.com/josepaulonunes/portugal-electricity-tracker" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> Code and full results</a>
</div>

<h2>Key findings</h2>

<ul class="findings">
  <li><strong>More wind and solar, lower prices.</strong> Since 2023, the average price is about 113 €/MWh in hours when wind and solar cover less than 10% of consumption, and about 15 €/MWh when they cover more than 80%.</li>
  <li><strong>Each extra point of wind and solar lowers the price by about 0.94 €/MWh</strong>, controlling for demand, hydro and the year. One extra GW of demand raises it by about 8 €/MWh (about 68,000 hours since 2019, R² of 0.49).</li>
  <li><strong>The duck curve has arrived.</strong> In 2019 prices were almost flat during the day. Now solar pushes midday prices down, while evening prices stay high.</li>
  <li><strong>Solar is losing value.</strong> The solar capture rate (the price solar plants receive compared with the average price) fell from 102% in 2019 to about 50% in 2026, because all solar plants produce at the same hours.</li>
  <li><strong>Batteries are worth more every year.</strong> A 1 MW battery with 4 hours of storage, charging in the cheapest hours and discharging in the most expensive, would have earned about 9 thousand € in 2019 and about 130 thousand € per year at the 2026 pace. The cheaper midday gets, the more storage is worth.</li>
  <li><strong>Near zero and negative prices are now common.</strong> There were 19 hours with a price at or below 1 €/MWh in 2019 and 1,190 so far in 2026. Negative prices appeared in 2024 and reached 541 hours so far in 2026.</li>
</ul>

<h2>Price by share of wind and solar</h2>
<img class="figure" loading="lazy" src="/electricity-tracker/price_by_renewable_share.png" alt="Average price by share of wind and solar">

<h2>Price by hour of the day</h2>
<img class="figure" loading="lazy" src="/electricity-tracker/duck_curve.png" alt="Average price by hour of the day in 2019, 2023 and 2025">

<h2>Solar capture rate</h2>
<img class="figure" loading="lazy" src="/electricity-tracker/solar_capture_rate.png" alt="Solar capture rate by year">

<h2>Value of a battery</h2>
<img class="figure" loading="lazy" src="/electricity-tracker/battery_value.png" alt="Yearly profit of a 1 MW battery">

<h2>Data and method</h2>
<p>Hourly day-ahead prices for Portugal from the REN DataHub API (2019 to June 2026) and from OMIE market files (from July 2026), converted from Spanish to Portuguese time. Production by source every 15 minutes from the REN DataHub API, converted to hourly averages. The data is stored in CSV files and loaded into a SQLite database for the analysis with SQL and Python. The regression of the hourly price on the share of wind and solar, the share of hydro, demand and year fixed effects is estimated by OLS with Newey-West (HAC) standard errors. A Python script run every day by GitHub Actions adds the newest data, and the app is built with Streamlit. The code is on <a href="https://github.com/josepaulonunes/portugal-electricity-tracker" target="_blank" rel="noopener">GitHub</a>.</p>

<p class="disclaimer">Personal project built with public data only. The views expressed are my own and do not represent ERSE.</p>
