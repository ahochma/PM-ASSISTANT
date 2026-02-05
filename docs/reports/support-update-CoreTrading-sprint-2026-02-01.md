# Support Team Update — CoreTrading Sprint [2026-02-01] — **Server changes only**

Generated from: `CoreTrading_sprint_-_[2026_02_01]_-_Active.csv`  
**Only DONE tasks (Completed At filled) that are server-side changes.**

---

## Headline [Plus500UK >> CA activity reports]

**Description**  
UK CA report deliverables completed on server this sprint: MiFIR CSV, UKMIR Derivatives/Margins, Capital Adequacy (incl. Summary), Trade Per Instrument, Client Money Report, Open Positions, Market Surveillance CFD, Lossmaking Equity CFDs change, AdminStats/CSV. Support: new/updated UK CA report formats and timelines; refer to Asana project for specifics.

**Asana link**  
https://app.asana.com/0/0/1212611130679018

---

## Headline [ReportingService – Eliminate InstrumentUpdates via EventsService]

**Description**  
ReportingService work completed: transition to instrument updates via Rabbit only (Eliminate InstrumentUpdates via EventsService). Support: internal backend change; no customer-facing impact unless ops/reporting questions arise.

**Asana link**  
https://app.asana.com/0/0/1212241974097593

---

## Headline [Move OnBestExecutionProvidersMaintenance to InstrumentsService]

**Description**  
Best-execution maintenance logic moved from ReportingService to InstrumentsService; feature-flag config added (instruments-service/enable-best-execution-params-update-flow). Support: backend/ops; escalate only if reporting or instrument params questions.

**Asana link**  
https://app.asana.com/0/0/1212557567291496

---

## Headline [Reduce leverage for open positions X days before earnings]

**Description**  
Server work completed: DB column renames (InstrumentsEventsMarginsUpdate: OverrideInitialMarginPercentage, OverrideMaintenanceMarginPercentage); config store parameter for when the event is fired. Support: leverage/margin changes before earnings are server-driven; direct detailed questions to R&D/ops.

**Asana link**  
https://app.asana.com/0/0/1212744594520331
