---
keywords: Targeting
description: Learn how Adobe [!DNL Target] shows and calculates the conversion rate, lift, confidence, and confidence interval for each experience.
title: How Do I View the Conversion Rate, Lift, and Confidence Level?
feature: Reports
exl-id: b4cfe926-eb36-4ce1-b56c-7378150b0b09
---
# Conversion rate

The conversion rate, lift, confidence and confidence interval are reported for each experience.

The following illustration shows the chart header for a sample activity with the [!UICONTROL Conversion Rate], [!UICONTROL Lift], and [!UICONTROL Confidence] headers highlighted.

![conversion-rate image](assets/conversion-rate.jpg)

>[!NOTE]
>
>In all data, duplicate orders are ignored if an `orderID` is passed. The audit report lists the ignored duplicate orders.

## Conversion Rate {#section_07A36846C4E84D0881906809B9CE5A74}

Shows the median conversion rate, confidence, interval, and the number of conversions.

For example, examine the following Conversion Rate report column:

![conversion-rate-detail image](assets/conversion-rate-detail.jpg)

The first line is the control experience. It shows a 15% conversion rate, with three conversions. The second line, Experience B, shows a 15% conversion rate, with a confidence interval of plus or minus 15.65% and three conversions.

>[!NOTE]
>
>Currently, the confidence interval is calculated only for binary metrics.

## Lift {#section_0F409572C720433D9378092ABC999982}

Compares the conversion rate for each experience against the control experience.

Lift = (Experience CR - Control CR) / Control CR

If control is 0, there is no percentage lift.


## Retail Data {#section_30A674731BA6440E9BB93C421BE990EE}

AOV, RPV, and Sales data are displayed for each experience if you inserted a Place Order (`orderConfirmPage`) mbox and selected it as the conversion mbox. 

## Confidence Level and Confidence Interval {#concept_0D0002A1EBDF420E9C50E2A46F36629B}

For each experience, the confidence and confidence interval are displayed.

You can perform offline calculations for Analytics for Target (A4T), but it requires a step with data exports in [!DNL Analytics]. For more information, see "Performing Offline Calculations for Analytics for Target (A4T)" below.

### Confidence {#section_26FE5E44BDD5478792A65FCFD83DCCDC}

The confidence of an experience or offer that is displayed is a probability (expressed as a percentage) of obtaining a result less extreme than the one that is actually observed, if the null hypothesis is true, (in essence, if there is no difference in conversion rates between that experience or offer, and the control experience/offer). In terms of p-values, this confidence displayed is 1 - p-value. Put more simply, higher confidence indicates that the data is less consistent with the assumption that the the control and non-control offer/experience have equal conversion rates. 

The confidence rounds up to 100.00% when the confidence is greater than or equal to 99.995%. 

![conf_report image](assets/conf_report.png)  ![conf_report_detail image](assets/conf_report_detail.png)

Before making any business decisions, try to wait until your sample size is large enough and that the four bars of confidence on one or more experiences stays consistent for a continuous length of time to ensure the results are stable.


### Confidence Interval {#section_F582738DFE1648C78B93D81EBC6CACF7}

>[!NOTE]
>
>Currently, the confidence interval is calculated only for binary metrics.

The *confidence interval* is a range of estimates within which the true value of the metric can be found at a given confidence level. Target always displays 95% confidence intervals. The confidence interval appears as a light gray +/- percentage in the Conversion Rate column. In the example below, the confidence interval for Experience B's lift is plus or minus 15.65%.

![conversion_rate image](assets/conversion_rate.png)

**Example:** An experience's observed RPV is $10, and its 95% **confidence interval** is $5 to $15. Unknown to us, its true RPV is $12. Then, if we ran this test multiple times, 95% of the time the confidence interval we calculate will contain the _true_ value of the RPV of $12. 

**What impacts the confidence interval?** The formula follows standard statistical methods for calculating confidence intervals.

* **Sample size:** As sample grows the interval will shrink or narrow. This is preferred as it means your reports are getting closer to the true value of the success metric. 
* **Standard deviation smaller:** More similar results, such as similar AOVs or similar numbers or visitors converting each day, reduces the standard deviation.

## Confidence Calculation and How to Perform It Offline {#section_86F7C231943043A5B8B6BFE67B706E3B}

The [downloaded CSV report](/help/main/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) includes only raw data and does not include calculated metrics, such as revenue per visitor, lift, or confidence used for A/B tests.

To calculate these calculated metrics, download the Target's [Complete Confidence Calculator](/help/main/assets/complete_confidence_calculator.xlsx) Excel file to input the activity's value, or review [Statistical calculations in A/Bn tests](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

>[!NOTE]
>
>This calculator is for Target-based reporting and not for A4T reporting.

## Performing Offline Calculations for Analytics for Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

You can perform offline calculations for A4T, but it requires a step with data exports in [!DNL Analytics].

For A4T, we use a [Welch's t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} calculation for continuous variables (rather than binary metrics). In Analytics, a visitor is always tracked, and every action taken is counted. Therefore, if the visitor purchases multiple times or visit a success metric multiple times, those additional hits are counted. This makes the metric a continuous variable. To perform the Welch's t-test calculation, the "sum of squares" is required to calculate the variance, which is used in the denominator of the t-statistic. [Statistical calculations in A/Bn tests](/help/main/c-reports/statistical-methodology/statistical-calculations.md) explains the details of the mathematical formulas used. The sum of squares can be retrieved from [!DNL Analytics]. To get the sum of squares data, you need to perform a visitor-level export for the metric you are optimizing to, for a sample time period.

For example, if you're optimizing to page views per visitor, you'd export a sample of the total number of page views on a per visitor basis for a specified time frame, perhaps a couple of days (a few thousand data points is all you need). You would then square each value and sum the totals (the order of operations is critical here). This "sum of squares" value is then used in the Complete Confidence Calculator. Use the "revenue" section of that spreadsheet for these values.

**To use the [!DNL Analytics] data export feature to do this:**

1. Log in to [!DNL Adobe Analytics]. 
1. Click **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]**. 
1. On the **[!UICONTROL Data Warehouse Request]** tab, fill in the fields.

   For more information about each field, see "Data Warehouse Descriptions" in [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html).

   | Field | Instructions |
   |--- |--- |
   |Request Name|Specify a name for your request.|
   |Reporting Date|Specify a time period and granularity.<br>As best practice, choose no more than an hour or one day of data for your first request.  Data Warehouse files take longer to process the longer the time period requested, so it is always a best practice to request a small time period data first to make sure your file returns the expected result. Then, go to the Request Manager, duplicate your request, and ask for more data the second time. Also, if you toggle granularity to anything other than "None," the file size will increase drastically.<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png)|
   |Available Segments|Apply a segment, as needed.|
   |Breakdowns|Select the desired dimensions:  Standard is out-of-the-box (OOTB), while Custom includes eVars & props. It is recommended you use "Visitor ID" if visitor ID level information is needed, rather than "Experience Cloud Visitor ID."<ul><li>Visitor ID is the final ID used by Analytics. It will either be AID (if the customer is legacy) or MID (if the customer is new or cleared cookies since the MC visitor ID service was launched).</li><li>Experience Cloud Visitor ID will only be set for customers who are new or cleared cookies since the MC visitor ID service was launched.</li></ul>|
   |Metrics|Select your desired metrics. Standard is OOTB, while Custom includes custom events.|
   |Report Preview|Review your settings before scheduling the report.<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png)|
   |Schedule Delivery|Enter an email address to deliver the file to, name the file, then select [!UICONTROL Send Immediately].<br>Note: The file can be delivered via FTP under [!UICONTROL Advanced Delivery Options]<br>![Schedule Delivery](/help/main/c-reports/assets/datawarehouse3.png).|

1. Click **[!UICONTROL Request this Report]**.

   File delivery can take up to 72 hours, depending on the amount of data requested. You can check on the progress of your request at any time by clicking [!UICONTROL Tools] > [!UICONTROL Data Warehouse] > [!UICONTROL Request Manager].

   If you would like to re-request data that you've requested in the past, you can duplicate an old request from the [!UICONTROL Request Manager] as needed.

For more information about [!DNL Data Warehouse], see the following links in the [!DNL Analytics] Help documentation:

* [Create a Data Warehouse request](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html) 
* [Data Warehouse best practices](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)

## Counting Methodology {#concept_EC19BC897D66411BABAF2FA27BCE89AA}

You can choose to view reports by different counting methodologies to understand how your activities affect your users across their lifetimes or during a single session.

Counting methodology is supported for the following activity types:

* A/B Test

  As an exception, Auto-Target A/B activities support only the default "Visit" counting methodology. 

* Experience Targeting (XT) 
* Multivariate Test (MVT)

  For the MVT Element contribution report, Target does not support Activity Impressions for Revenue Metric types. 

* Recommendations

Only the default counting methodology (Visits) is currently supported for Automated Personalization (AP) activities.

You can view reports by the following counting methodologies:

* **Visitor:** A unique participant in the activity, for the life of the activity.

  A person will be counted as a new entrant if he or she visits the site from a new computer or a new browser; deletes the cookie; or converts and returns to the activity with the same cookie. An entrant is identified by the PCID in the visitor's mbox cookie. If the PCID changes, the person is considered a new visitor. 

* **Visit:** A unique participant in an experience during a single 30-minute browser session.

  If a conversion is achieved or a visitor comes back to the site after being away at least 30 minutes, a returning visitor counts as a new visit. A visit is identified by the `sessionID` in the visitor's mbox cookie. When the `sessionID` changes, the visit is considered new.

* **Impression/Page View:** Counted each time a visitor loads any page of the activity.

  A single visit might include several impressions of, for example, your homepage.

>[!NOTE]
>
>Usually, counts are determined by cookies and session activity. However, if you reach the final conversion point of an activity and then re-enter the activity, you are considered a new entrant and a new visit to the activity. This is true even if your PCID and `sessionID` values do not change.

## Why does [!DNL Target] recommend using Welch's t-tests? {#t-test}

A/B tests are experiments to compare the mean value of some business metric in a control variant (also known as an experience) to the mean value of that same metric in one or more alternate experiences.

[!DNL Target] recommends using [Welch's t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test), as these require fewer assumptions than alternatives like z-tests, and are the appropriate statistical test for doing pairwise comparisons of (quantitative) business metrics between a control experiences and alternate experiences.  

### In more detail

When running online A/B tests, each user/visitor is randomly assigned to a single variant. Subsequently, we make measurements of the business metric(s) of interest (e.g. conversions, orders, revenue, etc.) for visitors in each variant. The statistical test we use then tests the hypothesis that the mean business metric (e.g. conversion rate, orders per user, revenue per user, etc.) is equal for the control and a given alternate variant.

Although the business metric itself might be distributed according to some arbitrary distribution, the distribution of the mean of this metric (within each variant) should converge to a normal distribution via the [Central Limit Theorem](https://en.wikipedia.org/wiki/Central_limit_theorem). Note that although there is no guarantee on how quickly this sampling distribution of the mean will converge to normal, this condition is typically achieved given the scale of visitors in online testing. 

Given this normality of the mean, the test statistic to be used can be shown to follow a t-distribution, because it is the ratio of a normally distributed value (the difference in means of the business metric) to a scaling term based on an estimate from the data (the standard error of the difference in means). The **t-test** is then the appropriate hypothesis test, given the test statistic follows a t-distribution.

### Why other tests are not used

A **z-test** is technically inappropriate because in the typical A/B testing scenario, the denominator of the test statistic is not a derived from a known variance, and instead must be estimated from the data. However for large enough sample sizes, the z-test and t-test are identical. 

**Chi-squared tests** are not used because these are appropriate for determining whether there is a qualitative relationship between two variants (i.e. a null hypothesis that there is no difference between variants). T-tests are more appropriate for the scenario of _quantitatively_ comparing metrics.

The **Mann-Whitney U test** is a nonparametric test, which is appropriate when the sampling distribution of the mean business metric (for each variant) is not normally distributed. However as discussed earlier, given the magnitudes of traffic involved in online testing, the Central Limit Theorem typically applies, and so the t-test can be safely applied.

More complex methods like **ANOVA** (which generalize t-tests to more than two variants) can be applied when a test has more than two experiences ("A/Bn tests"). However, ANOVA answers the question of "whether all variants have the same mean," while in the typical A/Bn test we are more interested in _which specific variant_ is best. In [!DNL Target], we therefore apply regular t-tests comparing each variant to a control, with a Bonferroni correction to account for multiple comparisons.