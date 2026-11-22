# Repository Guidelines

## Stack

ShopLedger is a Node.js application using Express 4 and `body-parser`. The browser interface is plain HTML, CSS, and JavaScript. It stores application state in `data/db.json`; there is no database service, frontend framework, build system, test framework, or configured linter.

## Module Map

- `server.js` creates the Express app, serves `public/`, mounts routes, and serves invoice HTML.
- `routes/` contains the product, order, customer, and report API handlers.
- `lib/` contains order, inventory, pricing, coupon, tax, ledger, invoice, date, report, and JSON-store logic.
- `config.js` contains shop, tax, inventory, and coupon settings.
- `public/` contains the UI; `data/db.json` is the local data file.

Keep changes limited to the module the ticket is about. Follow existing CommonJS and plain browser JavaScript patterns, and add no dependencies.

## Commands

- `npm start` starts the Express app on `PORT`, or port `3000` by default.
- `npm test` currently exits with an error because it is a placeholder, not a test suite.
- There is no build command or lint command configured.

## Change and Test Rules

Before changing behavior, write characterization tests that capture existing behavior and the intended change. The repository has no test framework today; keep tests dependency-free. Tests must never read from or write to `data/db.json`; use isolated test data instead. Do not modify unrelated modules as part of a ticket.
