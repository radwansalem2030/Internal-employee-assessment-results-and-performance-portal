# Questionnaire Result Portal

Open `index.html` via a static web server / GitHub Pages.

Data sources:
- results.csv
- hierarchy.xlsx
- question_bank.xlsx

Login session: 60 minutes.

Population KPI rule:
- Required population = all Lead/Supervisor hierarchy employees in scope.
- Add any actual result submissions not already in that required population.
- Completed = unique Functional Codes with a result in scope.
- Pending = required Lead/Supervisor employees with no result.
- Functional Code is the unique key.
- Scores and stored answers are not recalculated or modified by the portal.
