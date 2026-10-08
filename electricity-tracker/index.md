---
layout: default
title: Sun Down, Prices Up | José Nunes
---

<p class="back-link"><a href="/#projects">&larr; Back to projects</a></p>

<h1 class="page-title">Sun Down, Prices Up: Wind, Solar and Europe's Electricity Prices</h1>

<p class="page-lead">
More wind and solar should mean cheaper electricity, and on average it does. But it also means very cheap middays, expensive evenings and more and more hours where producers pay to sell their power. I wanted to know how big these effects really are, so I built a tracker that downloads hourly day-ahead prices for 26 European markets every day, with a closer look at Portugal, where I work on energy regulation.
</p>

<p class="page-lead">
Short answer: negative prices went from rare to routine in a few years, solar now earns about half the average price in most countries, and that same gap is what makes batteries more valuable every year.
</p>

<div class="project-links page-links">
  <a href="https://european-electricity-tracker.streamlit.app/" target="_blank" rel="noopener"><i class="fa-solid fa-up-right-from-square"></i> Open the live app</a>
  <a href="https://github.com/josepaulonunes/european-electricity-tracker" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> Code and full results</a>
</div>

<h2>Live app</h2>

<div class="viz-box" id="app-box">
  <img class="figure viz-preview" src="/electricity-tracker/app_preview.png" alt="Map of tomorrow's electricity prices across Europe">
  <button type="button" class="viz-load" id="app-load"><i class="fa-solid fa-hand-pointer"></i> Load the live app</button>
</div>

<script>
// Show a light image first; load the Streamlit app only when the visitor asks for it
document.getElementById("app-load").addEventListener("click", function () {
  document.getElementById("app-box").innerHTML = '<iframe src="https://european-electricity-tracker.streamlit.app/?embed=true" ' +
    'title="European Electricity Tracker" style="width:100%; height:900px; border:1px solid #e3e3e3; border-radius:8px;"></iframe>';
});
</script>
<p class="viz-note">The app runs on Streamlit Community Cloud and updates every afternoon. If nobody has opened it for a while, it can take a few seconds to wake up. On a phone, it works best <a href="https://european-electricity-tracker.streamlit.app/" target="_blank" rel="noopener">in its own page</a>.</p>

<h2>Key findings</h2>

<ul class="findings">
  <li><strong>Negative prices are no longer rare.</strong> Adding up all 26 markets, there were 829 hours with a negative price in 2019 and 7,744 in 2025. The Netherlands, Germany and Spain had the most in 2025, with over 550 hours each.</li>
  <li><strong>Solar is worth about half the average price.</strong> In 2019 solar plants earned roughly the average market price everywhere (92% to 113%). In 2025 it was between 50% and 65% in most countries, because all solar panels produce at the same hours and push those prices down together.</li>
  <li><strong>That gap is what pays batteries.</strong> A 1 MW battery with 4 hours of storage, buying in the cheapest hours and selling in the most expensive, would have earned about 155 thousand € in the Baltic states in 2025, against about 50 thousand € in Norway and Northern Italy, where prices move much less during the day.</li>
  <li><strong>Prices are still very different across Europe.</strong> In 2025 the average price went from 41 €/MWh in Finland to 116 €/MWh in Northern Italy. Portugal was the 6th cheapest of 26, at 66 €/MWh.</li>
  <li><strong>In Portugal, each extra point of wind and solar lowers the price by about 0.94 €/MWh</strong>, holding demand, hydro and the year constant (about 68,000 hours since 2019, R² of 0.49, Newey-West standard errors). Since 2023 the average price is about 113 €/MWh when wind and solar cover less than 10% of consumption, and about 15 €/MWh when they cover more than 80%.</li>
  <li><strong>Portugal is catching up fast on negative prices.</strong> It had none until 2024, and by October 2026 it already had more than 500 hours, almost three times as many as in the whole of 2025.</li>
</ul>

<h2>Hours with a negative price in 2025</h2>
<img class="figure" loading="lazy" src="/electricity-tracker/europe_negative_hours.png" alt="Hours with a negative price in 2025 by country">

<h2>Solar capture rate in 2025</h2>
<img class="figure" loading="lazy" src="/electricity-tracker/europe_capture_rate.png" alt="Solar capture rate in 2025 by country">

<h2>What a battery earns in each country</h2>
<img class="figure" loading="lazy" src="/electricity-tracker/europe_battery_value.png" alt="Yearly profit of a 1 MW battery in 2025 by country">

<h2>Portugal: price by hour of the day</h2>
<img class="figure" loading="lazy" src="/electricity-tracker/duck_curve.png" alt="Average price by hour of the day in Portugal in 2019, 2023 and 2025">

<h2>Portugal: price by share of wind and solar</h2>
<img class="figure" loading="lazy" src="/electricity-tracker/price_by_renewable_share.png" alt="Average price in Portugal by share of wind and solar">

<h2>Data and method</h2>
<p>Hourly day-ahead prices for 26 bidding zones since 2019, and solar, wind and consumption for the 15 largest, come from the ENTSO-E Transparency Platform API. For Portugal I also use the REN DataHub API (prices until June 2026 and production by source every 15 minutes) and OMIE's daily market files, and I checked that the three sources give the same Portuguese prices. The data is cleaned with pandas, stored as CSV files and loaded into SQLite for the analysis with SQL and Python. The solar capture rate is the average price weighted by solar production, divided by the simple average price. The Portuguese regression is an OLS of the hourly price on the share of wind and solar, the share of hydro, demand and year fixed effects, with Newey-West (HAC) standard errors. Every afternoon GitHub Actions runs two Python scripts that add the newest data, and the app is built with Streamlit and Plotly. Countries with several market zones are shown with one of them (Northern Italy, Western Denmark, Stockholm and Oslo). The code is on <a href="https://github.com/josepaulonunes/european-electricity-tracker" target="_blank" rel="noopener">GitHub</a>.</p>

<h2>Limits</h2>
<p>The battery numbers are an upper bound: the battery buys in the cheapest hours and sells in the most expensive ones without checking the order of the hours, and network tariffs and wear are left out. The solar capture rate uses market prices only. The regression shows strong associations, not a clean causal effect, since it leaves out the daily gas price.</p>

<p class="disclaimer">Personal project built with public data only. The views expressed are my own and do not represent ERSE.</p>
