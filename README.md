# Google Play Store Review Scraper

Notebook ini berfungsi untuk melakukan **scraping ulasan (reviews) aplikasi di Google Play Store** menggunakan library [`google-play-scraper`](https://pypi.org/project/google-play-scraper/).  
Dengan scraper ini, kamu bisa mengambil ribuan ulasan aplikasi lengkap dengan rating, tanggal, hingga isi komentar.

## Fitur

- Mengambil ribuan ulasan aplikasi berdasarkan **App ID** (package name).
- Bisa memilih **bahasa ulasan** (contoh: `lang='id'` untuk Bahasa Indonesia).
- Sorting ulasan berdasarkan:
  - Terbaru
  - Rating tertinggi
  - Rating terendah
- Menyimpan hasil scraping dalam bentuk **DataFrame** menggunakan `pandas` (bisa diekspor ke CSV/Excel).

## Dependensi

Pastikan kamu sudah menginstal library berikut:

```bash
pip install google-play-scraper pandas numpy jupyter
```

## Cara Menggunakan

1. Buka notebook `Scaper_From_GooglePlay.ipynb` dengan Jupyter.
2. Ganti variabel `app_id` sesuai aplikasi yang ingin kamu scrape.
   - `app_id` bisa ditemukan di URL aplikasi.  
     Contoh: untuk aplikasi WhatsApp →
     ```
     https://play.google.com/store/apps/details?id=com.whatsapp
     ```
     maka `app_id = "com.whatsapp"`
3. Jalankan seluruh sel notebook.
4. Atur parameter scraping sesuai kebutuhan:
   - `lang='id'` → bahasa ulasan (Indonesia).
   - `count=30000` → jumlah maksimal ulasan yang diambil.
   - `sort=Sort.NEWEST` → urutan ulasan.
   - `filter_score_with=5` → hanya ambil ulasan dengan rating tertentu (opsional).
5. Hasil ulasan akan ditampilkan di notebook, dan bisa diekspor ke CSV/Excel.

## Catatan

- Google Play dapat membatasi jumlah ulasan yang bisa diambil, gunakan parameter `continuation_token` jika ingin melanjutkan scraping lebih banyak ulasan.
- Gunakan data hanya untuk **pembelajaran atau riset pribadi**, karena scraping dapat melanggar Terms of Service Google Play.

## Lisensi

Proyek ini hanya untuk tujuan edukasi dan riset.  
Gunakan secara bijak dan sesuai etika.
