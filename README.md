# Formatting

All `json/**/*.json` files are automatically formatted on pull requests by a GitHub Action.  
The Action uses **Prettier** and follows **.editorconfig** (LF, 4 spaces, final newline).

## Opt out
If you don’t want specific files formatted, add them to **.prettierignore**.

## Format manually
Install Node.js (includes npm): https://nodejs.org/en/download

Install deps and run Prettier locally:
```bash
npm ci
npm run format
# or just:
npx prettier --write "json/**/*.json"
```
To check without changing files:
```
npm run format:check
```

# SYNC from TST1

It is good to sync text from tst1 to get the latest changes from the business. Just run sync and check if the changes are correct.

```bash
sh sync
```

A GitHub Action also runs this sync automatically on working days at 08:00 UTC and opens or updates a PR titled `Sync from TST1` when it detects changes.

# Credit-card bullet copy

The redesigned credit-card `scenes.intro` and Express v2 (`/express/v2`)
`responseObject.scenes.creditCard`
support an additive `bulletItems` array. Each item contains `text` and an optional
`description` for the smaller grey detail below it. Consumers may also accept `title`
as the main-text alias. Keep `"description": null` when no detail is displayed so
copy can be added again without changing the JSON structure.

Consumers supporting this format should prefer `bulletItems` and render
`bulletsHeadline` above the Express list. Older consumers can continue using the
credit-card `bullets` string array or Express `detail` text. Keep those fallback
values in sync with the structured copy; do not change their types. Adding,
editing, or removing structured items and descriptions requires no application
change in consumers supporting this format.
