# models/

All the Excel work — the quantitative core of the portfolio.

I keep a hard line between blank and built. `templates/` holds clean, reusable frameworks with the formulas wired up but no company data. `builds/` holds those frameworks once they're populated and working. The reason is simple: the moment you start typing numbers into your only copy of a template, you've lost the template. Separating the two means a pristine starting point is always one folder away.
