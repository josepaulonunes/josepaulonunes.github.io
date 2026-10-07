---
layout: default
title: Rockets and Feathers? | José Nunes
---

<p class="back-link"><a href="/#projects">&larr; Back to projects</a></p>

<h1 class="page-title">Rockets and Feathers? How Oil Prices Reach the Pump in Portugal</h1>

<p class="page-lead">
When oil gets more expensive, pump prices seem to go up straight away. When oil gets cheaper, they seem to take forever to come down. Economists call this "rockets and feathers". I tested whether it happens in Portugal with weekly data for gasoline and diesel since 2019, looking at each step from crude oil to the pump. I also compared Portugal with Spain and tried to predict next Monday's price change.
</p>

<p class="page-lead">
Short answer: petrol stations pass on rises and falls in the same way. The only clear gap is diesel against crude oil, and it comes from the 2022 energy crisis.
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
  <li><strong>Petrol stations pass on rises and falls equally.</strong> Against the ENSE reference price, a 1 cent rise in the cost raises the diesel pump price by 0.90 cents in the long run and a 1 cent fall lowers it by 0.85 cents (p = 0.37). For gasoline it is 0.78 both ways. Cuts take a week or two longer to reach the pump, but by week 3 the gap is gone.</li>
  <li><strong>Diesel against crude oil is the only exception, and it comes from 2022.</strong> A 1 cent rise in Brent raises the diesel price before taxes by 1.34 cents, a fall lowers it by only 0.80 (p = 0.047). Without 2022, or with 4 or more weeks in the model, the difference is no longer significant. That year refined diesel became much more expensive than crude after the sanctions on Russia.</li>
  <li><strong>High margins do not last, low ones do.</strong> When the diesel pump price is above its usual level compared with the reference price, half of the gap closes in about 2 weeks. When it is below, it takes about 16 weeks. That is the opposite of rockets and feathers.</li>
  <li><strong>Taxes are about half of the price.</strong> On average since 2019, taxes are 49% of what you pay for a litre of diesel.</li>
  <li><strong>Portugal is more expensive than Spain only because of taxes.</strong> The gap is 17.6 cents per litre for gasoline and 12.3 cents for diesel. Before taxes, Portugal is 2 to 3 cents cheaper.</li>
  <li><strong>Monday's price change can be predicted quite well.</strong> Tested on 2025 and 2026, the model misses by about 1 cent per litre on average. Assuming no change misses by 2 to 3 cents, and copying last week's change in the reference price misses by about 1.2 cents.</li>
</ul>

<h2>Rockets and feathers, week by week</h2>
<p>How much of a 1 cent change in the cost has reached the pump after each week. Red is a rise, blue a fall. If prices were rockets and feathers, the red line would climb faster and end higher. Against the reference price, both lines end up in the same place.</p>
<img class="figure" loading="lazy" src="/fuel-prices/cumulative_response.png" alt="Cumulative response of pump prices to cost rises and falls, week by week">

<h2>What makes up the price of a litre of diesel</h2>
<img class="figure" loading="lazy" src="/fuel-prices/diesel_price_decomposition.png" alt="Diesel price decomposition">

<h2>Portugal vs Spain, price without taxes</h2>
<img class="figure" loading="lazy" src="/fuel-prices/portugal_vs_spain_pretax_gap.png" alt="Portugal minus Spain, price without taxes">

<h2>Forecasting Monday's pump price change</h2>
<img class="figure" loading="lazy" src="/fuel-prices/monday_forecast_diesel.png" alt="Monday forecast for diesel">

<h2>Data and method</h2>
<p>Weekly data from January 2019 to September 2026. Brent crude and the EUR/USD exchange rate from FRED, Portuguese pump prices with and without taxes from the European Commission Weekly Oil Bulletin, and gasoline and diesel reference prices from ENSE. Pass-through is estimated with an asymmetric distributed lag model by OLS with Newey-West standard errors. I check the results without 2022, with 1 to 6 weeks of lags and with an asymmetric error correction model (Engle and Granger), and test the Monday forecast out of sample on 2025 and 2026. The full specification, regression tables and code are on <a href="https://github.com/josepaulonunes/fuel-prices-portugal" target="_blank" rel="noopener">GitHub</a>.</p>

<p class="disclaimer">Personal project built with public data only. The views expressed are my own and do not represent ERSE.</p>
