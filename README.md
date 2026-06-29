# Task 1
# Subscription Product Onboarding Optimization: A/B Test Analysis

## Business Problem Statement

**1. The Decision to be Made**
Leadership must decide the future of the new onboarding and activation campaign. The primary decision is whether to launch the treatment experience to the entire user base, reject it in favor of the existing control experience, continue testing to gather more data, or roll it out only to selected, high-performing user segments.

**2. Who the Decision Impacts**
This decision directly impacts **new users** signing up for the subscription product, as it defines their initial product experience and activation journey. Internally, it impacts the **Product, Marketing, and Customer Support teams** responsible for user growth, platform stability, and query resolution.

**3. Metrics That Should Improve**
The campaign's primary objective is to drive growth and early engagement. Therefore, the core success metric is the **Paid Conversion Rate** (`converted_to_paid`). Secondary success metrics include improved **Engagement Scores** (`engagement_score`), Trial Initiation Rate (`started_trial`), and Onboarding Completion Rate (`completed_onboarding`).

**4. Risks That Must be Monitored (Guardrails)**
A higher conversion rate is not inherently successful if it attracts low-intent users or creates friction. We must strictly monitor the following guardrail metrics:
* **Refund Rate (`refund_requested`)**: An increase indicates buyer's remorse or misleading onboarding.
* **Support Ticket Volume (`support_tickets_30d`)**: Spikes indicate user confusion or technical friction in the new flow.
* **Revenue Quality (`revenue_30d`)**: We must ensure that increased conversions do not coincide with a significant drop in Average Revenue Per User (ARPU).

**5. Required Evidence for a Recommendation**
Before recommending a full launch, we require:
* **Statistically significant uplift** in the Paid Conversion Rate (and/or Engagement Score) for the treatment group compared to the control.
* **Flat or improved guardrail metrics**, ensuring that any increase in conversion does not cause a statistically significant rise in refund requests or support tickets.
* **Segment analysis** confirming the treatment does not severely underperform in any major geographic region, device type, or traffic source.


# Task 4
# Subscription Product Onboarding Optimization: A/B Test Analysis

## Business Problem Statement

**1. The Decision to be Made**
Leadership must decide the future of the new onboarding and activation campaign. The primary decision is whether to launch the treatment experience to the entire user base, reject it in favor of the existing control experience, continue testing to gather more data, or roll it out only to selected, high-performing user segments.

**2. Who the Decision Impacts**
This decision directly impacts **new users** signing up for the subscription product, as it defines their initial product experience and activation journey. Internally, it impacts the **Product, Marketing, and Customer Support teams** responsible for user growth, platform stability, and query resolution.

**3. Metrics That Should Improve**
The campaign's primary objective is to drive growth and early engagement. Therefore, the core success metric is the **Paid Conversion Rate** (`converted_to_paid`). Secondary success metrics include improved **Engagement Scores** (`engagement_score`), Trial Initiation Rate (`started_trial`), and Onboarding Completion Rate (`completed_onboarding`).

**4. Risks That Must be Monitored (Guardrails)**
A higher conversion rate is not inherently successful if it attracts low-intent users or creates friction. We must strictly monitor the following guardrail metrics:
* **Refund Rate (`refund_requested`)**: An increase indicates buyer's remorse or misleading onboarding.
* **Support Ticket Volume (`support_tickets_30d`)**: Spikes indicate user confusion or technical friction in the new flow.
* **Revenue Quality (`revenue_30d`)**: We must ensure that increased conversions do not coincide with a significant drop in Average Revenue Per User (ARPU).

**5. Required Evidence for a Recommendation**
Before recommending a full launch, we require:
* **Statistically significant uplift** in the Paid Conversion Rate (and/or Engagement Score) for the treatment group compared to the control.
* **Flat or improved guardrail metrics**, ensuring that any increase in conversion does not cause a statistically significant rise in refund requests or support tickets.
* **Segment analysis** confirming the treatment does not severely underperform in any major geographic region, device type, or traffic source.


## Data Preparation & Quality Checks

### 1. Duplicate User IDs
* **Check:** Found 8 duplicate user records.
* **Action:** Removed duplicates, keeping the first occurrence. Remaining rows: 1400.

### 2. Missing Values
* **Check & Action:**
  * `device_type`: 18 missing. Imputed with 'Unknown'.
  * `traffic_source`: 24 missing. Imputed with 'Unknown'.
  * `days_to_convert`: 1328 missing. Expected behavior for users who did not convert. Left as NaN.
  * `engagement_score`: 14 missing. Imputed appropriately based on data type.
### 3. Invalid Binary Values
* **Check:** Validating that boolean flags only contain 0 or 1.
  * No invalid binary values found. All columns conform to [0, 1].

### 4. Outliers in Revenue
* **Check:** Analyzed `revenue_30d` for extreme values. The 99th percentile for converted users is $7317.26.
* **Action:** Found 1 outliers exceeding this threshold. Capped revenue at the 99th percentile to prevent artificial skewing of ARPU calculations.

### 5. Group Counts & Segment Distribution
* **Group Counts:** Control = 690, Treatment = 710.
* **Segment Distribution Check:** Verified distribution of `device_type`, `region`, and `traffic_source` across experiment groups to ensure no sample ratio mismatch (SRM) or biased randomization.
  * *Device Type Distribution:* Appears balanced between groups.
