---
layout: default
title: Fuel Prices in Portugal vs Brent | José Nunes
---

<p class="back-link"><a href="/#projects">&larr; Back to projects</a></p>

<h1 class="page-title">Fuel Prices in Portugal vs Brent</h1>

<p class="page-lead">
How do Portuguese pump prices for gasoline and diesel respond to oil prices, and do they rise faster than they fall ("rockets and feathers")? If they do, is it the petrol stations or the refining and wholesale market? How do Portuguese prices compare with Spain, and can next Monday's price change be predicted?
</p>

<div class="project-links page-links">
  <a href="https://public.tableau.com/app/profile/jos.nunes7914/viz/FuelpricesinPortugalvsBrent/Fuelpricesdashboard" target="_blank" rel="noopener"><i class="fa-solid fa-up-right-from-square"></i> Open dashboard in Tableau Public</a>
  <a href="https://github.com/josepaulonunes/fuel-prices-portugal" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> Code and full results</a>
</div>

<h2>Interactive dashboard</h2>

<div class="viz-wide">
  <div class="viz-scale" id="viz-scale">
    <iframe id="viz" src="https://public.tableau.com/views/FuelpricesinPortugalvsBrent/Fuelpricesdashboard?:showVizHome=no&:embed=true&:toolbar=no&:tabs=no" title="Fuel prices in Portugal vs Brent dashboard" width="1200" height="1000" scrolling="no" loading="lazy"></iframe>
  </div>
</div>

<script>
function fitViz() {
  var box = document.getElementById("viz-scale");
  var frame = document.getElementById("viz");
  var scale = box.clientWidth / 1200;
  frame.style.transform = "scale(" + scale + ")";
  box.style.height = (1000 * scale) + "px";
}
window.addEventListener("load", fitViz);
window.addEventListener("resize", fitViz);
</script>
<p class="viz-note">On a phone, the dashboard works best in <a href="https://public.tableau.com/app/profile/jos.nunes7914/viz/FuelpricesinPortugalvsBrent/Fuelpricesdashboard" target="_blank" rel="noopener">Tableau Public</a>.</p>

<h2>Key findings</h2>

<ul class="findings">
  <li><strong>Diesel rises faster than it falls against crude oil.</strong> In the long run, a 1 cent rise in Brent raises the pre-tax diesel price by about 1.34 cents, while a 1 cent fall lowers it by only 0.80 cents (p = 0.047).</li>
  <li><strong>But this comes from 2022.</strong> When I drop the 2022 energy crisis, the gap shrinks (1.08 vs 0.78) and is no longer significant (p = 0.29). Against the ENSE reference price the gap is not significant either.</li>
  <li><strong>Petrol stations pass on rises and falls equally.</strong> From the ENSE reference price to the pump, diesel rises and falls are passed on almost the same (0.90 vs 0.85, p = 0.37). Falls reach the pump a week or two later, but by week 3 both are the same. Gasoline shows no asymmetry at any stage.</li>
  <li><strong>High diesel margins are corrected fast, low ones slowly.</strong> An error correction model shows that when the retail margin is above its normal level, half of the gap closes in about 2 weeks. When it is below, it takes about 16 weeks. That is the opposite of what "rockets and feathers" would predict.</li>
  <li><strong>Taxes make up about half of the price.</strong> On average since 2019, taxes are 49% of the price of a litre of diesel.</li>
  <li><strong>Portugal vs Spain:</strong> fuel in Portugal costs 17.6 cents per litre more than in Spain for gasoline and 12.3 cents more for diesel, but the whole gap comes from taxes. Before taxes, Portuguese prices are 2 to 3 cents lower.</li>
  <li><strong>Monday forecast:</strong> on 2025 and 2026 data, the model predicts Monday's pump price change with an average error of about 1 cent per litre. A "no change" forecast misses by 2 to 3 cents, and simply copying last week's change in the reference price misses by about 1.2 cents.</li>
</ul>

<h2>Rockets and feathers, week by week</h2>
<p>How much of a 1 cent cost change has reached the pump after each week. Red is a cost rise, blue a cost fall.</p>
<img class="figure" src="/fuel-prices/cumulative_response.png" alt="Cumulative response of pump prices to cost rises and falls, week by week">

<h2>What makes up the price of a litre of diesel</h2>
<img class="figure" src="/fuel-prices/diesel_price_decomposition.png" alt="Diesel price decomposition">

<h2>Portugal vs Spain, price without taxes</h2>
<img class="figure" src="/fuel-prices/portugal_vs_spain_pretax_gap.png" alt="Portugal minus Spain, price without taxes">

<h2>Forecasting Monday's pump price change</h2>
<img class="figure" src="/fuel-prices/monday_forecast_diesel.png" alt="Monday forecast for diesel">

<h2>Data and method</h2>
<p>Weekly data from January 2019 to September 2026. Brent crude and the EUR/USD exchange rate from FRED, Portuguese pump prices with and without taxes from the European Commission Weekly Oil Bulletin, and gasoline and diesel reference prices from ENSE. Pass-through is estimated with an asymmetric distributed lag model by OLS with Newey-West standard errors. I check the results without 2022 and with an asymmetric error correction model (Engle and Granger), and test the Monday forecast out of sample on 2025 and 2026. The full specification, regression tables and code are on <a href="https://github.com/josepaulonunes/fuel-prices-portugal" target="_blank" rel="noopener">GitHub</a>.</p>

<p class="disclaimer">Personal project built with public data only. The views expressed are my own and do not represent ERSE.</p>
