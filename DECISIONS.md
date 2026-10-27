# SIP creation — decisions from /sip-prototype

## Main page after picking a stock — Figma 14030:20305 (28 Okt 2026)
- Stock card (bordered): logo, ticker, name, pencil button to change stock; green "Potensi kenaikan …" strip inside the card.
- **Nominal on the page** again: "Nominal pembelian" input + $5 / $10 / $25 / $50 chips (no nominal sheet in this path).
- Jadwal and Durasi as two dropdown rows in one bordered box: "Jadwal nabung rutin — Setiap Hari ⌄", "Durasi — Sampai dihapus ⌄".
- Picking a stock prefills **$10, Setiap Hari, Sampai dihapus**, so the plan is complete straight away (info box + button show).
- Jadwal sheet button reads **Simpan**; Durasi sheet keeps **Selesai**.
- Info box first bullet uses the full day name: "Pembelian pertama pada **Rabu, 28 Okt 2026** …".
- Rencana SIP tab label shows the count: "Rencana SIP (1)".
- Before a stock is picked, the empty state with step icons (Figma 13947:15639) is unchanged.

## Rencana SIP — Figma 14014:19075 (27 Okt 2026)
- Title "Rencana SIP kamu" + note that SIP buys run when the US market opens (21.30 WIB).
- One card per plan: logo + ticker, "Aktif" label, three cells Nominal / Frekuensi (Harian, Mingguan, Bulanan) / Autodebit (next debit date).
- Infobox below the cards: keep enough funds in Rekening Saham AS, link "Deposit Rekening Saham AS" (not wired up).
- Tab label is plain "Rencana SIP" (no count). Empty state kept from earlier rounds; Figma doesn't show one.
- The variant picker pill is gone; the page opens straight on the prototype.

## Initial state + stock list — Figma 13947:15639 and 14006:18615 (27 Okt 2026)
- Hub rows: icon per step (line graphic / dollar / jadwal calendar / calendar), blue once the step is reachable, grey before.
  Titles "Pilih saham", "Tentukan nominal", "Jadwal pembelian", "Durasi"; no subtitles or "… terlebih dahulu" hints.
  Filled rows keep the grey label + bold value, with the blue icon instead of the check badge.
- Tabs restyled as the Figma currency switcher; header #083c96; disabled CTA is primary at 40% opacity.
- No status bar. The whole screen scrolls (header included); the hub footer stays pinned to the bottom.
- Stock list: chip "📅 {N} tahun terakhir"; line "Return saham 1 tahun terakhir" / "Avg. return N tahun terakhir";
  right column "+42,5%" over "dalam 1 tahun" (1 year) or "per tahun" (3 / 5 years, no "/thn" suffix).
- Percentages use a decimal comma everywhere ("+42,5%").
- Nominal sheet: amount chips keep their width when another one is tapped.

## Current direction — Figma 13959:20993 (26 Okt 2026, "use this approach for now")
- Stock row: logo + ticker + name + chevron, no badge; green strip below:
  "Potensi kenaikan **+x%** dalam 1 tahun terakhir" (red "Perubahan harga −x%" when negative).
- Filled rows (Figma 14003:19054): **blue** check badge, small grey label above a bold value:
  - "Nominal pembelian" / **$5**
  - "Jadwal nabung rutin" / **Setiap tanggal 22** (or Setiap Senin / Setiap hari bursa)
  - "Durasi" / **3 Bulan** or **Sampai dihapus** (no extra subtitle)
- Unfilled rows keep the numbered badge with "… terlebih dahulu" hints.
- No "Ubah" labels; chevrons only.
- Info box = bullet list (replaces Money first for now):
  - Pembelian pertama pada **{Sel, 10 Nov 2026}** atau hari bursa berikutnya jika bursa libur,
  - Pembelian selanjutnya setiap **{tanggal 10 | Senin | hari bursa}**.
  - Fixed duration: Pembelian terakhir **{Senin, 11 Jan 2027}**. / Sampai dihapus: Berjalan terus sampai dihapus.
  - Single purchase (1 bulan, monthly): first bullet only, ending with a period.
- Sumber Dana: grey label, bold "Rekening Saham AS" + Autodebit tag.
- Info box and Sumber Dana stay hidden until all 4 steps are filled; disabled CTA always shown.

## Stock list — Figma 13950:15951 (updated, 26 Okt 2026)
- White header "Pilih Saham", search "Cari Saham AS".
- Two chips: **📅 Return {1|3|5} tahun terakhir** (period sheet) and **Semua Kategori** (category sheet: Semua / ETF / Teknologi / Konsumer / Keuangan / Komunikasi).
- Line "Return saham 1 tahun terakhir" with **⇅ Return Tertinggi** link on the right (sort sheet: Return Tertinggi / Terendah / Paling Populer / Nama A–Z).
- Default period: **1 tahun** (as in Figma).
  - 1 tahun: "+42.0%" / "dalam 1 tahun".
  - 3 / 5 tahun: **annualized** "+18.0%/thn" / "rata-rata 3 tahun"; line reads "Rata-rata return per tahun, N tahun terakhir".
  - Not listed long enough: "—" / "Belum N tahun", always sorted last.
- Sort follows the selected period; main-page strip follows it too ("Potensi kenaikan rata-rata +22.0%/thn dalam 5 tahun terakhir").
- Explored and set aside: category tabs, sparkline rows, curated sections.
- Data needed: 3- and 5-year price history per stock (prototype values are simulated).

## Sheets — Figma (26 Okt 2026)
- **Nominal Pembelian** (13972:18937): "Nominal beli {TICKER}", input, chips $5/$10/$25/$50, "Selanjutnya", numeric keypad (1–9, koma, 0, hapus).
  Comma is the decimal separator; max 2 decimals, max 5 digits before the comma; prefilled $10.
- **Jadwal Pembelian** (13994:18551): "Atur Jadwal" option chips Harian/Mingguan/Bulanan (default Harian).
  Mingguan → "Setiap hari" Senin–Jumat (default Senin); Bulanan → "Beli setiap tanggal" grid **1–28** (no 29–31).
  Grey note "Dibeli otomatis setiap …", then "Pembelian pertama {Hari d Mmm yyyy}", button "Selanjutnya".
- **Durasi Nabung** (13972:20316): radio list Sampai dihapus / 1 / 3 / 6 / 12 Bulan, each with "Pembelian terakhir {Hari, d Mmm yyyy}";
  default Sampai dihapus; choice confirmed with **Selesai** (tapping an option no longer closes the sheet).

## Hub info box — Money first (superseded by the bullet list above, kept for reference)
- Direction: **Money first** — lead with how much leaves the account, then the date span.
- Fixed duration (1/3/6/12 bulan):
  - Label "Total yang akan didebit", big total (e.g. **$650**), sub "26 pembelian × $25"
  - Row: Mulai {Sen, 2 Nov 2026} → Selesai {Sen, 26 Apr 2027}
  - Single purchase: one row "Tanggal beli {date}" instead of Mulai → Selesai
- "Sampai dihapus":
  - **No money block for now** — no per-purchase amount and no monthly estimate
  - Row only: Mulai {date} → Selesai "Sampai dihapus"
- Footnote: "Kalau bursa AS libur, dibeli di hari bursa berikutnya."
- Invalid amount: money block hidden, dates stay.
- Incomplete setup: info box and Sumber Dana are **hidden**; only the disabled "Mulai Nabung Rutin" button shows. Both appear once all 4 steps are filled.
- Rejected:
  - Paragraph (original): five facts in one block, total buried at the end.
  - Key facts (label/value list): equal weight on every fact, repeats hub rows.
  - One-liner + "Lihat jadwal": holiday rule hidden until expanded.
  - Date range bar: ticks blur into a solid line for daily plans.
  - Next debit: tallest box; "when" mattered less than "how much".
  - Plain steps: longest copy, repeats Sumber Dana.

## Flow decided in earlier rounds
- Hub with tabs Mulai Nabung / Rencana SIP; steps Saham → Nominal → Jadwal → Durasi, each locked until the previous is done.
- Stock picker: **Sparkline** list (1-year price chart + 1-year return pill, filters Semua / Saham / ETF). Added to Figma as "SIP – Pilih Saham (Sparkline)".
- Nominal: bottom sheet after picking a stock (inline-on-hub version was tried and reverted).
- Durasi: Sampai dihapus / 1 / 3 / 6 / 12 bulan, as its own step.
- Confirmation: Figma "Konfirmasi SIP" sheet (13945:15637) → success sheet → Rencana SIP tab.
- Confirmation summary alternatives explored but not adopted: Sentence, Timeline, Stats + calendar.

## Open questions
- US market holidays are not in the date math yet (e.g. Thanksgiving 26 Nov 2026).
- "12 bulan" weekly = 53 purchases (365 days); confirm whether the end date is exclusive.
- Returns and prices in the prototype are simulated; need real price history.
- Compliance review for showing historical returns next to a buy flow.
