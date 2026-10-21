# Kamus data dashboard

Semua berkas memakai WGS84 (EPSG:4326) dan dihubungkan lewat `cell` (nomor sel grid 5 km, tahap 01).
Tanggal dalam format ISO (YYYY-MM-DD). Status tiap lapisan (DATA / HASIL / ASUMSI / ILUSTRASI) ada di `meta.json`.

| Berkas | Isi |
|---|---|
| `meta.json` | judul, versi, tanggal data, titik asal prakiraan & minggu targetnya, status lapisan, definisi skenario |
| `grid.geojson` | poligon sel 5 km (`cell`) |
| `batas.geojson`, `kabupaten.geojson` | batas provinsi & kabupaten |
| `sel.csv` | per sel: lokasi, kabupaten/kecamatan/desa, luas daratan, rezim api, peluang musiman, kelas bivariat `k` (peluang-keterpaparan), waktu tempuh, titik buta, luas terbakar tahun berjalan |
| `prakiraan.csv` | per titik asal (`data_sampai`) × sel: `st` (sedang terbakar), `p_h1`…`p_hN` peluang terkalibrasi ≥1 hotspot pada minggu ke-h, `keyakinan` (titik asal terbaru) |
| `prioritas.csv` | sel PADAMKAN / AWASI / zona h4 per titik asal |
| `hotspot_mingguan.csv` | jumlah titik per sel per minggu (Senin) tahun berjalan, per sensor & sumber |
| `hotspot_terakhir.geojson` | titik hotspot beberapa minggu terakhir |
| `kabupaten_ringkas.csv` | agregasi per kabupaten: nilai harapan E = Σ p_musim × luas, titik buta, sel per rezim, luas terbakar |
| `verifikasi_kabupaten.csv` | prakiraan beku vs kejadian: sel teramati, harapan sel, tangkapan oleh 10% sel peluang tertinggi |
| `unit_*.{geojson,csv}`, `restorasi_unit.csv` | unit pengelola & prioritas restorasi (bila diizinkan) |
| `kategori_musim.csv`, `pos.csv`, `metrik/` | prakiraan musiman provinsi, pos (asumsi bila belum ada data Daops), metrik model |
| `manifest.json` | daftar berkas, ukuran, md5 |

Lisensi: kode MIT; hasil analisis CC BY 4.0 ("Analisis: Manessa 2026"); data pihak lain mengikuti lisensi sumbernya.
Prototipe riset. Bukan peringatan resmi; rujukan resmi: SiPongi (Kementerian Kehutanan) dan BMKG. Peluang adalah keluaran model statistik pada sel 5 km dan dapat keliru.

Versi: **publik**.
