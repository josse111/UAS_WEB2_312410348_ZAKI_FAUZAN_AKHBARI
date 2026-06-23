# 📚 Aplikasi E-Library Admin Panel (Tugas UAS Pemrograman Web 2)

Aplikasi Web **E-Library Admin Panel** ini dibangun sebagai proyek Ujian Akhir Semester (UAS) pada mata kuliah Pemrograman Web 2. Sistem ini menerapkan arsitektur pemisahan modern antara **Backend (API Server)** dan **Frontend (Single Page Application)**.

**Nama: Zaki Fauzan Akhbari**

**Nim: 312410348**

**Kelas: I241D**

---

## 📸 Dokumentasi & Screenshot Aplikasi

### 1. Halaman Login Admin
<img width="1802" height="892" alt="Screenshot 2026-06-23 201511" src="https://github.com/user-attachments/assets/24df5fbd-7469-47ea-9e9a-8701306ec4be" />

### 2. Halaman Dashboard Utama & Tabel CRUD
<img width="1896" height="992" alt="Screenshot 2026-06-23 210157" src="https://github.com/user-attachments/assets/b02ddc05-3b4c-413a-8a4e-951bb5f7796a" />

---

## 📂 Struktur Direktori Proyek

```text
UAS_Web2_E_Library/
│
├── backend-api/          # Source code server CodeIgniter 4 (RESTful API)
│   ├── app/
│   │   ├── Config/       # Konfigurasi rute (Routes.php), Filters, & CORS
│   │   ├── Controllers/  # AuthController & BookController
│   │   └── Models/       # BookModel untuk interaksi ke tabel MySQL
│   └── public/
│
├── frontend-spa/         # Antarmuka Single Page Application (SPA)
│   └── index.html        # File utama berisi struktur HTML, Tailwind CSS, & logika Vue 3
│
└── README.md             # Dokumentasi proyek uas
```
---

## 🛠️ Pembahasan Arsitektur & Teknologi

### 1. Konsep Decoupled Architecture (Pemisahan Backend & Frontend)
Proyek ini mengadopsi arsitektur modern di mana **Backend** dan **Frontend** berdiri sebagai entitas terpisah:
- **Backend API (CodeIgniter 4):** Berperan murni sebagai penyedia data (*Data Provider*). Menggunakan arsitektur MVC (Model-View-Controller), namun komponen *View* ditiadakan dan diganti dengan respons format **JSON** agar bisa dikonsumsi oleh perangkat/platform apa pun.
- **Frontend SPA (Vue.js 3):** Berperan sebagai pengatur antarmuka pengguna (*User Interface*). Logika aplikasi dijalankan sepenuhnya di sisi client (browser), sehingga interaksi terasa sangat instan.

### 2. Mekanisme Kerja Single Page Application (SPA)
Tidak seperti web tradisional yang harus memuat ulang seluruh halaman (`hard reload`) setiap kali berpindah menu, aplikasi ini memanfaatkan **Vue.js 3 Reactive State**. Ketika admin berhasil login atau melakukan manajemen data (CRUD), Vue 3 secara cerdas hanya memperbarui bagian komponen HTML yang berubah saja (*DOM Manipulation*). Hal ini membuat penggunaan memori lebih efisien dan menghemat kuota internet karena tidak ada aset CSS/JS yang diunduh berulang kali.

### 3. Penanganan Masalah Kebijakan CORS (Cross-Origin Resource Sharing)
Karena Frontend berjalan pada protokol lokal browser/Live Server (`http://127.0.0.1:5500` atau `file:///`) sedangkan Backend API berjalan pada port terpisah (`http://localhost:8080`), browser secara otomatis akan memblokir request demi keamanan lintas asal (*Same-Origin Policy*). 

Untuk mengatasi hal tersebut, proyek ini mengonfigurasi header pengaman khusus pada file backend rute:
```php
header("Access-Control-Allow-Origin: *");
header("Access-Control-Allow-Headers: Content-Type, Authorization, X-Requested-With");
header("Access-Control-Allow-Methods: GET, POST, OPTIONS, PUT, DELETE");
```
Pernyataan di atas memerintahkan server CodeIgniter untuk menerima ketukan data dari luar demi keperluan integrasi lingkungan pengembangan (development environment).

## 🚀 Fitur Utama Sistem
- **Sistem Autentikasi Instan:** Menggunakan token statis lokal yang aman untuk mem-bypass autentikasi admin di sisi klien secara kilat.

**Manajemen Inventaris Buku (CRUD):**

- **Create:** Menambahkan data koleksi buku baru langsung ke dalam tabel.

- **Read:** Menampilkan data inventaris aktif lengkap dengan detail judul, penulis, penerbit, stok, dan label status.

- **Update:** Mengubah detail informasi data buku secara instan melalui sinkronisasi form pengisian.

- **Delete:** Menghapus data buku dengan fitur konfirmasi pengaman bawaan.

- **Status Badge Dinamis:** Visualisasi otomatis untuk status buku (Tersedia, Dipinjam, atau Hilang) menggunakan variasi komponen Tailwind CSS.

## 👤 Akun Uji Coba Admin
Gunakan kredensial berikut untuk menguji sistem pada halaman login panel:

- **Username:** admin

- **Password:** admin123
