# trading-lab

Ruang eksplorasi riset bot trading (XAUUSD, indeks, kripto). Terpisah dari repo produksi `trading-desk`.

## Aturan
- Akun **demo saja**. Tidak ada uang asli, tidak ada eksekusi order dari sesi ini.
- Jangan masukkan token, password, API key, atau nomor akun ke repo.
- Data harga besar (M1 beberapa GB) tidak di-commit. Ambil ulang dari MetaTrader 5 atau Yahoo Finance.
- Angka harus bisa ditelusuri ke skrip. Tanpa angka karangan. Laporkan hasil negatif apa adanya.
- Balas dalam Bahasa Indonesia, ringkas.

## Protokol riset
- Pembagian kronologis: latih 2021-07..2023-12, valid 2024-01..2025-06, kunci 2025-07..2026-10.
- Pilih parameter di latih, cek di valid, buka kunci sekali. Semua varian dilaporkan, bukan hanya yang terbaik.
- Biaya akun Zero: komisi + slip ~ $0,21/oz emas (round trip), USTEC Rp22.746/lot. Tanpa lookahead.
- Monte Carlo: blok 4 minggu dari data sejarah; hitung juga skenario edge dipotong 50%.

Hasil dan ide yang sudah dicoba: lihat `NOTES.md`.
