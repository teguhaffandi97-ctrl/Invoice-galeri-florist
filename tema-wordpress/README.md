# Tema biru untuk galeriflorist.id (WordPress)

Website memakai tema **Razzi**, halaman depan dibuat dengan **Elementor**, tombol "Pesan Sekarang" dari plugin
**Click to Chat**, cache **LiteSpeed**. Logo tema dan CSS Tambahan tidak bisa diubah lewat REST API, jadi dipasang
dari dashboard.

## Cara memasang (±5 menit)

1. **Logo** — Tampilan → Sesuaikan → Header → Logo: unggah `logo-header-untuk-latar-biru.png`.
   Jika ada pengaturan logo terpisah untuk HP (Header Mobile), ganti juga dengan file yang sama.
2. **Ikon situs** — Tampilan → Sesuaikan → Identitas Situs → Ikon Situs: unggah `ikon-situs-512.png`.
3. **Warna** — Tampilan → Sesuaikan → CSS Tambahan: tempel seluruh isi `css-tambahan-tema-biru.css`, lalu Terbitkan.
4. Jika belum berubah: di bilah admin atas, LiteSpeed Cache → Purge All, lalu muat ulang halaman.

Untuk kembali ke tampilan lama: hapus kode di CSS Tambahan dan pasang lagi logo lama.

## Isi CSS

Header, menu samping HP, dan footer biru tua; tombol utama kuning; tombol "Pesan Sekarang" dan "Lainnya" biru;
strip keunggulan dan kotak ajakan bergradasi biru; FAQ bertema biru; warna utama Razzi (`--rz-color-primary`) biru
yang sama. Juga memperbaiki halaman HP yang bisa bergeser ke samping (tombol "Pesan Sekarang" lebih lebar dari
kartu produk) dan logo menu samping HP yang gepeng (dipaksa 60×60 oleh tema).

## Pengujian

Diuji dengan menyisipkan CSS ke HTML asli halaman depan dan halaman produk (posisi sama dengan CSS Tambahan WordPress,
akhir `<head>`) di Chromium, layar HP 390 px dan komputer 1366 px: tidak ada error, lebar halaman HP 390 px
(sebelumnya 410 px). Lihat `contoh-sebelum-sesudah-*.jpg`.
