# Lab4. Command Line Interface (CLI) pada MikroTik

## 1. Pengertian CLI

**Command Line Interface (CLI)** merupakan metode konfigurasi MikroTik menggunakan perintah berbasis teks. Berbeda dengan Winbox yang menggunakan tampilan **GUI**, CLI memungkinkan konfigurasi dilakukan secara langsung melalui terminal.

CLI sangat berguna untuk memahami struktur perintah MikroTik dan sering digunakan dalam pembelajaran jaringan seperti **GNS3** dan **EVE-NG**.

## 2. Akses Terminal MikroTik

Terminal MikroTik dapat diakses melalui beberapa metode, antara lain:

* **Winbox → Terminal**
* **PuTTY → SSH / Telnet**
* **CMD → Telnet**
* **Console**
* **TikApp**

## 3. Perintah Dasar MikroTik

Berikut beberapa konfigurasi yang dapat dilakukan melalui CLI:

##### A. Mengganti Identitas Router

```bash
/system identity set name=MikroTik-LAB
```

##### B. Membuat Password Admin

```bash
/password
```

##### C. Membuat User Baru

```bash
/user add name=adminlab password=12345 group=full
```

##### D. Melihat Daftar User

```bash
/user print
```

##### E. Melihat Lisensi

```bash
/system license print
```

##### F. Melihat Interface

```bash
/interface print
```

##### G. Mengubah Nama Interface

```bash
/interface set ether1 name=WAN
```

##### H. Menambahkan IP Address

```bash
/ip address add address=192.168.10.1/24 interface=ether1
```

##### I. Melihat IP Address

```bash
/ip address print
```

##### J. Mengubah IP Address

```bash
/ip address set [find address="192.168.10.1/24"] address=192.168.20.1/24
```

##### K. Menambahkan NAT

```bash
/ip firewall nat add chain=srcnat out-interface=ether1 action=masquerade
```

##### L. Melihat Konfigurasi NAT

```bash
/ip firewall nat print
```

##### M. Menambahkan Gateway

```bash
/ip route add gateway=192.168.10.254
```

##### N. Melihat Routing

```bash
/ip route print
```

##### O. Mengatur DNS

```bash
/ip dns set servers=8.8.8.8
```

##### P. Melihat DNS

```bash
/ip dns print
```

##### Q. Melakukan Ping

```bash
/ping 8.8.8.8
```

## 4. Bantuan Perintah CLI

MikroTik menyediakan fitur bantuan untuk mempermudah pengguna ketika lupa sintaks atau ingin mengetahui perintah yang tersedia.

##### A. Menggunakan TAB

Tekan **TAB dua kali** untuk menampilkan pilihan perintah yang tersedia.

```bash
/ip address [TAB][TAB]
```

##### B. Menggunakan Tanda Tanya (?)

Tanda **?** dapat digunakan untuk melihat perintah beserta pilihan yang tersedia pada menu tertentu.

```bash
/ip address ?
```

##### C. Menyingkat Perintah

Beberapa perintah dapat ditulis secara singkat selama penulisan tersebut tidak menimbulkan kerancuan.

Contoh:

```bash
/ip add print
```

dapat digunakan untuk mengarah ke perintah:

```bash
/ip address print
```

##### D. Kembali ke Menu Sebelumnya

Gunakan perintah berikut untuk kembali satu tingkat ke menu sebelumnya:

```bash
..
```

## 5. Kesimpulan

CLI MikroTik merupakan cara konfigurasi router menggunakan teks melalui terminal. Metode ini memberikan pemahaman yang lebih baik mengenai struktur konfigurasi RouterOS dan dapat digunakan sebagai alternatif Winbox.

Dengan memahami perintah dasar, penggunaan **TAB**, tanda **?**, serta navigasi direktori menggunakan **..**, proses konfigurasi melalui CLI menjadi lebih mudah dan efisien.
