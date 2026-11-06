# SIP creation — decisions from /sip-prototype

## Stock first uses the Robinhood confirmation page (Figma 14385:17797, 6 Nov 2026)
- Stock first and Robinhood now share one "Beli Rutin X" page. Stock first shows everything up front (opens on it with $10 and Setiap bulan);
  Robinhood is progressive disclosure (Jadwal → Nominal → the same page).
- Stock first orders the rows Nominal then Jadwal (per Figma); Robinhood keeps Jadwal then Nominal, its step order.
- Stock first's inline amount input is gone: Nominal opens Robinhood's keypad page over the confirmation (Simpan / back);
  Jadwal still opens the Jadwal Pembelian sheet.
- Schedule copy follows the Robinhood page ("Setiap tanggal 22."); Figma 14385:17797 omits the full stop. **Unknown** which is intended.

## Robinhood confirmation per Figma 14380:16024 (6 Nov 2026)
- Rows reordered: **Jadwal Pembelian** first, then **Nominal per pembelian** (schedule-first, matching the flow order).
- Schedule copy is short ("Setiap tanggal 22.", "Setiap hari Kamis.", "Setiap hari bursa Senin - Jumat.");
  an end date goes on its own line ("Berakhir 5 Desember 2026"). Day names stay capitalised (Figma has "kamis").
- Button reads **Konfirmasi Beli Rutin** (was Konfirmasi); editing still reads Simpan Perubahan.

## Review tweaks (6 Nov 2026)
- Robinhood **Atur sendiri** row has no chevron (it opens the sheet like the other options).
- Stock first page button reads **Konfirmasi Beli Rutin** (was Beli Rutin); editing still reads Simpan Perubahan.

## Schedule sheets and Robinhood Atur sendiri row per Figma (6 Nov 2026)
- **Quick amount chips:** the selected chip keeps the grey outline with the light blue fill (no blue border), on both nominal inputs.
- **Jadwal pembelian sheet (14383:15323):** a divider above the summary, which is plain 14px regular black (Figma has semibold; regular per review)
  ("Dibeli otomatis seminggu sekali, setiap hari Kamis.").
- **Atur Jadwal Sendiri (14349:302927):** Harian reads "Beli setiap hari bursa, Senin - Jumat."; Bulanan has a "Beli setiap tanggal" label;
  labels are 13px semibold; the summary is plain 14px regular black.
  The summary only mentions an end date when one is set; "Tanpa batas waktu." is not added (per review).
- **Robinhood Atur sendiri row (14380:15747):** the schedule is the title ("Sebulan sekali, setiap tanggal 22.") with "Berakhir 5 Desember 2026"
  below it when there is an end date, and Ubah on the right.

## Beli Rutin pages, schedule-first Robinhood, Atur Jadwal Sendiri with end date (6 Nov 2026)
- **SIP page (Figma 14148:26959):** title **Beli Rutin Saham AS**, new intro line, and the tabs (**Mulai Beli Rutin** / **Rencana SIP**)
  moved from the blue header to the top of the white sheet as a grey segmented control.
- **Stock first is one page, "Beli Rutin X" (14380:15604):** title with the 32px logo, Nominal (Money input + chips), Jadwal Pembelian
  (a sentence such as "Sebulan sekali, setiap tanggal 22. Berakhir 5 Desember 2026", opens the schedule sheet), Sumber Dana,
  the market-holiday infobox, then the agreement and **Beli Rutin**, which creates the plan. The confirmation sheet and the
  Jangka waktu row are gone; the stock card and its Ubah link too (back returns to the list).
  An empty or invalid amount shows its error when Beli Rutin is tapped. Editing a plan uses the same page with Simpan Perubahan.
- **Jadwal pembelian sheet (14163:77220):** Setiap bulan (default for a new plan, today's date), Setiap minggu, Setiap hari, Atur sendiri.
  Picking a preset clears an end date set under Atur sendiri.
- **Atur Jadwal Sendiri (14349:302305):** Harian | Mingguan | Bulanan segmented control. Harian reads "Beli setiap Hari Bursa, Senin - Jumat.";
  Mingguan picks one weekday; Bulanan shows a 1–31 calendar. Then **Jangka waktu**: Tanpa batas waktu or Tentukan Tanggal Berakhir,
  which shows a date field (the browser's date picker; starts one month after the first purchase, no earlier than it).
  Tanggal 29–31 fall back to the month's last day. The summary line follows Figma ("…setiap tanggal 22. Berakhir 5 Desember 2026").
- **Robinhood is now schedule first (14380:15899 → 14245:90472 → 14380:16024):**
  - **Jadwal Beli Rutin X:** radios on the left — Sebulan sekali (default), Seminggu sekali, Setiap hari, Atur sendiri (chevron);
    once Atur sendiri is set the row shows the schedule sentence with **Ubah**. Infobox, Lanjut.
  - **Nominal Beli Rutin X:** a large centred "$10" with quick chips and the keypad (replaces the Money input card).
  - **Beli Rutin X:** stacked rows (Nominal, Jadwal Pembelian, Sumber Dana), infobox, agreement, **Konfirmasi**. The Jangka Waktu row
    and the "Pembelian pertama" text are gone; the end date is part of the Jadwal sentence. Ubah on Detail Rencana still opens it
    as Ubah Nabung Rutin with Simpan Perubahan.
- Unknown / not in Figma: the edit-mode title of the Stock first page (kept "Beli Rutin X"), and the day picker's look on Mingguan
  for the sheet (reused the grey chips with the blue selected state).

## Robinhood order, in-place edits, fixed stock from USDP / Portfolio (2 Nov 2026)
- **Robinhood is now nominal first** (Figma 14245:90472 → 14245:90649 → 14237:29565):
  - **Tentukan nominal** shows the stock card (no Ubah), then a card with the PD **Money input** (label, grey 40px field, as in Stock first) and quick chips; the keypad types into it (Figma 14245:90472, updated 2 Nov).
  - **Tentukan jadwal** shows a "Beli AAPL $10 · **Ubah Nominal**" card (Figma's "10$" is written "$10"); Ubah Nominal goes back a step.
  - Switching Approach mid-setup maps Atur Rencana ↔ Tentukan nominal.
- **Changing a value on Konfirmasi no longer slides back through the steps.** Nominal / Jadwal open that step over Konfirmasi with a short fade (180 ms in, 150 ms out).
  The button reads **Simpan** and returns to Konfirmasi with the new value. Back discards the change. Ubah Nominal is hidden while editing the schedule.
  Jangka Waktu still opens its sheet.
- **Stock first: the stock "Ubah" link is hidden when SIP was opened for a stock** from USDP or Portfolio (Beli Rutin). From the SIP page's stock list it stays.
  Robinhood has no stock Ubah in either case.
- Escape now does what the page's back button does (exit to USDP / Portfolio, cancel an edit), not always a plain pop.
- **Ubah on Detail Rencana (Robinhood) opens Ubah Nabung Rutin** (Figma 14245:102793): the Konfirmasi page with that title, a divider under Sumber Dana
  and **Simpan Perubahan**. Rows edit in place as on Konfirmasi; saving updates the plan and returns to Rencana Aktif with "Berhasil mengubah SIP".
  The Konfirmasi page title is **Konfirmasi Beli Rutin** (was Konfirmasi Nabung Rutin in Figma).
  Stock first still edits on Atur Rencana. A daily plan reads "Setiap Hari Bursa" and the note "hari bursa, Senin–Jumat" on both pages.
- **Konfirmasi Beli Rutin updated to Figma 14237:29565**: the divider under Sumber Dana now shows on Konfirmasi too (was edit only), and the grey info box
  adds "Jika bursa AS libur, pembelian dilakukan di hari bursa berikutnya." (also on Ubah Nabung Rutin).
- Fix: when Nominal is edited from Konfirmasi, the quick chips and keypad now update the visible input. Before, they updated the Tentukan nominal page still mounted underneath.

## Robinhood approach, Portfolio entry point, USDP alert (2 Nov 2026)
- **Gear "Pilih saham" is now "Approach"**, with a new **Robinhood** option (`pick=rh`, Figma section 14237:28057).
  - Same SIP page, stock list, Rencana Aktif, Atur sendiri and Jangka waktu sheets as Stock first; after picking a stock it's one step per page:
    **Tentukan jadwal Beli Rutin** (14237:28679, radios) → **Tentukan Nominal** (14237:29364, keypad on the page) → **Konfirmasi Nabung Rutin** (14237:29565).
  - Konfirmasi rows go back to their step (Nominal, Jadwal) or open the Jangka waktu sheet. The button (**Buat SIP**, was Lanjut in Figma) stays disabled until the T&C box is ticked, then the plan is created and Rencana Aktif opens with the toast, as in Stock first.
  - Copy: Figma's lowercase "setiap senin" is written "Senin"; weekly / monthly presets use today's weekday / date, as in Stock first.
  - Switching between Stock first and Robinhood mid-setup lands on the other flow's setup page (Atur Rencana ↔ Tentukan jadwal).
  - Not built: the "Nabung Rutin dengan SIP 👍 / Coba Sekarang" banner (14237:86346) in the section, since its placement isn't shown.
- **Entry point → Portfolio** (`entry=porto`, Figma 14237:88544): "Yuk, nabung rutin dengan SIP" → SIP page.
  META, TSLA, NVDA and NFLX open the stock sheet (14237:89186, built in HTML so it works for each stock; the figures are the frame's samples).
  The sheet's **Beli Rutin** opens SIP with that stock; back returns to Portfolio. Lihat Selengkapnya, Take Profit / Stop Loss, Jual and Beli do nothing.
- **USDP** now uses frame 14237:89583: the alert (bell) icon is in the top bar, between search and star. It isn't tappable.

## Entry points: Saham AS home and USDP (2 Nov 2026)
- The prototype now **opens on the Saham AS home** (Figma 14163:78084), not the SIP page.
  - **SIP** shortcut and the Nabung Rutin **Mulai Nabung** button → SIP page (Buat Rencana SIP). SIP's back arrow returns to home.
  - **AAPL** in Paling Banyak Dibeli → **USDP** (14237:86068). **Beli Rutin** → Atur Rencana with AAPL already picked.
    Back returns to USDP; **Ubah** goes to the SIP stock list instead.
- These two screens are **Figma renders with tappable areas** (`assets/entry/`, cut into fixed top, scrolling body and fixed bottom bar),
  not rebuilt in HTML: they're host screens, only there to enter SIP. Other taps on them do nothing.
  Trade-off: the exports are 1x (360px) scaled to 390px, so they're slightly soft on retina screens.
- Coming back to home keeps its scroll position.
- **Gear → Entry point: Discovery | USDP** (`entry=home|usdp`) picks the start screen. USDP starts on the stock page; its back still goes to home.
  Switching it starts over on that screen; other gear changes keep the current screen; Reset (R) starts on the chosen entry point.

## Figma update: SIP page, nominal, Rencana Aktif (2 Nov 2026)
- **Pilih saham (14148:26959):** the category pills are now PD **Chips, Filled M** (grey rgba(0,0,0,.04), 13px, radius 6;
  selected: blue tint, #3278f0 border, #2264d4 text). New category **Dividen Rutin** (KO, PG, MSFT, AAPL, TSM, VOO; derived, Figma shows the label only).
- **Atur Rencana (14143:26715):** the big centred amount is replaced by the **Money input** (14197:28710): left label
  "Nominal per pembelian" (12px bold), a 40px grey field with "$" in text-2 and the amount in black (16px), quick chips 6px below.
  Focus shows a #3278f0 border, an invalid amount a red border. The grey section is #f5f5f5 (ui/page/flat-2).
- **Rencana Aktif (14197:28046):** the "Pembelian berikutnya" calendar icon is 16px.
  The frame still shows a Berhenti GOOGL card; stopped plans stay removed (see 30 Okt), so it isn't added back.

## Icons — friz-xc/pd-design-artifacts (28 Okt 2026)
- Icons come from `assets/icons` in the PD design-artifacts repo (filled, 24px, recolored to the text color), embedded in `index.html`:
  chevron-left (back), chevron-right, chevron-down (dropdowns), search, check, x (close), calendar, sort-list, filter,
  pencil (change stock), arrow-up-right ("Potensi kenaikan" strip), alert (error messages), backspace (keypad).
- Not in the repo yet, kept as the prototype's own outline icons: **info** (neutral notes and the info box) and the confetti/success art.

## Rencana Aktif card — Figma 14197:28046 (30 Okt 2026)
- Stock first, Rencana Aktif → Figma (the default):
  - The card cells are **Nominal · Jadwal · Jangka waktu** ("3 Bulan", "Tanpa Batas", "Sampai Nov 2026") on #f5f5f5.
  - The next purchase moved to a footer line: calendar icon + "Pembelian berikutnya **Hari ini, 30 Okt 2026**" (Hari ini / Besok / weekday).
  - The header keeps the Aktif tag + chevron. The border is rgba(0,0,0,.1).
- Cards are **sorted by next purchase** (today first, as in the frame).
- Figma copy slips not copied: "30 **Oct**" (English) and "Senin, 3 Nov 2026" (3 Nov 2026 is a Tuesday). Real Indonesian dates are used.

## Jadwal view (Figma 14197:27293 + fixes); stopped plans are removed (30 Okt 2026)
- **Stopped plans are removed, not listed.** Berhenti SIP deletes the plan. There are no Berhenti cards, no "Rencana dihentikan" section,
  no stopped detail and no Aktifkan lagi. The GOOGL sample is now an active $10 "Setiap tanggal 1" plan, so Contoh has 5 active plans.
  This supersedes the stopped-plan notes below.
- **Usulan → Layout list → Jadwal** (was "Tanggal"; `lay=date`): a **Jadwal | Rencana** switch under the heading.
  - **Jadwal** is the Figma date list: month headings, a date column (weekday + outlined circle; today blue and filled),
    white plan cards (logo, ticker, "$5 • Setiap Hari", chevron).
  - Fixes on top of Figma:
    - **Daily plans show once per week** on their first purchase day ("Setiap hari bursa · 5× minggu ini") instead of every day.
    - **"Hari ini · $5"** above today's purchases.
    - More space between days (16px) than between cards in a day (8px).
    - Limited to **4 weeks**, ending with "Menampilkan pembelian 4 minggu ke depan."
    - The failed-order tag still shows.
  - **Rencana** is the plan cards with status, last order and progress, so the overview isn't lost.
  - Figma's sample dates were off (1 Nov 2026 is a Sunday); the prototype computes real dates. GOOGL's tanggal 1 rolls to Senin 2 Nov.

## Rencana Aktif list — Figma 14153:38343 (update); sample plans; gear shows only what applies (30 Okt 2026)
- **Rencana Aktif list (Stock first, Figma mode):**
  - The infobox sits under the heading.
  - A black chevron follows the Aktif tag.
  - Stopped plans stay in the list as a compact card (logo, ticker, red **Berhenti** tag #f65858 on #ffe0e0, chevron).
  - The button reads **Tambah Rencana SIP**.
  - The tab count is active plans only. The GOOGL logo is from the frame (`assets/logos-40/GOOGL-glyph.svg`).
- **Stopped plan detail** (tap a Berhenti card; derived, not in Figma): the Berhenti tag and a **Dihentikan** date row
  replace Pembelian pertama / terakhir; the order history runs up to the stop. The only button is **Aktifkan lagi**, which moves the plan back to active.
- **Riwayat order → Contoh** now loads **5 sample plans**, one per case:
  - **NVDA** $25 Setiap Kamis, 3 bulan: last order **Gagal**.
  - **META** $5 Setiap Hari: all Berhasil.
  - **AAPL** $10 Setiap tanggal 15, 6 bulan: one Gagal in the middle.
  - **MSFT** $15 Setiap Senin: **ends in 10 days**.
  - **GOOGL** $5 Setiap Kamis: **Berhenti** 9 days ago.
  - Order dates follow each plan's schedule back from yesterday (or the stop date).
  - **Kosong** removes the samples. Plans you create get no invented history ("Belum ada order").
- **Gear panel** only shows chip groups that change something: **Layout list** shows only with Rencana Aktif → Usulan.

## Gear changes keep the current page (30 Okt 2026)
- Changing any gear option now keeps you where you are: tab, open pages (Atur Rencana, Detail Rencana, stock picker),
  the picked stock, amount and schedule, the category pill and the search text. Created plans already persisted.
- Open sheets close, since their content depends on the option just changed.
- Pages that only exist in one flow are dropped when switching flow: Atur Rencana is Stock first only, the stock picker page is the other explorations only.
  Detail Rencana works in both.
- **Reset (R)** still starts fresh.

## Usulan revised: no invested / value, neutral infobox, list layouts (30 Okt 2026)
- **Removed "Diinvestasikan / Nilai".** SIP buys land in the same holding as stock bought outside SIP, so a per-plan amount or return
  can't be attributed. Each card shows the latest order instead: "Order terakhir **Berhasil** · 23 Okt" (or Gagal, red), or "Belum ada order".
- **Infobox is neutral.** The page doesn't know the balance, so it doesn't judge it:
  "Pembelian 7 hari ke depan **$35**. Pastikan saldo Rekening Saham AS cukup sebelum 21.30 WIB di hari pembelian." + Deposit.
  The mock $20 balance now only drives which sample orders fail.
- **Gear "Layout list"** (Usulan only, `lay=card|row|group`):
  - **Kartu:** the Figma card + last order line + progress bar.
  - **Baris:** one compact row per plan in a bordered list. Logo 40, ticker, "$25 · Setiap Jumat", failed tag, progress; "Berikutnya / Hari ini" on the right.
  - **Grup:** the same rows under **Hari ini / 7 hari ke depan / Nanti** (with counts), by next purchase date.
  - **Tanggal** (added 30 Okt; reference: Google Calendar's schedule view): every purchase in the next **4 weeks**, one row per day that has purchases.
    - Left column: 3-letter weekday (SEN, SEL…) over a big date; **today** is a blue circle.
    - Right: a blue outlined chip per purchase, "Beli NVDA · $25" / "21.30 WIB · Setiap Kamis" + logo; today's chips are tinted.
    - Week separators ("2 – 8 NOV") and a month label when the month changes; days without purchases are skipped.
    - Trade-off: a daily plan shows on every weekday, like a daily event in a calendar.
- These replace the earlier balance check ("Saldo kurang …") and the Diinvestasikan / Nilai line.

## Rencana Aktif "Usulan", Riwayat order samples, gear panel by flow (30 Okt 2026)
- **Gear panel:** with **Stock first** picked, Jadwal / Opsi jadwal / Custom jangka waktu are hidden (they don't affect it).
  Two Stock first chips show instead. The other explorations show their old chips. URL params `ra=figma|plus`, `ord=none|sample`.
- **Riwayat order → Contoh** (`ord=sample`): each plan gets its last 5 scheduled purchases as past orders, 21:30 each.
  - The 3rd most recent is **Gagal**. The most recent is also Gagal when the plan's amount is above the mock balance (**$20**).
  - Detail Rencana's Riwayat order SIP lists them. With **Kosong**, a new plan shows "Belum ada order."
- **Rencana Aktif → Usulan** (`ra=plus`; not in Figma, all copy derived):
  - **Balance check** replaces the generic infobox. It totals the purchases due in the next 7 days and compares them with the mock $20 balance.
    Short: red box "Saldo kurang $10 untuk pembelian 7 hari ke depan. Butuh $30 · Saldo $20 · Deposit". Enough: green "Saldo $20 cukup …".
  - **Header line:** "3 rencana · ≈ $323.25 per bulan · dibeli saat bursa AS buka (21.30 WIB)".
  - **Cards** are sorted by next purchase. "Berikutnya" reads **Hari ini / Besok / Senin, 2 Nov**, and a chevron shows the card is tappable.
  - **Results:** "Diinvestasikan $75 · Nilai $76.58 +2,1%". Value is simulated from the stock's 1-year return over the plan's age. Without orders it reads "Belum ada pembelian".
  - **Order terakhir gagal** tag (red) replaces Aktif when the latest order failed.
  - **Progress** for plans with an end: a bar plus "5 dari 10 pembelian · berakhir 27 Nov 2026", or "**berakhir N hari lagi**" within 14 days.
  - **Rencana dihentikan (n):** stopped plans stay listed (dashed rows) with **Aktifkan lagi**, which restores the plan.
- Card logos: MSFT / META / NFLX / PG now use the Figma 40px logos scaled to 24px instead of the ticker circle (every exploration).

## Konfirmasi dividers, Detail Rencana update — Figma 14141:23739 / 14163:81578 (30 Okt 2026)
- **Konfirmasi:** dividers now group the rows. Jadwal + Jangka Waktu, then Pembelian pertama / terakhir, then Sumber Dana. Applies to every exploration.
- **Detail Rencana:**
  - Rows: **Nominal per pembelian**, Jadwal Pembelian, Jangka Waktu ("3 bulan", lowercase), **Pembelian pertama**, **Pembelian terakhir**
    (only when there is an end; full dates like "30 Oktober 2026"), Sumber Dana. **Tanggal Mulai is removed** here too.
  - **Riwayat order SIP:** a flat list with dividers (no cards). The empty line is just "Belum ada order."
  - Footer buttons are outlined, with icons: **× Berhenti SIP**, **✎ Ubah**.

## Embedded images (30 Okt 2026)
- Stock logos showed as broken frames in the Claude browser panel's file preview, which opens `index.html` without access to `assets/`.
- All 37 images are now embedded as data URIs by `tools/inline_assets.py` (the block between ASSETS:BEGIN / ASSETS:END).
  Code looks them up with `A('assets/…')`, and the three CSS backgrounds (radio on / off, selected date) use `--img-*` variables set from the same map.
- `assets/empty-plan/rect.png` was resized from 1024px to 288px (266 KB → 24 KB; it is drawn at about 143px), keeping `index.html` at about 360 KB,
  under the app's 512 KB preview limit.

## First purchase can be today; Tanggal Mulai off Konfirmasi; Detail Rencana (30 Okt 2026)
- **Stock first:** the first purchase can fall on **today**.
  - If the chosen weekday or date is today or still ahead this week / month, the plan buys then instead of waiting for next week / month.
    For example, Setiap minggu made on Jumat buys this Jumat, and Setiap hari Senin buys this coming Senin.
  - Days and dates already past roll to the next week / month; weekends roll to the next trading day.
  - The other explorations still start tomorrow.
  - Purchases run at the US market open (21.30 WIB). The prototype doesn't model a cut-off time after 21.30.
- **Konfirmasi:** Tanggal Mulai removed; it sat next to Pembelian pertama and read like a second start date. It stays on the detail page.
- **Detail page title:** "Detail Rencana" (was "Atur Rencana", the same as the create page).

## Detail SIP, Berhenti SIP, Ubah — Figma 14163:81578 / 14170:82168 (29 Okt 2026)
- **Rencana Aktif cards:** the three cells stretch to the same height when one label wraps (Figma 14153:38343).
- **Detail SIP** (tap a plan card), titled "Atur Rencana" as in Figma. This replaces my earlier Detail SIP page and its pause:
  - Grey block: stock card with Aktif tag, then Nominal / Jadwal Pembelian / Jangka Waktu / **Tanggal Mulai** (the day the plan was created) / Sumber Dana.
  - **Order SIP:** one card per executed purchase ("Beli NVDA", amount, Berhasil (green) / Gagal (grey) tag, date and time).
    A plan made in this session has not bought anything yet, so the list shows
    "Belum ada order. Pembelian pertama **Kamis, 5 Nov 2026**." instead of invented history.
  - Footer: two grey buttons **Berhenti SIP** | **Ubah**. Jeda / Lanjutkan SIP is removed (not in Figma).
- **Rencana Aktif empty state — Figma 14162:26213:** same illustration and copy; the button now reads **Buat Rencana SIP** with the auto-plan icon (was "Mulai Nabung"), back to the stock list. Stock first only.
- **Berhenti Nabung dengan SIP** sheet: "Setelah berhenti, Ajaib tidak akan menarik saldo untuk pembelian aset ini."
  Buttons **Kembali** (grey) | **Berhenti SIP** (blue). Confirming removes the plan and returns to Rencana Aktif.
- **Ubah** (not drawn in Figma; derived):
  - Opens Atur Rencana prefilled with the plan's amount, jadwal and jangka waktu. The stock can't be changed (no stock Ubah link).
  - Lanjut → Konfirmasi, where the CTA reads **Simpan Perubahan** and Tanggal Mulai keeps the original date.
  - Saving updates the plan in place and shows "Berhasil mengubah SIP".

## Stock first — Figma section 14141:22641 "Approach - Stock first" (29 Okt 2026)
Applies to the Stock first exploration only; the other explorations keep their copy.
- **"Today" is the real current date** (it was pinned to Selasa, 27 Okt 2026). Setiap minggu = today's weekday (Senin on a weekend),
  Setiap bulan = today's date, including 29–31 (shorter months use their last day; a weekend date rolls to the next trading day).
  All dates in every exploration now move with the real date.
- **Stock first is now the default** when the URL has no `?pick=` (gear panel: Pilih saham → Return chips / Search row still available).
- **Header / intro:** "SIP Saham AS" and "Lewat SIP (Systematic Investment Plan), beli saham AS otomatis dengan nominal tetap, sesuai jadwal pilihan."
  - Tabs: **Buat Rencana SIP / Rencana Aktif (n)**.
  - The initial frame says "SIP Aktif" for the second tab, but the Riwayat frames say "Rencana Aktif (1)". I used the latter, which matches its heading.
- **List:** title "Pilih saham", search "Cari kode atau nama, misal AAPL".
- **Atur Rencana** (was Atur Nabung Rutin):
  - "Nominal per pembelian" (no ticker).
  - Rows: "Jadwal pembelian — Setiap hari bursa / Setiap hari Selasa / Setiap tanggal 27" and "Jangka waktu — Tanpa batas waktu".
  - Infobox: "Pembelian pertama **Rabu, 28 Okt 2026**. Selanjutnya dibeli otomatis setiap **hari bursa**."
  - CTA **Lanjut**.
- **Jadwal pembelian:**
  - Options: Setiap hari / Setiap minggu / Setiap bulan / Atur sendiri. Sebulan 2 kali is gone.
  - Setiap minggu = **today's weekday** and Setiap bulan = **today's date** (sticky notes: "Once a week, today" / "today date").
  - Notes: "Dibeli otomatis **seminggu sekali**, setiap hari Selasa." / "… **sebulan sekali**, setiap tanggal 27."
  - The first purchase is still the next matching day after today, so a weekly-today plan starts next week.
- **Atur Jadwal Sendiri — 14163:77431 / 77671** (replaces Custom Jadwal):
  - Mingguan | Bulanan tabs. Mingguan: "Beli setiap" + a Senin–Jumat radio list, **one day**. Bulanan: "Beli setiap tanggal" + 1–28 grid, **one date**.
  - Note: "Dibeli otomatis seminggu sekali, **setiap hari Selasa.**"
  - The every-N and last-weekday rules are no longer offered; the engine still supports them.
- **Jangka waktu — 14148:28280:** Tanpa batas waktu / 1 / 3 / 6 / **9 bulan** / **1 tahun**. Labels "Tanpa batas waktu", "1 Tahun".
- **Konfirmasi — 14141:23739 / 23602 / 23669:**
  - Weekly reads "Setiap hari Kamis".
  - **Tanggal Mulai** is back. It shows **today** (the day the plan is created, e.g. "27 Oktober 2026"), next to Pembelian pertama.
    Figma's "25 November 2025" is a placeholder.
  - Figma's daily variant shows Pembelian terakhir with Tanpa batas waktu; I kept it hidden when there is no end.
- **Rencana Aktif — 14153:38170 / 14162:26213 / 14153:38343:**
  - Heading "Rencana Aktif", subtitle "Pembelian dilakukan saat bursa AS buka di hari yang dijadwalkan."
  - Cells: Nominal / **Jadwal** / **Pembelian Berikutnya**.
  - Infobox "Pastikan saldo Rekening Saham AS cukup sebelum jadwal pembelian.", button **Buat Rencana SIP**, alert "Berhasil membuat SIP".

## Atur Nabung Rutin polish — Figma 14143:26715 (29 Okt 2026)
- The white Jadwal / Jangka waktu section has 12px rounded top corners on the grey page and fills down to the footer.
- On this page the row label reads **Jangka waktu** (sentence case, like "Jadwal nabung rutin"); row values are black.
- The footer's "Sumber Dana" label is 12px.
- Pilih Tanggal in Custom Jadwal now takes **one date only**.

## Riwayat SIP card — Figma 14153:38343 (29 Okt 2026)
- Card cells are now **Nominal · Jadwal Pembelian · Selanjutnya** (they were Nominal · Frekuensi · Autodebit).
  Jadwal shows the actual schedule ("Setiap Rabu", "Setiap tanggal 1 & 15", "Setiap Hari"); long ones wrap. Selanjutnya is the next purchase ("—" when paused).
- This replaces my extra schedule line under the cells and the header chevron (not in Figma).
  The card is still tappable and opens Detail SIP.
- Cell labels, the subtitle and the infobox text use the lighter Figma greys (48% / 65% black).

## Durasi → Jangka Waktu (29 Okt 2026)
- Every on-screen **Durasi** now reads **Jangka Waktu**, in every exploration. That covers row and field labels, the "Jangka Waktu Nabung" sheet title,
  confirmation and Detail SIP rows, the error "Pilih jangka waktu terlebih dahulu", the guided CTA "Pilih Jangka Waktu", and the gear panel label.
- Older entries in this file still say Durasi, describing what was built at the time.

## Riwayat SIP improvements — beyond Figma 14067:20096 (29 Okt 2026)
- Proposed UX, not in Figma yet; all copy here is **derived**. Applies to the Riwayat / Rencana SIP tab in every exploration.
- **Plan card:**
  - The whole card is tappable, with a chevron next to the status tag.
  - A line under the cells names the real schedule and duration ("Setiap Senin & Kamis · 3 Bulan"); the Frekuensi cell alone hid custom schedules.
  - Every-N schedules read "Tiap 2 minggu" in the Frekuensi cell.
- **Detail SIP page:**
  - Logo, ticker, name, Aktif / Dijeda tag, nominal "per pembelian".
  - Rows: Jadwal Pembelian, Durasi, Pembelian berikutnya, Pembelian terakhir (when there is an end), Sumber Dana.
  - A "3 pembelian berikutnya" list with dates + amount and the bursa-libur note.
  - **Jeda SIP / Lanjutkan SIP** (outline) and **Hentikan SIP** (red text).
- **Jeda:** the tag turns grey "Dijeda", Autodebit shows "—", and the detail page replaces the upcoming list with
  "SIP sedang dijeda. Tidak ada autodebit sampai kamu lanjutkan lagi."
- **Hentikan:** a confirmation sheet "Hentikan SIP?" explains that no more autodebit happens and the stock already bought stays.
  On confirm the plan is removed and the app returns to Riwayat (the empty state if it was the last plan).

## Stock first: Konfirmasi footer, Buat SIP, Riwayat SIP (29 Okt 2026)
- **Atur Nabung Rutin — Figma 14143:26715 (updated):** the footer adds an infobox above Sumber Dana:
  "Pembelian awal **Rabu, 28 Okt 2026** dan akan ditagih setiap **hari Rabu**." It updates live from the schedule.
  The CTA reads **Konfirmasi** (it was Mulai Nabung Rutin).
- **Konfirmasi SIP:** the CTA reads **Buat SIP** (it was Beli Otomatis). This applies to every exploration.
- **Riwayat SIP — Figma 14067:20096:**
  - Stock first: after **Buat SIP**, the app lands on the Riwayat SIP tab instead of the success sheet.
    A green "Berhasil membuat SIP" alert sits above a sticky **Buat SIP baru** button (back to the list); it hides after 5 s or on ×.
  - Plan cards use the 24px brand logos where available, in every exploration.
  - Tab names stay **Buat SIP Baru / Riwayat SIP** from 14148:26959. This frame still shows Mulai Nabung / Rencana SIP (1).
  - The other explorations keep the success sheet.

## Confirmation without totals — Figma 14141:23531 (29 Okt 2026)
- Removed **Jumlah pembelian** and **Total dana** (and "Total dana per bulan") from Konfirmasi SIP for now. This applies to every exploration.
- Rows now: **Jadwal Pembelian**, Durasi, Pembelian pertama, Pembelian terakhir (only when there is an end; none for Sampai dihapus),
  a divider, then Sumber Dana.
- Not copied: Figma's "Tanggal Mulai 25 November 2025" row. It duplicates Pembelian pertama and shows a past date.

## Stock first — new exploration (29 Okt 2026)
- Gear panel **Pilih saham → Stock first** (`?pick=first`, key 0). It uses its own Figma sheets, so the Jadwal / Opsi jadwal axes don't apply to it.
- **Initial state — Figma 14148:26959:** the tab card reads **Buat SIP Baru / Riwayat SIP**. The white panel holds the stock list itself:
  "Pilih saham untuk nabung rutin", a "Cari Saham AS" search, category pills, then rows (40px logo, ticker, name, chevron; no return).
  - Pills are **Trending · Fundamental · AI & Tech · ETF Pilihan**. Figma's two "Category 5" placeholders are left out.
  - Which stock sits in each category is **derived**. Trending follows the Figma order: NVDA, AAPL, META, MSFT, AMZN, NFLX, PG, then the rest.
  - Logos come from the Figma frame (`assets/logos-40/`). Stock without one falls back to the ticker circle.
- **Atur Nabung Rutin — Figma 14143:26715:** opens when a stock is tapped.
  - Grey top: a stock card with **Ubah** (back to the list), "Nominal Nabung Rutin **NVDA**", a 36px centered $ input and $5/$10/$25/$50 pills (default $10).
  - Then the Jadwal nabung rutin / Durasi dropdown rows (Setiap Hari / Sampai dihapus) and the usual Sumber Dana + Mulai Nabung Rutin footer.
  - Figma's label says "AAPL" on an NVDA card; the prototype uses the selected ticker.
- **Jadwal pembelian — 14148:27475:** the preset radio list. Here **Custom** opens a second sheet instead of expanding inline.
- **Custom Jadwal — 14148:27684 / 28056 / 28175** (back arrow returns to the preset list):
  - "Beli setiap **[1] [Hari ▾]**". The number accepts 1–12; empty or out of range disables Simpan.
  - Unit **Hari:** every N trading days.
  - Unit **Minggu:** "Ulangi setiap" Senin–Jumat chips, more than one allowed (Figma's Filled chips = 0..many). Every N weeks; the first week with a match counts as week 1.
  - Unit **Bulan:** **Setiap Tanggal {today}** · **Setiap {today's weekday} akhir bulan** (the last one of each month) · **Pilih Tanggal** (date grid, **one date only**; tapping another date moves the selection). Every N months.
  - The note names the result and the first purchase ("Dibeli otomatis setiap Senin & Kamis, 2 minggu sekali, mulai Kamis, 29 Okt 2026.").
  - The today-based chips use the prototype's today (27 Okt, Selasa); Figma shows 29 / Kamis because it was drawn on 29 Okt.
- **Durasi Nabung — 14148:28280:** radios Sampai dihapus / 1 / 3 / 6 / 12 Bulan; no Custom and no subtitles.

## Preset jadwal — Figma 14148:27475 (29 Okt 2026)
- The Jadwal sheet (both One sheet and Separated) was too much at once: 3 frequencies + a 5-day row or 28-date grid + 6 durasi chips.
- **Preset** (new default, gear panel "Opsi jadwal", `&opts=preset|full`, keys 8–9): a radio list from Figma,
  title "Jadwal pembelian", 24px radios, 12px to the label, 16px between rows, note line under the list:
  - **Setiap hari:** every trading day, "Dibeli otomatis setiap hari bursa, Senin–Jumat."
  - **Seminggu sekali:** the weekday of the first trading day after today (Rabu for 27 Okt), so the first buy is as soon as possible.
  - **Sebulan sekali:** that same day's date, capped at 28 (tanggal 28).
  - **Sebulan 2 kali:** tanggal 1 & 15.
  - The note always names the day or date the preset picked ("Dibeli otomatis setiap hari Rabu.").
  - Preset defaults (soonest day, 1 & 15) are **derived**, not from Figma or data; swap them for the most-used schedules when known.
- **Custom (not in Figma yet, my proposal):** opens inline under the Custom radio, indented to the label:
  Mingguan / Bulanan, then **one or more** weekdays (Sen–Jum) or dates (1–28), as checkboxes.
  It starts from whatever was selected before (e.g. 1 & 15 after Sebulan 2 kali). The note adds the monthly count ("setiap hari Senin & Kamis, ±9× per bulan").
  With nothing selected: "Pilih minimal satu hari / tanggal." and Simpan is disabled. Reopening restores Custom and its picks.
  Labels everywhere read "Setiap Senin & Kamis" / "Setiap tanggal 1 & 15"; purchase dates, counts and totals handle several days a week or dates a month.
  Open question: cap the number of picks (e.g. max 4 dates a month)?
- Durasi in Preset mode: **Sampai dihapus · 6 Bulan · 12 Bulan · Custom** (1 and 3 bulan are still reachable through Custom).
- **Semua opsi** keeps the previous sheet unchanged for comparison.

## Rencana SIP empty state, custom Durasi, prototype options (29 Okt 2026)
- **Rencana SIP empty state — Figma 14115:24269:** "Montase / Not Found" illustration (225×150, Figma layers in `assets/empty-plan/`),
  "Belum ada rencana nabung rutin" (14px bold) + "Yuk, mulai nabung rutin dengan SIP dan tingkatkan aset investasimu secara konsisten." (12px, #445B70),
  full-width **Mulai Nabung** button back to the form; block centred in the white area. Plan cards (14014:19075) unchanged once plans exist.
- **Durasi: Custom** as a 6th option (fills the 3×2 chip grid in One sheet; 6th radio in the separate Durasi sheet).
  Choosing it shows "Berakhir pada" + a month calendar (Sen–Min, ‹ › month navigation). Allowed range: the first purchase date up to 5 years out;
  earlier dates and months are disabled. Default selection: first purchase + 3 months. The last purchase is the last buy day on or before the chosen date.
  Labels: row / card "s.d. 15 Jan 2027", confirmation "Durasi: Sampai 15 Jan 2027", radio subtitle "Pembelian terakhir …" ("Pilih sendiri tanggal berakhirnya" before choosing).
  With the calendar open, the One sheet is taller than the screen and scrolls; the summary bullets sit below the calendar.
- **Custom durasi picker — open exploration** (gear panel "Custom durasi", `&cal=calendar|month|count`, keys 5–7; default **Month**):
  - **Calendar:** full month grid, day precision (above). Many taps for far dates; the One sheet scrolls about 75px.
  - **Month:** "Sampai bulan", ‹ year › + 12 month chips (4×3); ends on the last purchase in that month; live "35× pembelian · total $350".
    Labels "s.d. Jun 2027" / confirmation "Sampai Juni 2027". One sheet overflows by about 10px.
  - **Count:** "Jumlah pembelian", [−] 24× pembelian [+] + quick 10× / 25× / 50× / 100× (hidden when over the 5-year max);
    ends on the Nth purchase; live "Berakhir Senin, 30 Nov 2026 · total $240". Labels "24× pembelian" / "24 kali pembelian".
    Keeps the count when the schedule changes (end date moves). Fits without scrolling.
- **Prototype options** collapse into a gear button (top right); tapping it opens the options as an overlay panel
  (Pilih saham / Jadwal + Reset). It closes on outside tap or Escape; keys 1–4 and R still work.

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
