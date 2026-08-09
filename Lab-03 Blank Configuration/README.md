# LAB 3 — BLANK CONFIGURATION MIKROTIK

## Pengertian Blank Configuration

Blank Configuration merupakan kondisi MikroTik ketika perangkat berada dalam keadaan tanpa konfigurasi jaringan bawaan. Kondisi ini biasanya digunakan ketika pengguna ingin memulai pengaturan router dari awal dan menentukan sendiri konfigurasi yang diperlukan.

Pada kondisi Blank Configuration, MikroTik tidak memiliki IP Address bawaan sehingga IP Address akan terlihat sebagai:

```text
0.0.0.0
```

Berbeda dengan Default Configuration yang sudah memiliki beberapa pengaturan dasar, Blank Configuration memberikan kebebasan kepada pengguna untuk menentukan konfigurasi MikroTik sesuai dengan kebutuhan jaringan.

## Membuat Blank Configuration

Ketika MikroTik pertama kali digunakan atau setelah dilakukan proses Reset Configuration, Winbox dapat menampilkan konfigurasi bawaan dari perangkat.

Jika konfigurasi bawaan tersebut ingin dihapus dan MikroTik ingin dikembalikan ke kondisi kosong, pengguna dapat memilih:

**Remove Configuration**

Jika MikroTik sebelumnya sudah memiliki konfigurasi dan ingin dikembalikan ke kondisi kosong, proses Reset Configuration dapat dilakukan dengan memilih:

**No Default Configuration**

Dengan memilih opsi tersebut, MikroTik tidak akan menggunakan konfigurasi default setelah proses reset selesai.

---

## Ciri-Ciri Blank Configuration

Beberapa kondisi yang dapat ditemukan pada MikroTik setelah menggunakan Blank Configuration antara lain:

### 1. IP Address

MikroTik tidak memiliki IP Address bawaan sehingga alamat yang terlihat adalah:

IP Address = 0.0.0.0

Walaupun tidak memiliki IP Address, MikroTik masih dapat diakses menggunakan Winbox melalui port Ethernet.

### 2. Interface Wireless

Pada Blank Configuration, interface wireless:

wlan1

berada dalam keadaan disabled.

Nama interface juga masih menggunakan nama bawaan dan belum dilakukan perubahan sesuai kebutuhan konfigurasi.

### 3. Firewall

Pada menu:

IP → Firewall → Filter Rules

tidak terdapat rule Firewall yang telah dikonfigurasi.

Hal tersebut menunjukkan bahwa bagian Firewall masih dalam keadaan kosong dan belum memiliki aturan yang dibuat sebelumnya.

---

## Perbedaan Default Configuration dan Blank Configuration

Secara sederhana, perbedaan keduanya dapat dilihat sebagai berikut:

### 1.Default Configuration :
- Memiliki konfigurasi bawaan	
- IP Address default tersedia
- Beberapa layanan sudah dikonfigurasi	
- Lebih mudah digunakan secara langsung	
- Cocok untuk pengguna pemula

### Blank Configuration :
- Tidak memiliki konfigurasi bawaan
-	IP Address 0.0.0.0
-	Konfigurasi masih kosong
-	Harus dikonfigurasi sesuai kebutuhan
-	Cocok untuk belajar konfigurasi dari awal
  
## Kelebihan Blank Configuration

Blank Configuration memiliki beberapa kelebihan, terutama bagi pengguna yang ingin memahami konfigurasi MikroTik secara lebih mendasar.

Beberapa kelebihannya yaitu:

Konfigurasi dapat dibuat dari awal.
Pengguna dapat menentukan pengaturan sesuai kebutuhan.
Tidak bergantung pada konfigurasi bawaan.
Cocok digunakan untuk pembelajaran MikroTik.
Membantu pengguna memahami fungsi dari setiap konfigurasi jaringan.

---

## Kesimpulan

Blank Configuration merupakan kondisi MikroTik yang belum memiliki konfigurasi jaringan bawaan. Pada kondisi ini, IP Address MikroTik akan berada pada:

```0.0.0.0```

Blank Configuration dapat digunakan sebagai titik awal untuk mempelajari konfigurasi MikroTik dari dasar. Pengguna dapat menentukan sendiri pengaturan jaringan yang diperlukan tanpa harus mengikuti konfigurasi bawaan perangkat.

Pada kondisi ini, interface wlan1 masih dalam keadaan disabled dan konfigurasi Firewall pada Filter Rules masih kosong.

Dengan menggunakan Blank Configuration, pengguna dapat lebih memahami bagaimana sebuah MikroTik dikonfigurasi dari awal serta mengetahui fungsi dari setiap bagian yang terdapat di dalam RouterOS.
