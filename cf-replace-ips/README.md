## Tambahkan atau ganti subdomain Cloudflare menggunakan IP yang terdaftar

Skrip ini adalah skrip Bash yang dirancang untuk mengubah catatan DNS di Cloudflare untuk subdomain tertentu. Ini akan menanyakan kredensial Cloudflare dan detail modifikasi catatan A kepada pengguna, lalu menghapus catatan A yang ada untuk subdomain yang ditentukan dan menambahkan catatan A baru ke subdomain yang sama di cloudflare Anda berdasarkan IP yang tercantum dalam file CSV.

Setelah menerima informasi yang diperlukan untuk mengakses Cloudflare, subdomain dan jalur file CSV, skrip ini menyimpan informasi ini untuk digunakan nanti dalam file konfigurasi di jalur eksekusi skrip.

Skrip ini menggunakan Cloudflare API untuk mengambil data A yang ada untuk subdomain, menghapusnya, dan menambahkan data A baru untuk setiap alamat IP yang tercantum dalam file CSV.

Untuk menjalankan skrip, Anda harus memiliki yang berikut ini:

- Akun Cloudflare dengan kunci API, ID Zona, dan alamat email yang terkait dengannya.
- File CSV yang berisi daftar alamat IP baru untuk subdomain di mana setiap IP tercantum dalam satu baris.
- Script disimpan dalam file dengan ekstensi ".sh".
- File skrip harus dapat dieksekusi menggunakan perintah "chmod +x cf-replace-ips.sh".
### Linux/Mac
Untuk menjalankan skrip di terminal MacOSX/Linux, unduh dan ekstrak folder skrip ke folder beranda Anda, lalu navigasikan ke folder tersebut, lalu lakukan hal berikut:
```
cd ~/cf-replace-ips
bash ./cf-replace-ips.sh
```

### jendela
Untuk Windows, Anda perlu menginstal paket untuk menjalankan skrip bash, saya sarankan menginstal [Cygwin](https://www.cygwin.com) yang sesuai berdasarkan versi Windows Anda.
Untuk menjalankan skrip di Cygwin, unduh skrip dan salin folder skrip ke folder rumah Cygwin Anda (biasanya terletak di 'C:\Cygwin\home\namaAnda'), lalu jalankan Cygwin dan ikuti langkah-langkah di bawah ini Berikan:
```
cd ~/cf-replace-ips
bash ./cf-replace-ips.sh
```

Saat skrip dijalankan, skrip tersebut meminta pengguna untuk kredensial Cloudflare dan detail modifikasi data A. Jika Anda sudah memberikan nilai ini, nilai tersebut akan ditampilkan kepada pengguna sebagai default.

Skrip ini harus digunakan dengan hati-hati, karena dapat mengubah data DNS untuk subdomain, yang berpotensi memengaruhi ketersediaan situs web. Disarankan untuk mengujinya di lingkungan non-produksi terlebih dahulu.