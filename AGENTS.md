# Repository Guidelines

## Stack and Module Map

ShopLedger is a CommonJS Node.js app using Express and body-parser. The browser UI uses plain HTML, CSS, and JavaScript. Application data is stored in `data/db.json`.

- `server.js` configures Express, serves `public/`, and mounts the routers.
- `routes/` handles product and coupon queries, orders, customers and settlements, reports, and pricing preview.
- `lib/` contains order, inventory, pricing, coupon, tax, ledger, invoice, reporting, date, and JSON store logic.
- `config.js` holds shop, tax, inventory, and coupon settings. `public/` holds the UI; `docs/` holds documentation.

## Commands

- `npm start` runs `node server.js` (port 3000 by default; override with `PORT`).
- `npm test` currently exits with `no test specified`; no test framework, build, or lint command is configured.

## Change Rules

- Before changing behavior, write characterization tests that capture the existing behavior and the intended change.
- Change only the module the ticket is about. Avoid unrelated cleanup or edits in neighboring modules.
- Tests must never read or write `data/db.json`; use isolated test data.
- Add no dependencies. Use the existing runtime and packages.
