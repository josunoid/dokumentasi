Panduan Instalasi Ubuntu Server adalah panduan bagaimana cara menggunakan Ubuntu sebagai sistem operasi untuk membangun sebuah server analitik. Aplikasi server yang dibahas yaitu Fremis, Visionaire, PostgreSQL, Vanilla Dashboard dsb. 
## Keterampilan dan Pengetahuan Pendukung
Hal-hal yang dapat mendukung dalam memahami langkah-langkah konfigurasi server dalam panduan ini:

1. Pengetahuan jaringan komputer.
2. Paham struktur direktori di Linux.
3. Paham atribut file dan hak akses di Linux.
4. Dapat menggunakan perintah dasar Linux.
5. Dapat menggunakan text editor berbasis CLI (Command Line Interface).

## Persiapan
1. Unduh [Ubuntu Server ISO](https://ubuntu.com/download/server)
2. Persiapkan media instalasi, seperti USB bootable atau CD/DVD.

## Proses Instalasi
1. Masukkan media instalasi yang sudah Anda persiapkan ke dalam komputer server.
2. Nyalakan komputer dan atur boot dari media instalasi.
3. Pilih opsi "Install Ubuntu Server" dari menu boot.
4. Pilih bahasa instalasi, lokasi, dan layout keyboard yang sesuai.
5. Atur nama host, user, dan kata sandi administrator (root).
6. Pilih tipe instalasi (standalone server atau yang lainnya).
7. Partisi hard drive sesuai kebutuhan (20% untuk partisi  / (root), 80% untuk partisi /data)
8. Konfirmasi partisi dan mulai proses instalasi.
9. Saat diminta, masukkan pilihan software tambahan, seperti server SSH (wajib)
10. Tunggu hingga instalasi selesai.
11. Setelah selesai, reboot sistem.

## Konfigurasi Lanjutan
1. Setel konfigurasi jaringan, seperti IP Address dan DNS.
2. Update dan upgrade paket tambahan yang dibutuhkan.
3. Pastikan semua konfigurasi dan pengaturan telah diuji dan berjalan dengan baik.
4. Buat dokumentasi tambahan tentang konfigurasi khusus dan panduan administrasi.

Dokumentasi ini hanya memberikan panduan umum. Anda harus mengadaptasikannya sesuai dengan kebutuhan user
