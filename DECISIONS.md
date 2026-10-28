# SIP creation — decisions from /sip-prototype

## Icons — friz-xc/pd-design-artifacts (28 Okt 2026)
- Icons come from `assets/icons` in the PD design-artifacts repo (filled, 24px, recolored to the text color), embedded in `index.html`:
  chevron-left (back), chevron-right, chevron-down (dropdowns), search, check, x (close), calendar, sort-list, filter,
  pencil (change stock), arrow-up-right ("Potensi kenaikan" strip), alert (error messages), backspace (keypad).
- Not in the repo yet, kept as the prototype's own outline icons: **info** (neutral notes and the info box) and the confetti/success art.

## Where the summary lives (28 Okt 2026)
- **Creation page:** no summary at all; the footer is just Sumber Dana + "Mulai Nabung Rutin" (the 3-bullet info box and the one-line "Pembelian pertama" are removed).
  The One sheet keeps its short Figma bullets as live feedback while choosing.
- **Confirmation sheet = the full commitment:** amount + "per pembelian", then Jadwal, Durasi, Pembelian pertama, Pembelian terakhir (or "Sampai dihapus"),
  Jumlah pembelian (14× / ≈ 21× per bulan), **Total dana** ($140 / "Total dana per bulan ≈ $210", emphasized between dividers), Sumber Dana,
  and the note "Jika bursa AS libur, pembelian dilakukan di hari bursa berikutnya." Replaces Jadwal Pembelian / Tanggal Mulai / Jadwal Rutin / Jangka Waktu.
- Explored and dropped for the One sheet summary: Sentence ("Kamu akan beli $10 NVDA setiap…"), Facts box (first/last/count/total), Timeline (date pills).
  Count and total belong on the confirmation sheet, not while choosing.

## Jadwal + Durasi sheets — Figma 14111:21681 (28 Okt 2026)
- Sheet chrome (these two sheets only): 26px top radius, 64px light grabber, 20px title, 24px close icon, content padding 10/16 with 16px gaps, Simpan button with 36px bottom space.
- Jadwal: labels 12px black; option chips 32px, 6px gap, grey fill / blue tint + border when selected; weekly days spelled out (Senin–Jumat).
  Monthly calendar 1–28 in a full-width 7-column grid of 40px cells, selected date = dark blue (#165BCC) circle.
- Note is plain text, grey lead + black bold rest: "Dibeli otomatis **setiap hari bursa, Senin–Jumat.**" / "**setiap hari senin.**" / "**setiap tanggal 22.**"
- **Removed** the divider and "Pembelian pertama …" line from the Jadwal sheet (not in Figma); the first purchase date still shows in the info box on the main page.
- Durasi: 24px radios (blue #3A83F9 on, grey #A9BCC7 off), 14px bold title over 12px grey "Pembelian terakhir {Hari, d Mmm yyyy}"; button **Simpan**.

## Initial state: pick card with return chips — Figma 14082:21972 (28 Okt 2026)
- Replaces the empty "Pilih Saham ›" row. Grey (#f5f5f5) container holding a white bordered card:
  **Pilih saham untuk nabung rutin** (14px) over grey "*Return 1 tahun terakhir" (10px), then a horizontally scrolling chip rail with a white fade on the right edge;
  below the card, row **Lihat semua saham & ETF ›** opens the stock list.
- Chips (32px, 12px text, pill): real brand logos from Figma (`assets/logos/`), ticker, green 1-year return as a whole percent.
  Order NVDA +44%, AAPL +32%, TSLA +24%, AMZN +44%. Simulated 1-year returns for these four were set to the Figma values so the list, strip and chips agree.
  Tapping a chip picks the stock directly (prefills $10, Setiap Hari, Sampai dihapus).
- Same frame restyles the rest of the page: 24px between sections; Nominal input 40px, 4% grey fill, radius 8, 16px bold; $5–$50 chips 24px outlined, 11px;
  Jadwal/Durasi box border #e3e8ea, radius 8, 12px row padding with dividers; footer shadow, "Rekening Saham AS" black, Autodebit tag #e1f2fa / #3a83f9.
- Status bar is back (Figma Android bar, 24px: wifi, signal, battery, 12:30 in Roboto Medium). It stays fixed while the screen scrolls,
  sits above pushed pages, and turns white with dark icons on white pages. Phone frame corner radius 8px (was 44px).
- **Stock first = Any order (28 Okt 2026).** The whole form is visible from the start; the stock-first order is enforced only by the CTA error below.
  - Tried and reverted: **Reveal** (only the stock card + "Pilih Saham" CTA until a stock is picked, then Nominal + Jadwal fade in).
  - Rejected: **List first** (opening on the stock list hid the SIP intro and the Rencana SIP tab behind an extra screen).
  - Still worth exploring, not prototyped: a "Nabung Rutin" entry on each stock's detail page that opens this form with the stock prefilled.
- **CTA "Mulai Nabung Rutin" is always enabled** (as in Figma). Errors are **plain red text** (no icon, no red outline) under the field,
  and **only one shows at a time**, priority stock → nominal → jadwal (a lower error stays hidden while a higher one shows):
  1. no stock → "Pilih saham terlebih dahulu" under the pick card, focus moves to the card; cleared when a stock is picked;
  2. no / invalid nominal → "Masukkan nominal per pembelian" / "Minimal $1…" under the amount input, focus moves to the input;
  3. jadwal / durasi missing → "Pilih jadwal nabung rutin terlebih dahulu" / "Pilih durasi terlebih dahulu" under the Jadwal box,
     or "Tentukan jadwal nabung rutin terlebih dahulu" under the One sheet row; the sheet no longer opens by itself. Cleared on Simpan.
- Amount chips $5–$50 on the page: the selected chip uses the bottom-sheet active option style (blue tint, #3278F0 border, #2264D4 text).
- Open exploration, two independent axes in the picker (URL `?pick=chips|row&sched=split|one`, keys 1–2 / 3–4):
  pick style × schedule style. Schedule **Separated** = Jadwal + Durasi rows; **One sheet** = one row → combined sheet;
  once saved it becomes the summary card from 14111:23123 ("Jadwal Nabung Rutin · Ubah", Frekuensi / Durasi rows; whole card opens the sheet).
  One sheet content (14111:21744): "Frekuensi" chips, day/date picker, "Durasi" as 5 chips in a 3-column grid (no radio list),
  divider, then a grey bullet summary: "Dibeli otomatis **setiap hari bursa**, Senin–Jumat." / "**setiap hari senin**" / "**setiap tanggal 22**"
  and "Pembelian berjalan terus sampai dihapus" or "Pembelian terakhir **Senin, 23 Nov 2026**". Fits without scrolling, even on Bulanan.
- Pick styles: **Return chips** (14082:21972, default) vs **Search row** (14067:20236:
  one bordered row with US-stock icon, "Pilih saham untuk nabung rutin" and a search icon; 16px section spacing)
  vs **One sheet** (14111:21442: Jadwal + Durasi replaced by one row "Tentukan jadwal Nabung Rutin" with calendar icon; schedule starts empty,
  no prefill on stock pick; the row opens one "Jadwal Nabung Rutin" sheet with Atur Jadwal on top and the Durasi radios below, one Simpan;
  once saved the row reads "Jadwal nabung rutin / Setiap tanggal 22 · 3 Bulan"). The combined sheet isn't in Figma yet; built from the two existing sheets.
  With Bulanan selected it is taller than the screen and scrolls inside the sheet.
  CTA error order in this option: stock → nominal → opens the combined sheet.
- Figma "SemiBold" renders as Lato Bold (Google Fonts has no Lato 600).
- Nominal, Jadwal and Durasi stay active before a stock is picked.
- Chip returns are whole percents (Figma); everywhere else keeps one decimal ("+44,0%").
- Explored and set aside (decided from /sip-prototype picker):
  - Round 1, stock-first hero cards: **Tiles** (4 logo tiles), **Popular list** (rows with return), **Categories** (category grid), **Inline search** (search field in the card). All locked the fields below until a stock was picked, which added a step without adding information.
  - Round 2, content and approach: **Copy fixes** (ETFs first, "Return 1 tahun terakhir · bukan jaminan", "Naik +x%" strip, monthly total + disclaimer in the footer),
    **Starter** (prefilled VOO $10/hari plan, one tap to apply), **Risk first** (Stabil / Bertumbuh / Agresif cards with a volatility meter),
    **Budget first** (Rp500 rb / 1 jt / 2 jt per month → per-buy amount at a simulated rate).
  - Open questions carried from round 2, not resolved by this choice: "Estimasi return" and "Potensi kenaikan" read as forecasts; return-sorted chips put volatile single stocks before ETFs;
    the monthly commitment (≈ $210/bulan at $10 daily) isn't shown before the CTA. Check the wording with compliance.

## Initial state — Figma 14067:20236 (28 Okt 2026, superseded by 14082:21972)
- Same layout as the picked state, empty: placeholder card "Pilih Saham ›", "Nominal pembelian" input with **$0** placeholder (no chip selected),
  Jadwal **Setiap Hari** and Durasi **Sampai dihapus** preset from the start.
- Footer: **Sumber Dana always shown**; info box only once the plan is complete; disabled "Mulai Nabung Rutin".
- Picked state label reads "Nominal pembelian {TICKER}". Picking a stock prefills $10 only if no amount was entered yet.
- Durasi sheet button now **Simpan** (all sheets opened from the page use Simpan).
- Replaces the step-icon empty state (Figma 13947:15639).

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
