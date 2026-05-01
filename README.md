
# UTS - Tumbler Store Mobile App

Rismanita Lestari | 1123150058 | TI 23 M SE

---

Aplikasi mobile berbasis Flutter untuk mengelola dan menampilkan produk tumbler. Aplikasi ini terhubung dengan backend Golang melalui REST API untuk proses autentikasi dan pengolahan data.

Link Demo App YT : https://youtu.be/Yy3t6UN8duM?si=COHrVWlXoM2Z2AO5

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
* Menambahkan produk ke keranjang
* Mengelola keranjang (tambah, kurang, hapus item)
* Select item untuk checkout
* Perhitungan total harga secara real-time
* Halaman checkout dengan ringkasan pesanan
* Simulasi proses pembayaran (checkout sukses)
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

## API Flow

1. User login menggunakan Firebase Authentication
2. Firebase mengembalikan ID Token
3. Token dikirim ke backend
4. Backend memverifikasi token dan mengembalikan JWT
5. JWT disimpan di local storage
6. JWT digunakan untuk request API berikutnya (get product, dll)

---

## Demo Flow Aplikasi

1. Register akun
2. Verifikasi email
3. Login
4. Masuk ke dashboard (catalog produk)
5. Tambah produk ke keranjang
6. Kelola keranjang (tambah/kurang/hapus)
7. Pilih item untuk checkout
8. Masuk ke halaman checkout
9. Klik tombol bayar (simulasi sukses)
10. Kembali ke dashboard

## Struktur Folder Flutter

```text
lib/
├── core/
│   └── routes/              # App router
├── features/
│   ├── auth/
│   │   └── presentation/
│   │       ├── pages/       # Login, Register, Verify Email
│   │       └── providers/
│   └── dashboard/
│       ├── data/
│       │   └── models/      # ProductModel
│       ├── domain/
│       │   └── repositories/
│       └── presentation/
│           ├── pages/       # DashboardPage, ProductDetailPage
│           └── providers/
└── main.dart
```

---

## State Management

Aplikasi menggunakan Provider sebagai state management dengan konsep ChangeNotifier.

Beberapa state yang dikelola:
* AuthProvider → mengelola autentikasi user
* ProductProvider → mengelola data produk
* CartProvider → mengelola keranjang, termasuk:
  - tambah/hapus item
  - selected item
  - total harga
  - checkout flow

Setiap perubahan state akan memanggil notifyListeners() untuk update UI secara real-time.

---

## Batasan Masalah

Beberapa keterbatasan pada versi aplikasi saat ini:

* Belum terintegrasi dengan payment gateway (hanya simulasi checkout)

