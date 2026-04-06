# Travel Budget Planner

A single-page travel budget planning tool. Set an annual budget, add trips with multi-stop itineraries, track expenses by category, and export to Excel — all in your browser.

## Features

- **Annual Dashboard** — yearly budget, summary cards (spent, points, out-of-pocket, remaining), progress bar, category breakdown
- **Trip Management** — trips with name, starting/returning location, dates, status (Planned / Booked / Completed)
- **Multi-Stop Trips** — each trip has shared/trip-wide expenses plus individual stops with their own expenses and notes
- **8 Expense Categories** — Flights, Airport Transfers, Transportation, Accommodation, Food, Activities, Travel Prep, Extras
- **Math in Fields** — type `10 + 7.50` in any amount field and it auto-calculates on tab/click away
- **Points Tracking** — track points/credits used per trip, see out-of-pocket vs total spent
- **Notes** — per-year, per-trip, and per-stop notes
- **Year Management** — switch between years (2020+), add custom years
- **Excel Export** — one workbook with a sheet per year, categories as columns, trips with collapsible stop rows
- **Portable Storage** — save data directly into the HTML file for use across devices

## Usage

Open `index.html` in any modern browser. No server or build step required.

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
- [ExcelJS](https://github.com/exceljs/exceljs) via CDN for Excel export
- localStorage + embedded JSON for data persistence
