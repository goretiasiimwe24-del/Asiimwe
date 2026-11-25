# FreshBasket Online Grocery (E-Commerce Prototype)

**Course:** MGT3151 E-Business, E-Commerce and E-Governance, Uganda Christian University, Advent 2026
**Project direction:** B (E-Commerce), B2C online grocery
**Group:** [XX]  |  **Live demo:** [paste GitHub Pages URL]

A bounded, functional prototype of an online grocery store. It uses **fictitious data and sandbox payments only**. No real card, mobile-money PIN, OTP, national ID or other sensitive data is collected.

## Minimum end-to-end workflow
Discover/search, select item, cart/order, mock checkout/payment, fulfilment/status, after-sales (return request).

| Role | What they can do |
|---|---|
| Guest | Browse, search, filter and sort 50 products |
| Customer | Cart, sandbox checkout, order tracking (Placed, Packed, Out for delivery, Delivered), return request |
| Admin | Update order stages, approve or reject returns, edit stock, view users and audit log |

## Demo accounts (fictitious)
| Role | Email | Password |
|---|---|---|
| Customer | customer@demo.test | Demo123 |
| Admin | admin@demo.test | Admin123 |

New customers can also register on the Sign in page. Use fictitious details only. Checkout phone numbers must look like `0700000000`.

## Run it
**Option 1 (no install):** download or clone the repository and double-click `index.html`.

**Option 2 (local server):** `python3 -m http.server 8000`, then open http://localhost:8000

**Option 3 (hosted):** GitHub Pages. See `docs/GIT_WORKFLOW.md`.

Use **Reset demo data** on the Admin page to return to the starting state.

## Database (design and server-side path)
`db/schema.sql` creates the MySQL schema (8 tables) and seeds 50 products in 8 categories.
```
mysql -u root -p < db/schema.sql
```
The seeded password hashes are placeholders; replace them with real bcrypt hashes. The demo front end keeps its state in the browser (localStorage) so it runs without a server.

## Repository structure
```
index.html            Prototype (HTML, CSS, JavaScript in one file)
db/schema.sql         MySQL schema and seed data
data/                 Sample fictitious products and users (CSV)
docs/
  TEST_CASES.md       10 test cases with results table
  test-evidence/      Screenshots of test runs (add here)
  SECURITY_PRIVACY.md Threat analysis, controls, backup approach
  ROLE_MATRIX.md      Who did what, per phase
  CONTRIBUTIONS.md    Individual contribution statements
  AI_USE_DECLARATION.md
  GIT_WORKFLOW.md     Branching, commits, pushing, Pages, examiner access
  SUBMISSION_LINKS.txt
VERSIONS.md           Tool and browser versions
package.json          Project metadata and run script (no dependencies)
```

## Testing
See `docs/TEST_CASES.md`. Record the actual result, screenshot name and status for each case, and save screenshots in `docs/test-evidence/`.

## Known limitations
- State is stored in the browser, not on a shared server.
- Demo passwords are visible in the page code. A production build must hash passwords (bcrypt) and use server-side sessions over HTTPS.
- Payments and notifications are simulated.

## Team
See `docs/ROLE_MATRIX.md` and `docs/CONTRIBUTIONS.md`. Commit history shows each member's work.

## License
Educational use. See `LICENSE`.
