# Task 6
# Hypothesis Test Design: Onboarding & Activation Campaign

## 1. Null Hypothesis ($H_0$)
The new onboarding campaign (Treatment) does not improve the paid conversion rate compared to the existing experience (Control). Any observed increase is due to random chance. 
**Mathematical representation:** $p_{treatment} \le p_{control}$

## 2. Alternate Hypothesis ($H_A$)
The new onboarding campaign (Treatment) significantly improves the paid conversion rate compared to the existing experience (Control). 
**Mathematical representation:** $p_{treatment} > p_{control}$

## 3. Test Type
**One-tailed test (Right-tailed)**
*Rationale:* The business decision is strictly about whether to roll out the new campaign to *improve* conversion. We are testing for a specific directional effect (an increase). If the new campaign performs the same or worse than the control, the business decision remains the same: do not launch. 

## 4. Significance Level ($\alpha$)
**$\alpha = 0.05$ (5%)**
*Rationale:* This standard threshold means we are willing to accept a 5% risk of committing a Type I error (recommending the launch of the new campaign when it doesn't actually improve conversion). It provides a solid balance between being agile and requiring statistical rigor.

## 5. Metric Being Tested
**Paid Conversion Rate** (The proportion of total users who convert to a paid subscription).

## 6. Reason for Choosing this Metric
As established in our KPI framework, the Paid Conversion Rate is our **North Star Metric**. While trial starts and onboarding completion rates are helpful leading indicators, actual paid conversion is the only metric that proves the campaign successfully communicated the product's core value and drives direct business growth (Monthly Recurring Revenue).

## 7. Interpretation Logic & Business Decision
To make our final recommendation, we will calculate the p-value of the experiment data.

* **Scenario A: p-value < 0.05**
  * **Statistical interpretation:** We reject the null hypothesis ($H_0$). The data provides strong evidence that the Treatment genuinely increases the conversion rate.
  * **Business decision:** **Launch.** Recommend rolling out the new onboarding campaign to all users, *provided* that guardrail metrics (refunds, support tickets, ARPU) have not significantly worsened.

* **Scenario B: p-value $\ge$ 0.05**
  * **Statistical interpretation:** We fail to reject the null hypothesis ($H_0$). There is not enough evidence to confidently say the Treatment is better; the observed difference could just be noise.
  * **Business decision:** **Do not launch.** Retain the Control experience or iterate on the campaign design for a future test


# Task 7
# Hypothesis Test Design: Onboarding & Activation Campaign

## 1. Null Hypothesis ($H_0$)
The new onboarding campaign (Treatment) does not improve the paid conversion rate compared to the existing experience (Control). Any observed increase is due to random chance. 
**Mathematical representation:** $p_{treatment} \le p_{control}$

## 2. Alternate Hypothesis ($H_A$)
The new onboarding campaign (Treatment) significantly improves the paid conversion rate compared to the existing experience (Control). 
**Mathematical representation:** $p_{treatment} > p_{control}$

## 3. Test Type
**One-tailed test (Right-tailed)**
*Rationale:* The business decision is strictly about whether to roll out the new campaign to *improve* conversion. We are testing for a specific directional effect (an increase). If the new campaign performs the same or worse than the control, the business decision remains the same: do not launch. 

## 4. Significance Level ($\alpha$)
**$\alpha = 0.05$ (5%)**
*Rationale:* This standard threshold means we are willing to accept a 5% risk of committing a Type I error (recommending the launch of the new campaign when it doesn't actually improve conversion). It provides a solid balance between being agile and requiring statistical rigor.

## 5. Metric Being Tested
**Paid Conversion Rate** (The proportion of total users who convert to a paid subscription).

## 6. Reason for Choosing this Metric
As established in our KPI framework, the Paid Conversion Rate is our **North Star Metric**. While trial starts and onboarding completion rates are helpful leading indicators, actual paid conversion is the only metric that proves the campaign successfully communicated the product's core value and drives direct business growth (Monthly Recurring Revenue).

## 7. Interpretation Logic & Business Decision
To make our final recommendation, we will calculate the p-value of the experiment data.

* **Scenario A: p-value < 0.05**
  * **Statistical interpretation:** We reject the null hypothesis ($H_0$). The data provides strong evidence that the Treatment genuinely increases the conversion rate.
  * **Business decision:** **Launch.** Recommend rolling out the new onboarding campaign to all users, *provided* that guardrail metrics (refunds, support tickets, ARPU) have not significantly worsened.

* **Scenario B: p-value $\ge$ 0.05**
  * **Statistical interpretation:** We fail to reject the null hypothesis ($H_0$). There is not enough evidence to confidently say the Treatment is better; the observed difference could just be noise.
  * **Business decision:** **Do not launch.** Retain the Control experience or iterate on the campaign design for a future test.

## 8. Test Execution & Results
**Test Performed:** Z-Test for Two Proportions (Right-tailed)

**Summary of Test Inputs:**
* **Control Group:** 690 users, 22 conversions (Rate: **3.19%**)
* **Treatment Group:** 710 users, 50 conversions (Rate: **7.04%**)

**Test Output:**
* **Z-Statistic:** 3.2640
* **P-value:** 0.000549

**Decision Rule:**
Our significance level ($\alpha$) is set at 0.05. 
* Because our p-value (0.000549) is **less** than 0.05, we **reject** the null hypothesis.

**Business Interpretation:**
The statistical test confirms that the new onboarding campaign (Treatment) drives a statistically significant increase in the paid conversion rate compared to the existing experience. The probability that this uplift occurred by random chance is virtually zero. Because we have rejected the null hypothesis, the data strongly supports a business recommendation to launch the new campaign, pending a final review of guardrail metrics to ensure no negative operational side effects.
