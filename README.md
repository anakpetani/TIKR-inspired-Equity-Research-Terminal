# TIKR Clone — Stock Research Platform (Demo Tugas)

Clone sederhana platform riset saham [TIKR](https://www.tikr.com) untuk keperluan demo tugas.
Dibangun sebagai **single-file web app** (HTML + CSS + JavaScript) — 100% offline, tanpa build step, tanpa dependency.

## 🚀 Cara Menjalankan

### Lokal
Double-click `index.html` — langsung jalan di browser modern (Chrome/Edge/Firefox).

### Online (GitHub Pages)
Setelah repo di-push, aktifkan **Settings → Pages → Deploy from branch: `main` / root**.
Aplikasi akan hidup di `https://<username>.github.io/<repo-name>/`.

## ✨ Fitur

| Tab | Fitur |
|---|---|
| **Overview** | Grafik harga interaktif (1M/3M/6M/1Y) + tooltip, deskripsi perusahaan, key statistics (P/E, P/B, EV/EBITDA, ROE, dll.) |
| **Financials** | Income Statement, Balance Sheet, Cash Flow Statement (FY2019–FY2023) dengan toggle *As Reported ↔ Standardized* |
| **Analyst Forecast** | Estimasi konsensus 3 tahun ke depan + price target (Low/Avg/High) & rating Buy/Hold/Sell |
| **Valuation** | DCF builder interaktif — atur growth, margin, tax, WACC, terminal growth → fair value per saham |
| **Peers/Comps** | Tabel perbandingan antar saham yang sudah ditambahkan ke project |

### Fitur Tambah Saham
- Tombol **＋ Tambah Saham** untuk memasukkan perusahaan baru (ticker + harga minimal).
- Financial historis & forecast di-generate otomatis dari input; tersimpan di `localStorage` (persisten).
- Saham bisa di-edit dan dihapus; tombol **Reset** mengembalikan ke data awal.

## 📊 Sumber Data
- **Harga & grafik: REAL & otomatis** — diambil langsung dari Yahoo Finance (ticker `BRPT.JK`, dll.), auto-refresh tiap 30 detik, pembulatan sesuai tick size BEI. Badge **● LIVE** di header menunjukkan status koneksi; tombol **⟳ Refresh** untuk refresh manual.
  - 3 jalur fallback: fetch langsung → CORS proxy (corsproxy.io → allorigins.win) → harga terakhir tersimpan saat offline.
- **Data fundamental (financials, forecast, target harga): dummy realistis** — bukan data real-time dan bukan saran investasi. Bisa diedit lewat fitur Tambah/Edit Saham.
- Saham awal: **PT Barito Pacific Tbk (IDX: BRPT)** — peer lain (TPIA, BREN, dll.) bisa ditambahkan lewat fitur Tambah Saham, harga-nya juga akan live otomatis.

## 🗂️ Struktur
```
index.html   # seluruh aplikasi (HTML/CSS/JS dalam satu file)
```

## 🛣️ Ide Pengembangan Selanjutnya
- Sambungkan data live (Yahoo Finance / API IDX) via backend kecil
- Grafik kontribusi segmentasi pendapatan
- Export tabel ke Excel/CSV
- Mode terang/gelap
