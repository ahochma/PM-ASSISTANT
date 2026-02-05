Swap-Free Charging Model
Product Proposal
Background
Today, leveraged positions held overnight are charged an Overnight Funding fee.
For Swap-Free (Islamic) customers, this fee is not charged due to religious restrictions.
As a result, we currently absorb the cost of holding leveraged positions overnight for these customers, with no direct monetization.
The goal is to introduce a Swap-Free charging model that creates revenue, stays compliant with Islamic principles, and remains fair to users.

Problem
Swap-Free users can hold leveraged positions overnight without any cost.


This creates a revenue gap compared to standard accounts and the market



Product Goal
Introduce a Swap-Free charging mechanism that:
Generates incremental revenue
Is fair across position sizes and holding periods because the cost is linked directly to how much exposure the user takes and for how long.
Is simple enough to explain, build, and iterate
Can be adjusted over time based on real data
The product won’t introduce new churn motion due to a non-competitive model





Key Insights from Analysis made by the Trading team - Fee vs OVF islamic accounts.xlsx
Most positions that are opened for more than a week are closed within 30 days-(around 75%)


The majority of positions are relatively small in notional value. 


A fixed daily fee can translate into a very high implied annual cost for small positions.


There is no reliable way to fully predict churn or behavior change before launch.


Conclusion: precision is important, but over-complexity at v1 is risky.
Competitors:
Broker
Free Period
Position Size Limit
Fee After Free Period
Special Rules
ADSS
Up to 14 days
Up to 3 lots
Standard swap applies
Hard cap on size and time
Equiti
Up to 7 days
No clear limit
Daily admin fee
Triple fee on Wednesday
Capital.com
No free period
No size limit
Cost via wider spreads
Futures & crypto only
Proposed Model
Up to 7 days (≤10K$)
10K$
Tiered admin fee
Size based + time based 



Proposed Direction (v1)
Grace Period + Time-Based Fee
Grace period


No charge for the first 7 days a position is held open.


Post-grace charging


A fixed custody fee applies per time unit after day 7.


Fee increases only with time held open, not daily compounding.


Position size handling


Fee is calculated based on the position size at opening.


Position size does not change over time for charging purposes.




Why This Approach
Grace period protects short-term and active traders.


Time-based charging aligns cost with longer holding behavior.


Fixing position size at opening reduces technical and product complexity.


Accepts that v1 will not be perfect, but will be measurable and adjustable.


Open Questions (to be finalized before launch)
Exact fee levels and time brackets - TBD


Upper caps or protections for small positions


How fees are displayed in the UI


Communication to existing customers


Solution:
Up to10K$ position size:
Holding Period
Daily Fee per Lot (USD)
Notes
Day 0 to Day 7
$0
Same as Equiti
Day 8 to Day 14
$4
Light holding cost
Day 15+
$8
Discourages long holding



Above 10K$ position size:
Holding Period
Daily Fee per Lot (USD)
Notes
Day 0 to Day 7
$4
No free period
Day 8 to Day 14
$6
Higher cost for size
Day 15+
$10
Strong control on exposure



Risks & Mitigations
Risk: Higher cost perception for small users
 Mitigation: Grace period + clear upfront disclosure


Risk: Churn impact hard to predict
 Mitigation: Start with conservative pricing and monitor closely


Risk: Compliance and user explanation concerns
 Mitigation: Frame as custody/administration fee, not interest



