# Employee Assessment Performance Portal — Final September 2026

## Package files
- `index.html` — portal interface
- `results.xlsx` — August 2026 historical results + final September 2026 results
- `hierarchy.xlsx` — final September/current hierarchy
- `hierarchy_august.xlsx` — August 2026 historical hierarchy snapshot
- `question_bank.xlsx` — August 2026 + September 2026 question banks
- `results_raw.csv` — latest September raw export retained for audit/reference

## Portal rules
- August and September use separate hierarchy snapshots and question banks.
- Required population is all current-month Lead/Supervisor employees in scope.
- Actual completed submissions outside the required population are retained as Additional Submissions.
- Pending is required employees with no completed result in the selected month.
- Functional Code is the unique employee key.
- Performance uses the latest completed result per Functional Code for the selected month.
- Device audit retains all raw attempts for the selected month.

## Added in this version
- Nadim Sameh Moris Louca (Functional Code `30020000`) displays `Sr. VP Operations Excellence` under his name when logged in, and the top-right role chip uses the same title. His underlying permission remains `Director / Head`.
- Added a separate `Persistent Low Performers` view. By default it compares the two latest available months (currently August vs September), includes employees at or below `70%` in both months, and shows the lowest `10` by two-month average.
- The persistent-low view is dynamic: comparison months, threshold, and Top N can be changed from the page without changing the rest of the portal.

## Changes in v2
- Added 19 September HR employees to `hierarchy.xlsx`, mapped to their existing city/regional manager codes so their existing responses resolve to employee profiles.
- Removed the internal test submission for Functional Code `30020897` from both `results.xlsx` (September) and `results_raw.csv`; no assessment result is altered or recalculated for other employees.
- Renamed the user-facing `Locations` view to `Cities` without changing its underlying data structure.
- Updated `Top 5` ordering: current-month score remains primary; when scores tie, employees with a previous-month result are considered first, then the lower previous-month score, then higher improvement, then Functional Code for deterministic ordering.
