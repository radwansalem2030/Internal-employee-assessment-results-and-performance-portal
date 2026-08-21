# Assessment Results Portal

Static GitHub Pages portal for the temporary employee assessment reporting workflow.

## Files
- `index.html` — portal application
- `results.csv` — assessment submissions
- `hierarchy.xlsx` — employee hierarchy, roles and reporting relationships
- `question_bank.xlsx` — 18 questions, correct answers and references

## Rules implemented
- Required-to-test = Position contains **Lead** or **Supervisor**.
- Completion = an eligible Functional Code exists in `results.csv`.
- Lead/Supervisor = own result only.
- City Manager / Regional Manager = recursive descendants using Direct Manager Code.
- Director / Head = full eligible population.
- Product scores are calculated from Q1–Q18 using the Question Bank.
- Employee feedback shows full answer text, not A/B/C/D.
- Pending lists show actual employees grouped by region/governorate/city.
- Non-eligible submissions remain visible only in Data Quality and are excluded from completion KPIs.

## Run locally
Because browsers may block local `file://` fetches, run a small local server:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.

## GitHub Pages
Upload the four files to the repository root and enable GitHub Pages for the branch/folder containing them.

## Important security note
This is a static, temporary reporting portal. The data files are part of the website and are therefore client-accessible to anyone who can access the site. The Functional Code login is an application filter, not secure authentication. For sensitive production use, move the data and authentication to a protected backend.
