\# LAPORAN ANALISIS PERBANDINGAN: VM VS CONTAINER

\*\*Mata Kuliah:\*\* Sistem Operasi

\*\*Nama:\*\* IID MUJAHID

\*\*NIM:\*\* 241111102



\## 1. Pendahuluan

Laporan ini disusun untuk membandingkan dua teknologi virtualisasi yang digunakan dalam pengerjaan Soal 2, yaitu Virtual Machine (menggunakan Oracle VirtualBox) dan Containerization (menggunakan Docker). Analisis didasarkan pada pengalaman langsung selama proses instalasi dan deployment web server.



\## 2. Tabel Perbandingan Teknis

Berdasarkan praktik yang telah dilakukan, berikut adalah perbedaan mendasar antara keduanya:



| Fitur | Virtual Machine (VirtualBox) | Docker Container |

| :--- | :--- | :--- |

| \*\*Arsitektur\*\* | Memerlukan Guest OS penuh (kernel terpisah). | Berbagi kernel dengan Host OS (Linux Kernel). |

| \*\*Efisiensi RAM\*\* | Memakan RAM secara statis (misal: 2GB terkunci untuk VM). | Menggunakan RAM secara dinamis sesuai beban aplikasi. |

| \*\*Ukuran Storage\*\* | Sangat besar (ukuran file VDI mencapai hitungan GigaByte). | Sangat kecil (image Nginx/MySQL hanya hitungan MegaByte). |

| \*\*Waktu Booting\*\* | Lambat (perlu proses booting OS dari awal). | Instan (container langsung jalan dalam hitungan detik). |

| \*\*Kemudahan Update\*\* | Harus masuk ke OS dan update manual satu per satu. | Cukup ganti versi di file config dan jalankan `--build`. |



\## 3. Analisis Berdasarkan Pengalaman Praktikum



\### A. Kompleksitas Instalasi

Pada bagian Virtualization (2a), proses instalasi Ubuntu Server memakan waktu cukup lama karena harus melakukan konfigurasi ISO, partisi disk, dan setup user manual. Sedangkan pada Containerization (2b), seluruh infrastruktur (Nginx \& MySQL) dapat dibangun secara otomatis hanya dengan satu file konfigurasi `docker-compose.yml`.



\### B. Masalah Perizinan (Permission Issues)

Selama praktikum, ditemukan kendala "403 Forbidden" pada Docker karena file disimpan di Shared Folder Windows. Hal ini membuktikan bahwa meskipun Docker sangat efisien, ia tetap bergantung pada sistem izin (permission) kernel Linux yang harus diatur menggunakan perintah `chmod`.



\### C. Portabilitas

Struktur direktori project yang sudah dirapikan memudahkan pemindahan tugas. Jika tugas ini dipindahkan ke laptop lain, pengguna hanya perlu menginstall Docker dan menjalankan perintah `up`, tanpa perlu mengulang proses instalasi Ubuntu dari nol.



\## 4. Kesimpulan Akhir

Untuk kebutuhan deployment aplikasi web skala kecil hingga menengah seperti tugas UAS ini, \*\*Docker Container adalah pilihan yang jauh lebih efisien\*\* dibandingkan VM karena menghemat resource laptop dan mempercepat waktu kerja. VM hanya digunakan jika kita benar-benar membutuhkan lingkungan sistem operasi yang terisolasi secara total dari host.