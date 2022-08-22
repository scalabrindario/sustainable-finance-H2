# Sustainable Finance Homework 2

## Introduction
The objectives of this homework are the following:
- Evaluate the (weighted average) carbon intensity of a business-as-usual (BAU) portfolio
- Build a decarbonized portfolios of stocks based on the mean-variance criterion (effcient frontier)
- Evaluate the relative performance of BAU and decarbonized portfolios

Our group is in charge of analyzing firms based in Emerging Countries from a financial perspective. In [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1), we were asked to deal mainly with “traditional” financial data while in this homework, we added a variable of interest in our computations, namely the Environmental (E) score, which is part of the fast-growing sustainability-related area of the ESG scores. Specifically, the E score is a rating composed of four main themes, which can be further broken down into 14 variables (See Table below for further information). The aim of this homework is to assess the relationship between environmental scores and financial performance.

<table align= "center">
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
#### In Question 5 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1), you calculated efficient portfolios with various target returns. Take these portfolios, calculate and report the weighted-average E score of these portfolios. Comment on the E score of the portfolios. Which firms are driving the E score down? Plot the volatility of E score of the various portfolios

In this question, we took the three optimal portfolios we calculated in Question #5 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1) from our random sample of 50 firms with the target return of 2%, 4%, and 5.8%. Next, we calculated the relative weighted-average environmental score taking the average score of each firm until now and plotted in the figure below.

<p align="center"><img src="https://drive.google.com/uc?id=1I2YCwb9S5lV1BDwwqsrhzjJxdowULlWR" width="800"/></p>


From the figure above we can notice a slightly positive correlation between these two variables. This result is quite fascinating since it goes against Bolton & Kacperczyk (2021) finding [[4]](#4).
The two authors found “that stocks of firms with higher total CO2 emissions (and changes in emissions) earn higher returns”. In our case, it’s the opposite: companies with higher environmental scores are correlated with higher returns. Though it’s important to say that CO2 emissions are not the equivalent of the E score, but these latter are taken into account to compute the E score.

To assess what are the companies that drive the environmental score down, we decided to sort the assets in the portfolios by the worst environmental score, and display the bottom 50% (e.g., in the first portfolio we have only 10 out of 20 companies).

Surprisingly, as we can see in the table below, for the first portfolio, we have two financial firms driving the drop in the environmental score. The first one is The Saudi British Bank (SABB), while the second one is Huaxi Securities. This finding is unusual since these two firms are active in the service sector and therefore, we didn’t expect them to drive down the E score. To further develeop our analysis we can evaluate the 3 scopes of these two companies.

<p align="center"><img src="https://drive.google.com/uc?id=1yo-jCdQsjzhWcBuCaVxMKA-chMNQux1w" width="800"/></p>

However, we can imagine that their activities don’t require big amounts of electricity (Scope 2) and don’t pollute nor emit CO2 (Scope 1). As a consequence, we may think that this bad result in terms of environmental score is generated by their lending exposure (Scope 3). SABB, indeed, is very close to the Kingdom of Saudi Arabia and its oil companies. In addition, we know that HSBC, SABB’s parent company, has taken part in a scandal in which it was discovered that big banks, despite net-zero pledges, have been still funding new oil and gas activities [[5]](#5).

Even though this argument is fascinating, by checking the file “scope3intensity”, we found that SABB and Huaxi have very low emissions, meaning that it’s not scope 3 to drive their low E score. In conclusion we could claim that probably this values are the result of lack of information about the environmental practices of these companies. According to recent research, there is not a shared and unique ESG definition.

On top of that, the ESG trend is mainly present in North America and Europe, while emerging countries are lagging behind. In these countries, ESG criteria/definition/ratings are “obscure” and “unstandardized”, and several companies come up with their own versions of ESG definition, which undermine the credibility of their disclosures [[6]](#6). Indeed, Meuer et al. (2019) found 33 different definitions of corporate sustainability in usage [[7]](#7).

Besides these two companies, there are also firms belonging to industries that we expected to drive down the environmental score of portfolios. We have two companies active in iron and steel production, and one in the coal industry. Hebei Iron and Steel Co Ltd is a Chinese iron and steel manufacturing conglomerate, as well as the second-largest steel producer worldwide. Then there is Feng Hsin Steel Co Ltd, which is operating in the same industry. As we know, iron and steel production are extremely energy consuming, accounting for 7.2% of the energy-related CO2 emissions [[8]](#8).

In addition, there are other several impacts on the environment, including air emissions, wastewater contaminants, hazardous wastes, and solid wastes [[9]](#9). This terrible environmental impact has consequences on people’s life. For instance, China’s Hebei province, where the Chinese conglomerate is based, has some of the highest air pollution concertation in the country [[10]](#10). As forementioned, we have also a Coal player, namely Coal India Ltd, which is the world largest coal producer [[11]](#11) with a massive environmental and social impact, that includes air, noise, water pollution, land degradation and far-reaching consequences on local biodiversity [[12]](#12).

In the second (first table below) and third portfolios (second table below) the number of companies significantly decreases, from twenty of the first portfolio, to eight (i.e., four companies removed as shown in the first table below) and two respectively (i.e., two companies removed as shown in Table 6). Likewise, in both the average Environmental score is relatively high compared to the first one. Once again, the lowest Environmental score in the second portfolio is unexpectedly represented by a financial actor. The same reasoning before mentioned could be applied to this case.

Another interesting fact to point out is the weight in the portfolio of the top 50% polluting companies. As we can see from the table above, this number is ~40%, which means that we are outweighing the investments in the top 50% cleanest companies. This pattern increases in first table below and second table below since we want to push the return of the portfolio higher, and so we are investing more in certain companies. Given the fact that we are reducing our diversification and investing in less firms, the volatility increases (as shown in image below with the three pink points) because of the unsystematic risk. For instance, in the third portfolio (where we push the return up to 5.8%), we are “obliged” to invest basically in only one firm (to be precise we invest ~98% on it). This can also be observed in second image below where the batch of the top 50% polluting companies is represented only by one company (which is equal to the ~2% of the portfolio).

<p align="center"><img src="https://drive.google.com/uc?id=1kn28EVwWHRE9QevU8i6EZs5vneHhBRj2" width="700"/></p>

<p align="center"><img src="https://drive.google.com/uc?id=1qAcXB7DB0uOL4gATxRO1_9hNkH-Lv1Se" width="600"/></p>

Finally, we plotted all the 50 assets and the portfolios in the volatility-Environmental score space image below, where we can see a slight positive correlation between volatility and environmental score. This result is not what typically argues the literature. In fact, the usual hypothesis is that companies leading the ESG, and sustainability scores have a more prudent management apparatus even in their operations, and this risk aversion is reflected also in the volatility in the stock markets [[13]](#13).

<p align="center"><img src="https://drive.google.com/uc?id=1lAHuXUC6La9cwUhI00vLQ0UKADRQAxKZ" width="500"/></p>

Once again, the growing demand from informed consumers seeking sustainable, ethical, and socially responsible products and services has aided sustainable finance development even during a crisis. For instance, Yoo et al. (2021) [[14]](#14) examined the effect of ESG performance on stock returns and volatility during the COVID-19 pandemic. They came out with the following findings:
- Higher ESG indicates higher return and lower volatility
- Firms pursuing higher reputation show lower returns and higher volatility
- Firms in lower return groups benefit more than other firms

We expected to obtain similar results to those of Yoo et al. (2021) but instead, we have the opposite correlation between volatility and E score. A possible explanation could be linked to the nature of our sample: emerging markets. In these countries, it is more complicated to follow sustainable trends for various reasons, so it may be more cost-effective not to adhere to high sustainability standards [[15]](#15). Possible explanations for the difficulty of adopting a policy of environmental sustainability include:
- Sustainable development is often not possible in war-torn countries as there are other priorities on hand
- Natural occurrences, such as earthquakes and tsunamis, can pose a threat to sustainability as they can destroy certain elements of infrastructure
- The governmental trade-off between immediate profit and investment toward sustainable technologies
- Corruption
- Lack of funding (endogenous negative effect) and reliable data
This set of reasons is responsible to create instability in sustainable investments [[16]](#16).

## Exercise 3
#### This question is a follow-up of Question 8 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1). First, take the same 50 selected firms. Then, create a minimum variance portfolio with monthly rebalancing with an additional constraint: you exclude the worst firms in terms of E score. Specifically, exclude the bottom tercile of the distribution in month t − 1 for E scores. Report summary statistics on the performance of this portfolio as well as its E score. How do the performance measures compare with the minimum variance portfolio from Question 4 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1). 

##### Summary Statistics

| Letter Rating         | Q4 – HW1  | Q3 – HW2  |
|-----------------------|-----------|-----------|
| Annualized Return     | 10.46%    | 12.17%    |
| Annualized Volatility |  0.14     | 0.15      |
| Minimum Return        |  -15.30%  | -15.18%   |
| Maximum Return        |  11.98%   |  14.48%   |
|  Sharpe Ratio         |   -0.03   |    0.05   |
|  Environmental Score  |    N/A    |    4.73   |

From the table above we can see that by excluding the sample’s bottom tercile in terms of E score (i.e., the most polluting firms), the annualized return increases by ~2 percent points and the annualized volatility by 0.01. As we can observe from Figure below, the additional environmental constraint that we included in our portfolio composition started to have an impact in 2014, when, as forementioned, the number of companies disclosing environmental scores surged. Before that year, the number of companies publishing environmental scores in our randomly selected batch was not relevant.

<p align="center"><img src="https://drive.google.com/uc?id=1RtVpPrgfcKeltkUdAseDDRt1D6hwqeRv" width="800"/></p>

At the same time, it is important to highlight that the gap started to be non-negligible in 2018, and in 2020. The gap for two mains reasons:
- The presence of more sustainable companies
- The overall trend that drove up the average environmental score

On the other hand, from the figure below we can observe that the volatility decreased in 2016. We have already pointed out this event in question #4 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1), and the reason behind it is linked to the surge in the number of companies available that year.
This happened since we considered only available companies because for several months we didn't have information for some enterprises (i.e., Nan values for returns or E score). This event has a significant magnitude in 2018, which would probably correspond to the jump in Chinese firms disclosing ESG scores. Furthermore, is interesting to see how the volatility increases afterward, and this coincides with a sharp increase in returns (see image above).

<p align="center"><img src="https://drive.google.com/uc?id=19geWsEzzPj77qSR-Harg4WcF0-hpm0T5" width="800"/></p>

As we can see from the image below, the Sharpe ratio goes from being negative to positive. It means that the return’s investment is greater than the risk-free rate. However, as we discussed in class, a Sharpe ratio could be considered “acceptable” starting from 0.2/0.3, which unfortunately is not the case for the whole period.

<p align="center"><img src="https://drive.google.com/uc?id=1oiVcempRmCfpsscorWrTO_8hIIh40-2G" width="800"/></p>

In our case, the Sharpe ratio stabilizes at 0.1 after some rapid falls happened in 2016 and in mid-2018. These bounces are the results of some sharp changes in volatility. Next, in 2020 it assumes a positive trend, and as we can observe in all the other iamges of this exercise the same upward is mirrored in return, volatility, and environmental score respectively.

When the analysis results in a negative Sharpe ratio, it either means the risk-free rate is greater than the portfolio’s return, or the portfolio's return is expected to be negative. In either case, a negative Sharpe ratio does not convey any useful meaning.

In addition, we were able to compute the environmental score of the portfolio, which is 4.73. Therefore, the portfolio would receive a BBB rating, or in other terms, it would be considered an “average” according to the MSCI ESG ratings.

In the figure below, we plotted the monthly environmental rating. Unfortunately, in 2012, the small batch of enterprises considered didn’t report with continuity. This fact reflects our analysis previously mentioned in exercise #1.

Besides that, after 2012 the environmental score starts a steep and positive change, starting from 3 and arriving at around 7. This trend happens because not only are more and more companies committed to sustainability behaviors, but also since each month we put additional environmental constraints that enhance the E score of our portfolio.

<p align="center"><img src="https://drive.google.com/uc?id=1cigtcb_rz9qXHPrWfI8WO5duB4a_yZDZ" width="800"/></p>

## Exercise 4
#### For each month, sort firrms based on E score into quintiles. Create equally-weighted and value-weighted portfolios for each time period and E score. Report the average returns for each quintile portfolio as well as a portfolio that goes long in the highest quintile and short the lowest quintile. Comment on your results. What can explain the relationship between the return of your portfolios and firms' E score?

To fulfill the task, for each month, we started by taking only those assets where the needed information was available, specifically return, size, and E score. This allows to avoid “Nan” values and wrong calculations (“Nan” values would always appear in the lowest quantile). Then we calculated the cumulative return for each quantile.

From the figure below we can see that the equally weighted portfolios outperform the market- weighted ones in all quintiles. This is because, when an investor decides to adopt an equally weighted approach means that he/she is more exposed to small-sized companies, which in our case tend to have higher returns compared to big-sized companies. An equally weighted portfolio is also more secure in terms of concentration risk as, compared to the market value- weighted portfolio, it leads to a higher degree of diversification, which is preferable in order to avoid high dependency on just a few large corporations.

<p align="center"><img src="https://drive.google.com/uc?id=1a-_-zxRbXR_DQqyJ6TQAXlCtWgrmTXlF" width="800"/></p>

Regarding the effect of the environmental score, we cannot retrieve a relevant pattern between the return and the E score. This fact is evident from the figure above, where high quintiles (higher environmental score) do not systematically correspond to higher or lower returns. The same is true for the opposite scenario, low quintiles (lower environmental score) do not systematically coincide with a higher or lower return. Indeed, we see instead that the best performers are the second and the fourth quintile. This could suggest that extreme strategies, namely focusing only on being sustainable or not being it at all, are not good strategies. Perhaps, a trade-off between the two approaches could lead to better results. Alternatively, we can think that enterprises that went all-in on sustainability heavily invested, and won’t see the results in the short term. However, those are just rough assumptions since we haven’t found any empirical study on that.

After dividing all the companies into five quintiles (both for equally weighted and for market- value weighted), we pursued a strategy that goes long in the highest quintile (higher environmental score) and shorts the lowest quintile (lower environmental score). This means that we are betting on the future outlook of the market since we are keeping in our portfolio the greenest firms, while each month we are selling (more precisely shorting), the most polluting enterprises.

Beforehand performing any calculations, we could already notice from the figure above that it is not a profitable strategy since the lowest quantiles in terms of E score have higher returns compared to the top ones. This can be simply observed by the height of the bars or just looking at the figure below.

In particular, in the table below shows how the Market Value Weighted Portfolio has a negative return of 1.9%, slightly outperforming the Equally Weighted one, which has a loss of -0.2%.

| Portfolio                        | Annualized Return  |
|----------------------------------|--------------------|
| Equally Weighted Portfolio       |      -0.044%       | 
| Market Value Weighted Portfolio  |       -0.2%        |

The main reason behind this difference between the two portfolios is the gap that the market value-weighted portfolio has between the fifth quintile (return of the greenest companies) and the first quintile (return of the most polluting firms). While this gap is extremely narrow in the case of the equally weighted portfolio.
Even if going with an opposite strategy (short with the less polluting, and long with the most polluting) would have given a positive return, we would have never suggested taking such an approach because of the risk taken, the negative impact on society this would bring, and the growing trend toward sustainable issues that could invert the returns compared to the past.

<p align="center"><img src="https://drive.google.com/uc?id=1GbvMDcaWlpACMcC3tzpAKFX8YPS5owgI" width="800"/></p>

To answer the question about the possible causal effect between the average environmental score and the average return of a firm, we computed the correlation between those two variables to see whether or not such a relationship exists.
Contrary to what we were expecting at the beginning of this homework, there is no significant correlation in our ~1’500 firm-specific sample. This fact is straightforward in the figure below. To be more precise this correlation is 0.02, which is positive but of irrelevant magnitude. Therfore the so-called carbon premium, namely “the return that compensates investors for taking on the transition risk” [[17]](#17), seems not to appear.

<p align="center"><img src="https://drive.google.com/uc?id=1uSNwZKuM1sFuh8i01bzDh0h6xPB4ACSi" width="800"/></p>

However, our result comes from a very small set of enterprises which is not representative of the whole market trend.

Nonetheless, several studies suggest that actually some relationships exist. Reviewing the literature, we retrieved the following information:
1. **Improved financial performances due to ESG become more noticeable over longer time horizons**: it has been shown that everything else being constant, a study with an implied long-term focus is 76% more likely to find a positive or neutral result [[18]](#18). However, in our specific sample is probably still too early to see this difference.
2. **ESG investing provides downside protection, especially during a social or economic crisis**: this is a recently highlighted topic that came out because of the huge amount of new data available during an important crisis such as COVID-19 [[19]](#19).
3. **Studies indicate that managing for a low carbon future improves financial performance**: recent research shows that mitigating climate change through decarbonization strategies leads to better financial performances for both corporates and investors [[20]](#20).
4. **ESG disclosure on its own does not drive financial performance**: just 26% of studies that focused on disclosure alone found a positive correlation with financial performance compared to 53% for performance-based ESG measures [[20]](#20).

The possible explanation for such relationships could be due to several confounder factors. Indeed, benefits emerge when companies embed sustainability into their core business. The mediating factors can be identified, quantified, and monetized to assess the financial benefits of sustainability actions. When a company embeds sustainability in its strategy and practice, it improves innovation, risk management, stakeholder engagement, media coverage, customer loyalty, employee relations, operational efficiency, and so on. These, drive greater profitability, lower cost of capital, and higher valuation, which are translated into short and long-term value creation for shareholders and society [[20]](#20). The image below represents the pattern that causes the correlation.

<p align="center"><img src="https://drive.google.com/uc?id=1pBc0-eprG50Rzsv85vIGSAOAT6nxYNw5" width="800"/></p>

## Exercise 5
#### Take the minimum variance portfolio from Question 4 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1) and calculate its E score. Reallocate its composition in order to improve the E score by 20%. Comment on the changes it took in order to improve the E score (e.g. how many and which firrms (firm names) had to be removed in the most recent year of your sample in order to achieve these objectives)

We adopted two different strategies to compute those portfolios, the first is the “naive” one, while the second respects the mathematical problem of minimization of the volatility while increasing the ESG score.

**Naive Method**

The naive approach does not iterate for each month, but rather shows a simplistic approach that could be used while creating a new portfolio at a specific time. We started by creating the minimum volatility portfolio in the last period of our dataset. Next, we computed the average environmental score of the portfolio, and we sorted the assets in the portfolio by the worst E score. This allows dropping those assets that are pushing the average environmental score down until reaching the target of an additional 20%. In this case, we see that after 4 iterations we completely dropped the assets shown in the image below.
<p align="center"><img src="https://drive.google.com/uc?id=17crLp80Zyyliz-nTJ7tbJCKXn_aAyJyC" width="800"/></p>

In this way, we improved the average environmental score, but we cannot assess whether it still respects the minimum volatility objective.


**Optimizer Method**

To correctly address the issue, we used an optimizer to recreate all the monthly re-balanced portfolios with minimum volatility that we had in Q4 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1). At the same time, we added the constraint of having an environmental score of 1.2 times bigger than the same month of the portfolio compute in Q4 of [Homework 1](https://github.com/scalabrindario/sustainable-finance-H1).

<p align="center"><img src="https://drive.google.com/uc?id=1eJx7T9GLLpP8dilaxaGUCytnfYbCeVe4" width="800"/></p>

We can see from the figure above above that it performs well, however, not every month was possible to reach the additional environmental target. This is because, in the simple minimum variability portfolio, the weights were mainly allocated toward assets with the highest environmental score in our sample. To improve this portfolio, we should move away from the minimum volatility point (hence increasing the risk).

We can see from the figure below that is anyway impossible possible to reach the same volatility with this additional constraint. When we augment the environmental score, we are subject to an increase in risk. When the number of assets available is small, this difference is way more remarkable. This phenomenon is evident in the figure below, in the period before 2012.

<p align="center"><img src="https://drive.google.com/uc?id=12_Flkb9dnRbgw-dDUqV_TYPSyn6_vFmZ" width="800"/></p>

If we take a closer look at the second part of this graph (from 2012 onwards), we see that the difference is very small. Again, this is normal, because the information availability of several assets increased. The more assets we have, the more optimal combinations can be found. Therefore, as shown in the figure below, the volatility of both portfolios is the same.

<p align="center"><img src="https://drive.google.com/uc?id=1W40-Ojj1mv4HpIjUMLZ3B7rVyU5DebQ3" width="800"/></p>

Last but not least, it is important to see what is the comparison of the two strategies in terms of returns, which is shown in the iamge below. As we can see, the portfolio with an increase of 20% of the environmental score, has a higher return. This can be explained by the fact that the higher volatility between the last period of 2009 and the whole 2010, created a gap between the two portfolios. This is a good signal, we indeed showed that is possible to improve the impact of the investments while getting better performance. Our result debunks the common opinion that green investments should be pursued only for sustainable purposes, overlooking the financial side. In this case is possible to “do well by doing good”.

<p align="center"><img src="https://drive.google.com/uc?id=1k8BPNbf56tr779cQVdyPyCtNkAogCrlt" width="800"/></p>

Looking in more detail at the image below, which focuses only on the period September 2007 – July 2010, we can also notice that the new portfolio was more resilient during the 2008 crisis even if the risk was supposed to be higher. This evidence goes in the same direction as what Broadstock et Al. (2021) found [[22]](#22). The authors showed how ESG performance is positively correlated with the short-term cumulative returns of stocks during a crisis, in particular during the COVID-19 pandemic. They claimed high-performing ESG companies are more resilient during tough periods since investors may interpret ESG performance as a signal of future stock performance and/or risk mitigation in times of crisis.

<p align="center"><img src="https://drive.google.com/uc?id=1d5YDByCkc8fusqdRCAvyvDwr0bMejNtv" width="800"/></p>

Specifically, they found that higher environmental scores positively affect returns. This event can be explained by the fact that to achieve a high E score an enterprise must have performed well in all the areas linked with the environment. In this direction, literature provides evidence that firms' engagement in ESG activities catalyzes firms' mechanisms for innovation capacity creation, which in turn reflects on their performance levels [[23]](#23), [[24]](#24). All the efforts (both financially and not financially) made to mitigate exposure to long-term environmental risks (which are captured by the E score) prepare companies to navigate away from negative business impacts such as those emerging during the 2008 financial crisis or COVID-19 pandemic.

Looking more in depth at where the changes in the last portfolio occurred, we can see from image below that, with this approach, we dropped only 3 firms and added 4 new ones. 

<p align="center"><img src="https://drive.google.com/uc?id=1bJ-pUocjP2t4THbQ3psRqdyFVQRumuH5" width="800"/></p>

However, the weight of those is quite trivial. This approach relies more on changing the allocation between (see image below) all the assets rather than just avoiding those with a lower E score, which is only a consequence.

<p align="center"><img src="https://drive.google.com/uc?id=1ci-8l3gh8mdgMtqUfnGZUREmDB2jDhYO" width="800"/></p>

As shown in the table above, the weights of 3 companies passed from positive to zero, meaning that we removed them from the portfolio because of their poor environmental performances. These companies are “Zhejiang Dahua Technology Co Ltd”, “Jiangsu Yangnong Chemical Co Ltd”, and “Hyundai Motor”. At the same time, we added four other companies: “Jiangsu Zhongang Construction Group Co Ltd”, “Absa Group Ltd”, “OCI Co Ltd”, and “Kepco Plant S&”.
We could assume that the incoming companies should belong to “greener” industries compared to the outgoing ones. This could be true for some of them. For instance, “Kepco Plant S&” is a company specializing in reliable high-quality maintenance of hydroelectric, thermal, and nuclear power plants while “Absa Group Ltd” is a bank, and therefore it makes sense that it has better environmental scores than “Hyundai Motor”, which it is a car producer. However, one of the removed companies is operating in the Technology industry (specifically it sells video surveillance products and services), therefore this industry-related reasoning it’s not always straightforward. We should keep in mind indeed that E scores are industry adjusted. Moreover, some companies have such tiny weights that they only slightly have an impact.

As a consequence, it might be meaningful to mention that ESG rating agencies are extremely subjective in their ratings and thus it might be misleading to find always a logical motivation behind those ratings. As Timothy Doyle argues, “ratings don’t rate”, since there are several aspects in their analysis that are out of their control, and the fact that different agencies rates differently are an indicator of that [[25]](#25):

- There are several limitations and a lack of standardization for Environmental and Social disclosures. The auditing process behind those disclosures is often opaque, without any possibility to verify reported data. Agencies rely on assumptions and the subjective nature of ratings.
- Agencies are biased towards higher market capitalization companies compared to lower market-cap ones. The former category tends to receive higher scores compared to the latter one.
- There is also a geographic bias that influences agencies to better evaluate EU-based companies. This could be particularly insightful in our case since we are focusing on emerging markets. Moreover, this bias is worth even for two companies active in the same industry “doing the same general thing” but with different scores depending on their headquarters location.
- Another relevant bias is the industry-related one. “Significant differences in business models and risk exposure, companies in the same industry are unfairly evaluated under the same model”. More in general, rating agencies fail to identify risks.

Timothy Doyle is not the only one that complains about ESG ratings, also Elon Musk in some recent tweets showed a strong opposition against ESG scores.
On top of that, Tesla published its 2021 Impact report [[26]](#26), which claimed that “Current environmental, social and governance (ESG) reporting does not measure the scope of positive impact on the world.” The report was in response to the low ESG scores that Tesla obtained compared to its competitors. The report also explains how other automakers can gain higher ESG ratings even if they are only slightly decreasing their greenhouse gas emissions while continuing to produce fossil fuel cars.

It's also important to mention that Tesla never provided transparency in terms of disclosing its Scope 1 and Scope 2 carbon emissions, water use, or waste management. However, this is changing, since more and more shareholders are pressing the company on ESG [[27]](#27).

What is interesting is the vision that Tesla shares on ESG:
>“We need to create a system that measures and scrutinizes actual positive impact on our planet, so unsuspecting individual investors can choose to support companies that can make and prioritize positive change”

## Collaborators
- [Dario Scalabrin](https://www.linkedin.com/in/scalabrindario/)
- [Filippo Trapanese](https://www.linkedin.com/in/https://www.linkedin.com/in/filippo-trapanese-2729b3206/)
- [Massimo Poretti](https://www.linkedin.com/in/poretti-massimo/)
- [Soukaynah El Maliki](https://www.linkedin.com/in/soukaynah-el-maliki-63b7b71aa/)


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

## License 
[MIT](https://choosealicense.com/licenses/mit/)
