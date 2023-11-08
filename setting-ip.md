Berikut panduan langkah-demi-langkah untuk mengatur alamat IP statis di Ubuntu Server menggunakan Netplan:

## Langkah 1: Cek Nama Interface Jaringan
Sebelum kita mengatur alamat IP statis, kita perlu mengetahui nama antarmuka jaringan yang akan kita konfigurasi. Anda dapat mengecek nama antarmuka dengan perintah berikut:
``` console
ip a
```
Hasilnya akan menunjukkan daftar antarmuka jaringan yang ada di server Anda. Catat nama antarmuka yang akan diubah, biasanya bernama `ensX` (`X` adalah nomor).


## Langkah 2: Edit File Konfigurasi Netplan
1. Buka file konfigurasi Netplan menggunakan editor teks. Misalnya, kita akan mengedit file konfigurasi default yang biasanya bernama `00-netcfg.yaml`. Gantilah dengan nama file yang sesuai jika Anda memiliki nama file yang berbeda.
   ``` console
   sudo nano /etc/netplan/00-netcfg.yaml
   ```
2. Dalam file ini, Anda akan melihat sesuatu seperti ini:
   ``` console
   network:
     version: 2
     renderer: networkd
     ethernets:
       ensX:
         dhcp4: yes
   ```
   Gantilah `ensX` dengan nama antarmuka yang sesuai yang Anda catat sebelumnya.
3. Ubah konfigurasi `dhcp4` menjadi `no` untuk menonaktifkan alamat IP dinamis. Kemudian, tambahkan konfigurasi alamat IP statis di bawahnya, seperti ini:
   ``` console
   network:
     version: 2
     renderer: networkd
     ethernets:
       ensX:
        dhcp4: no
        addresses: [192.168.1.100/24] # Ganti dengan alamat IP dan subnet mask yang sesuai
        gateway4: 192.168.1.1 # Ganti dengan gateway Anda
        nameservers:
          addresses: [8.8.8.8, 8.8.4.4] # Ganti dengan DNS server yang Anda inginkan
   ```
Pastikan untuk mengganti alamat IP, subnet mask, gateway, dan server DNS sesuai dengan konfigurasi jaringan Anda.
4. Simpan perubahan (tekan `Ctrl` + `O`, lalu `Enter`) dan keluar dari editor (tekan `Ctrl` + `X`).

## Langkah 3: Terapkan Konfigurasi Netplan
Setelah mengedit file konfigurasi, Anda perlu menerapkan perubahan dengan menjalankan perintah berikut:
``` console
sudo netplan apply
```
## Langkah 4: Verifikasi Konfigurasi
Anda dapat memeriksa apakah konfigurasi telah berhasil diterapkan dengan menjalankan perintah:
``` console
ip a
```

Anda sekarang memiliki alamat IP statis yang diatur untuk antarmuka jaringan yang Anda konfigurasi. Pastikan untuk melakukan uji koneksi dan memastikan semuanya berfungsi dengan baik.

Ini adalah panduan dasar untuk mengatur alamat IP statis di Ubuntu Server menggunakan Netplan. Pastikan untuk mengganti nilai-nilai yang sesuai dengan konfigurasi jaringan Anda
