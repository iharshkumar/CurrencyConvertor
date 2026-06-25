# Currency Convertor

Simple client-side currency converter that fetches exchange rates from the `@fawazahmed0/currency-api` CDN and displays converted amounts.

## Files
- `index.html` — main page with UI
- `style.css` — styles
- `codes.js` — mapping of currency codes to country codes (`countryList`)
- `script.js` — application logic (populates selects, fetches rates, updates UI)

## Setup
No build step required. Open `index.html` in a browser (Chrome/Edge/Firefox).

## Usage
1. Enter an amount.
2. Choose a source currency and a target currency.
3. Click "Get Exchange Rate" to fetch latest rate and display the converted amount.

## Notes about the API
- The app uses the CDN endpoint: `https://cdn.jsdelivr.net/npm/@fawazahmed0/currency-api@2024-03-06/v1/currencies/{base}.json`
- The response returns a JSON object with currency codes as keys and rates as values. The script requests the `{base}.json` file and looks up the target currency key.

## Troubleshooting
- If the console shows a 404 for a currency pair, try converting a different base currency (e.g., `USD` or `EUR`). Some base files may be missing on the CDN.
- If you see `Unexpected token` when parsing JSON, the server returned an error page — the script now checks `response.ok` and displays a friendly message in the UI.
- Ensure `codes.js` is loaded before `script.js` (it's already included before `script.js` in `index.html`).

## Contributing
Fix bugs or improve UI by editing the files in this folder and reloading the page.

## License
MIT
