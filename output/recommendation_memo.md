# Task 1
## Executive Summary & Problem Framing

I recently conducted an A/B test evaluating a new onboarding and activation campaign (Treatment) against our existing experience (Control). Before analyzing the experimental data and finalizing our recommendation, I have established the following evaluation framework to ensure alignment with our core business objectives:

* **The Decision:** I must decide whether to launch the new onboarding experience globally, reject it, extend the testing period, or deploy it exclusively to targeted user segments.
* **Impact:** This change affects all incoming new users and operational teams (Product, Customer Support).
* **Targeted Improvements:** I are optimizing for an increased **Paid Conversion Rate** and higher **Engagement Scores**. 
* **Monitored Risks (Guardrails):** I must ensure the new flow does not artificially inflate conversions at the cost of user satisfaction. I are strictly monitoring **Support Ticket Volume**, **Refund Requests**, and **30-Day Revenue** to prevent low-quality growth.
* **Evidence Required:** A "Launch" recommendation requires conclusive, statistically significant evidence that the new campaign improves primary conversion metrics *without* causing a detrimental, statistically significant impact on our guardrail metrics (support loads and refunds). 

The complete data analysis and final verdict based on this framework will follow in the detailed report.

# Task 9 
## 1. Executive Summary
We have concluded the A/B test evaluating the new onboarding and activation campaign. While the treatment group successfully drove a highly significant increase in our primary conversion metric, it simultaneously triggered severe operational risks, specifically a massive spike in customer support tickets and buyer refunds. Because the new experience degrades user satisfaction and heavily burdens our support operations, the recommendation is to **Do not launch** the campaign in its current state.

## 2. North Star Metric
Our North Star metric for this initiative is the **Paid Conversion Rate** (the percentage of users who convert to a paid subscription) [cite: 3]. It directly measures the campaign's ability to drive business growth and early user commitment [cite: 5]. 

## 3. KPI Tree Explanation
To ensure a balanced evaluation, our KPI tree breaks down the North Star into primary drivers: Traffic Quality, Onboarding Efficiency, and Product Value & Early Engagement. Crucially, the KPI tree also establishes strict **Guardrail Metrics** (Support Ticket Volume, Refund Rate, and Revenue Quality) to ensure that top-of-funnel conversion increases do not come at the expense of user experience or long-term operational stability [cite: 3].

## 4. Experiment Result Summary
* **Paid Conversion Rate:** Increased from 3.19% (Control) to 7.04% (Treatment) [cite: 5].
* **Support Ticket Rate:** Increased from 14.78% (Control) to 24.79% (Treatment).
* **Buyer Refund Rate:** Increased from 0.00% (Control) to 6.00% (Treatment).
* **Average Revenue Per User (ARPU):** Remained stable ($50.10 Control vs. $54.25 Treatment, not a statistically significant difference).

## 5. Hypothesis Test Interpretation
We conducted a right-tailed Z-test for two proportions to evaluate the Paid Conversion Rate [cite: 5].
* **Result:** The test yielded a Z-statistic of 3.2640 and a p-value of 0.000549 [cite: 5].
* **Interpretation:** Because the p-value (0.000549) is far below our 0.05 significance level, we successfully rejected the null hypothesis [cite: 5]. The data confirms that the Treatment drives a statistically significant increase in paid conversion [cite: 5]. 

## 6. Guardrail Analysis
Despite the conversion win, our guardrail metrics failed catastrophically:
* **Support Tickets (Severe Risk):** The Treatment group saw a 10-percentage-point surge in support tickets (reaching nearly 25%). This indicates the new onboarding flow is highly confusing or technically flawed.
* **Refunds (Moderate Risk):** 6% of the users who converted to paid in the Treatment group subsequently requested a refund, compared to 0% in the Control group. This signals buyer's remorse and suggests the new flow might be misleading users into subscribing.

## 7. Segment-Level Insight
We analyzed the support ticket surge across device types (Mobile, Desktop, Tablet) and regions to see if the issue was isolated. The degradation in user experience was universal. Mobile users in the Treatment group experienced a 25.2% support ticket rate, and Desktop users saw a 23.9% rate. Because the friction is not isolated to a specific device, browser, or region, a targeted rollout is not viable.

## 8. Final Recommendation: Do Not Launch
**Recommendation: DO NOT LAUNCH.** 
Although the campaign successfully boosted conversions by pushing more users through the funnel, it did so by creating a "leaky bucket." Rolling this out globally would immediately overwhelm our Customer Support team [cite: 3]. Furthermore, it risks damaging brand trust due to the misleading nature of the flow (evidenced by the refund spike). 

## 9. Risks and Limitations
* **Short-Term Data:** The test only evaluated 30-day revenue and 30-day support tickets [cite: 3]. Long-term retention (e.g., Month 2 churn) of the Treatment cohort could be even worse given the high early refund rate.
* **Root Cause Ambiguity:** The quantitative data tells us *that* users are confused, but qualitative data (like session recordings or support ticket text analysis) is required to know *why* they are confused.

## 10. Next Steps
1. **Halt the Rollout:** Keep all new users on the existing Control experience.
2. **Qualitative Deep Dive:** Have the Product and UX teams analyze the support tickets generated by the Treatment group to identify the specific steps causing friction.
3. **Iterate and Retest:** Redesign the onboarding flow to address these friction points. Launch a new A/B test (V2) aiming to capture the conversion uplift of the Treatment without triggering the support and refund penalties.
