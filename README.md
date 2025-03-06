# Perpustakaan Digital

Sistem perpustakaan digital yang memungkinkan pengguna untuk mengakses dan mengelola koleksi buku fisik dan digital secara online.

## Fitur Utama

### Pengguna
- Autentikasi pengguna (login/register)
- Pencarian buku fisik dan digital
- Peminjaman buku fisik
- Pembacaan buku digital
- Riwayat peminjaman
- Profil pengguna
- Notifikasi status peminjaman

### Admin
- Manajemen buku fisik dan digital
- Manajemen pengguna
- Manajemen peminjaman
- Laporan dan statistik
- Pengaturan sistem

## Teknologi yang Digunakan

- PHP 7.4+
- MySQL 5.7+
- Bootstrap 5.3
- Bootstrap Icons
- HTML5
- CSS3
- JavaScript

## Struktur Database

### Tabel Users
- id (INT, PRIMARY KEY)
- username (VARCHAR)
- password (VARCHAR)
- nama_lengkap (VARCHAR)
- email (VARCHAR)
- role (ENUM: 'user', 'admin')
- created_at (TIMESTAMP)

### Tabel Books
- id (INT, PRIMARY KEY)
- judul (VARCHAR)
- penulis (VARCHAR)
- penerbit (VARCHAR)
- tahun (YEAR)
- kategori (VARCHAR)
- deskripsi (TEXT)
- stok (INT)
- gambar (VARCHAR)
- created_at (TIMESTAMP)

### Tabel Digital_Books
- id (INT, PRIMARY KEY)
- judul (VARCHAR)
- penulis (VARCHAR)
- penerbit (VARCHAR)
- tahun (YEAR)
- kategori (VARCHAR)
- deskripsi (TEXT)
- file_path (VARCHAR)
- gambar (VARCHAR)
- created_at (TIMESTAMP)

### Tabel Borrowings
- id (INT, PRIMARY KEY)
- user_id (INT, FOREIGN KEY)
- book_id (INT, FOREIGN KEY)
- tanggal_pinjam (DATE)
- tanggal_kembali (DATE)
- status (ENUM: 'dipinjam', 'dikembalikan', 'terlambat')
- created_at (TIMESTAMP)

## Instalasi

1. Clone repositori ini
2. Import file `perpustakaan.sql` ke database MySQL
3. Konfigurasi koneksi database di `config/database.php`
4. Jalankan di web server (Apache/Nginx)

## Struktur Folder

```
perpustakaan/
├── admin/
│   ├── dashboard.php
│   ├── books.php
│   ├── digital_books.php
│   ├── users.php
│   └── borrowings.php
├── assets/
│   ├── css/
│   ├── js/
│   └── images/
├── config/
│   ├── database.php
│   └── auth.php
├── uploads/
│   ├── books/
│   └── digital/
├── index.php
├── login.php
├── register.php
├── profile.php
├── katalog.php
├── detail_buku.php
├── detail_digital.php
└── README.md
```

## Kontribusi

Silakan berkontribusi dengan membuat pull request atau melaporkan issues.

## Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE). 