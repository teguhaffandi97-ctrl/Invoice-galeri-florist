# Toko online Galeri Florist

Halaman pesan bunga bergaya aplikasi (tema biru) untuk dipasang di `https://galeriflorist.id/app/`.
Terpisah dari aplikasi invoice di folder utama.

## Isi

- Katalog dengan pencarian dan filter kategori, keranjang, formulir pengiriman (tanggal, alamat, ucapan kartu),
  lalu pesanan dikirim ke WhatsApp toko.
- Produk, harga, foto, dan kategori diambil otomatis dari WooCommerce di galeriflorist.id
  (`/wp-json/wc/store/v1/products`, data publik, tanpa login). Salinan terakhir disimpan di browser pengunjung,
  jadi katalog tetap tampil jika website sedang lambat.
- Jika produk tidak bisa dimuat dan belum ada salinan, tampil pesan dengan tombol "Coba lagi" dan WhatsApp.
  Daftar `PRODUK_CADANGAN` di `index.html` bisa diisi sebagai cadangan.

## Pengaturan

Di awal `<script>` pada `index.html`, bagian **PENGATURAN**:

- `TOKO.whatsapp` — nomor WhatsApp admin (**wajib**, belum diisi).
- `TOKO.jamBuka`, `TOKO.instagram` — opsional.
- `TOKO.website` — alamat website WooCommerce (sudah `https://galeriflorist.id`).

## Status

- Diuji di Chromium (layar HP 360/390 px dan komputer) dengan data tiruan berformat WooCommerce Store API:
  harga diskon, harga "mulai dari" (produk variasi), stok habis, produk tanpa kategori, lebih dari 100 produk,
  dan website gagal dimuat.
- **Belum diuji dengan website asli** galeriflorist.id: domain itu diblokir dari sesi pembuatan.
  Perlu dicek: apakah situsnya memakai WooCommerce, dan apakah `https://galeriflorist.id/wp-json/wc/store/v1/products`
  mengembalikan daftar produk.

## Cara memasang

1. Panel hosting → File Manager → `public_html`, buat folder `app`.
2. Unggah semua file di folder ini ke `public_html/app/`.
3. Buka `https://galeriflorist.id/app/`, lalu tambahkan link-nya di menu WordPress
   (Tampilan → Menu → Tautan Khusus).
