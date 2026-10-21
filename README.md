# BARA — Basis Risiko Api Kalimantan Barat

Dashboard spasial pengelolaan kebakaran hutan dan lahan (karhutla) Kalimantan Barat pada sel grid 5 km, dalam tiga fase:

| Fase | Pertanyaan | Isi |
|---|---|---|
| **Pra** | Di mana bersiap sebelum musim kemarau? | Rezim api, peluang musiman, risiko peluang × keterpaparan, waktu tempuh & titik buta |
| **Saat** | Minggu ini regu ke mana? | Peluang ≥1 hotspot 1–4 minggu ke depan, sel PADAMKAN dan AWASI, titik hotspot terbaru |
| **Pasca** | Seberapa tepat prakiraan, apa yang terbakar? | Prakiraan beku vs kejadian per minggu, tangkapan 10% sel teratas, luas terbakar MODIS MCD64A1 |
| **Simulasi** | Bagaimana kalau…? | Area penting, sel yang sudah ditangani, pembasahan (ilustrasi) |

**Situs:** https://manessa-md.github.io/bara-kalbar/

> Prototipe riset. Bukan peringatan resmi; rujukan resmi: SiPongi (Kementerian Kehutanan) dan BMKG.
> Peluang adalah keluaran model statistik pada sel 5 km dan dapat keliru.

## Isi repositori

```
index.html      halaman dashboard (Leaflet, tanpa server)
data/           data siap-saji hasil s11_dashboard.py (versi publik); kamus data di data/README.md
```

Versi publik hanya memuat data terbuka (FIRMS, MODIS MCD64A1, CHIRPS, ONI/DMI, batas administrasi) dan hasil model.
Prakiraan masuk setelah minggu targetnya lewat (arsip), bukan prakiraan operasional minggu berjalan.

## Memperbarui data

Data dihasilkan oleh pipeline `ScriptPy` (tahap 01–08), lalu tahap 11:

```
python s11_dashboard.py --repo "<folder klon repo ini>"
```

Skrip menulis ulang folder `data/` setelah memeriksa kolom sensitif dan ukuran berkas. Setelah itu lakukan commit dan push.

## Lisensi dan kredit

Kode: MIT. Hasil analisis: CC BY 4.0. Data pihak lain mengikuti lisensi sumbernya.
Analisis: Manessa 2026 · Departemen Geografi, Universitas Indonesia.
