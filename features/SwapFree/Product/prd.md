Swap-Free Administrative Fee System
Product Requirements Document
Author: Amit Hochma
 Date: January 2026
 Version: 1.0
 Status: Draft for Review

1. Executive Summary
The Swap-Free Administrative Fee System introduces a compliant, position size-based fee model for Islamic (swap-free) CFD accounts in the UAE market.
Today, overnight funding costs for swap-free customers are fully absorbed by the platform, with no monetization. Competitors apply administrative fee models that are accepted by regulators and customers. This initiative closes that revenue gap while staying aligned with Islamic finance principles.
The solution is based on:
A 7-bin position size fee structure


A 7-day grace period


Dynamic bin reassignment


Equity-based fee deduction


Whitelist support - a list of accounts that are excluded from the fee (Optional)


Fees are framed strictly as administrative or custody fees, never as interest.


2. User Journeys
2.1 User Journey
Swap-Free Account Holder
Pre-Trade
User opens the trade screen
Estimated “Administrative fee (Swap-Free)” is displayed - 0$ for 7 days and then based on position size with the ability to see all the bins prices details on tooltip.
Fee is shown per day and clearly marked as administrative
Grace Period
	4. Position is opened
 	6. No fees are charged
Post Grace Period
 	7. Daily fee is calculated based on current bin
 	8. Fee is deducted from Online PL
 	9. Fee impact is visible in real time
Bin Changes
	 10. Position size changes due to price movement
	 11. Bin is recalculated (daily)
	 12. Fee per day updates accordingly


3. Success Criteria
3.1 User Success
Clear understanding of fees
No surprise charges
Grace period protection
Transparent fee display


3.2 Business Success
Incremental revenue generation
No material churn increase in UAE

3.3 Compliance Success
Zero regulatory findings
Clear administrative fee framing
Full auditability

4. Product Scope
4.1 MVP Scope
Position size calculation engine
7-bin fee model
7-day grace period
Daily fee calculation and deduction (same time as OVF)
Dynamic bin reassignment
User whitelist
Minimal UI indicators
Basic reporting and audit logs
Representation also on the closed positions screen


5. Domain-Specific Requirements
5.1 Islamic Finance Rules
Fees must be administrative or custody based
No reference to interest or funding rates
Explicit disclosure in UI and terms



5.2 Regulatory
SCA compliance
Transparent fee disclosure

6. Functional Requirements
FR1: Position Size Calculation
Total notional value of position - The fee is based on each position’s size, as opposed to the total / aggregated positions size per instrument type.
Supports multiple instruments
Updates with price movement (daily update)
Currency conversion supported 
On partial closed positions, the grace period is still counted.
On partial close, we will close the relative part of the position and will take the relative part of the sum total fee that was counted for the position.
In Admin on the Admin Fee Calculator we will add bin column, bin rate, and Daily Admin Fee.
FR2: Bin Assignment
7 bins based on position size
Configurable thresholds
Automatic reassignment on threshold crossing will change on calculation time
FR3: Grace Period
7 days per position
No fees during grace period
FR4: Fee Calculation
Daily fee = bin rate 
Applies only after grace period
The instrument rate would be based on the rates of OVF. (the latest feed 30 minute before the OVF time)
Fees will be calculated in USD only. We should save the currency conversion rate during the time of the fee calculation. (the latest feed 30 minute before the OVF time)
The fee calculation time would be the time we calculate OVF.
FR5: Fee Deduction
Deduct from Position Online PL
Daily scheduled execution
Full audit logging - Similar to the Dynamic Overnight Fee Calculator.
FR6: Reporting
Fee logs
Bin history
Closed positions representation
Revenue reporting
Admin Commissions
Management Stats
Tableau - Positions, Revenues, Commissions
Admin- Support ‘Show Admin Fee Details’ button that shows the fee details



7. Open Decisions
Communication plan for existing customers. 
What do we do with open positions that were opened in the old model?



8. References
Internal
Product Concept
Figma
Asana


External
eToro swap-free documentation
Equiti swap-free documentation
TMGM swap-free account
Taurex swap-free account
