# 📘 Laporan Praktikum Pertemuan Ke-6

🧑‍🎓 **Reevan Azepha Islamy Iskandar — 4524210083**

# 📚 AuthBook — Aplikasi Manajemen Buku dan Penulis

AuthBook merupakan aplikasi web berbasis Laravel yang dikembangkan untuk memenuhi tugas Praktikum 6 mata kuliah Pemrograman Berbasis Web (PBW). Aplikasi ini digunakan untuk mengelola data buku dan penulis melalui dashboard administrasi menggunakan Filament.

Aplikasi menyediakan fitur pengelolaan data buku dan penulis, termasuk penambahan, penampilan, pengubahan, dan penghapusan data. Selain itu, pengelolaan buku dilengkapi dengan dukungan unggah sampul buku. Data aplikasi disimpan menggunakan database SQLite.

<p align="center">
  <img src="https://img.shields.io/badge/Laravel-12-FF2D20?style=for-the-badge&logo=laravel&logoColor=white" alt="Laravel">
  <img src="https://img.shields.io/badge/PHP-8.2-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP">
  <img src="https://img.shields.io/badge/Filament-Admin_Panel-F59E0B?style=for-the-badge&logo=filament&logoColor=white" alt="Filament">
  <img src="https://img.shields.io/badge/SQLite-Database-07405E?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite">
</p>

## 📋 Daftar Isi

- [Tentang Aplikasi](#-tentang-aplikasi)
- [Fitur Utama](#-fitur-utama)
- [Tech Stack](#-tech-stack)
- [Persyaratan Sistem](#-persyaratan-sistem)
- [Instalasi](#-instalasi)
- [Konfigurasi Database](#-konfigurasi-database)
- [Penggunaan Aplikasi](#-penggunaan-aplikasi)
- [Struktur Database](#-struktur-database)
- [Struktur Project](#-struktur-project)
- [Testing](#-testing)
- [Penutup](#-penutup)

## 🎯 Tentang Aplikasi

AuthBook adalah aplikasi manajemen data buku dan penulis yang dikembangkan menggunakan framework Laravel dan Filament. Filament digunakan untuk membangun dashboard administrasi sehingga pengelolaan data dapat dilakukan melalui antarmuka berbasis web.

Aplikasi ini menerapkan konsep Model-View-Controller (MVC), Eloquent ORM, migration database, serta relasi antarmodel untuk mengelola data buku dan penulis.

### Modul Aplikasi

1. **Dashboard Admin** — Antarmuka administrasi untuk mengelola data.
2. **Manajemen Buku** — Mengelola informasi buku yang tersimpan dalam database.
3. **Manajemen Penulis** — Mengelola informasi penulis buku.
4. **Sampul Buku** — Mendukung pengunggahan dan penyimpanan gambar sampul buku.

## ✨ Fitur Utama

- 📚 **Manajemen Buku** — Menambahkan, melihat, mengubah, dan menghapus data buku.
- ✍️ **Manajemen Penulis** — Mengelola data penulis.
- 🔗 **Relasi Buku dan Penulis** — Menghubungkan data buku dengan penulis melalui relasi model.
- 🖼️ **Upload Sampul Buku** — Mendukung pengelolaan file gambar sampul buku.
- 🖥️ **Dashboard Administrasi** — Menggunakan Filament untuk mempermudah pengelolaan data.
- 🗄️ **Database SQLite** — Menyimpan data aplikasi dalam basis data relasional.
- ⚙️ **Laravel Migration** — Mengelola struktur tabel database.
- 🧩 **Eloquent ORM** — Mempermudah interaksi antara aplikasi dan database.

## 🛠️ Tech Stack

### Backend

- **Laravel** — Framework pengembangan aplikasi web.
- **PHP** — Bahasa pemrograman backend.
- **Eloquent ORM** — Pengelolaan data dan relasi antarmodel.

### Admin Panel

- **Filament** — Framework untuk membangun dashboard administrasi.
- **AuthorResource** — Resource untuk pengelolaan data penulis.
- **BookResource** — Resource untuk pengelolaan data buku.

### Database

- **SQLite** — Sistem manajemen basis data relasional.
- **Laravel Migration** — Pengaturan struktur tabel database.

### Development Tools

- **Composer** — Pengelola dependensi PHP.
- **Node.js dan npm** — Pengelola dependensi frontend.
- **PHP Artisan** — Menjalankan perintah pengembangan Laravel.

## 💻 Persyaratan Sistem

Sebelum menjalankan aplikasi, pastikan perangkat telah memiliki:

- PHP versi yang sesuai dengan kebutuhan proyek Laravel.
- Composer.
- Node.js dan npm.
- Git untuk melakukan clone repository.

## 🚀 Instalasi

### 1. Clone Repository

Jalankan perintah berikut di terminal:

```bash
git clone https://github.com/USERNAME/NAMA-REPOSITORY.git
```

Masuk ke direktori proyek:

```bash
cd authbook
```

Ganti URL repository dengan alamat GitHub proyek Praktikum 6 milik kamu.

### 2. Install Dependencies

Install dependensi PHP:

```bash
composer install
```

Install dependensi frontend:

```bash
npm install
```

### 3. Setup Environment

Salin file `.env.example` menjadi `.env`.

Untuk Windows Command Prompt:

```cmd
copy .env.example .env
```

Untuk Git Bash:

```bash
cp .env.example .env
```

Generate application key:

```bash
php artisan key:generate
```

### 4. Konfigurasi Database SQLite

Buka file `.env` dan pastikan konfigurasi database menggunakan SQLite:

```env
DB_CONNECTION=sqlite
```

Pastikan file database tersedia pada lokasi berikut:

```text
database/database.sqlite
```

Jika file tersebut belum tersedia, buat file kosong bernama `database.sqlite` di dalam folder `database`.

### 5. Jalankan Migration

Jalankan perintah berikut untuk membuat tabel database:

```bash
php artisan migrate
```

Migration akan membuat tabel berdasarkan definisi yang tersedia di folder `database/migrations`, termasuk tabel pengguna, penulis, dan buku.

### 6. Build Assets

Untuk menjalankan proses pengembangan frontend:

```bash
npm run dev
```

Untuk membangun aset produksi:

```bash
npm run build
```

### 7. Jalankan Aplikasi

Jalankan server Laravel:

```bash
php artisan serve
```

Buka browser dan akses:

http://127.0.0.1:8000

Untuk membuka dashboard administrasi Filament, akses:

http://127.0.0.1:8000/admin

Pastikan akun administrator sudah tersedia sebelum mencoba login ke dashboard.

## 🌐 Penggunaan Aplikasi

1. Jalankan aplikasi Laravel melalui terminal.
2. Buka halaman dashboard administrasi Filament.
3. Login menggunakan akun administrator yang tersedia.
4. Pilih menu **Books** untuk mengelola data buku.
5. Pilih menu **Authors** untuk mengelola data penulis.
6. Tambahkan data baru melalui formulir yang tersedia.
7. Ubah atau hapus data sesuai kebutuhan.
8. Gunakan fitur unggah sampul buku apabila diperlukan.

## 🗄️ Struktur Database

Aplikasi menggunakan SQLite sebagai penyimpanan data. Berdasarkan migration dan model yang tersedia, tabel utama yang digunakan adalah:

### 1. Tabel Authors

Tabel `authors` digunakan untuk menyimpan data penulis buku.

### 2. Tabel Books

Tabel `books` digunakan untuk menyimpan data buku dan informasi yang berkaitan dengan penulis.

### 3. Tabel Users

Tabel `users` digunakan untuk menyimpan data pengguna aplikasi sesuai konfigurasi autentikasi Laravel.

### 4. Tabel Pendukung Laravel

Laravel juga menyediakan migration untuk tabel pendukung, seperti `cache` dan `jobs`, sesuai kebutuhan konfigurasi aplikasi.

Relasi antara buku dan penulis dikelola melalui model Eloquent. Detail kolom dan foreign key mengikuti definisi migration pada proyek.

## 📂 Struktur Project

Berikut gambaran struktur utama proyek AuthBook:

```text
authbook/
├── app/
│   ├── Filament/
│   │   └── Resources/
│   │       ├── AuthorResource/
│   │       ├── AuthorResource.php
│   │       ├── BookResource/
│   │       └── BookResource.php
│   ├── Http/
│   │   └── Controllers/
│   ├── Models/
│   │   ├── Author.php
│   │   ├── Book.php
│   │   └── User.php
│   ├── Policies/
│   │   ├── AuthorPolicy.php
│   │   └── BookPolicy.php
│   └── Providers/
├── bootstrap/
├── config/
├── database/
│   ├── factories/
│   ├── migrations/
│   ├── seeders/
│   └── database.sqlite
├── public/
├── resources/
│   ├── css/
│   ├── js/
│   └── views/
├── routes/
│   └── web.php
├── tests/
├── .env.example
├── artisan
├── composer.json
├── composer.lock
└── package.json
```

### Keterangan Struktur

- `app/Models/` — Menyimpan model `Author`, `Book`, dan `User`.
- `app/Filament/Resources/` — Menyimpan konfigurasi resource dashboard administrasi.
- `app/Policies/` — Mengatur kebijakan otorisasi akses terhadap data.
- `database/migrations/` — Menyimpan definisi struktur tabel database.
- `database/seeders/` — Menyediakan tempat untuk pengisian data awal.
- `resources/views/` — Menyimpan template halaman website.
- `routes/web.php` — Mendefinisikan rute halaman utama.
- `public/` — Menyimpan aset publik dan file yang dapat diakses melalui web.
- `tests/` — Menyimpan kode pengujian aplikasi.

## 🧪 Testing

Laravel menyediakan fasilitas untuk menjalankan pengujian otomatis melalui perintah:

```bash
php artisan test
```

Aspek yang dapat diuji antara lain:

- Koneksi aplikasi dengan database SQLite.
- Penambahan data buku.
- Pengubahan dan penghapusan data buku.
- Penambahan dan pengelolaan data penulis.
- Relasi antara buku dan penulis.
- Validasi formulir.
- Pengunggahan sampul buku.
- Hak akses pengguna terhadap dashboard administrasi.

Hasil pengujian perlu diperiksa setelah perintah dijalankan untuk memastikan aplikasi berjalan sesuai kebutuhan.

## 📄 Penutup

Melalui Praktikum 6, mahasiswa dapat memahami penerapan Laravel dan Filament untuk membangun aplikasi pengelolaan data berbasis web. AuthBook menerapkan konsep MVC, Eloquent ORM, migration, relasi antarmodel, serta operasi CRUD untuk data buku dan penulis.

Aplikasi ini diharapkan dapat menjadi dasar untuk pengembangan sistem manajemen perpustakaan yang lebih lengkap pada tahap berikutnya.

---

<p align="center">
  <b>Dibuat dengan ❤️ menggunakan Laravel dan Filament</b>
  <br>
  <i>Praktikum 6 — Pemrograman Berbasis Web</i>
</p>
