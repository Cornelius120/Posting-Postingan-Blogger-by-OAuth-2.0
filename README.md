# 📝 Posting-Postingan-Blogger-by-OAuth-2.0

Antarmuka web kustom untuk mempermudah pembuatan dan publikasi postingan Blogger via Google OAuth 2.0. Cocok untuk pengelola blog yang ingin efisien, aman, dan bebas ribet — lengkap dengan unggahan gambar ke ImgBB dan penjadwalan postingan cerdas.

---

## ✨ Fitur Utama

* 🔐 **Login Aman via Google OAuth 2.0**
* 🕊️ **Penulisan Konten HTML atau Visual**
* 🍿️ **Manajemen Label Otomatis (localStorage)**
* 🗓️ **Penjadwalan Cerdas (misal: "Setelah 5 Menit")**
* 🖼️ **Unggah Gambar ke ImgBB**
* 📆 **Deskripsi Penelusuran & Kontrol Komentar**
* 💾 **Auto-Save Judul dan Label di localStorage**

---

## 📌 Deskripsi Proyek

Aplikasi web mandiri yang dibangun di atas Google Blogger API dan otentikasi OAuth 2.0. Pengguna dapat:

* Menulis konten secara langsung dari web
* Menyisipkan gambar via ImgBB
* Mengatur label dan metadata postingan
* Menjadwalkan postingan agar tidak terdeteksi sebagai spam
* Menyimpan data input otomatis di browser (localStorage)

---

## ⚙️ Konfigurasi Awal

### 1. 🔧 Siapkan Google Cloud Console (OAuth 2.0 & Blogger API)

1. Buka [Google Cloud Console](https://console.cloud.google.com/)

2. Buat proyek baru (misal: `Blogger Post Creator Project`)

3. Aktifkan **Blogger API**:

   * Masuk ke `APIs & Services` > `Library`
   * Cari "Blogger API" > Klik **Enable**

4. Buat OAuth Client ID:

   * Masuk ke `APIs & Services` > `Credentials`
   * Klik `+ Create Credentials` > Pilih **OAuth Client ID**
   * Tipe: **Web Application**
   * Tambahkan:

     * `Authorized JavaScript origins`: `https://urlwebbloggerkamu.blogspot.com`
     * `Authorized redirect URIs`: `https://urlwebbloggerkamu.blogspot.com`
   * Salin `Client ID` yang diberikan

5. Update kode HTML:

   ```javascript
   const CLIENT_ID = 'CLIENT_ID_ANDA_DI_SINI'; // ganti dengan Client ID asli
   const BLOG_ID = 'BLOG_ID_ANDA_DI_SINI';     // ganti dengan ID blog kamu
   ```

> 💡 **Tips:** BLOG\_ID bisa kamu temukan di URL dashboard Blogger saat buka daftar postingan.

---

### 2. 🖼️ Dapatkan ImgBB API Key (Opsional)

Untuk fitur unggah gambar:

1. Buka [https://api.imgbb.com/](https://api.imgbb.com/)
2. Login / daftar akun
3. Dapatkan **API Key**
4. Update kode HTML:

   ```javascript
   const IMGBB_API_KEYS = ['API_KEY_IMGBB_KAMU'];
   ```

---

### 3. 📄 Penempatan di Halaman Blogger

> **Catatan:** Tempatkan kode di **Pages**, bukan **Posts**.

1. Masuk ke **Dashboard Blogger**
2. Pilih **Pages (Halaman)** > Klik **New Page**
3. Judul halaman: `Blogger Post Creator`
4. Ubah ke tampilan **HTML view**
5. Tempelkan seluruh isi file `blogger-post-creator.html`
6. Klik **Publish**

---

## 🚀 Cara Menggunakan Aplikasi

1. **Buka Halaman** yang sudah kamu buat di Blogger
2. **Login Google**: Klik `Hubungkan Akun Google`
3. **Tulis Postingan:**

   * Masukkan **Judul**
   * Isi konten (HTML/Visual)
   * **Unggah Gambar** ke ImgBB (jika diaktifkan)
   * Masukkan **Label** (pisahkan dengan koma)
   * Atur **Deskripsi Penelusuran (SEO)**
   * Pilih opsi **Komentar**
4. **Penjadwalan:**

   * Publikasi sekarang
   * Jadwal otomatis (misal: "Setelah 5 Menit")
   * Atau pilih tanggal/waktu spesifik
5. Klik **Buat Postingan**

---

## 🔐 Keamanan & Privasi

* Aplikasi hanya mengakses akun Google Anda setelah Anda memberikan izin eksplisit
* Tidak ada informasi pribadi disimpan di server (semua proses terjadi di browser Anda)
* Menggunakan `localStorage` hanya untuk kenyamanan pengguna lokal

---

## 💪 Teknologi yang Digunakan

* [Blogger API v3](https://developers.google.com/blogger/docs/3.0/)
* [Google Identity Services](https://developers.google.com/identity)
* [ImgBB API](https://api.imgbb.com/)
* HTML, CSS (Dark Mode), JavaScript murni

---

## 💡 Tips Tambahan

* Gunakan halaman ini untuk semua aktivitas posting agar tetap konsisten
* Refresh halaman tidak akan menghapus judul/label (karena localStorage)
* Anda bisa membuat beberapa halaman untuk beberapa blog (gunakan BLOG\_ID berbeda)

---

## 📬 Kontak & Kontribusi

Jika Anda memiliki saran atau ingin berkontribusi, silakan buka issue atau pull request!

---

## 📄 Lisensi

Proyek ini dilisensikan di bawah MIT License. Bebas digunakan dan dimodifikasi.

---

Selamat ngeblog dengan lebih mudah dan terstruktur! 🚀
