# uas-iidmujahid-sistemoperasi-2
\# Dokumentasi Virtualisasi



\## Tujuan

Dokumentasi ini dibuat untuk menjelaskan proses pembuatan dan konfigurasi

mesin virtual menggunakan Oracle VirtualBox sebagai bagian dari tugas UAS

mata kuliah Sistem Operasi.



\## Spesifikasi VM

\- \*\*OS:\*\* Ubuntu Server 24.04.3 LTS

\- \*\*Hypervisor:\*\* Oracle VirtualBox

\- \*\*CPU:\*\* 2 Core

\- \*\*RAM:\*\* 2 GB

\- \*\*Storage:\*\* 25 GB

\- \*\*Network:\*\* NAT dengan Port Forwarding (Host 8080 → Guest 8080)



\## Ringkasan Implementasi

Mesin virtual menjalankan Ubuntu Server 22.04 LTS dengan konfigurasi jaringan

NAT dan port forwarding agar layanan pada guest dapat diakses dari host.

Screenshot proses instalasi dan konfigurasi disertakan pada folder `screenshots`.



\## Detail Login (Credentials)

\- \*\*Username:\*\* Iid Mujahid-102

\- \*\*Password:\*\* 241111---



\## Cara Akses

1\. Jalankan VM di VirtualBox

2\. Buka browser di Windows dan akses: http://localhost:8080



\## Kesimpulan

Virtualisasi memungkinkan sistem operasi dijalankan secara terisolasi tanpa

mengganggu sistem utama dan mempermudah pengujian serta deployment layanan.
