# M.A.G.I.C. (MFI Analysis, Graphing, Interpolation, & Calculation)

**A fully browser-based web application for analyzing Luminex data files** — including preprocessing, curve fitting, and data visualization. No installation required.

## 🚀 Overview

**M.A.G.I.C.** is a self-contained HTML application that replicates and extends the functionality of a Python-based Luminex analysis pipeline. It includes:

- CSV parsing (raw Luminex exports, standards, cutoffs)
- Preprocessing of data (handling 96- or 384-well formats)
- Curve fitting using **SciPy (via Pyodide)**
- Background correction
- Hook effect detection
- Optional filtering of low-performing standards
- Interactive graphing with **Chart.js**
- Downloadable output files (.csv and .zip)

## 🔧 How to Use

1. Open `LuminexExtractorAnalyser.html` in any modern browser (Chrome/Edge/Firefox).
2. Upload your Luminex `.csv` file.
3. Optionally upload a Standards and/or Cutoff file.
4. Adjust analysis options (background sample, dilution factor, etc.).
5. Click **Preprocess**, then **Run Analysis**.
6. View results in:
   - Graphs (with toggles for log/linear axes)
   - Data tables
   - Summary outputs
7. Download outputs individually or as a ZIP file.

## 📁 Input Files

- **Luminex Data** (`.csv`): Raw export from Luminex software.
- **Standards File** (`.csv`, optional): Two columns – `Sample`, `Concentration`
- **Cutoff File** (`.csv`, optional): Two columns – `Analyte`, `Cutoff`

## 📦 Output Files

- Cleaned data CSV
- Leftover/unused data CSV
- Analyte-specific analysis summaries
- Graphs and fitted curve stats
- ZIP archive of all generated results

## 🧪 Key Features

- Works offline once loaded
- No server-side code — fully runs in-browser
- Automatically detects standards (with option to override)
- Compatible with both 96-well and 384-well formats
- Pyodide integration for native Python curve fitting

## ⚙️ Built With

- [Chart.js](https://www.chartjs.org/) – Interactive graphing
- [PapaParse](https://www.papaparse.com/) – CSV parsing
- [JSZip](https://stuk.github.io/jszip/) – ZIP file generation
- [FileSaver.js](https://github.com/eligrey/FileSaver.js/) – Local file downloads
- [Pyodide](https://pyodide.org/) – Python in WebAssembly (SciPy/Numpy)

## 🧠 Developer Notes

- Pyodide may take a moment to load (~5–10s) on first use.
- Designed for Luminex/Bio-Plex CSV outputs (Milliplex, MagPix etc.).
- If standards are missing or not matched, auto-concentrations will be inferred (e.g., `Standard1`, `Standard2`, etc.).

## 📜 License

MIT License © 2025