---
layout: default
title: José Nunes
---

<div class="profile-header">

  <img class="profile-picture" src="/profile.jpg" alt="José Nunes">

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
I'm an economist intern at ERSE, Portugal's energy sector regulator, working on regulatory impact assessments and economic analysis across electricity, natural gas, fuels, and electric mobility. My interests are in macroeconomics, finance, and industrial organization.
</p>

<!-- =========================================================
     PROJECTS: hidden until P1 has a live dashboard.
     To publish: remove the comment markers around the block
     below, uncomment the Projects link in _layouts/default.html,
     add screenshots to /img/ and replace the LINK-TO placeholders.
     ========================================================= -->
<!--
<h2 id="projects">Projects</h2>

<div class="projects">

  <div class="project-card">
    <img src="/img/ecb-policy-monitor.png" alt="ECB Policy Monitor dashboard">
    <div class="project-body">
      <h3>ECB Policy Monitor</h3>
      <p>Is the ECB too tight or too loose? Taylor rule, output gap and inflation breakdown for the euro area, updated automatically every week.</p>
      <div class="tags"><span>Python</span><span>SQL</span><span>statsmodels</span><span>Streamlit</span><span>GitHub Actions</span></div>
      <div class="project-links">
        <a href="https://LINK-TO-STREAMLIT-APP"><i class="fa-solid fa-chart-line"></i> Live dashboard</a>
        <a href="https://github.com/josepaulonunes/ecb-policy-monitor"><i class="fa-brands fa-github"></i> Code</a>
      </div>
    </div>
  </div>

  <div class="project-card">
    <img src="/img/euro-bond-market-lab.png" alt="Euro Area Bond Market Lab">
    <div class="project-body">
      <h3>Euro Area Bond Market Lab</h3>
      <p>From bailout to below France: what drives euro area sovereign spreads, fundamentals or panic?</p>
      <div class="tags"><span>R</span><span>fixest</span><span>Quarto</span><span>Shiny</span></div>
      <div class="project-links">
        <a href="https://LINK-TO-SHINY-APP"><i class="fa-solid fa-chart-line"></i> Live app</a>
        <a href="https://LINK-TO-QUARTO-REPORT"><i class="fa-solid fa-file-lines"></i> Report</a>
        <a href="https://github.com/josepaulonunes/euro-bond-market-lab"><i class="fa-brands fa-github"></i> Code</a>
      </div>
    </div>
  </div>

  <div class="project-card">
    <img src="/img/eu-fuel-price-monitor.png" alt="EU Fuel Price Monitor report">
    <div class="project-body">
      <h3>EU Fuel Price Monitor</h3>
      <p>Rockets and feathers: do pump prices react faster to oil price increases than to decreases?</p>
      <div class="tags"><span>Power Query</span><span>Power BI</span><span>DAX</span><span>SQL</span></div>
      <div class="project-links">
        <a href="https://LINK-TO-REPORT"><i class="fa-solid fa-chart-column"></i> Report</a>
        <a href="https://github.com/josepaulonunes/eu-fuel-price-monitor"><i class="fa-brands fa-github"></i> Code</a>
      </div>
    </div>
  </div>

</div>
-->

<h2 id="academic">Academic Work</h2>

<p class="section-note">Papers and essays from my bachelor's degree at Nova SBE.</p>

<ul class="papers">

<li>
<a href="/PISA_ICT_Math.pdf"><strong>The Impact of ICT Regulations on the Achievement Gap in Mathematics: A Cross-Sectional Analysis</strong></a>
<div class="paper-meta">Econometrics course paper · Co-authored · WLS, Python · Grade 19/20 · <span class="clickable-paper">Summary</span></div>
<div class="abstract">
<p>Does stricter school-level regulation of phones and digital devices narrow the maths gap between disadvantaged students and their better-off peers? Using PISA 2022 data on about 82,000 students in ten economies, we estimate weighted least squares models that add socioeconomic, behavioural, school and country fixed-effect controls step by step. Once country fixed effects are included, moving from the least to the most regulated schools is associated with about 25 more points in maths (more than a year of schooling), and about 35 points for disadvantaged students. These are associations from cross-sectional data, not causal effects.</p>
<p><strong>My contribution:</strong> the results section and the Python code, including all graphs.</p>
</div>
</li>

<li>
<a href="/EU_Innovation_Gaps.pdf"><strong>Socioeconomic and Structural Factors in Innovation Gaps: Eastern vs. Western European Union</strong></a>
<div class="paper-meta">Econometrics course paper · Co-authored · OLS, R · Grade 18/20 · <span class="clickable-paper">Summary</span></div>
<div class="abstract">
<p>Why do Eastern EU member states file far fewer patents than Western ones? Using 2017 data for 27 EU countries (patent applications to the European Patent Office, R&amp;D spending, tertiary education, population and unemployment), we estimate OLS models with an East–West indicator and check robustness with HC3 robust standard errors, VIF and RESET tests. Even after these controls, Eastern countries file roughly 45% fewer patents: the factors we measure do not close the gap, which points to institutional differences our data cannot capture.</p>
<p><strong>My contribution:</strong> the results, the robustness checks and the R code, including all graphs.</p>
</div>
</li>

<li>
<a href="/Tuition_Fee_Reform.pdf"><strong>Tuition Fee Reform: Policy Recommendation</strong></a>
<div class="paper-meta">Public Economics policy essay · Single-authored · Grade 18/20 · <span class="clickable-paper">Summary</span></div>
<div class="abstract">
<p>Should university students pay higher tuition fees? Drawing on evidence from Germany's 2007 tuition fee reforms and on public economics tools (externalities, tax incidence, the Ramsey rule and welfare criteria), I argue that raising fees reduces enrolment, falls hardest on low-income students, and is both inefficient and inequitable.</p>
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
