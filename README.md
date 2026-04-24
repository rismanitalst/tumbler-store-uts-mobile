
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

* Login user (email & Google)
* Register akun
* Verifikasi email
* Menampilkan data produk dari API
* Refresh data (pull to refresh)
* Handling loading dan error state
* Logout

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

Nah ini poin penting yang sering bikin bingung. Jangan clone repo README doang, karena itu cuma “etalase”. Yang dijalanin itu **frontend + backend**.

Cara jelasinnya di README biar nggak ambigu gini:

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

