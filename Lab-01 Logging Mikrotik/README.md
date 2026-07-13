# Lab1. Logging in MikroTik

Pada panduan ini akan dijelaskan beberapa metode yang dapat digunakan untuk mengakses atau melakukan **remote login ke router MikroTik**. Setiap metode memiliki fungsi yang sama, yaitu untuk masuk ke sistem MikroTik, tetapi menggunakan aplikasi dan port yang berbeda.

Sebelum memulai, pastikan router MikroTik telah terhubung ke komputer menggunakan **kabel RJ45**, seperti pada topologi jaringan yang telah dibuat. Selain itu, pastikan perangkat berada dalam kondisi **Default Configuration** agar proses login berjalan dengan lancar.

<img width="1536" height="1024" alt="ChatGPT Image 12 Jul 2026, 22 52 30" src="https://github.com/user-attachments/assets/f505d774-a441-40e3-a99e-4fbb72dcfcc1" />

---

# 1. Login Menggunakan Winbox

Winbox merupakan aplikasi resmi dari MikroTik yang paling banyak digunakan karena tampilannya sederhana dan mudah digunakan. Aplikasi ini bekerja melalui **port 8291/TCP**.

### Langkah-langkah

1. Unduh aplikasi Winbox melalui situs resmi MikroTik atau gunakan file yang telah disediakan.
2. Jalankan aplikasi Winbox, kemudian pilih menu **Neighbors** dan klik **Refresh**.
3. Setelah router terdeteksi, pilih **MAC Address** agar koneksi lebih stabil dibandingkan menggunakan IP Address.
4. Masukkan informasi login berikut:

   * Username: **admin**
   * Password: *(kosong)*
5. Klik tombol **Connect**.

Apabila proses berhasil, maka akan muncul tampilan utama Winbox dan router siap dikonfigurasi.

---

# 2. Login Melalui WebFig

WebFig adalah antarmuka berbasis web yang memungkinkan pengguna mengelola MikroTik tanpa harus menginstal aplikasi tambahan. Layanan ini menggunakan **port 80/TCP**.

### Langkah-langkah

1. Buka browser, misalnya Google Chrome atau Microsoft Edge.
2. Pada kolom alamat, masukkan IP default MikroTik:

```text
192.168.88.1
```

3. Login menggunakan:

   * Username: **admin**
   * Password: *(kosong)*
4. Tekan **Enter** atau klik **Login**.

Jika berhasil, halaman WebFig akan ditampilkan dan Anda dapat mulai melakukan konfigurasi melalui browser.

---

# 3. Login Menggunakan Telnet atau SSH

Selain menggunakan tampilan grafis, MikroTik juga dapat diakses melalui **Command Line Interface (CLI)**.

### Telnet

* Menggunakan **port 23/TCP**.
* Protokol ini sudah jarang digunakan karena data yang dikirim tidak terenkripsi.

### SSH

* Menggunakan **port 22/TCP**.
* Lebih aman karena komunikasi telah dienkripsi, sehingga lebih direkomendasikan.

### Langkah-langkah

1. Unduh dan buka aplikasi PuTTY.
2. Masukkan alamat IP MikroTik:

```text
192.168.88.1
```

3. Tentukan nomor port sesuai protokol yang dipilih:

   * **22** untuk SSH.
   * **23** untuk Telnet.
4. Pilih jenis koneksi (**SSH** atau **Telnet**).
5. Klik **Open**.
6. Login menggunakan username **admin** dan password dikosongkan.

Apabila berhasil, akan muncul tampilan terminal MikroTik (CLI) yang siap digunakan untuk menjalankan perintah.

---

# 4. Transfer File Menggunakan FTP

FTP (**File Transfer Protocol**) merupakan layanan yang digunakan untuk mengirim atau mengambil file dari router MikroTik. Protokol ini bekerja pada **port 20 dan 21/TCP**.

Melalui FTP, pengguna dapat memindahkan file konfigurasi, backup, maupun file lainnya antara komputer dan MikroTik.

### Langkah-langkah

1. Tekan **Windows + R**.
2. Ketik:

```text
optionalfeatures
```

3. Aktifkan fitur **FTP Client** (atau fitur yang tersedia pada versi Windows yang digunakan), kemudian klik **OK**.
4. Buka **Command Prompt (CMD)**.
5. Jalankan perintah berikut:

```text
ftp 192.168.88.1
```

6. Login menggunakan:

   * Username: **admin**
   * Password: *(kosong)*

Setelah berhasil login, Anda dapat mengunggah maupun mengunduh file dari router MikroTik.

---

# Kesimpulan

MikroTik menyediakan beberapa metode akses, yaitu **Winbox**, **WebFig**, **Telnet**, **SSH**, dan **FTP**. Masing-masing memiliki kelebihan dan fungsi yang berbeda, sehingga pengguna dapat memilih metode yang paling sesuai dengan kebutuhan.

Agar proses koneksi berhasil, pastikan:

* Router telah terhubung ke komputer menggunakan kabel RJ45.
* Lampu indikator pada port Ethernet menyala.
* IP Address dan port yang digunakan sudah benar.
* MikroTik masih berada pada konfigurasi bawaan (Default Configuration).

Dengan memahami berbagai metode akses tersebut, proses konfigurasi dan pengelolaan router MikroTik akan menjadi lebih mudah.

---

# Penutup

Demikian panduan mengenai beberapa cara mengakses router MikroTik. Semoga materi ini dapat membantu dalam proses belajar maupun praktik konfigurasi jaringan.

Terima kasih atas perhatiannya.

**Wassalamu'alaikum Wr. Wb.**




