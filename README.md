# U-Market

Website e-commerce untuk komunitas jual beli Universitas Lampung, dirancang sebagai pengganti grup WhatsApp "U Marketplace". Dikembangkan sebagai proyek skripsi S1 Teknik Informatika Universitas Lampung (Nov 2025 – Apr 2026) dengan metode Scrum.

**Tautan:** [Desain Figma (Hi-Fi)](https://www.figma.com/design/rNeNJWTLGPSDrvweBg0dRt/umarket-hi-fi?node-id=1-2) · [Portofolio](https://alyaporto.vercel.app)

## Latar Belakang

Survei terhadap 34 pengguna grup WhatsApp "U Marketplace" menunjukkan tiga masalah utama: informasi produk cepat tertimbun oleh pesan lain, pencarian produk sulit dilakukan, dan konfirmasi pesanan masih manual. U-Market menyatukan katalog produk, pencarian, keranjang, checkout, dan status pesanan dalam satu platform.

## Tim

| Peran | Nama | Keterangan |
|---|---|---|
| Frontend Developer | Alya Ananda Putri | Desain Hi-Fi di Figma, implementasi antarmuka dengan Vue.js dan Tailwind CSS, pengujian |
| Backend Developer | Annisa Tri Hapsari | API dan basis data (Laravel) |
| Product Owner | Yessi Mulyani, M.T. | Penentuan kebutuhan dan prioritas fitur |
| Scrum Master | Nurrahma, M.T. | Fasilitasi proses Scrum |

Kode frontend berada di folder `resources/js`, `resources/css`, dan `resources/views`. Kode backend berada di `app`, `routes`, `config`, dan `database`.

## Fitur

**Pembeli**
- Katalog produk di landing page dan beranda
- Pencarian produk berdasarkan nama produk atau toko
- Detail produk dengan pemilih jumlah sesuai stok
- Keranjang: pilih semua, ubah jumlah, hapus item
- Checkout dengan ringkasan per toko dan halaman konfirmasi pesanan
- Pesanan Saya per status, dengan tombol Hubungi Penjual
- Profil pengguna dan pengelolaan rekening bank

**Penjual**
- Toko Saya: saldo penjualan, ringkasan pesanan (masuk, perlu dikirim, dikirim), tambah/ubah/hapus produk
- Profil toko publik berisi galeri produk

**Admin**
- Dashboard: jumlah pengguna, total transaksi, grafik penjualan, produk populer
- Manajemen produk, manajemen pengguna, dan riwayat penjualan

**Umum**
- Login dan register dengan validasi form
- Konfirmasi logout, halaman Syarat & Ketentuan, dan halaman Hubungi Kami

## Teknologi

| Bagian | Teknologi |
|---|---|
| Frontend | Vue.js 3.5, Tailwind CSS 3.4, JavaScript |
| Backend | Laravel (autentikasi dengan Sanctum) |
| Desain | Figma |
| Proses dan kolaborasi | Scrum, Trello, Git & GitHub |

## Hasil Pengujian

- **Blackbox Testing:** seluruh test case valid.
- **User Experience Questionnaire (UEQ), 50 responden:** 5 dari 6 dimensi berkategori *Excellent* dan 1 dimensi *Good*.

| Dimensi | Rata-rata (skala -3 sampai +3) |
|---|---|
| Efisiensi | 2,07 |
| Kejelasan | 2,04 |
| Daya Tarik | 2,00 |
| Ketepatan | 1,99 |
| Stimulasi | 1,87 |
| Kebaruan | 1,32 |

## Proses Pengembangan

Pengembangan dilakukan dalam 4 sprint:

1. **Sprint 1:** perancangan 15 desain High Fidelity di Figma.
2. **Sprint 2:** implementasi landing page, login/register, beranda, detail produk, pencarian, keranjang, dan profil pengguna.
3. **Sprint 3:** implementasi checkout, konfirmasi pesanan, pesanan saya, serta halaman admin.
4. **Sprint 4:** implementasi Toko Saya, profil toko, Syarat & Ketentuan, Hubungi Kami, serta pengujian dan evaluasi UEQ.

## Tampilan

| Beranda | Detail Produk |
|---|---|
| ![Beranda](docs/screenshots/beranda.png) | ![Detail Produk](docs/screenshots/detail-produk.png) |

| Toko Saya | Dashboard Admin |
|---|---|
| ![Toko Saya](docs/screenshots/toko-saya.png) | ![Dashboard Admin](docs/screenshots/dashboard-admin.png) |

## Menjalankan di Lokal

Prasyarat: PHP, Composer, Node.js (npm), dan database MySQL.

```bash
git clone https://github.com/alyaananda19/E-Commerce-U-Market.git
cd E-Commerce-U-Market

composer install
npm install

cp .env.example .env
php artisan key:generate
```

Atur koneksi database di file `.env`, lalu jalankan:

```bash
php artisan migrate --seed
npm run dev
php artisan serve
```

Buka `http://127.0.0.1:8000` di browser. Akun contoh untuk mencoba tersedia di `database/seeders`.

## Struktur Folder

```
resources/js       Komponen dan halaman Vue.js (frontend)
resources/css      Gaya Tailwind CSS
resources/views    Titik masuk aplikasi (Blade)
app, routes        Logika dan API backend (Laravel)
config             Konfigurasi aplikasi
database           Migration dan seeder
docs               Dokumentasi dan screenshot
```

## Catatan

- Repo ini dibuat dari salinan proyek asli tanpa riwayat commit lama.
- Seluruh data pada seeder adalah data contoh.
- Berkas `.env` tidak disertakan. Gunakan `.env.example` sebagai acuan.
