# PANDUAN DAN SCRIPT VIDEO PRESENTASI
## PROYEK AKHIR: SMART RECEIPT SCANNER & EXPENSE LOGGER

* **Nama Mahasiswa:** [NAMA_MAHASISWA]
* **NIM:** [NIM_MAHASISWA]
* **Durasi Target:** 15 - 30 Menit
* **Mata Kuliah:** Komputasi Awan (3 sks)
* **Dosen Pengampu:** Yutika Amelia Effendi, Ph.D.

---

## RENCANA ALOKASI WAKTU (TIMELINE)
1. **Pendahuluan / Intro:** 1 - 2 Menit
2. **Penjelasan Arsitektur Cloud & Overview Proyek:** 5 Menit
3. **Demo Aplikasi Secara Langsung (Live Demo):** 5 - 8 Menit
4. **Demonstrasi Modul Analisis Data (Machine Learning):** 5 - 8 Menit
5. **Kesimpulan & Tanya Jawab (Q&A):** 3 Menit

---

## 🎬 NASKAH DAN PANDUAN LANGKAH DEMI LANGKAH

### BAGIAN 1: PENDAHULUAN / INTRO (Durasi: 1 - 2 Menit)
* **Visual:** Wajah presenter di kamera depan (headshot), bersikap profesional dengan latar belakang rapi. Menampilkan slide judul presentasi.
* **Tindakan Presenter:** Memberi salam pembuka, senyum ramah, memperkenalkan diri dan judul proyek.

**Script Bahasa Indonesia:**
> *"Selamat pagi/siang/sore kepada Ibu Yutika Amelia Effendi, Ph.D. selaku dosen pengampu mata kuliah Komputasi Awan, serta rekan-rekan sekalian. Perkenalkan, nama saya **[NAMA_MAHASISWA]** dengan NIM **[NIM_MAHASISWA]** dari Program Studi Teknik Robotika dan Kecerdasan Buatan, Fakultas Teknologi Maju dan Multidisiplin, Universitas Airlangga.*
> 
> *Pada kesempatan kali ini, saya akan mempresentasikan hasil pengerjaan Case-based Project Tugas Akhir mata kuliah Komputasi Awan yang berjudul **'Pengembangan Sistem Smart Receipt Scanner & Expense Logger Berbasis Cloud Computing dengan Analisis Data Transaksi Otomatis'**.*
> 
> *Aplikasi ini dirancang untuk mengatasi masalah yang sering dihadapi oleh banyak orang, yaitu kesulitan dalam melacak pengeluaran harian akibat tumpukan struk fisik yang mudah hilang dan proses pencatatan manual yang melelahkan. Dengan memanfaatkan komputasi awan serverless dan kecerdasan buatan, kita dapat mengotomatisasi seluruh proses pencatatan keuangan ini hanya dengan sekali potret struk belanja. Mari kita mulai pembahasannya."*

---

### BAGIAN 2: PENJELASAN ARSITEKTUR CLOUD & OVERVIEW PROYEK (Durasi: 5 Menit)
* **Visual:** Menampilkan slide diagram arsitektur cloud (diagram blok/flowchart) dan daftar teknologi yang digunakan.
* **Tindakan Presenter:** Menjelaskan alur data dari ponsel pengguna hingga masuk ke basis data cloud, serta menjelaskan alasan pemilihan teknologi serverless ini.

**Script Bahasa Indonesia:**
> *"Sebelum kita masuk ke demo aplikasi, mari kita pelajari terlebih dahulu arsitektur cloud yang melandasi sistem ini. Sistem ini dibangun dengan konsep **Serverless Architecture** menggunakan gabungan layanan Cloud IaaS, PaaS, SaaS, dan MaaS.*
> 
> *Berikut adalah komponen utama teknologi yang digunakan:*
> 1. **Google OAuth 2.0 (Identity Management as a Service - IDaaS)**: *Kami menggunakan Google Sign-In untuk mengelola identitas pengguna secara aman. Pengguna tidak perlu membuat password baru; sistem langsung mengotentikasi melalui akun Google mereka secara terenkripsi.*
> 2. **Vercel Hosting**: *Hosting frontend aplikasi menggunakan platform PaaS Vercel untuk memastikan waktu muat (loading time) yang sangat cepat menggunakan CDN global.*
> 3. **Vercel Serverless Functions**: *Backend aplikasi dibangun menggunakan fungsi Python serverless. Ini berarti kode backend hanya dieksekusi saat ada unggahan gambar struk (scale-to-zero), menghemat biaya server dan meminimalkan pemeliharaan sistem.*
> 4. **Google Gemini 1.5 Flash (Model as a Service - MaaS)**: *Kami menggunakan API LLM Multimodal Gemini untuk menganalisis gambar struk belanja. Gemini melakukan OCR cerdas secara real-time dan langsung memformat teks struk ke bentuk JSON terstruktur.*
> 5. **Google Sheets (Software as a Service - SaaS)**: *Sebagai database cloud terpusat. Data yang sudah terstruktur disimpan langsung ke baris Google Sheets milik pengguna secara terintegrasi.*
> 
> *Mengapa arsitektur ini dipilih? Pertama, efisiensi biaya. Sistem ini berjalan sepenuhnya pada batas gratis (free tier) masing-masing penyedia layanan, sehingga biaya operasionalnya adalah nol rupiah. Kedua, performa tinggi. Pemrosesan OCR berat yang biasanya membebani memori ponsel dipindahkan sepenuhnya ke server superkomputer Google melalui Gemini API."*

---

### BAGIAN 3: DEMO APLIKASI SECARA LANGSUNG (LIVE DEMO) (Durasi: 5 - 8 Menit)
* **Visual:** Perekaman layar (screen recording) browser desktop dengan mode responsif mobile, atau rekaman layar smartphone secara langsung.
* **Tindakan Presenter:** Memandu penonton melalui alur kerja aplikasi secara bertahap.

**Langkah-langkah Demo & Script:**
1. **Langkah 1: Halaman Login (Google OAuth)**
   > *"Sekarang kita berada di halaman utama aplikasi. Antarmuka web ini dirancang dengan gaya glassmorphic CSS yang modern dan responsif untuk mobile. Langkah pertama yang dilakukan oleh pengguna adalah melakukan login dengan menekan tombol 'Sign In with Google'. Proses ini dialihkan secara aman ke halaman autentikasi resmi Google."*
   
2. **Langkah 2: Menjelaskan Mode Sandbox (Mock API)**
   > *"Setelah berhasil login, pengguna akan diarahkan ke dashboard utama. Di sini, saya menyediakan fitur **Sandbox Mode**. Fitur ini sangat berguna bagi pengguna yang ingin menguji coba aplikasi tanpa perlu memasukkan API key Gemini asli. Mari kita coba mengunggah sebuah struk belanja dalam mode Sandbox ini. Sistem secara otomatis menghasilkan simulasi ekstraksi data JSON dengan cepat untuk memastikan komponen frontend dan penyimpanan terhubung dengan baik."*

3. **Langkah 3: Menggunakan Cloud Mode (Pemindaian Struk Riil dengan Gemini)**
   > *"Selanjutnya, kita akan berpindah ke **Cloud Mode**. Di sini, kita akan menggunakan API key Google Gemini yang sesungguhnya untuk memproses gambar struk belanja asli. Saya akan memilih gambar struk belanja dari galeri. Gambar ini dikonversi menjadi format Base64 di browser dan dikirim ke backend serverless Vercel.*
   
   *Di backend, Gemini 1.5 Flash menganalisis citra struk ini, mengekstrak Nama Merchant (misalnya 'Indomaret'), Tanggal Transaksi, detail item barang, total belanja, dan memprediksi kategori pengeluarannya. Proses ekstraksi selesai, dan hasilnya muncul di layar dalam waktu beberapa detik saja!"*

4. **Langkah 4: Verifikasi Update Database (Google Sheets)**
   > *"Setelah data berhasil diekstraksi, aplikasi secara otomatis mengirimkan request untuk menyimpan data tersebut ke Google Sheets database. Mari kita buka Google Sheets kita secara berdampingan. Seperti yang bisa Anda lihat di layar, baris baru berisi detail transaksi dari struk yang baru saja kita pindai langsung muncul secara real-time. Data ini sekarang aman tersimpan di cloud."*

---

### BAGIAN 4: DEMONSTRASI MODUL ANALISIS DATA (Durasi: 5 - 8 Menit)
* **Visual:** Menampilkan Jupyter Notebook (`analysis.ipynb`) di layar komputer.
* **Tindakan Presenter:** Menjelaskan blok-blok kode Python untuk pembersihan data, visualisasi, dan pelatihan model klasifikasi machine learning.

**Langkah-langkah Penjelasan & Script:**
1. **Langkah 1: Sinkronisasi dan Loading Dataset**
   > *"Bagian berikutnya dari proyek ini adalah analisis data transaksi. Saya telah menulis Jupyter Notebook dengan nama file 'analysis.ipynb'. Pertama, kita mengimpor pustaka penting seperti Pandas, Scikit-Learn, dan Matplotlib. Kita menarik dataset transaksi secara langsung dari cloud database Google Sheets menggunakan URL ekspor CSV."*

2. **Langkah 2: Data Preprocessing (Pembersihan Data)**
   > *"Sebelum melatih model machine learning, data harus dibersihkan. Kita menangani nilai kosong (missing values), menyelaraskan tipe data tanggal dan nominal uang, serta melakukan normalisasi teks pada kolom nama merchant dengan mengubah huruf kapital menjadi huruf kecil (lowercase) serta menghapus karakter simbol khusus."*

3. **Langkah 3: Feature Engineering & Pembagian Data (Train/Test Split)**
   > *"Untuk mengubah teks nama merchant menjadi bentuk yang dapat dipahami komputer, kita menggunakan metode TF-IDF Vectorizer. Setelah fitur teks siap, kita membagi dataset dengan rasio **80% untuk data latih (training set)** dan **20% untuk data uji (testing set)** menggunakan fungsi train_test_split dari Scikit-Learn."*

4. **Langkah 4: Pelatihan Model Klasifikasi (Machine Learning Model)**
   > *"Untuk memprediksi kategori pengeluaran transaksi secara otomatis berdasarkan nama merchant, kita melatih model klasifikasi **Naive Bayes (MultinomialNB)** atau **Logistic Regression**. Model ini dilatih menggunakan data training yang berisi riwayat merchant dan kategori yang sudah dikoreksi sebelumnya."*

5. **Langkah 5: Evaluasi Model (Confusion Matrix & Grafik)**
   > *"Mari kita lihat hasil evaluasi model kita pada data uji. Seperti yang tampak pada output notebook, model kami berhasil mencapai akurasi sebesar **88%**. Kita juga memplot **Confusion Matrix** menggunakan Seaborn untuk melihat performa detail masing-masing kategori.*
   
   *Di sini terlihat bahwa kategori Utilities dan Transport memiliki presisi yang sangat tinggi karena kata kuncinya yang unik (seperti 'PLN' atau 'Gojek'). Sementara itu, terdapat sedikit tumpang tindih antara kategori Groceries dan Food & Beverage karena beberapa minimarket menjual keduanya. Kami juga menampilkan grafik visualisasi tren pengeluaran bulanan pengguna."*

---

### BAGIAN 5: KESIMPULAN & TANYA JAWAB (Q&A) (Durasi: 3 Menit)
* **Visual:** Wajah presenter kembali ke kamera depan penuh. Menampilkan slide kesimpulan dan ceklis komponen penilaian.
* **Tindakan Presenter:** Merangkum pencapaian proyek, memverifikasi kriteria kelulusan dari PDF instruksi, mengucapkan terima kasih, dan menutup presentasi.

**Script Bahasa Indonesia:**
> *"Sebagai kesimpulan, proyek Smart Receipt Scanner & Expense Logger ini berhasil mengintegrasikan solusi komputasi awan serverless dengan kecerdasan buatan untuk menyelesaikan masalah pencatatan keuangan harian secara praktis dan otomatis.*
> 
> *Bila merujuk pada komponen penilaian proyek akhir:*
> 1. **Inovasi Penggunaan Cloud Computing (25%)**: *Telah diimplementasikan dengan baik menggunakan teknologi serverless terintegrasi (Vercel Functions + Google OAuth IDaaS + Gemini MaaS + Google Sheets SaaS).*
> 2. **Kelengkapan Tahapan Analisis Data (30%)**: *Proses analisis data dari crawling, pembersihan data, rekayasa fitur, split data, pelatihan model machine learning, hingga evaluasi matriks performa telah diselesaikan secara lengkap di Jupyter Notebook.*
> 3. **Kode Program (25%)**: *Seluruh repositori kode program telah diuji coba dan berjalan tanpa error baik di lokal maupun di cloud production.*
> 4. **Kualitas Laporan & Video (20%)**: *Telah disusun laporan komprehensif berformat markdown dengan referensi literatur pendukung yang lengkap.*
> 
> *Demikian presentasi dari proyek akhir Komputasi Awan ini. Saya sangat terbuka terhadap segala masukan, pertanyaan, maupun saran dari Ibu Yutika Amelia Effendi, Ph.D. demi penyempurnaan sistem ini di masa mendatang.*
> 
> *Terima kasih atas perhatiannya, mohon maaf apabila ada kesalahan kata. Selamat pagi/siang/sore."*
