# Catatan riset (per 31 Okt 2026)

## Yang berjalan (demo)
**Volspike (VS)**: lonjakan volume M5 (> 2x median 60 candle), masuk searah candle lonjakan, TP 10R, SL >= 0,13% harga,
maks 3 posisi searah, tutup akhir hari UTC. Emas (lewati jam 12-13 UTC dan Minggu) dan NASDAQ (USTEC). Ditambah **Noise** (intraday NASDAQ).
Edge ada di struktur payoff (menang ~26%, 6,7% trade >= 5R memberi ~67% keuntungan), bukan di arah: TP=SL=1R hanya menang 52,4%.

Backtest 2021-07..2026-10, Zero 20 jt, VS emas + VS NASDAQ + Noise risiko 0,4%: median 1 tahun ~x3, DD median ~36%.
Forward test demo baru 3 minggu: cocok dengan backtest per sinyal (korelasi +1,00), tapi 3 minggu terakhir emas -46,6R (rekor terburuk sejak 2021).
Titik cek forward: 200 trade (~pertengahan Des 2026) dan 400 trade (~akhir Jan 2027).

## Sudah dicoba dan NEGATIF (jangan diulang tanpa ide baru)
- Rantai ICT penuh (sweep M5 -> MSS -> displacement -> FVG limit, 144 varian): -0,12R/trade, 5 dari 144 positif di latih+valid (kebetulan).
- CRT/Turtle Soup live: -0,22R. SMC/MSNR/QM 350+ konfigurasi: 0 lolos latih. SNR+trendline H1: 107/158 positif di latih, 12/158 di uji.
- Gradient boosting sebagai penilai trade VS (25 fitur, walk-forward): korelasi skor-R +0,008.
- Fitur ICT + boosting di semua sweep (4.667) dan MSS (1.561): kuartil atas ~0R (impas), tidak profit.
- Filter tren searah (D1/H4): membuang separuh trade dan hasil turun 4-6x; hanya bobot lot (lawan tren x0,5) mengurangi DD ~5 poin.
- Aturan "satu arah" (tolak sinyal berlawanan): memotong median ~35% tanpa menurunkan DD di Monte Carlo.
- Scalping M1-M5 dengan TP kecil (win 57-62%): semua rugi setelah biaya.
- Spot kripto (Indodax): VS buy-only negatif; tren harian BTC+ETH ~ +30%/th, DD 33%, 2025-26 datar.
- Saham IDX tren harian 20 saham: -1,5%/th (beli-tahan +8,5%/th dengan bias penyintas).
- Flip cepat: peluang x10 dalam seminggu ~ 3-5% per percobaan, risiko habis 60-90%.

## Ide yang belum diuji
- Ukuran lot menurut tren (sudah diuji sebagai bobot, hasil sedang), sinyal baru di luar VS, mesin non-emas dengan struktur payoff serupa.
- Edge forward: tunggu data live sebelum mengubah risiko.

## Batas yang disepakati
- Berhenti dan evaluasi bila akun 20 jt turun ke ~12 jt (-40%).
- Risiko VS 0,4% (jauh di bawah Kelly 3%); naik hanya setelah forward test mendukung.
