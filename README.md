# Proyek UAS: Simulasi ATM Sederhana

## Deskripsi Proyek
Proyek ini adalah sebuah program Simulasi Anjungan Tunai Mandiri (ATM) sederhana berbasis CLI (*Command Line Interface*) yang dikembangkan menggunakan bahasa pemrograman Python.Proyek ini dikerjakan untuk memenuhi tugas Ujian Akhir Semester (UAS) mata kuliah Algoritma Pemrograman di Institut Teknologi dan Bisnis Asia Malang, tahun 2026.

Simulasi ini dirancang untuk menerapkan logika dasar sistem transaksi perbankan, melatih struktur kontrol pemrograman (seperti `if/else` dan `looping`), serta manajemen data menggunakan JSON.

## Fitur Utama
* **Autentikasi (Login)**: Pengguna harus memasukkan 3 digit Akun Bank dan 6 digit PIN ATM[cite: 64]. [cite_start]Sistem memberikan batas maksimal 3 kali percobaan salah sebelum program dihentikan otomatis[cite: 60, 65, 67, 78].
* **Cek Saldo**: Menampilkan sisa saldo pengguna saat ini, yang sudah dikonversi secara otomatis ke dalam format mata uang Rupiah[cite: 109, 110].
* **Setor Tunai (Deposit)**: Memungkinkan pengguna menyetorkan uang ke dalam rekening, dengan aturan jumlah yang disetor harus lebih dari 0[cite: 115, 116].
* **Tarik Tunai (Withdraw)**: Fitur untuk melakukan penarikan uang. [cite_start]Terdapat validasi agar penarikan gagal jika saldo tidak mencukupi (jumlah harus di antara 0 hingga total saldo)[cite: 127, 130].
* **Transfer Antar Pengguna**: Pengguna dapat memindahkan saldo ke rekening lain di dalam *database*[cite: 80, 85]. [cite_start]Fitur ini dilindungi dengan validasi akun tujuan, larangan transfer ke rekening sendiri, dan konfirmasi ulang nama penerima beserta nominal sebelum dieksekusi[cite: 90, 91, 95].

## Teknologi dan Struktur Data
* **Python Built-in Libraries**: Proyek ini dibangun tanpa *library* eksternal tambahan.
  * `json`: Digunakan untuk memuat (`load_data`) dan memperbarui (`save_data`) data dari file `user.json` yang bertindak sebagai *database*[cite: 36, 186].
  * `time`: Digunakan untuk menambahkan jeda (*delay*) satu detik pada terminal agar interaksi terasa lebih nyata[cite: 185].
  * `os`: Digunakan untuk memverifikasi apakah file *database* `user.json` tersedia di direktori saat program dijalankan[cite: 187, 199].
* **Error Handling**: Program menangkap kesalahan input (misalnya ketika *user* menginput huruf, padahal sistem meminta angka/`ValueError`) sehingga program tidak *crash*.

## Cara Menjalankan Program
1. Pastikan komputer Anda sudah terinstal Python.
2. Unduh atau *clone* repository ini ke lokal mesin Anda.
3. Pastikan file `user.json` (sebagai tempat penyimpanan data) berada di folder/direktori yang sama dengan skrip Python utama.
4. Buka terminal atau *command prompt*, arahkan ke folder proyek, dan jalankan program dengan perintah:
   `python nama_file_anda.py`
5. Gunakan data Akun Bank dan PIN yang terdapat di dalam `user.json` untuk mencoba masuk ke dalam sistem ATM.
