# Toko online Galeri Florist

Halaman pesan papan karangan bunga bergaya aplikasi (tema biru) untuk dipasang di `https://galeriflorist.id/app/`.
Terpisah dari aplikasi invoice di folder utama.

## Isi

- Katalog dengan pencarian dan filter kategori, keranjang, formulir pesanan papan (tanggal kirim, alamat acara,
  untuk siapa/acara apa, tulisan di papan, nama pengirim), lalu pesanan dikirim ke WhatsApp toko.
- Produk, harga, foto, dan kategori diambil otomatis dari WooCommerce di galeriflorist.id
  (`/wp-json/wc/store/v1/products`, data publik, tanpa login). Salinan terakhir disimpan di browser pengunjung,
  jadi katalog tetap tampil jika website sedang lambat.
- Jika produk tidak bisa dimuat dan belum ada salinan, tampil pesan dengan tombol "Coba lagi" dan WhatsApp.
  Daftar `PRODUK_CADANGAN` di `index.html` bisa diisi sebagai cadangan.

## Pengaturan

Di awal `<script>` pada `index.html`, bagian **PENGATURAN**:

- `TOKO.whatsapp` — nomor WhatsApp admin (sudah diisi 088242815991).
- `TOKO.instagram` — sudah diisi `galerifloristt` (dari deskripsi produk di website).
- `TOKO.ongkir` — aturan ongkir yang tampil di keranjang (dari deskripsi produk: gratis ongkir Makassar & Sungguminasa).
- `TOKO.jamBuka` — opsional.
- `TOKO.website` — alamat website WooCommerce (sudah `https://galeriflorist.id`).

## Status

- Diuji di Chromium (layar HP 360/390 px dan komputer) dengan data tiruan berformat WooCommerce Store API:
  harga diskon, harga "mulai dari" (produk variasi), stok habis, produk tanpa kategori, lebih dari 100 produk,
  dan website gagal dimuat.
- Pemilik sudah membuka `https://galeriflorist.id/wp-json/wc/store/v1/products` dan API itu mengembalikan produk
  (mis. "Papan Hitam Ucapan (Model 2)", Rp 850.000, kategori "Karangan Bunga Papan Hitam", foto 16:9 sampai 3840 px).
  Tampilan disesuaikan dengan bentuk data itu: foto katalog 16:9 dengan `srcset` (ukuran kecil untuk kartu),
  deskripsi per paragraf, nama kategori tanpa awalan "Karangan Bunga".
- Halaman belum dibuka langsung terhadap website asli dari sesi pembuatan (domain diblokir); pengujian memakai data
  tiruan yang meniru bentuk data asli.

## Cara memasang

1. Panel hosting → File Manager → `public_html`, buat folder `app`.
2. Unggah semua file di folder ini ke `public_html/app/`.
3. Buka `https://galeriflorist.id/app/`, lalu tambahkan link-nya di menu WordPress
   (Tampilan → Menu → Tautan Khusus).
