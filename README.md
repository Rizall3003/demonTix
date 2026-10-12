# 🎟️ DemonTix — Kelompok 8

**DemonTix** adalah aplikasi berbasis web untuk pemesanan dan penjualan tiket konser, acara olahraga, serta destinasi wisata. Aplikasi ini dikembangkan menggunakan Laravel sebagai backend dan Vue.js sebagai frontend, dengan database MySQL untuk mengelola data aplikasi.

## ✨ Fitur Utama

- 🎫 Penjualan dan pemesanan tiket event
- 🎵 Informasi event konser, olahraga, dan wisata
- 🖼️ Pengelolaan gambar dan informasi event
- 💳 Pengelolaan bukti pembayaran
- 🗄️ Integrasi database MySQL
- 🔌 Komunikasi frontend dan backend melalui API

## 🛠️ Teknologi yang Digunakan

| Teknologi | Kegunaan |
|---|---|
| Laravel | Backend dan REST API |
| Vue.js | Frontend |
| MySQL / MariaDB | Database |
| Axios | HTTP client |
| SweetAlert2 | Notifikasi dan dialog |
| Vite | Development server frontend |
| Composer | Dependency management PHP |
| npm | Dependency management frontend |

## 📂 Struktur Project

```text
DemonTix-Kel-8/
├── backend/
│   ├── app/
│   ├── database/
│   │   ├── migrations/
│   │   └── ...
│   ├── public/
│   ├── routes/
│   ├── storage/
│   │   └── app/
│   │       └── public/
│   │           ├── bukti_pembayaran/
│   │           └── events/
│   ├── .env.example
│   └── composer.json
│
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── vite.config.js
│
├── demontix1.sql
└── README.md
```

> Nama file SQL dan struktur folder di atas harus disesuaikan dengan nama serta isi repository yang sebenarnya.

## 🚀 Instalasi dan Menjalankan Aplikasi

### Prasyarat

Pastikan perangkat sudah memiliki:

- PHP sesuai versi Laravel yang digunakan
- Composer
- Node.js dan npm
- MySQL atau MariaDB
- Git

### 1. Clone Repository

```bash
git clone https://github.com/Rizall3003/demonTix.git
cd DemonTix-Kel-8
```

### 2. Setup Backend Laravel

Masuk ke direktori backend:

```bash
cd backend
```

Install dependency:

```bash
composer install
```

Buat file environment dari template:

```bash
cp .env.example .env
```

Jika menggunakan Windows, kamu juga dapat menyalin `.env.example` secara manual menjadi `.env`.

Generate application key:

```bash
php artisan key:generate
```

### 3. Konfigurasi Database

Buat database MySQL sesuai konfigurasi aplikasi, misalnya:

```sql
CREATE DATABASE demontix;
```

Atur koneksi database di `backend/.env`:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=demontix
DB_USERNAME=root
DB_PASSWORD=
```

Sesuaikan username dan password dengan konfigurasi MySQL lokal.

### 4. Import Database

Database SQL sudah tersedia di repository.

Jika file SQL bernama `demontix.sql` dan berada di root project, import menggunakan phpMyAdmin:

1. Buka phpMyAdmin.
2. Pilih database `demontix`.
3. Buka tab **Import**.
4. Pilih file `demontix.sql`.
5. Klik **Import** atau **Go**.

Alternatif melalui terminal, jalankan dari root project:

```bash
mysql -u root -p demontix < demontix.sql
```

Jika MySQL tidak menggunakan password, kamu dapat menyesuaikan perintah tersebut dengan konfigurasi lokal.

> **Penting:** Jika database SQL sudah berisi tabel dan data awal, jangan langsung menjalankan `php artisan migrate:fresh`, karena perintah tersebut menghapus tabel yang ada. Pastikan struktur database hasil import sesuai dengan versi kode backend.

### 5. Siapkan File Gambar Event
Folder gambar tersedia di repository. Pastikan file berada pada lokasi yang sesuai dengan struktur Laravel:

```text
backend/storage/app/public/
└── events/
```

Buat symbolic link agar file di storage dapat diakses melalui folder public:

```bash
php artisan storage:link
```

Secara default, Laravel akan membuat:

```text
backend/public/storage
```

yang mengarah ke:

```text
backend/storage/app/public
```

Contoh URL gambar event:

```text
http://localhost:8000/storage/events/nama-file-gambar.jpg
```

Ganti `nama-file-gambar.jpg` dengan nama file yang benar-benar tersedia.

### 6. Jalankan Backend

Dari direktori `backend`, jalankan:

```bash
php artisan serve
```

Backend Laravel biasanya tersedia di:

http://localhost:8000

### 7. Setup Frontend

Buka terminal baru dari root project:

```bash
cd frontend
```

Install dependency:

```bash
npm install
```

Jalankan frontend:

```bash
npm run dev
```

Frontend Vue.js biasanya tersedia di:

http://localhost:5173

Jika URL backend dikonfigurasi melalui environment variable frontend, pastikan nilainya sesuai dengan alamat server Laravel lokal.

Contoh konfigurasi jika proyek menggunakan `VITE_API_URL`:

```env
VITE_API_URL=http://localhost:8000
```

Gunakan nama variabel yang memang dibaca oleh kode frontend.

## 👨‍💻 Developer

**Kelompok 8**  
Mata Kuliah Pemrograman Web  
Fakultas Ilmu Komputer  
Universitas Amikom Yogyakarta

---

<p align="center">
  🎟️ DemonTix — Event Ticketing Web Application
</p>
