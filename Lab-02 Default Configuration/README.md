# LAB 2 — DEFAULT CONFIGURATION MIKROTIK

 Dokumentasi Praktikum MikroTik RouterOS  
 
---

##  A. Tujuan Lab

Setelah membaca lab ini, diharapkan dapat:

1. Memahami apa yang dimaksud dengan Default Configuration pada MikroTik.
2. Mengetahui konfigurasi bawaan yang tersedia pada MikroTik.
3. Memahami fungsi port WAN dan LAN.
4. Mengetahui IP Address default pada jaringan LAN.
5. Mengetahui konfigurasi WLAN pada MikroTik.
6. Mengetahui fungsi DHCP Server dan DHCP Client.
7. Mengetahui konfigurasi DNS, Firewall, dan NAT.
8. Memahami cara mengakses MikroTik menggunakan Winbox.

---

#  B. Pengertian Default Configuration

**Default Configuration** merupakan konfigurasi bawaan yang telah disediakan oleh MikroTik ketika perangkat pertama kali digunakan.

Konfigurasi ini dibuat agar MikroTik dapat digunakan dengan lebih mudah tanpa harus melakukan konfigurasi jaringan dari awal.

Pada konfigurasi default, MikroTik telah memiliki beberapa pengaturan dasar seperti:

```text
WAN
LAN
Wireless
DHCP Client
DHCP Server
DNS
Firewall
NAT
IP Address
```

# C. Akses Awal MikroTik

Pada konfigurasi default, ether1 digunakan sebagai WAN Port.

Port tersebut telah mendapatkan perlindungan dari Firewall. Pada bagian:

```IP → Firewall → Filter Rules```

terdapat aturan yang melakukan Drop terhadap input dari ether1.

Akibatnya, MikroTik tidak dapat langsung diakses melalui ether1 menggunakan MAC Address pada Winbox.

Untuk melakukan akses awal, gunakan port:

ether2
ether3
ether4

---

# D. Akses MikroTik Menggunakan Winbox

Langkah akses MikroTik menggunakan Winbox:

1. Hubungkan MikroTik

Hubungkan komputer dengan MikroTik melalui port LAN:

2. Buka Winbox

Jalankan aplikasi Winbox pada komputer.

3. Cari MikroTik

Pada bagian Neighbors, cari perangkat MikroTik yang terhubung.

4. Pilih MikroTik

Pilih perangkat MikroTik menggunakan MAC Address atau IP Address yang tersedia.

5. Login

Masukkan username dan password sesuai konfigurasi perangkat.

6. Periksa Default Configuration

Setelah berhasil masuk, akan muncul informasi mengenai konfigurasi default MikroTik.

Tekan:

OK

untuk melanjutkan.

---

# E. Konfigurasi Default Router Mode

Pada Router Mode, terdapat beberapa konfigurasi bawaan MikroTik.

Konfigurasi	Status / Nilai
Port WAN	ether1
DHCP Client	Enabled
Firewall	Enabled
Wireless	Bagian dari LAN Bridge
IP LAN	192.168.88.1/24
IP Address LAN Default
192.168.88.1/24

IP tersebut merupakan IP Address default yang digunakan pada jaringan LAN MikroTik.
