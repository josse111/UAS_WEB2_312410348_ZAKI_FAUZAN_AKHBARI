# 📚 Aplikasi E-Library Admin Panel (Tugas UAS Pemrograman Web 2)

Proyek ini dibangun untuk memenuhi tugas Ujian Akhir Semester (UAS) pada mata kuliah Pemrograman Web 2 dengan studi kasus Sistem Manajemen Inventaris E-Library. Sistem ini menerapkan arsitektur *Decoupled* yang memisahkan antara **Backend (API Server)** dan **Frontend (Single Page Application)**.

**Nama: Zaki Fauzan Akhbari**

**NIM: 312410348**

**Kelas:I241D**
---

## 📸 Dokumentasi & Screenshot Aplikasi

### 1. Skema Relasi Tabel Database (phpMyAdmin Designer)
<img width="1913" height="995" alt="image" src="https://github.com/user-attachments/assets/dba3b99e-4332-4c7d-9ae8-68fdd9db9725" />


### 2. Uji Coba Request API Gagal (Error 401 Unauthorized via Postman)
<img width="1466" height="477" alt="Screenshot 2026-06-23 195454" src="https://github.com/user-attachments/assets/612725b1-cfc1-41f7-805c-15d67d0dc0ed" />


### 3. Antarmuka Halaman Login Admin
<img width="1802" height="892" alt="Screenshot 2026-06-23 201511" src="https://github.com/user-attachments/assets/8f590dc7-c353-4b41-85e3-739ecc6e4b2e" />


### 4. Halaman Dashboard Utama & Tabel Manajemen Data CRUD
<img width="1896" height="992" alt="Screenshot 2026-06-23 210157" src="https://github.com/user-attachments/assets/509e96b1-63f5-4f86-864a-4d91982e0906" />

---

## 📂 Pengorganisasian Folder Proyek

Sesuai instruksi ketentuan pengumpulan, repositori ini dibagi menjadi dua folder utama:

```UAS_Web2_E_Library/
- backend-api/ (Berisi seluruh ekosistem framework CodeIgniter 4 untuk server RESTful API)
- frontend-spa/ (Berisi file index.html, implementasi framework Vue.js 3, dan aset Tailwind CSS)
- README.md (Dokumentasi lengkap proyek UAS)
```
---

## 🛠️ Pembahasan Arsitektur & Teori Teknologi

### 1. Konsep Decoupled Architecture (Pemisahan Backend & Frontend)
Proyek ini mengadopsi arsitektur modern di mana Backend dan Frontend berdiri sebagai entitas terpisah:
- Backend API (CodeIgniter 4): Berperan murni sebagai penyedia data (Data Provider). Menggunakan arsitektur MVC (Model-View-Controller), namun komponen View ditiadakan dan diganti dengan respons format JSON agar bisa dikonsumsi oleh Frontend secara independen.
- Frontend SPA (Vue.js 3): Berperan sebagai pengatur antarmuka pengguna (User Interface). Logika aplikasi dijalankan sepenuhnya di sisi client (browser), sehingga interaksi terasa sangat instan.

### 2. Mekanisme Kerja Single Page Application (SPA)
Tidak seperti web tradisional yang harus memuat ulang seluruh halaman (hard reload) setiap kali berpindah menu, aplikasi ini memanfaatkan Vue.js 3 Reactive State. Ketika admin berhasil login atau melakukan manajemen data (CRUD), Vue 3 secara cerdas hanya memperbarui bagian komponen HTML yang berubah saja (DOM Manipulation). Hal ini membuat penggunaan memori lebih efisien dan menghemat kuota internet karena tidak ada aset CSS/JS yang diunduh berulang kali.

### 3. Proteksi Endpoint API (AuthFilter & Token Security)
Untuk mengamankan database dari serangan luar, endpoint kritis seperti penambahan, pembaruan, dan penghapusan buku dilindungi oleh AuthFilter di sisi CodeIgniter 4. Jika request dikirim tanpa membawa Token Validasi yang sah di bagian Header Authorization, server backend akan otomatis menolak akses dan membalas dengan status HTTP 401 Unauthorized demi menjaga integritas data perpustakaan.

---

## ⚙️ Petunjuk Instalasi & Menjalankan Proyek Secara Lokal

Berikut langkah-langkah untuk menjalankan aplikasi ini di komputer lokal Anda:

### Persiapan Backend (API Server):
1. Pastikan aplikasi XAMPP sudah terinstal dan hidupkan module Apache serta MySQL.
2. Import file database MySQL proyek ini (`uas_elibrary.sql`) melalui phpMyAdmin.
3. Buka terminal atau command prompt, lalu masuk ke direktori backend: `cd backend-api`.
4. Jalankan perintah server lokal CodeIgniter 4: `php spark serve`.
5. Server backend akan aktif berjalan di alamat `http://localhost:8080`.

### Persiapan Frontend (SPA Antarmuka):
1. Masuk ke direktori frontend: `cd frontend-spa`.
2. Buka file `index.html` menggunakan browser Google Chrome secara langsung, atau jalankan menggunakan ekstensi "Live Server" di VS Code untuk mendapatkan alamat `http://127.0.0.1:5500`.
3. Gunakan akun demonstrasi berikut untuk masuk ke dashboard:
   - **Username:** admin
   - **Password:** admin123

---

## 🔗 Tautan Tontonan Demo & Presentasi

Berikut adalah link video demonstrasi fungsionalitas program dan presentasi arsitektur proyek:
- **Link Demo Aplikasi:** [TEMPEL_LINK_DEMO_SITUS_JIKA_ADA_ATAU_HAPUS_BARIS_INI]
- **Link Video Presentasi Proyek (YouTube/Drive):** [TEMPEL_LINK_VIDEO_PRESENTASI_TUGAS_UAS_DI_SINI]
