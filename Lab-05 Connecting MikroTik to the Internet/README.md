# LAB 5 — Menghubungkan MikroTik ke Internet

## 1. Tujuan

Lab ini membahas cara menghubungkan MikroTik ke internet melalui **Winbox (GUI)**. Konfigurasi dibagi menjadi dua metode, yaitu menggunakan **IP Dynamic** dan **IP Static**.

Pembagian interface:

```text
ether1-WAN → Terhubung ke Internet / ISP
ether2-LAN → Terhubung ke PC / Client
```

---

# A. Internet dengan IP Dynamic

IP Dynamic adalah alamat IP yang diperoleh MikroTik secara otomatis dari router ISP menggunakan layanan **DHCP Client**.

## 1. Menentukan Nama Interface

Buka **Winbox → Interfaces**.

Ubah nama interface:

```text
ether1 → ether1-WAN
ether2 → ether2-LAN
```

Tujuannya agar fungsi masing-masing port lebih mudah dikenali.

---

## 2. Mengatur DHCP Client pada WAN

Masuk ke:

```text
IP → DHCP Client → +
```

Kemudian atur:

```text
Interface : ether1-WAN
```

Klik:

```text
Apply → OK
```

MikroTik kemudian akan meminta IP secara otomatis dari router ISP.

Status IP dapat diperiksa pada bagian **DHCP Client**. Jika sudah mendapatkan **Address** dan statusnya aktif, berarti DHCP Client berhasil.

---

## 3. Mengecek IP Address

Buka:

```text
IP → Addresses
```

Pada menu tersebut dapat dilihat alamat IP yang terpasang pada interface MikroTik.

---

## 4. Menguji Koneksi Internet

Untuk memastikan MikroTik sudah terhubung ke internet, buka:

```text
Tools → Ping
```

Masukkan alamat:

```text
8.8.8.8
```

Kemudian klik **Start**.

Jika muncul balasan ping, koneksi dari MikroTik ke internet berhasil.

---

## 5. Mengatur IP LAN

Masuk ke:

```text
IP → Addresses → +
```

Isi:

```text
Address   : 192.168.10.1/24
Interface : ether2-LAN
```

Klik:

```text
Apply → OK
```

Konfigurasi ini digunakan sebagai alamat gateway untuk jaringan lokal.

---

## 6. Membuat NAT

Agar komputer pada jaringan LAN dapat mengakses internet melalui MikroTik, buat konfigurasi NAT.

Masuk ke:

```text
IP → Firewall → NAT → +
```

Pada tab **General**, isi:

```text
Chain         : srcnat
Out. Interface : ether1-WAN
```

Kemudian buka tab **Action**:

```text
Action : masquerade
```

Klik:

```text
Apply → OK
```

NAT akan menerjemahkan koneksi dari jaringan LAN sehingga dapat diteruskan melalui koneksi WAN.

---

# 2. Internet dengan IP Static

IP Static menggunakan alamat IP yang sudah ditentukan dan tidak diperoleh secara otomatis melalui DHCP.

Konfigurasi dilakukan melalui Winbox.

## 1. Memberikan IP Static pada WAN

Masuk ke:

```text
IP → Addresses → +
```

Masukkan IP yang diberikan oleh ISP.

Contoh format:

```text
Address   : IP-STATIC/Prefix
Interface : ether1-WAN
```

Klik:

```text
Apply → OK
```

> Nilai IP Static harus disesuaikan dengan data dari ISP. File sumber LAB 5 tidak memberikan nilai IP Static secara lengkap.

---

## 2. Mengatur Gateway

Masuk ke:

```text
IP → Routes → +
```

Masukkan gateway sesuai informasi dari ISP.

```text
Gateway : Gateway-ISP
```

Klik:

```text
Apply → OK
```

---

## 3. Mengatur DNS

Masuk ke:

```text
IP → DNS
```

Masukkan DNS Server yang digunakan.

Setelah itu klik:

```text
Apply → OK
```

---

## 4. Mengatur IP LAN

Masuk kembali ke:

```text
IP → Addresses → +
```

Masukkan:

```text
Address   : 192.168.10.1/24
Interface : ether2-LAN
```

Klik:

```text
Apply → OK
```

---

## 5. Membuat NAT

Masuk ke:

```text
IP → Firewall → NAT → +
```

Pada tab **General**:

```text
Chain          : srcnat
Out. Interface : ether1-WAN
```

Pada tab **Action**:

```text
Action : masquerade
```

Klik:

```text
Apply → OK
```

---

# C. Pemeriksaan Konfigurasi

Setelah semua konfigurasi selesai, lakukan pengecekan melalui Winbox:

```text
Interfaces
IP → Addresses
IP → DHCP Client
IP → Routes
IP → DNS
IP → Firewall → NAT
```

Kemudian lakukan pengujian koneksi melalui:

```text
Tools → Ping
```

Gunakan:

```text
8.8.8.8
```

Jika ping mendapatkan **reply**, MikroTik sudah dapat berkomunikasi dengan internet.

---

# D. Topologi Sederhana

```text
             INTERNET / ISP
                    │
                    │
              ether1-WAN
                    │
              ┌───────────┐
              │  MikroTik │
              └───────────┘
                    │
              ether2-LAN
                    │
                    │
                PC / Client
```

## E. Kesimpulan

MikroTik dapat dihubungkan ke internet melalui **Winbox GUI** menggunakan IP Dynamic maupun IP Static.

Pada konfigurasi Dynamic, MikroTik mendapatkan IP WAN secara otomatis melalui **DHCP Client**. Sementara itu, konfigurasi Static menggunakan IP, gateway, dan DNS yang diberikan oleh ISP.

Interface **ether1-WAN** berfungsi sebagai jalur internet, sedangkan **ether2-LAN** digunakan untuk jaringan lokal. NAT **masquerade** diperlukan agar client LAN dapat mengakses internet melalui MikroTik.

