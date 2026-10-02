---
layout: default
title: "Rockets and Feathers: Oil Price Pass-Through to Fuel Prices | José Nunes"

<p class="back-link"><a href="/#projects">&larr; Back to projects</a></p>

<h1 class="page-title">Rockets and Feathers: Oil Price Pass-Through to Fuel Prices in Portugal</h1>

<p class="page-lead">
When oil prices rise, do pump prices follow faster than when they fall? This "rockets and feathers" pattern is a long standing question in energy and competition policy. Using weekly data since 2019, this project tests it for gasoline and diesel in Portugal, separates the role of refining and wholesale markets from that of petrol stations, compares prices before and after taxes with Spain, and forecasts next Monday's pump price change.
</p>

<div class="project-links page-links">
  <a href="https://public.tableau.com/app/profile/jos.nunes7914/viz/FuelpricesinPortugalvsBrent/Fuelpricesdashboard" target="_blank" rel="noopener"><i class="fa-solid fa-up-right-from-square"></i> Open dashboard in Tableau Public</a>
  <a href="https://github.com/josepaulonunes/fuel-prices-portugal" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> Code and full results</a>
</div>

<h2>Interactive dashboard</h2>

<div class="viz-box" id="viz-box">
  <img class="figure viz-preview" src="/fuel-prices/tableau_dashboard.png" alt="Fuel prices in Portugal vs Brent dashboard" width="1186" height="991">
  <button type="button" class="viz-load" id="viz-load"><i class="fa-solid fa-hand-pointer"></i> Load interactive dashboard</button>
</div>

<script>
// Show a light image first; load the Tableau dashboard only when the visitor asks for it
function fitViz() {
  var box = document.getElementById("viz-scale");
  var frame = document.getElementById("viz");
  if (!box || !frame) { return; }
  var scale = box.clientWidth / 1200;
  frame.style.transform = "scale(" + scale + ")";
  box.style.height = (1000 * scale) + "px";
}

document.getElementById("viz-load").addEventListener("click", function () {
  var holder = document.getElementById("viz-box");
  holder.innerHTML = '<div class="viz-scale" id="viz-scale">' +
    '<iframe id="viz" src="https://public.tableau.com/views/FuelpricesinPortugalvsBrent/Fuelpricesdashboard?:showVizHome=no&:embed=true&:toolbar=no&:tabs=no" ' +
    'title="Fuel prices in Portugal vs Brent dashboard" width="1200" height="1000" scrolling="no"></iframe></div>';
  fitViz();
});

window.addEventListener("resize", fitViz);
</script>
<p class="viz-note">The interactive version loads from Tableau Public and can take a few seconds. On a phone, it works best directly in <a href="https://public.tableau.com/app/profile/jos.nunes7914/viz/FuelpricesinPortugalvsBrent/Fuelpricesdashboard" target="_blank" rel="noopener">Tableau Public</a>.</p>

<h2>Key findings</h2>

<ul class="findings">
  <li><strong>Diesel rises faster than it falls against crude oil.</strong> In the long run, a 1 cent rise in Brent raises the pre-tax diesel price by about 1.34 cents, while a 1 cent fall lowers it by only 0.80 cents (p = 0.047).</li>
  <li><strong>But not against the wholesale reference price.</strong> Using the ENSE reference price, diesel rises and falls are passed on almost equally (0.90 vs 0.85, p = 0.37). The asymmetry comes from refining and wholesale markets, not from petrol stations.</li>
  <li><strong>Gasoline shows no asymmetry</strong> against either cost measure.</li>
  <li><strong>Taxes make up about half of the price.</strong> On average since 2019, taxes are 49% of the price of a litre of diesel.</li>
  <li><strong>Portugal vs Spain:</strong> fuel in Portugal costs 17.6 cents per litre more than in Spain for gasoline and 12.3 cents more for diesel, but the whole gap comes from taxes. Before taxes, Portuguese prices are 2 to 3 cents lower.</li>
  <li><strong>Monday forecast:</strong> last week's change in the reference price predicts Monday's pump price change with an average error of about 1 cent per litre on 2025 and 2026 data, less than half the error of a "no change" forecast.</li>
</ul>

<h2>Rockets and feathers</h2>
<img class="figure" loading="lazy" src="/fuel-prices/rockets_feathers_comparison.png" alt="Long run pass-through of cost rises and falls">

<h2>What makes up the price of a litre of diesel</h2>
<img class="figure" loading="lazy" src="/fuel-prices/diesel_price_decomposition.png" alt="Diesel price decomposition">

<h2>Portugal vs Spain, price without taxes</h2>
<img class="figure" loading="lazy" src="/fuel-prices/portugal_vs_spain_pretax_gap.png" alt="Portugal minus Spain, price without taxes">

<h2>Forecasting Monday's pump price change</h2>
<img class="figure" loading="lazy" src="/fuel-prices/monday_forecast_diesel.png" alt="Monday forecast for diesel">

<h2>Data and method</h2>
<p>Weekly data from January 2019 to September 2026. Brent crude and the EUR/USD exchange rate from FRED, Portuguese pump prices with and without taxes from the European Commission Weekly Oil Bulletin, and gasoline and diesel reference prices from ENSE. Pass-through is estimated with an asymmetric distributed lag model by OLS with Newey-West standard errors. The full specification, regression tables and code are on <a href="https://github.com/josepaulonunes/fuel-prices-portugal" target="_blank" rel="noopener">GitHub</a>.</p>

<p class="disclaimer">Personal project built with public data only. The views expressed are my own and do not represent ERSE.</p>
