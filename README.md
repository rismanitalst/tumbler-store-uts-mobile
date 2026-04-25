
# UTS - Tumbler Store Mobile App

Rismanita Lestari | 1123150058 | TI 23 M SE

---

Aplikasi mobile berbasis Flutter untuk mengelola dan menampilkan produk tumbler. Aplikasi ini terhubung dengan backend Golang melalui REST API untuk proses autentikasi dan pengolahan data.

---

## Struktur & Repository

Aplikasi ini dipisah jadi dua bagian:

* **Frontend (Flutter)**
  [https://github.com/rismanitalst/UTS_tumbler_store](https://github.com/rismanitalst/UTS_tumbler_store)
  → berisi tampilan aplikasi, halaman login, register, dashboard, dan interaksi user

* **Backend (Golang API)**
  [https://github.com/rismanitalst/UTS_tumbler_store_backend](https://github.com/rismanitalst/UTS_tumbler_store_backend)
  → berisi REST API untuk autentikasi, pengolahan data, dan koneksi ke database MySQL

---

## Fitur

* Login user
* Register akun
* Verifikasi email
* Menampilkan data produk dari API
* Filter produk berdasarkan kategori
* Pencarian produk via search bar
* Refresh data (pull to refresh)
* Handling loading dan error state
* Detail produk (nama, harga, stok, kategori, deskripsi)
* Logout

---

## Teknologi

**Frontend**
Flutter, Dart, Material UI, Provider, Firebase Auth, Flutter Secure Storage

**Backend**
Golang (REST API, Gin Framework), MySQL (Laragon), Firebase Admin SDK

**Tools**
Git, GitHub, Postman, Laragon, imgBB

---

## Cara Menjalankan

### 1. Clone Project

Clone **dua repository** (frontend dan backend):

```bash
git clone https://github.com/rismanitalst/UTS_tumbler_store
git clone https://github.com/rismanitalst/UTS_tumbler_store_backend
```

---

### 2. Jalankan Database

* Buka Laragon
* Klik Start All
* Aktifkan MySQL
* Import database (jika ada)

---

### 3. Jalankan Backend

```bash
cd UTS_tumbler_store_backend
go mod tidy
go run main.go
```

Backend jalan di:
[http://localhost:8080](http://localhost:8080)

---

### 4. Jalankan Frontend (Flutter)

```bash
cd UTS_tumbler_store
flutter pub get
flutter run
```
---

## Alur Autentikasi

### Register

1. User isi nama, email, dan password
2. Sistem validasi input
3. Data dikirim ke backend / Firebase
4. Jika berhasil, user diarahkan ke halaman verifikasi email
5. Jika gagal, muncul pesan error (contoh "email sudah terdaftar" - cek firebase auth dan delete acc, kemudian daftar kembali dengan email yang sama)

### Verifikasi Email

1. User diminta cek email setelah register
2. Sistem cek status verifikasi secara otomatis
3. Jika sudah diverifikasi, user langsung masuk ke dashboard
4. Bisa kirim ulang email verifikasi
5. User bisa logout jika ingin ganti akun

### Login

1. Login dengan email/password atau Google
2. Jika berhasil → masuk dashboard
3. Jika email belum diverifikasi → ke halaman verifikasi
4. Jika gagal → muncul error

---

## Alur Dashboard

1. Setelah login, user masuk ke dashboard
2. Aplikasi otomatis fetch data produk
3. Saat loading, muncul indikator loading
4. Jika error, muncul pesan + retry
5. Jika berhasil, data tampil dalam bentuk grid 2 kolom
6. User bisa filter produk berdasarkan kategori
7. User bisa cari produk secara real-time via search bar
8. Pull to refresh untuk memuat ulang data produk

---

## Alur Detail Produk

1. User tap salah satu produk di dashboard
2. Aplikasi navigasi ke halaman detail produk
3. Halaman menampilkan foto produk, nama, harga, kategori, stok, dan deskripsi
4. Jika stok tersedia, tombol aktif
5. Jika stok habis, tombol otomatis nonaktif dan berubah jadi "Stok Habis"
6. User bisa kembali ke dashboard via tombol back

---

## Alur Logout

1. User klik icon logout di pojok kanan atas dashboard
2. Sistem hapus session di device (token dihapus dari secure storage)
3. Firebase session di-clear
4. Aplikasi redirect kembali ke halaman login
5. Data user tetap aman tersimpan di Firebase dan MySQL

---

## Batasan Masalah

Beberapa fitur masih dalam tahap pengembangan dan belum tersedia pada versi ini:

* **Tombol "Tambah ke Keranjang"** — tombol sudah tampil di halaman detail produk namun belum memiliki fungsi
* **Halaman Keranjang** — belum tersedia, user belum bisa melihat daftar produk yang dipilih
* **Halaman Transaksi / Checkout** — belum tersedia, proses pembelian belum dapat dilakukan
