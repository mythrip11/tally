# Tally

A fast, private expense tracker built as a single HTML file. It runs in any modern browser, works offline, and is designed for one-handed use on an iPhone.

## Features

- **One-tap logging.** Large category buttons (Transport, Grocery, Shopping, Food, Personal, Entertainment, Bills, Other) open a number pad. Add an optional note and tap **Log Expense**.
- **Credits.** Log money you receive with the **Log Credit** button. Credits are tracked separately and never count as spending.
- **Two currencies.** Each entry is saved as USD or INR. A switch at the top picks which currency you are viewing. There is no conversion between them.
- **Backdating.** Pick any past date when logging. It defaults to today.
- **Insights.** Total spent, credited and net for the month, change versus last month, daily average, largest expense, projected month-end, spending by category, a daily chart, and a 6-month trend. Optional monthly budgets for each currency.
- **History.** Search notes and amounts, filter by category or credits, and delete entries (with undo).
- **Export and backup.** Export everything as CSV or JSON, and restore from a JSON backup.
- **Optional cloud sync.** Keep multiple devices in step using a private GitHub repository.

## Using it

1. Open the page in Safari on your iPhone (or any browser on a computer).
2. On iPhone, tap **Share → Add to Home Screen** to get a full-screen app icon.
3. Tap a category, enter the amount, add a note if you like, and tap **Log Expense**.

You can also open the HTML file directly in a browser on a computer, but hosting it somewhere (for example GitHub Pages) is the most reliable way to use it on a phone.

## Where your data lives

All data is stored in your browser's local storage on the device you use. Nothing is sent anywhere unless you turn on cloud sync. Clearing Safari's website data or removing the Home Screen icon can erase it, so export a backup now and then (**⚙️ → Export**).

## Cloud sync (optional)

Sync stores your data as a single `data.json` file in a private GitHub repository that you own. Each device merges its changes with that file when the app opens and shortly after each change.

1. Create a **private** repository for your data (tick "Add a README file" so it is not empty).
2. In GitHub, go to **Settings → Developer settings → Personal access tokens → Fine-grained tokens** and create a token:
   - Repository access: **Only select repositories**, choose your data repository only.
   - Repository permissions: **Contents → Read and write**.
3. In the app, open **⚙️**, enter `your-username/your-data-repo` and the token under **Cloud sync**, then tap **Save & Sync now**.
4. Repeat step 3 on each device you want to keep in step.

Notes:

- Treat the token like a password. It is stored only on the device where you enter it.
- Entries added on different devices (even offline) are combined. Deleting an entry on one device removes it on the others.
- Every device should run the same version of the app, otherwise an older version may drop newer fields when it syncs.
- Anyone using the app with their own GitHub repository and token gets their own separate data.

## Backup and restore

- **Export:** ⚙️ → choose CSV or JSON → **Copy** or **Download file**.
- **Restore:** ⚙️ → paste a JSON backup under **Restore from backup** → **Import (merge)**. Existing entries are kept and duplicates are skipped.

## Tech

A single self-contained HTML file with vanilla JavaScript and compiled Tailwind CSS. No build step, no dependencies, no network needed except for optional sync.
