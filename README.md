# SIP Nabung Rutin — prototype

Interactive prototype of the SIP (Systematic Investment Plan) creation flow for US stocks.

**Live:** https://randy-ajaib.github.io/sip-prototype/

## Flow
0. **Entry points:** the prototype opens on the Saham AS home. The **SIP** shortcut and **Mulai Nabung** (Nabung Rutin section) open SIP;
   **AAPL** (Paling Banyak Dibeli) opens the stock page, where **Beli Rutin** opens the setup with AAPL already picked.
   **Portfolio:** "Yuk, nabung rutin dengan SIP" opens SIP; a stock opens its sheet, where **Beli Rutin** opens SIP with that stock.
   Gear → **Entry point** picks where it starts: **Discovery**, **USDP** or **Portfolio** (`?entry=home|usdp|porto`).
   Gear → **Approach** (`?pick=`) picks the setup flow: Return chips, Search row, **Stock first** or **Robinhood**. The last two share the
   "Beli Rutin X" confirmation page. **Stock first** (default) opens on it straight away with $10 and Setiap bulan filled in (all up front);
   Nominal opens the keypad page, Jadwal the Jadwal Pembelian sheet. **Robinhood** reaches it step by step (Jadwal → Nominal with keypad →
   confirmation; progressive disclosure). In both, **Atur sendiri** sets Harian / Mingguan / Bulanan and an optional end date.
1. **Pilih Saham:** stock list with search, return period (1 / 3 / 5 tahun), category and sort
2. **Nominal Pembelian:** amount sheet with quick chips and keypad
3. **Jadwal Pembelian:** Harian / Mingguan / Bulanan (dates 1–28)
4. **Durasi Nabung:** Sampai dihapus, 1, 3, 6 or 12 bulan
5. **Konfirmasi SIP → SIP berhasil diaktifkan → Rencana SIP**

## Run locally
Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 4317
```

## Notes
- Single self-contained HTML file (no build step). Images live in `assets/` but are also embedded in `index.html`
  as data URIs, so the page works where its folder isn't reachable (e.g. the Claude browser panel's file preview).
  **After adding or changing a file in `assets/`, run `python3 tools/inline_assets.py`** and reference it in code as `A('assets/…')`.
- Prices, returns and popularity are **simulated** placeholder data.
- US market holidays are not yet included in the date calculations.
- Design decisions and rejected options are recorded in [DECISIONS.md](DECISIONS.md).
