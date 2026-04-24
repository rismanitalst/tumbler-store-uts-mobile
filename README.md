
# UTS - Tumbler Store Mobile App

Rismanita Lestari | 1123150058 | TI 23 M SE

---

Aplikasi mobile berbasis Flutter untuk mengelola dan menampilkan produk tumbler. Aplikasi ini terhubung dengan backend Golang melalui REST API untuk proses autentikasi dan pengolahan data.

---

## Struktur & Repository

Project ini dipisah jadi dua bagian:

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

---

## Teknologi

**Frontend**
Flutter, Dart, Material UI

**Backend**
Golang (REST API), MySQL (Laragon)

**Tools**
Git, GitHub, Postman, Laragon

---

## Cara Menjalankan

### 1. Clone Project

Clone **dua repository** (frontend dan backend):

```bash
git clone https://github.com/rismanitalst/UTS_tumbler_store
git clone https://github.com/rismanitalst/UTS_tumbler_store_backend
```

---

### 2. Jalankan Backend

```bash
cd UTS_tumbler_store_backend
go mod tidy
go run main.go
```

Backend jalan di:
[http://localhost:8080](http://localhost:8080)

---

### 3. Jalankan Database

* Buka Laragon
* Klik Start All
* Aktifkan MySQL
* Import database (jika ada)

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
5. Jika gagal, muncul pesan error (contoh "email sudah terdaftar" cek firebase auth dan delete acc, kemudian daftar kembali dengan email yang sama)

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
5. Jika berhasil, data tampil dalam bentuk grid

---
