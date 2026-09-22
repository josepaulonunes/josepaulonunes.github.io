---
layout: default
title: José Nunes
---

<div class="profile-header">

  <img class="profile-picture" src="/profile.png" alt="José Nunes">

  <div class="profile-text">

    <h1>José Nunes</h1>

    <div class="subtitle">
      <p>BSc in Economics, Nova School of Business and Economics</p>
      <p>Lisbon, Portugal</p>
    </div>

  </div>

</div>

<p class="blurb">
I'm an economist intern at ERSE, Portugal's energy sector regulator, working on regulatory impact assessments and economic analysis across electricity, natural gas, fuels, and electric mobility. My interests are in industrial organization, macroeconomics, and finance. You can contact me at <a href="mailto:josepnunes3@gmail.com">josepnunes3@gmail.com</a>.
</p>

<h2>Academic Projects</h2>

<ul class="papers">

<li>
<a href="/PISA_ICT_Math.pdf"><strong>The Impact of ICT Regulations on the Achievement Gap in Mathematics: A Cross-Sectional Analysis</strong></a>
<span class="clickable-paper"> [Summary] </span>
<div class="abstract">
This study examines whether stricter school-level ICT regulation can reduce socioeconomic disparities in Mathematics performance. Using OECD PISA 2022 data from 81,850 students across ten developed economies, we estimate a series of Weighted Least Squares models incorporating socioeconomic, behavioural, demographic, institutional, and country-level controls. The results indicate that stronger ICT regulation is positively associated with Mathematics scores and has an additional positive association for students from disadvantaged socioeconomic backgrounds, suggesting that school-level digital policies may contribute to reducing achievement gaps.
<p><strong>My contribution:</strong> responsible for the results and R code (including all graphs). <strong>Grade:</strong> 19/20</p>
</div>
</li>

<li>
<a href="/EU_Innovation_Gaps.pdf"><strong>Socioeconomic and Structural Factors in Innovation Gaps: Eastern vs. Western European Union</strong></a>
<span class="clickable-paper"> [Summary] </span>
<div class="abstract">
This study investigates the extent to which socioeconomic and structural factors explain differences in innovation performance between Eastern and Western EU member states. Using patent applications to the European Patent Office (EPO) in 2017 as a proxy for innovation output, alongside Eurostat data on population, R&D expenditure, education levels, and unemployment, the analysis applies a series of OLS regression models incorporating an East-West regional indicator. The results show that while these socioeconomic and structural factors help explain patenting activity, a substantial and statistically significant gap between Eastern and Western EU countries persists even after controlling for them, suggesting that structural or institutional differences not captured by these variables continue to drive the divide in innovation output.
<p><strong>My contribution:</strong> responsible for the results, robustness checks, and R code (including all graphs). <strong>Grade:</strong> 18/20</p>
</div>
</li>

<li>
<a href="/Tuition_Fee_Reform.pdf"><strong>Tuition Fee Reform: Policy Recommendation</strong></a>
<span class="clickable-paper"> [Summary] </span>
<div class="abstract">
This paper examines the efficiency and equity impacts of higher education tuition fees, drawing on evidence from Germany's 2007 university fee reforms. Using key public economics concepts like positive externalities, Pigouvian subsidies, optimal taxation, and welfare theory, it shows that shifting costs onto students triggers severe market failures. The evidence reveals that even small fees drop overall enrollment, alter student mobility, and place an unfair burden on low income families.
<p>Ultimately, keeping tuition low or free is essential to safeguard equal opportunity, avoid underinvestment in education, and drive long term economic growth. <strong>Grade:</strong> 18/20</p>
</div>
</li>

</ul>

<script>
document.addEventListener("DOMContentLoaded", function () {
  document.querySelectorAll(".clickable-paper").forEach(function (el) {
    el.style.cursor = "pointer";
    el.addEventListener("click", function () {
      const next = el.nextElementSibling;
      if (next && next.classList.contains("abstract")) {
        next.style.display = (next.style.display === "block") ? "none" : "block";
        el.classList.toggle("open");
      }
    });
  });
});
</script>
