# 📚 Aplikasi E-Library Admin Panel (Tugas UAS Pemrograman Web 2)

Aplikasi Web **E-Library Admin Panel** ini dibangun sebagai proyek Ujian Akhir Semester (UAS) pada mata kuliah Pemrograman Web 2. Sistem ini menerapkan arsitektur pemisahan modern antara **Backend (API Server)** dan **Frontend (Single Page Application)**.

---

## 📸 Dokumentasi & Screenshot Aplikasi

*Silakan tempelkan screenshot aplikasi Anda pada bagian di bawah ini setelah di-upload ke GitHub.*

### 1. Halaman Login Admin
![Halaman Login Admin](TEMPEL_LINK_SCREENSHOT_LOGIN_DISINI)
*Keterangan: Tampilan form login admin yang dirancang bersih dan responsif menggunakan Tailwind CSS.*

### 2. Halaman Dashboard Utama & Tabel CRUD
![Halaman Dashboard](TEMPEL_LINK_SCREENSHOT_DASHBOARD_DISINI)
*Keterangan: Tampilan panel kontrol utama yang menampilkan data inventaris buku secara dinamis menggunakan Vue.js 3 tanpa reload halaman.*

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
