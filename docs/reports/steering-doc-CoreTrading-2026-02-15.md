# Steering Meeting Core Trading

**Team:** 		Core Trading  
**Sprint Starts:** 	15-Feb-2026  
**Sprint Ends:**    	01-Mar-2026

| Client | Version | Code Freeze Date | Publish Date | What is released |
| :---- | :---- | :---- | :---- | :---- |
|  |  |  |  |  |

## Executive summary

Core Trading’s next sprint (15 Feb–1 Mar 2026) focuses on platform reliability, 24/5 feeds, and UX. We are adding a Tableau Trading Cockpit dashboard under Admin/MgmtStats and continuing 24/5 U.S. stocks via Blue Ocean (new provider support and time-based provider switch). On the execution and research side we are delivering sorting for the trading instruments table (Web) and progressing option-chain and instruments behaviour (expiry handling, InstrumentsList CSV for options with no snapshot). We are also advancing the UX uplift of the info tab on iOS and Android bottom-sheet subnavigation. Tech and stability work includes VolatilityAbusePrevention wait-time reduction, EnqueueInstrumentChangedToEventsManager removal, Heating oil unavailability investigation, and reducing error-alert noise (Prod/QA/CurrenciesService/MarketData). Market and compliance items: Move Taiwanese and Malaysian users to the Hong Kong instrument group and TQQQ margin override on Taiwan.

## Development Team \- Work Candidates

All items appear in the following [Asana project](https://app.asana.com/1/1495426035223/project/1212645045116636/list/1212645045141175).

| Task | Short Description\Asana\Confluence Link OR Task Current Status \ Next step | Dev lead | Feature domain | Is Roadmap | Initiator | Is leftover from previous sprint | Client | Notes |
| ----- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| Roadmap |  |  |  |  |  |  |  |  |
| [Add Tableau 'Trading Cockpit' dashboard under Admin/MgmtStats](https://app.asana.com/0/1213018415024361/1213018415024361) | Add Tableau dashboard to Admin/Stats | Or Rotem | Admin/Stats |  |  |  |  |  |
| [Release plan for autodetect invalid locales](https://app.asana.com/0/1212799820313449/1212799820313449) | Plan for detecting invalid locales automatically | Ilan Ben Tal |  |  |  |  |  |  |
| [\[BE\] Support Blue Ocean feeds in the platform](https://app.asana.com/0/1212649751932675/1212649751932675) | 24/5 US stocks; new provider support and time-based switch | Zahy Volf | Financial instruments | Yes | Product | no | BE |  |
| [\[BE\] Support a new provider](https://app.asana.com/0/1212826524636701/1212826524636701) | Add BlueOcean proxies in QA (Bloomberg and ICE) |  |  |  |  |  | BE |  |
| [\[BE\] Time based provider switch](https://app.asana.com/0/1212826524636703/1212826524636703) | Switch between providers at configured time via admin |  |  |  |  |  | BE |  |
| [Add Sorting Capabilities to Trading Instruments Table](https://app.asana.com/0/1212918664405519/1212918664405519) \[Web\] | Sort trading table by Instrument, Change, Sell, Buy, High/Low | Elhanan Perlshtein | Research tools | no | Product | no | FE |  |
| [Move Taiwanese and Malaysian to 'Hong Kong' instrument group](https://app.asana.com/0/1212635057329238/1212635057329238) | Move Taiwan/Malaysia PLUSSEY users to Hong Kong group (no options) |  | Monetization | no | Trading | no | BE |  |
| [Add TQQQ override on Taiwan](https://app.asana.com/0/1212635247914625/1212635247914625) | Override initial margin of TQQQ to 20% in Taiwan |  | Monetization | no | Trading | no | BE |  |
| UX Improvements |  |  |  |  |  |  |  |  |
| [UX uplift of info tab \[web\] / iOS](https://app.asana.com/0/1211031188803163/1211031188803163) | UX uplift of the info tab; consolidated card-style layout | Luda Fux | UX | Yes | Product | Yes | iOS/web |  |
| [\[Android\] Bottom sheet Composable subnavigation graph support](https://app.asana.com/0/1212918955625340/1212918955625340) | Compose Navigation for bottom sheet; back stack, state, animations | Maxim Diland |  |  |  |  | FE | QD - Migrate to BottomSheet navigation |
| Other |  |  |  |  |  |  |  |  |
| [InstrumentsList csv download fails for options with no snapshot](https://app.asana.com/0/1212961760615259/1212961760615259) | Fix CSV download for options with no snapshot in Admin | Ella Sacks |  |  |  |  |  | Option Low DTE |
| [\[Dev\] Quick solution - Reduce wait time in VolatilityAbusePrevention](https://app.asana.com/0/1212918593000258/1212918593000258) | PublishInstrumentUpdates via Rabbit; configurable delay |  |  |  |  |  | BE |  |
| [EnqueueInstrumentChangedToEventsManager removal](https://app.asana.com/0/1212804305619175/1212804305619175) | Remove self-loop; enable fallback with FF | Yarden Ganon | InstrumentsService |  |  |  | BE |  |
| [Heating oil (430i) unavailability - 07/01/2025](https://app.asana.com/0/1212849866140179/1212849866140179) | Investigate Heating Oil DEAD state; Bloomberg/ICE behaviour | Zahy Volf |  |  |  |  |  |  |
| [Options with missing expiry](https://app.asana.com/0/1212995848712187/1212995848712187) | Natural Gas options expiry discrepancy; TF vs Unavailable | Ella Sacks |  |  |  |  |  |  |
| [Handle expiry gracefully when instrument has no feeds](https://app.asana.com/0/1212957593201066/1212957593201066) | Option with no feeds expired; UsersService/TradingService errors |  |  |  |  |  | BE |  |
| [Reduce number of error alerts](https://app.asana.com/0/1212918776415674/1212918776415674) | Fewer repeating alerts; thresholds/filtering for Prod/QA |  |  |  |  |  |  |  |
| [new asset type is not reflected in the account statement](https://app.asana.com/0/1213011442445562/1213011442445562) | Bug: account statement missing new asset type | Oleg Sternberg |  |  |  |  |  | Bugs |
| [Android - Trade screen crash while changing orientation (Options Chain)](https://app.asana.com/0/1213023333089113/1213023333089113) | Crashlytics; maybe after returning from background | Ilan Ben Tal |  |  |  |  | Android |  |
| [Dynamic spread simulator stopped working after SpreadIntervals](https://app.asana.com/0/1212924292951287/1212924292951287) | Simulator broken after SpreadIntervals change | Zahy Volf |  |  |  |  |  |  |
| [Release plan for autodetect invalid locales](https://app.asana.com/0/1212799820313449/1212799820313449) |  | Ilan Ben Tal |  |  |  |  |  |  |
| [Monthly aggregated Volume does not support the bi-weekly publish](https://app.asana.com/0/1212251745052817/1212251745052817) | Volume of new resolutions reset on publish | Zahy Volf |  |  |  |  |  |  |
| [MaintenanceCloseInactiveFunUsers](https://app.asana.com/0/1209066245129883/1209066245129883) | Move to ScheduledMaintenanceService; remove old code/FF |  | Internal Service |  |  |  |  |  |

## Experiments/Other notes:

*To be filled from sprint data or team input.*
