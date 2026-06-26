# Panduan Setup Google OAuth & Google Cloud Integration

Dokumen ini menjelaskan langkah-langkah untuk mengonfigurasi Google Cloud Console agar AuraScan dapat menggunakan Google OAuth 2.0, Google Sheets API, dan Gemini 1.5 Flash API secara langsung dari frontend (Cloud Mode).

---

## 1. Membuat Project Google Cloud
1. Buka [Google Cloud Console](https://console.cloud.google.com/).
2. Di pojok kiri atas, klik menu dropdown proyek lalu pilih **New Project**.
3. Beri nama proyek (misal: `AuraScan-Expense-Tracker`) lalu klik **Create**.

---

## 2. Mengaktifkan Google APIs
Anda perlu mengaktifkan tiga API di Google Cloud Console untuk proyek ini:
1. Buka menu pencarian atau masuk ke **APIs & Services > Library**.
2. Cari dan aktifkan masing-masing API berikut:
   - **Google Sheets API** (untuk menyimpan dan memperbarui data transaksi).
   - **Google Drive API** (untuk mencari dan membuat file spreadsheet di Google Drive pengguna).
   - **Generative Language API** (Google AI Developer API, digunakan oleh Gemini API REST endpoint).

---

## 3. Konfigurasi OAuth Consent Screen
1. Navigasi ke **APIs & Services > OAuth consent screen**.
2. Pilih User Type:
   - **External** (jika Anda menggunakan akun Gmail pribadi).
   - Klik **Create**.
3. Lengkapi **App information**:
   - App name: `AuraScan`
   - User support email: Pilih email Anda.
   - Developer contact information: Masukkan email Anda.
   - Klik **Save and Continue**.
4. Bagian **Scopes** (Cakupan):
   - Klik **Add or Remove Scopes**.
   - Tambahkan cakupan berikut secara manual atau pilih dari daftar:
     - `https://www.googleapis.com/auth/userinfo.profile` (untuk memuat profil & foto pengguna)
     - `https://www.googleapis.com/auth/userinfo.email` (untuk memuat email pengguna)
     - `https://www.googleapis.com/auth/spreadsheets` (untuk akses baca/tulis Google Sheets)
     - `https://www.googleapis.com/auth/drive.file` (untuk membuat & mencari spreadsheet baru)
     - `https://www.googleapis.com/auth/generative-language.tuning` (untuk memanggil Gemini API)
   - Klik **Update** lalu **Save and Continue**.
5. Bagian **Test users**:
   - **PENTING**: Karena aplikasi berada dalam status Testing, Anda harus menambahkan email Google yang akan digunakan untuk uji coba di tombol **Add Users**.
   - Tambahkan email Anda sendiri, lalu klik **Save and Continue**.

---

## 4. Membuat OAuth 2.0 Web Client Credentials
1. Navigasi ke **APIs & Services > Credentials**.
2. Klik **+ Create Credentials** di bagian atas, pilih **OAuth client ID**.
3. Pilih Application Type: **Web application**.
4. Beri nama credential (misal: `AuraScan Web Client`).
5. Di bagian **Authorized JavaScript origins**:
   - Jika Anda menggunakan Live Server di VS Code (default port 5500), klik **+ Add URI** dan masukkan: `http://localhost:5500`.
   - Jika Anda menggunakan server lokal lain, tambahkan origin yang sesuai (misal: `http://localhost` atau `http://127.0.0.1:port`).
6. Klik **Create**.
7. Jendela popup akan menampilkan **Your Client ID** (misal: `12345678-abcde.apps.googleusercontent.com`). Salin Client ID ini.

---

## 5. Konfigurasi Client ID di Aplikasi Web AuraScan
Anda memiliki dua cara untuk memasukkan Client ID ini ke dalam web app AuraScan:

### Cara A: Edit Kode Langsung (Direkomendasikan untuk Deployment)
1. Buka file `index.html`.
2. Temukan variabel `OAUTH_CLIENT_ID` di awal blok JavaScript script (sekitar awal tag `<script>`):
   ```javascript
   let OAUTH_CLIENT_ID = 'YOUR_CLIENT_ID.apps.googleusercontent.com';
   ```
3. Ganti placeholder tersebut dengan Client ID yang telah Anda salin sebelumnya.

### Cara B: Masukkan via Prompt Web App (Direkomendasikan untuk Pengujian Cepat)
1. Buka aplikasi di browser (melalui `http://localhost:5500`).
2. Klik tombol **Login dengan Google** atau **Hubungkan Cloud**.
3. Jika Client ID belum diset dalam kode, aplikasi akan memunculkan prompt dialog input.
4. Paste Client ID Anda di prompt tersebut dan tekan OK. Aplikasi akan menyimpan Client ID tersebut ke `localStorage` browser Anda secara otomatis sehingga Anda tidak perlu memasukkannya kembali.
