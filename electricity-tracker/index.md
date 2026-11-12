---
layout: default
title: Electricity Prices in Europe | José Sá Nunes
---

<style>
.et-hero {background: linear-gradient(135deg, #0b2545 0%, #1d4e89 60%, #f59e0b 135%); color: #fff; border-radius: 18px; padding: 28px 32px; margin: 0 0 1.4em;}
.et-hero h1 {margin: 0 0 0.3em; font-size: 2em; line-height: 1.2; color: #fff;}
.et-hero p {margin: 0 0 1em; opacity: 0.92; font-size: 1.05em;}
.et-btn {display: inline-block; margin: 0 8px 8px 0; padding: 0.5em 1.1em; border-radius: 999px; background: #fff; color: #0b2545; font-weight: 600; font-size: 0.92em;}
.et-btn.et-ghost {background: rgba(255,255,255,0.16); color: #fff;}
.et-btn::after {display: none;}
.et-btn:hover {opacity: 0.88;}
.et-stats {display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; margin: 1.4em 0;}
.et-stat {background: #fff; border: 1px solid #e5e7eb; border-radius: 14px; padding: 14px 16px; box-shadow: 0 1px 3px rgba(0,0,0,0.05);}
.et-stat b {display: block; font-size: 1.7em; line-height: 1.2; color: #0b2545;}
.et-stat span {font-size: 0.86em; color: #6b7280;}
.et-cards {display: grid; grid-template-columns: repeat(2, 1fr); gap: 14px;}
.et-card {background: #fff; border: 1px solid #e5e7eb; border-radius: 14px; padding: 16px 18px; box-shadow: 0 1px 3px rgba(0,0,0,0.05);}
.et-card h3 {margin: 0 0 0.4em; font-size: 1.05em; color: #0b2545;}
.et-card h3 i {color: #f59e0b; margin-right: 0.4em;}
.et-card p {margin: 0; font-size: 0.95em; color: #444;}
.et-figure {background: #fff; border: 1px solid #e5e7eb; border-radius: 14px; padding: 16px 18px; margin: 0 0 16px; box-shadow: 0 1px 3px rgba(0,0,0,0.05);}
.et-figure h3 {margin: 0 0 0.2em; font-size: 1.1em; color: #0b2545;}
.et-figure p {margin: 0 0 0.6em; font-size: 0.95em; color: #555;}
.et-figure img {display: block; width: 100%; max-width: 680px; height: auto; margin: 0 auto;}
.et-list li {margin-bottom: 0.5em;}
@media (max-width: 700px) {
  .et-hero {padding: 20px;}
  .et-hero h1 {font-size: 1.6em;}
  .et-stats {grid-template-columns: repeat(2, 1fr);}
  .et-cards {grid-template-columns: 1fr;}
}
</style>

<p class="back-link"><a href="/#projects">&larr; Back to projects</a></p>

<div class="et-hero">
<h1>Electricity Prices in Europe</h1>
<p>What happens to power prices when a country builds a lot of wind and solar? I track 26 European markets every day to find out.</p>
<a class="et-btn" href="https://european-electricity-tracker.streamlit.app/" target="_blank" rel="noopener"><i class="fa-solid fa-up-right-from-square"></i> Open the live app</a>
<a class="et-btn et-ghost" href="https://github.com/josepaulonunes/european-electricity-tracker" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> Code and full results</a>
</div>

<p class="page-lead">
More wind and solar should mean cheaper electricity, and on average it does. But it also means very cheap middays, expensive evenings and more and more hours where producers pay to sell their power. I wanted to know how big these effects really are, so I built a tracker that downloads hourly day-ahead prices for 26 European markets every day, with a closer look at Portugal, where I work on energy regulation.
</p>

<div class="et-stats">
<div class="et-stat"><b>26</b><span>markets tracked every day since 2019</span></div>
<div class="et-stat"><b>7,744</b><span>hours with a negative price in 2025, up from 829 in 2019</span></div>
<div class="et-stat"><b>53%</b><span>of the average price is what solar earned in Portugal in 2025 (102% in 2019)</span></div>
<div class="et-stat"><b>155k €</b><span>a year is what a 1 MW battery could make trading in the Baltics in 2025</span></div>
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
<p class="viz-note">The app runs on Streamlit Community Cloud and updates every afternoon. If nobody has opened it for a while, it can take a minute to wake up. On a phone, it works best <a href="https://european-electricity-tracker.streamlit.app/" target="_blank" rel="noopener">in its own page</a>.</p>

<h2>Key findings</h2>

<div class="et-cards">
<div class="et-card"><h3><i class="fa-solid fa-arrow-trend-down"></i>Negative prices are no longer rare</h3><p>Adding up all 26 markets, there were 829 hours with a negative price in 2019 and 7,744 in 2025. The Netherlands, Germany and Spain had the most in 2025, with over 550 hours each.</p></div>
<div class="et-card"><h3><i class="fa-solid fa-sun"></i>Solar is worth about half the average price</h3><p>In 2019 solar plants earned roughly the average market price everywhere (92% to 113%). In 2025 it was between 50% and 65% in most countries, because all solar panels produce at the same hours and push those prices down together.</p></div>
<div class="et-card"><h3><i class="fa-solid fa-battery-three-quarters"></i>That gap is what pays batteries</h3><p>A 1 MW battery with 4 hours of storage, buying in the cheapest hours and selling in the most expensive, would have made about 155 thousand € in the Baltic states in 2025, against about 50 thousand € in Norway and Northern Italy, where prices move much less during the day.</p></div>
<div class="et-card"><h3><i class="fa-solid fa-earth-europe"></i>Prices are still very different across Europe</h3><p>In 2025 the average price went from 41 €/MWh in Finland to 116 €/MWh in Northern Italy. Portugal was the 6th cheapest of 26, at 66 €/MWh.</p></div>
<div class="et-card"><h3><i class="fa-solid fa-wind"></i>More wind and solar, lower prices in Portugal</h3><p>Each extra point of wind and solar goes with a price about 0.94 €/MWh lower, holding demand, hydro and the year constant. Since 2023 the average price is about 113 €/MWh when wind and solar cover less than 10% of consumption, and about 15 €/MWh when they cover more than 80%.</p></div>
<div class="et-card"><h3><i class="fa-solid fa-bolt"></i>Portugal is catching up fast on negative prices</h3><p>It had none until 2024, and by October 2026 it already had more than 500 hours, almost three times as many as in the whole of 2025.</p></div>
</div>

<h2>Europe in 2025</h2>

<div class="et-figure">
<h3>Hours with a negative price</h3>
<p>The markets with the most wind and solar had more than 500 hours where producers paid to sell.</p>
<img loading="lazy" src="/electricity-tracker/europe_negative_hours.png" alt="Hours with a negative price in 2025 by country">
</div>

<div class="et-figure">
<h3>Solar capture rate</h3>
<p>What solar earned compared with the average price. At 100% solar earns the same as a plant that runs all day.</p>
<img loading="lazy" src="/electricity-tracker/europe_capture_rate.png" alt="Solar capture rate in 2025 by country">
</div>

<div class="et-figure">
<h3>What a battery makes in each country</h3>
<p>Yearly trading margin of a 1 MW battery with 4 hours of storage. Bigger daily price swings mean more money.</p>
<img loading="lazy" src="/electricity-tracker/europe_battery_value.png" alt="Yearly trading margin of a 1 MW battery in 2025 by country">
</div>

<h2>Portugal since 2019</h2>

<div class="et-figure">
<h3>Price by hour of the day</h3>
<p>In 2019 the price was almost flat during the day. In 2025 it drops at midday and jumps in the evening.</p>
<img loading="lazy" src="/electricity-tracker/duck_curve.png" alt="Average price by hour of the day in Portugal in 2019, 2023 and 2025">
</div>

<div class="et-figure">
<h3>Price by share of wind and solar</h3>
<p>The more of the consumption wind and solar cover, the lower the price.</p>
<img loading="lazy" src="/electricity-tracker/price_by_renewable_share.png" alt="Average price in Portugal by share of wind and solar">
</div>

<h2>Data and method</h2>

<ul class="et-list">
<li><strong>Data.</strong> Hourly day-ahead prices for 26 bidding zones since 2019, and solar, wind and consumption for the 15 largest, from the ENTSO-E Transparency Platform API. For Portugal I also use the REN DataHub API (prices until June 2026 and production by source every 15 minutes) and OMIE's daily market files. I checked that the three sources give the same Portuguese prices.</li>
<li><strong>Tools.</strong> The data is cleaned with pandas, stored as CSV files and loaded into SQLite for the analysis with SQL and Python. Every afternoon GitHub Actions runs two Python scripts that add the newest data. The app is built with Streamlit and Plotly.</li>
<li><strong>Solar capture rate.</strong> The average price weighted by solar production, divided by the simple average price.</li>
<li><strong>Regression.</strong> An OLS of the hourly Portuguese price on the share of wind and solar, the share of hydro, demand and year fixed effects, with Newey-West (HAC) standard errors. About 68,000 hours since 2019, R² of 0.49.</li>
<li><strong>Market zones.</strong> Countries with several zones are shown with one of them: Northern Italy, Western Denmark, Stockholm and Oslo.</li>
</ul>

<h2>Limits</h2>

<ul class="et-list">
<li>The battery numbers are a rough estimate of the trading margin, not a business case. The battery buys in the cheapest hours and sells in the most expensive ones without checking the order of the hours, and network tariffs, wear and the cost of the battery itself are left out.</li>
<li>Since October 2025 the market uses 15-minute prices. I average them into hours, so the latest negative hour counts are a bit low.</li>
<li>The solar capture rate uses market prices only.</li>
<li>The regression shows a strong link, not a clean causal effect, since it leaves out the daily gas price.</li>
</ul>

<p class="disclaimer">Personal project using public data. Views are my own.</p>
