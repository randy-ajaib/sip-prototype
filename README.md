# SIP Nabung Rutin — prototype

Interactive prototype of the SIP (Systematic Investment Plan) creation flow for US stocks.

**Live:** https://randyvarianda.github.io/sip-prototype/

## Flow
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
- Single self-contained HTML file (no build step).
- Prices, returns and popularity are **simulated** placeholder data.
- US market holidays are not yet included in the date calculations.
- Design decisions and rejected options are recorded in [DECISIONS.md](DECISIONS.md).
