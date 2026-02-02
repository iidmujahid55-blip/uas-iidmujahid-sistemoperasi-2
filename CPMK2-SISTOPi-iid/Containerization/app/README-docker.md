\# Dokumentasi Implementasi Docker (Containerization)



\## Deskripsi Project

Bagian ini berisi implementasi server menggunakan teknologi Container untuk efisiensi resource.

\- \*\*Web Server:\*\* Nginx (Image: `nginx:alpine`)

\- \*\*Database:\*\* MySQL (Image: `mysql:8.0`)

\- \*\*Port Mapping:\*\* Port 80 container diteruskan ke Port 8080 Host.



\## Struktur File

\- `docker-compose.yml`: File konfigurasi utama untuk menjalankan layanan Web dan Database secara bersamaan.

\- `Dockerfile`: File definisi image custom untuk Nginx.

\- `app/`: Folder tempat menyimpan source code (`index.html` dan `app.js`) yang terhubung langsung ke container (Volume Binding).



\## Cara Menjalankan (Deployment)

1\. Jalankan container: `docker compose up -d --build`

2\. Perbaikan Izin (Fix 403): `docker compose exec web chmod -R 755 /usr/share/nginx/html`

3\. Akses Website: http://localhost:8080