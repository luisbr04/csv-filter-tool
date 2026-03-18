[README.md](https://github.com/user-attachments/files/26097529/README.md)
# CSV Filter Tool

A fast, browser-based CSV viewer and filter tool built for large files — no installation, no server, no data ever leaves your computer.

---

## Features

- **Streaming file reader** — loads files in 4MB chunks so even 900MB+ CSVs open without freezing the browser
- **Excel-style column filters** — click the `▾` button on any column header to filter by specific values, just like Excel's AutoFilter
- **Smart high-cardinality detection** — columns with more than 5,000 unique values (e.g. product IDs, names) automatically switch to a text-based filter mode to avoid browser slowdowns
- **Virtualized dropdown lists** — only renders the visible rows in the filter dropdown at any time, keeping the UI smooth regardless of how many unique values a column has
- **Multi-level filter panel** — stack multiple filters with AND / OR logic across any columns
- **Dependent filtering** — when you open a column filter, it only shows values that exist given your other active filters (same behavior as Excel)
- **Filter types available:**
  - Contains / Does not contain
  - Exact match
  - Starts with / Ends with
  - Numeric range (min → max)
  - Is empty / Is not empty
  - Remove duplicates
- **Download filtered results** — exports only the filtered rows as a new CSV file
- **100% client-side** — all processing happens in your browser; no data is sent to any server

---

## How to Use

1. Open the tool in your browser
2. Drag and drop your CSV file onto the drop zone, or click to select it
3. Wait for the file to stream in (progress bar shows MB/s and rows read)
4. Use the **column header dropdowns** (`▾`) to filter by specific values
5. Use the **filter panel** at the top to add text/numeric/logic filters
6. Click **▶ Apply** to apply panel filters
7. Click **⬇ Download CSV** to save the filtered result

---

## Supported File Formats

- `.csv` — comma-separated values
- `.tsv` — tab-separated values
- `.txt` — plain text with comma separation

UTF-8 encoding is recommended. Files with BOM or non-UTF-8 encoding may have display issues on the first few characters.

---

## Performance Notes

| File size | Approximate load time |
|---|---|
| ~100 MB | 5–10 seconds |
| ~500 MB | 20–40 seconds |
| ~900 MB | 40–70 seconds |

Times vary based on your CPU and browser. Chrome and Edge generally perform better than Firefox for large file parsing.

The table preview shows the first **500 rows** for performance. The **Download CSV** button always exports all filtered rows.

---

## Hosting on GitHub Pages

1. Rename `csv_filter.html` to `index.html`
2. Create a new **public** GitHub repository
3. Upload `index.html` and this `README.md`
4. Go to **Settings → Pages**
5. Set source to `main` branch, `/ (root)` folder
6. Your tool will be live at `https://your-username.github.io/your-repo-name/`

---

## Privacy

This tool is entirely client-side. Your CSV data is:
- Never uploaded to any server
- Never stored in any database
- Never transmitted over the network
- Processed entirely in your browser's memory and discarded when you close the tab

---

## Browser Compatibility

| Browser | Support |
|---|---|
| Chrome 90+ | ✅ Recommended |
| Edge 90+ | ✅ Full support |
| Firefox 88+ | ✅ Full support |
| Safari 15+ | ✅ Full support |

---

## License

Copyright (c) 2026 Beltran. All Rights Reserved.

This software is proprietary and owned by Beltran. The only permitted use is accessing the tool through its official hosted URL for personal, non-commercial purposes. Copying, distributing, modifying, or using the source code in any form is strictly prohibited without explicit written authorization. See the [LICENSE](LICENSE) file for full terms.
