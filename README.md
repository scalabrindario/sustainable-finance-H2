# Sustainable Finance Homework 1

## Introduction
The objectives of this homework are the following:
- Evaluate the (weighted average) carbon intensity of a business-as-usual (BAU) portfolio
- Build a decarbonized portfolios of stocks based on the mean-variance criterion (e􏰁cient frontier)
- Evaluate the relative performance of BAU and decarbonized portfolios

Our group is in charge of analyzing firms based in Emerging Countries from a financial perspective. In [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1), we were asked to deal mainly with “traditional” financial data while in this homework, we added a variable of interest in our computations, namely the Environmental (E) score, which is part of the fast-growing sustainability-related area of the ESG scores. Specifically, the E score is a rating composed of four main themes, which can be further broken down into 14 variables (See Table below for further information). The aim of this homework is to assess the relationship between environmental scores and financial performance.

<table>
<thead>
  <tr>
    <th>Theme</th>
    <th>Specific Topics</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td rowspan="4">Climate Change</td>
    <td>Carbon Emissions</td>
  </tr>
  <tr>
    <td>Product Carbon Footprint</td>
  </tr>
  <tr>
    <td>Financing Environmental Impact</td>
  </tr>
  <tr>
    <td>Climate Change Vulnerability</td>
  </tr>
  <tr>
    <td rowspan="3">Natural Capital</td>
    <td>Water Stress</td>
  </tr>
  <tr>
    <td>Raw Material Sourcing</td>
  </tr>
  <tr>
    <td>Biodiversity &amp; Land Use</td>
  </tr>
  <tr>
    <td rowspan="3">Pollution &amp; Waste</td>
    <td>Toxic Emissions &amp; Waste</td>
  </tr>
  <tr>
    <td>Electronic Waste</td>
  </tr>
  <tr>
    <td>Packaging Material &amp; Waste</td>
  </tr>
  <tr>
    <td rowspan="4">Environmental Opportunities</td>
    <td>Opportunities in Clean Tech</td>
  </tr>
  <tr>
    <td>Opportunities in Renewable</td>
  </tr>
  <tr>
    <td>Opportunities in Green Building</td>
  </tr>
  <tr>
    <td>Energy</td>
  </tr>
</tbody>
</table>

## Exercise 1
#### Report summary statistics on the cross- sectional distribution of your group's variable of environmental score. Draw the histogram of the cross- sectional distribution of the variable of interest and comment on the summary statistics and the histogram.

In the preliminary phase of question #1, we took into account the dataset which contained information of environmental scores, and next, we aggregated the data per year. Therefore, we computed descriptive statistics shown in the table below.

<p align="center"><img src="https://drive.google.com/uc?id=1kE7rwvDFGSzkUxqze4x3zY_axzSvG2cP" width="800"/></p>

As we can observe in the row “count”, the number of companies increases overtime, which means that since 2007, more and more companies have started disclosing their environmental scores. This trend reflects the rise in public awareness for sustainability-related topics.
On top of that, we can see that there are two specific time spans where the surge take place, the first one in the period 2011-2013, while the second in 2017-2018.
To further analyze this phenomenon, we decided to look at the trend by country.

<p align="center"><img src="https://drive.google.com/uc?id=1vbmAzXB-TNmkSZsGF6DveoviSSUHINY0" width="800"/></p>

As we can see from the previous image, in the period 2011-2013 there is not a single country driving up the number of Environmental score disclosures, but it seems to be more a global trend. We discovered that this great acceleration coincides with the publication of several studies showing that positive corporate sustainability performance is correlated with positive financial results [[1]](#1), even if there is still no general agreement on this topic. We may think therefore that such an increase in awareness contributed to more disclosures.
It’s important to highlight, that the considered time span (2011-2013) just came after the global financial crisis, which heavily damaged the image of financial industry. Thus, banks, and more broadly financial providers, had the need to improve their public image and one viable way was through ESG reporting. Albeit our sample is not only composed by those kinds of companies, we believe that such a pattern could have contributed to the increase in disclosures.


On the other hand, in the period 2017-2018 the rapid surge of environmental reporting was driven mainly by China, which can be identified with the country code “CN” in the Figure above. This phenomenon was caused from the publish in 2016 of “Guidelines for Establishing the Green Financial System”, a new regulation jointly issued by People’s Bank of China (PBOC, China’s central bank) and the China Security Regulatory Commission (CSRC, the country’s top securities regulator) along with other 5 Chinese authorities.
This new regulation paved the way for the establishment of a mandatory environmental information disclosure system for public listed companies, pushing Chinese companies to report their environmental scores [[2]](#2).

For further investigations, we plotted the following three images, which show monthly descriptive information.

<p align="center"><img src="https://drive.google.com/uc?id=1S48MYYQ_xSb9Ker4uW29EtNaEhX_ldMR" width="800"/></p>

As we can see from all the three images, a significant change occurred in the period 2011-2013, which reflects the massive number of companies that started disclosing their environmental scores. This information is also captured in the standard deviation (Image on the right), which rapidly increases in the above-mentioned period and then it decreases in the following months. At the same time, we see that the gap between the highest (i.e. 10) and the lowest E score (i.e., 0) reaches the maximum possible value. From 2012, there are some firms that achieve the highest E score possible, while others are not sustainable at all (E score equals to zero).

Then, we decided to adopt MSCI ESG Rating Methodology [[3]](#3). to classify the environmental scores of our batch of companies.

| Letter Rating | Status    | Company Score  |
|---------------|-----------|----------------|
| AAA           | Leader    | 8.571 – 10.0   |
| AA            | Leader    | 7.143 – 8.570  |
| A             | Average   | 5.714 – 7.142  |
| BBB           | Average   | 4.286 – 5.713  |
| BB            | Average   | 2.857 – 4.285  |
| B             | Laggard   | 1.429 – 2.857  |
| CCC           | Laggard   | 0.0 – 1.428    |

In the period 2007-2021 the annual average Environmental score fluctuates between 4 and 5 points. Therefore, we can state that emerging countries tend to have companies with an “average” environmental score, according to MSCI ESG ratings methodology.

To look more in depth, we created the image below, which shows the environmental ratings of companies by year for the period 2007-2020.
<p align="center"><img src="https://drive.google.com/uc?id=1fePj_xHHlFQo8C1Qx16hBcVAvDpP3KJn" width="800"/></p>

The 2007 scenario shows a significant number of “average” companies, in particular more than 35% of the firms reports a BBB rating. It is important to underline that more than 25% of companies are laggards, while only ~5% of the total enterprises are leaders, with zero AAA companies. These figures perfectly picture the environmental public awareness of that year. A similar situation occurs in the following years: 2008, 2009, 2010 and 2011.
However, in 2012, given the high number of companies that start to disclose their environmental scores, the ratings distribution changes. The laggards expanded their share up to ~30% while leaders start to steadily increase.
In 2018, the entry into force in China of “Guidelines For Establishing The Green Financial System” didn’t affect much the distribution, even if the number of companies surged. This means that Chinese public listed companies were environmentally aligned with the other developing countries, already disclosed, companies.
Overall, we can observe that over the years the distribution slightly shifts towards right, which means that companies are becoming more sustainable under the environmental point of view.

## Exercise 2
#### In Question 5 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1), you calculated effcient portfolios with various target returns. Take these portfolios, calculate and report the weighted-average E score of these portfolios. Comment on the E score of the portfolios. Which firms are driving the E score down? Plot the volatility of E score of the various portfolios


## Exercise 3
#### This question is a follow-up of Question 8 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1). First, take the same 50 selected firms. Then, create a minimum variance portfolio with monthly rebalancing with an additional constraint: you exclude the worst firms in terms of E score. Specifically, exclude the bottom tercile of the distribution in month t − 1 for E scores. Report summary statistics on the performance of this portfolio as well as its E score. How do the performance measures compare with the minimum variance portfolio from Question 4 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1). 


## Exercise 4
#### For each month, sort firrms based on E score into quintiles. Create equally-weighted and value-weighted portfolios for each time period and E score. Report the average returns for each quintile portfolio as well as a portfolio that goes long in the highest quintile and short the lowest quintile. Comment on your results. What can explain the relationship between the return of your portfolios and firms' E score?

## Exercise 5
#### Take the minimum variance portfolio from Question 4 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1) and calculate its E score. Reallocate its composition in order to improve the E score by 20%. Comment on the changes it took in order to improve the E score (e.g. how many and which firrms (firm names) had to be removed in the most recent year of your sample in order to achieve these objectives)

-----------------------------
```
```

[[2]](#2)

<p align="center"><img src="https://drive.google.com/uc?id=1Qq3cbT1rN35bOvlB1aDzM4T-wSUXm50N" width="800"/></p>

## References
<a id="1">[1]</a> Clark, G. L., Feiner, A., & Viehs, M. (2015). From the stockholder to the stakeholder: How sustainability can drive financial performance. Available at SSRN 2508281.<br>
<a id="2">[2]</a> UN PAGE (2016), The People’s Bank Of China Issued The “Guidelines For Establishing The Green Financial System”, https://www.un-page.org/people’s-bank-china-issued-“guidelines-establishing-green-financial- system”<br>
<a id="3">[3]</a> MSCI ESG Research LLC (2022), MSCI ESG Ratings Methodology, https://www.msci.com/documents/1296102/21901542/ESG-Ratings-Methodology-Exec-Summary.pdf<br>
<a id="4">[4]</a> Bolton, P., & Kacperczyk, M. (2021). Do investors care about carbon risk? Journal of Financial Economics, 142(2), 517-549 <br>
<a id="5">[5]</a> BBC (2022), “Big banks fund new oil and gas despite net zero pledges”, https://www.bbc.com/news/business-60366054<br>
<a id="6">[6]</a> Columbia - School of International and Public Affairs (2018), “ESG investing: how to increase ESG investing in developing countries”, https://www.sipa.columbia.edu/academics/capstone-projects/esg-investing-how- increase-esg-investing-developing-countries<br>
<a id="7">[7]</a> Meuer, Johannes, Julian Koelbel, and Volker H. Hoffmann. (2020). "On the nature of corporate sustainability." Organization & Environment 33.3.<br>
<a id="8">[8]</a> Our World in Data (2022), “Emission by sector”, https://ourworldindata.org/emissions-by-sector<br>
<a id="9">[9]</a> Greenspec (2022), “Steel production & environmental impact”, https://www.greenspec.co.uk/building- design/steel-products-and-environmental-impact/<br>
<a id="10">[10]</a> The Guardian (2015), “Hebei's steel cities and China's pollution crisis – in pictures” https://www.theguardian.com/environment/gallery/2015/jan/13/hebeis-steel-cities-chinas-pollution-crisis-in- pictures<br>
<a id="11">[11]</a> ArchCoal, Inc. (2013), “Top 10 Global Coal Producers”, https://www.sec.gov/Archives/edgar/data/1037676/000110465913022192/a13-7797_1ex99d1.htm<br>
<a id="12">[12]</a> Mongobay, (2019), “Coal India Limited, world’s single largest coal producer, faltering on environmental norms: CAG report”, https://india.mongabay.com/2019/12/coal-india-limited-worlds-single-largest-coal-producer- faltering-on-environmental-norms-cag-report/<br>
<a id="13">[13]</a> J.-H. Tan, B. Moshinsky. (2020). Putting sustainability to the test: ESG outperformance amid volatility. Fidelity White Paper<br>
<a id="14">[14]</a> Yoo, S., Keeley, A. R., & Managi, S. (2021). Does sustainability activities performance matter during financial crises? Investigating the case of COVID-19. Energy Policy, 155, 112330<br>
<a id="15">[15]</a> Nikkei Asia. 2022. Current ESG scheme leaves emerging economies' efforts unrewarded. Available at: <https://asia.nikkei.com/Opinion/Current-ESG-scheme-leaves-emerging-economies-efforts-unrewarded><br>
<a id="16">[16]</a> IYNF - International Young Naturefriends. 2022. Sustainable Development and its Challenges in Developing Countries - IYNF - International Young Naturefriends. Available at: <https://www.iynf.org/2018/08/a-guide-to- sustainable-development-and-its-challenges-in-developing-countries/><br>
<a id="17">[17]</a> Bolton, Patrick and Kacperczyk, Marcin T., Global Pricing of Carbon-Transition Risk (January 3, 2022). Available at SSRN: https://ssrn.com/abstract=3550233 or http://dx.doi.org/10.2139/ssrn.3550233 <br>
<a id="18">[18]</a> Whelan, Tensie, et al. "ESG and financial performance." Uncovering the Relationship by Aggregating Evidence from 1 (2021): 2015-2020.<br>
<a id="19">[19]</a> Yoo, S., Keeley, A. R., & Managi, S. (2021). Does sustainability activities performance matter during financial crises? Investigating the case of COVID-19. Energy Policy, 155, 112330<br>
<a id="20">[20]</a> Atz, Ulrich, et al. "The Return on Sustainability Investment (ROSI): Monetizing financial benefits of Sustainability actions in companies." Sustainable Consumption and Production, Volume II. Palgrave Macmillan, Cham, 2021. 303-354.<br>
<a id="21">[21]</a> Whelan, Tensie, et al. "ESG and financial performance." Uncovering the Relationship by Aggregating Evidence from 1 (2021): 2015-2020.<br>
<a id="22">[22]</a> Broadstock, D. C., Chan, K., Cheng, L., & Wang, X. (2021). The role of ESG performance during times of financial crisis: Evidence from COVID-19 in China. Finance research letters, 38, 101716. https://doi.org/10.1016/j.frl.2020.101716<br>
<a id="23">[23]</a> Lioui, A., & Sharma, Z. (2012). Environmental corporate social responsibility and financial performance: Disentangling direct and indirect effects. Ecological Economics, 78, 100-111.<br>
<a id="24">[24]</a> Broadstock, D. C., Matousek, R., Meyer, M., & Tzeremes, N. G. (2020). Does corporate social responsibility impact firms' innovation capacity? The indirect link between environmental & social governance implementation and innovation performance. Journal of Business Research, 119, 99-110.<br>
<a id="25">[25]</a> Timothy M. Doyle (2018), Ratings that Don’t Rate: The Subjective World of ESG Ratings Agencies, American Council for Capital Formation, https://corpgov.law.harvard.edu/2018/08/07/ratings-that-dont-rate-the- subjective-world-of-esg-ratings-agencies/<br>
<a id="26">[26]</a> Tesla Inc. (2022), “Impact Report 2021”, https://www.tesla.com/ns_videos/2021-tesla-impact-report.pdf<br>
<a id="27">[27]</a> CNBC (2021), “Tesla posts record earnings but on one stock market number Elon Musk’s EV company is still disappointing”, https://www.cnbc.com/2021/10/20/is-tesla-an-esg-investment-the-case-for-and-against-elon- musks-evs.html<br>
