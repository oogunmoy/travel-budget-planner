# Travel Budget Planner

A single-page travel budget planning tool. Set an annual budget, add trips with multi-stop itineraries, track expenses by category, and export to Excel — all in your browser.

## Features

- **Annual Dashboard** — yearly budget, summary cards (spent, points/credits, out-of-pocket, remaining), progress bar, category breakdown
- **Trip Management** — trips with name, starting/returning location, dates, status (Planned / Booked / Completed)
- **Multi-Stop Trips** — each trip has shared/trip-wide expenses plus individual stops with their own expenses and notes
- **8 Expense Categories** — Flights, Airport Transfers, Transportation, Accommodation, Food, Activities, Travel Prep, Extras
- **Math in Fields** — type `10 + 7.50` in any amount field and it auto-calculates. Click back in to see your formula
- **Points & Credits** — track points used and credits/refunds per trip. Out-of-pocket and remaining budget adjust accordingly
- **Currency Converter** — per-stop local currency and exchange rate. See local amounts alongside USD
- **Notes** — per-year, per-trip, and per-stop notes
- **Year Management** — switch between years (2020+), add custom years
- **Year-over-Year Summary** — compare budget, spending, and trips across all years
- **Search** — filter trips by name, destination, or notes
- **Duplicate Trip** — copy a trip's structure as a template for a new one
- **Drag-and-Drop** — reorder stops within a trip by dragging (or use ▲/▼ buttons)
- **Excel Export** — one workbook with a sheet per year, categories as columns, collapsible stop rows
- **Import from Excel** — import trips from an existing spreadsheet
- **Dark/Light Theme** — toggle between navy/gold dark theme and warm cream light theme
- **Print-Friendly** — clean print layout for paper or PDF
- **Portable Storage** — save data directly into the HTML file for use across devices
- **Unsaved Changes Warning** — browser warns if you try to close with unsaved changes

## Usage

Open `index.html` in any modern browser. No server or build step required.

Or use the live version: **[oogunmoy.github.io/travel-budget-planner](https://oogunmoy.github.io/travel-budget-planner/)**

## How To Use

### Getting Started
1. Open the tool in your browser
2. Set your **Annual Travel Budget** at the top of the dashboard
3. Click **+ Add Trip** to create your first trip

### Adding a Trip
1. Enter the trip name, starting location, and first destination
2. Set the start/end dates and status (Planned, Booked, or Completed)
3. Click **Add Trip** — it appears in the trips list and auto-expands

### Adding Stops to a Trip
1. Expand a trip by clicking on it
2. Click **+ Add Stop** at the bottom of the trip
3. Each stop has its own destination, dates, expenses, and notes
4. Reorder stops by dragging them or using the ▲/▼ buttons

### Entering Expenses
- Each stop (and shared/trip-wide expenses) has 8 category fields
- Just type the dollar amount and move on
- **Math expressions:** type `10 + 7.50 + 15` and it calculates to `$33` when you click away. Click back in to see and edit the formula
- **Currency:** set a stop's local currency (e.g., `EUR`) and exchange rate (e.g., `0.92`). A column appears showing local amounts

### Points, Credits & Out-of-Pocket
- **Points Used ($):** enter the dollar value of points/miles used for the trip (e.g., AMEX points covering a $400 flight)
- **Credits ($):** enter refunds, shared bill reimbursements, etc.
- **Out-of-Pocket** = Total Spent − Points − Credits
- **Remaining Budget** = Budget − Out-of-Pocket (points/credits give you budget back)

### Saving Your Data
- Data auto-saves to your browser (localStorage) on every edit
- Click **💾 Save File** to bake all data into the HTML file itself
- The saved file is fully portable — move it to OneDrive, email it, open on another device

### Exporting to Excel
- Click **📊 Export to Excel** to download `Travel_Budget.xlsx`
- One sheet per year with data, categories as columns
- Trips are rows with stops grouped underneath (expand/collapse with Excel's +/− buttons)

### Importing from a Spreadsheet
- Click **📥 Import** and select an `.xlsx` file
- The tool looks for columns like "Departure Date", "From", "To", "Lodging", "Food", etc.
- Each row becomes a trip. Review and consolidate multi-stop trips after import

### Other Features
- **Search:** type in the search bar above trips to filter by name, destination, or notes
- **Duplicate:** click 📋 Duplicate on a trip to copy its structure with zeroed amounts
- **Year-over-Year:** scroll down to see a comparison table across all years
- **Theme:** click ☀️ Light / 🌙 Dark in the header to toggle
- **Print:** use your browser's print function (Ctrl+P) — the layout auto-adjusts for paper
- **Clear:** click 🗑️ Clear Year to wipe all data for the selected year

## How Storage Works

The tool uses two storage layers:

### 1. localStorage (automatic)
- Saves instantly on every edit
- Tied to your **specific browser** on your **specific device**
- Acts as working memory while you're editing
- Lost if you switch browsers or devices

### 2. Embedded Data (manual save)
- Click **💾 Save File** to write all data into the HTML file itself
- The file becomes fully self-contained — your data travels with it
- This is how you make data portable across browsers and devices

### Scenarios

| Situation | What happens |
|---|---|
| Same device, same browser | Just works — localStorage auto-saves everything |
| Same device, different browser | Data is gone unless you clicked 💾 Save File first |
| Different device | Data is gone unless you clicked 💾 Save File first |
| File on OneDrive / USB / email | Only has data from the last 💾 Save File |

### Portable Workflow

1. Make your edits in the browser
2. Click **💾 Save File** — data is written into the HTML file
3. Move/sync the file wherever you need (OneDrive, USB, email)
4. Open on any device or browser — data loads from the file
5. Edit, then click **💾 Save File** again before closing

**Think of it like a Word doc** — you edit, you save, the file has your work.

### Clearing Data

Click **🗑️ Clear Year** in the header to wipe all data for the selected year. Click 💾 Save File after to persist the cleared state.

## Privacy & Security

**Your data never leaves your device.** There are no servers, no accounts, no analytics, and no telemetry. The tool runs entirely in your browser.

- **No network requests with your data** — the only external request is loading the ExcelJS charting library from a CDN. Your financial data is never transmitted.
- **localStorage** is stored in your browser's profile folder on your machine. Only someone with access to your computer (or browser extensions) could read it.
- **Embedded data** lives as text inside the HTML file itself. It's as private as any file on your disk — whoever can open the file can see the data.
- **No third-party tracking** — no cookies, no fingerprinting, no external scripts beyond ExcelJS.

### Incognito / Private Browsing

localStorage works in incognito but is **wiped when you close the window**. To keep your data:

1. Use the tool normally in incognito
2. Click **💾 Save File** before closing the window
3. The saved HTML file contains all your data
4. Open it next time (even in incognito) and it loads from the embedded data

### Browser Extensions

Browser extensions *can* read localStorage for pages you visit. If this concerns you, rely on the 💾 Save File approach — embedded data doesn't depend on localStorage and is only accessible via the file itself.

## Tech Stack

- Vanilla HTML / CSS / JavaScript (single file, no build step)
- [ExcelJS](https://github.com/exceljs/exceljs) via CDN for Excel export and import
- localStorage + embedded JSON for data persistence
- HTML5 drag-and-drop for stop reordering
