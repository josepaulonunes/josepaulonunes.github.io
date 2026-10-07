---
layout: default
title: José Nunes
---

<div class="profile-header">

  <img class="profile-picture" src="/images/profile.jpg" alt="José Nunes">

  <div class="profile-text">

    <h1>José Nunes</h1>

    <div class="subtitle">
      <p>BSc in Economics, Nova School of Business and Economics</p>
      <p>Lisbon, Portugal</p>
    </div>

    <div class="social-links">
      <a href="mailto:josepnunes3@gmail.com" class="email-link" title="josepnunes3@gmail.com"><i class="fa-solid fa-envelope"></i><span>Email</span></a>
      <a href="https://linkedin.com/in/josepnunes/"><i class="fa-brands fa-linkedin"></i><span>LinkedIn</span></a>
      <a href="https://github.com/josepaulonunes"><i class="fa-brands fa-github"></i><span>GitHub</span></a>
    </div>

  </div>

</div>

<p class="blurb">
I'm an Economist Trainee at ERSE, Portugal's energy regulator, working on regulatory impact assessments and economic analysis across the electricity, fuel and natural gas sectors. My interests are in energy economics, macroeconomics and finance.
</p>

<h2 id="projects">Projects</h2>

<div class="projects">

  <div class="project-card">
    <a href="/electricity-tracker/" class="project-thumb"><img src="/electricity-tracker/duck_curve.png" alt="Average electricity price by hour of the day in Portugal"></a>
    <div class="project-body">
      <h3><a href="/electricity-tracker/">Sun Down, Prices Up: How Wind and Solar Changed Electricity Prices</a></h3>
      <p>As wind and solar grow, what happens to wholesale electricity prices, to the value of solar power and to the value of storage? Hourly data for Portugal since 2019, a regression with Newey-West standard errors, and a live app updated every day with tomorrow's prices and the best hours to store energy.</p>
      <div class="tags"><span>Python</span><span>SQL</span><span>pandas</span><span>statsmodels</span><span>Streamlit</span><span>GitHub Actions</span></div>
      <div class="project-links">
        <a href="/electricity-tracker/"><i class="fa-solid fa-file-lines"></i> Project page</a>
        <a href="https://portugal-electricity-tracker.streamlit.app/" target="_blank" rel="noopener"><i class="fa-solid fa-chart-line"></i> Live app</a>
        <a href="https://github.com/josepaulonunes/portugal-electricity-tracker" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> Code</a>
      </div>
    </div>
  </div>

  <div class="project-card">
    <a href="/fuel-prices/" class="project-thumb"><img src="/fuel-prices/thumbnail.jpg" alt="Fuel prices in Portugal dashboard"></a>
    <div class="project-body">
      <h3><a href="/fuel-prices/">Rockets and Feathers? How Oil Prices Reach the Pump in Portugal</a></h3>
      <p>Do pump prices go up faster than they come down when oil prices move? Weekly data for gasoline and diesel in Portugal since 2019, each step from crude oil to the pump, a comparison with Spain and a forecast of next Monday's price change.</p>
      <div class="tags"><span>Python</span><span>pandas</span><span>statsmodels</span><span>Tableau</span></div>
      <div class="project-links">
        <a href="/fuel-prices/"><i class="fa-solid fa-file-lines"></i> Project page</a>
        <a href="https://public.tableau.com/app/profile/jos.nunes7914/viz/FuelpricesinPortugalvsBrent/Fuelpricesdashboard" target="_blank" rel="noopener"><i class="fa-solid fa-chart-line"></i> Dashboard</a>
        <a href="https://github.com/josepaulonunes/fuel-prices-portugal" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> Code</a>
      </div>
    </div>
  </div>

</div>

<h2 id="academic">Academic Work</h2>

<p class="section-note">Written during my bachelor's degree.</p>

<ul class="papers">

<li>
<a href="/PISA_ICT_Math.pdf"><strong>The Impact of ICT Regulations on the Achievement Gap in Mathematics: A Cross-Sectional Analysis</strong></a>
<span class="clickable-paper">[Summary]</span>
<div class="abstract">
<p>Does stricter school-level regulation of phones and digital devices narrow the maths gap between disadvantaged students and their better-off peers? Using PISA 2022 data on about 82,000 students in ten economies, we estimate weighted least squares models that add socioeconomic, behavioural, school and country fixed-effect controls step by step. Once country fixed effects are included, moving from the least to the most regulated schools is associated with about 25 more points in maths (more than a year of schooling), and about 35 points for disadvantaged students. These are associations from cross-sectional data, not causal effects.</p>
<p><strong>My contribution:</strong> Wrote the results section and coded all figures and tables. <strong>Grade:</strong> 19/20</p>
</div>
</li>

<li>
<a href="/EU_Innovation_Gaps.pdf"><strong>Socioeconomic and Structural Factors in Innovation Gaps: Eastern vs. Western European Union</strong></a>
<span class="clickable-paper">[Summary]</span>
<div class="abstract">
<p>Why do Eastern EU member states file far fewer patents than Western ones? Using 2017 data for 27 EU countries (patent applications to the European Patent Office, R&amp;D spending, tertiary education, population and unemployment), we estimate OLS models with an East-West indicator and check robustness with HC3 robust standard errors, VIF and RESET tests. Even after these controls, Eastern countries file roughly 45% fewer patents: the factors we measure do not close the gap, which points to institutional differences our data cannot capture.</p>
<p><strong>My contribution:</strong> Wrote the results section, ran the robustness checks, and coded all figures and tables in R. <strong>Grade:</strong> 18/20</p>
</div>
</li>

<li>
<a href="/Tuition_Fee_Reform.pdf"><strong>Tuition Fee Reform: Policy Recommendation</strong></a>
<span class="clickable-paper">[Summary]</span>
<div class="abstract">
<p>Should university students pay higher tuition fees? Drawing on evidence from Germany's 2007 tuition fee reforms and on public economics tools (externalities, tax incidence, the Ramsey rule and welfare criteria), I argue that raising fees reduces enrolment, falls hardest on low-income students, and is both inefficient and inequitable.</p>
<p><strong>Grade:</strong> 18/20</p>
</div>
</li>

</ul>

<script>
document.addEventListener("DOMContentLoaded", function () {
  // Email: copy the address and show it (many people have no mail app, so mailto alone does nothing)
  document.querySelectorAll(".email-link").forEach(function (el) {
    el.addEventListener("click", function () {
      var addr = "josepnunes3@gmail.com";
      if (navigator.clipboard) { navigator.clipboard.writeText(addr).catch(function () {}); }
      var label = el.querySelector("span");
      label.textContent = "Copied: " + addr;
      setTimeout(function () { label.textContent = "Email"; }, 2500);
    });
  });

  document.querySelectorAll(".clickable-paper").forEach(function (el) {
    el.style.cursor = "pointer";
    el.addEventListener("click", function () {
      const next = el.closest("li").querySelector(".abstract");
      if (next) {
        next.style.display = (next.style.display === "block") ? "none" : "block";
        el.classList.toggle("open");
      }
    });
  });
});
</script>
