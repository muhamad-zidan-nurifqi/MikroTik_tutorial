# Lab2. Default Configuration 

<img width="1536" height="1024" alt="ChatGPT Image 12 Jul 2026, 22 52 30" src="https://github.com/user-attachments/assets/4d9a7a29-1e2c-49d2-8517-8d4502db1222" />

 
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

- WAN
- LAN
- Wireless
- DHCP Client
- DHCP Server
- DNS
- Firewall
- NAT
- IP Address

# C. Akses Awal MikroTik

Pada konfigurasi default, ether1 digunakan sebagai WAN Port.

Port tersebut telah mendapatkan perlindungan dari Firewall. Pada bagian:

```IP → Firewall → Filter Rules```

<img width="750" height="477" alt="Screenshot 2026-08-12 202716" src="https://github.com/user-attachments/assets/06e07980-7008-4442-bd20-0caa4b800470" />


terdapat aturan yang melakukan Drop terhadap input dari ether1.

Akibatnya, MikroTik tidak dapat langsung diakses melalui ether1 menggunakan MAC Address pada Winbox.

Untuk melakukan akses awal, gunakan port:

ether2
ether3
ether4

<img width="1536" height="1024" alt="ChatGPT Image 9 Agu 2026, 19 21 36" src="https://github.com/user-attachments/assets/02c28324-bf04-47de-a63e-a18d2858172c" />


---

# D. Akses MikroTik Menggunakan Winbox

Langkah akses MikroTik menggunakan Winbox:

1. Hubungkan MikroTik

Hubungkan komputer dengan MikroTik melalui port LAN:

<img width="1536" height="1024" alt="ChatGPT Image 9 Agu 2026, 19 21 36" src="https://github.com/user-attachments/assets/d1f638df-3929-4a30-8878-4ebbd73bc0b8" />

2. Buka Winbox




Jalankan aplikasi Winbox pada komputer.

3. Cari MikroTik

Pada bagian Neighbors, cari perangkat MikroTik yang terhubung.

<img width="1920" height="396" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/b256e1c9-793a-4c76-8611-9e740f570510" />


4. Pilih MikroTik

Pilih perangkat MikroTik menggunakan MAC Address atau IP Address yang tersedia.

5. Login

Masukkan username dan password sesuai konfigurasi perangkat.

6. Periksa Default Configuration

Setelah berhasil masuk, akan muncul informasi mengenai konfigurasi default MikroTik.

<img width="661" height="494" alt="Screenshot (28)" src="https://github.com/user-attachments/assets/19f7bee5-caa1-42f3-8959-13cba2886ff2" />


Tekan:

OK

untuk melanjutkan.

---

# E. Konfigurasi Default Router Mode

Pada Router Mode, terdapat beberapa konfigurasi bawaan MikroTik.

- Konfigurasi	Status / Nilai
- Port WAN	ether1
- DHCP Client	Enabled
- Firewall	Enabled
- Wireless	Bagian dari LAN Bridge
- IP LAN	192.168.88.1/24
- IP Address LAN Default
- 192.168.88.1/24

IP tersebut merupakan IP Address default yang digunakan pada jaringan LAN MikroTik.
