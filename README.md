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
