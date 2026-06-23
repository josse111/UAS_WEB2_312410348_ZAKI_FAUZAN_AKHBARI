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
