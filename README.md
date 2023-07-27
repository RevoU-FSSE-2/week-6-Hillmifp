[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/nj7iw4Wb)
Menjalankan Aplikasi Node.js dengan Docker di Visual Studio Code
Tutorial ini akan membimbing Anda dalam proses menjalankan aplikasi Node.js menggunakan Docker di Visual Studio Code. Tutorial ini berasumsi bahwa Anda memiliki proyek Node.js tanpa file package.json dan ingin mengemasnya dalam kontainer menggunakan Docker.

Persyaratan
Docker terpasang pada sistem Anda.
Visual Studio Code terpasang pada sistem Anda.
Langkah 1: Menyiapkan Aplikasi Node.js Anda
Pastikan Anda memiliki file-filenya dalam direktori "nodejs_project" (ganti dengan nama folder proyek sesungguhnya).

Langkah 2: Membuat Dockerfile
Di dalam direktori "nodejs_project", buat file bernama "Dockerfile" (tanpa ekstensi file) menggunakan teks editor. File ini akan berisi instruksi untuk membangun gambar Docker untuk aplikasi Node.js Anda.

Buka "Dockerfile" dan tambahkan konten berikut:

Dockerfile
Copy code
# Gunakan gambar resmi Node.js sebagai gambar dasar
FROM node:14

# Tetapkan direktori kerja di dalam kontainer
WORKDIR /usr/src/app

# Salin semua file dari direktori saat ini (proyek Node.js Anda) ke direktori kerja kontainer
COPY . .

# Tetapkan perintah default untuk menjalankan aplikasi Node.js Anda
CMD ["node", "app.js"]
Simpan dan tutup Dockerfile.

Langkah 3: Membangun Gambar Docker
Buka Visual Studio Code dan navigasikan ke direktori "nodejs_project".

Buka terminal terintegrasi di Visual Studio Code dan jalankan perintah berikut untuk membangun gambar Docker:

bash
Copy code
docker build -t my_node_app .
Catatan: Flag -t memberi tag pada gambar dengan nama "my_node_app", tetapi Anda dapat memilih nama lain sesuai preferensi.

Langkah 4: Menjalankan Kontainer Docker
Setelah gambar Docker dibangun, Anda dapat menjalankan kontainer Docker berdasarkan gambar tersebut.

Di terminal terintegrasi, jalankan perintah berikut:

bash
Copy code
docker run -d --name my_node_container my_node_app
Perintah ini menjalankan kontainer Docker dalam mode terlepas (-d), memberi nama kontainer sebagai "my_node_container" (--name), dan menggunakan gambar "my_node_app" yang telah kita bangun sebelumnya.

Langkah 5: Mengakses Aplikasi yang Berjalan
Dengan kontainer berjalan, Anda dapat mengakses aplikasi Node.js Anda di http://localhost:3000 (asumsi aplikasi berjalan pada port 3000 di dalam kontainer). Jika aplikasi Node.js Anda mendengarkan port lain, lakukan pemetaan port kontainer ke port di sistem host Anda menggunakan flag -p.

Contoh, jika aplikasi Node.js berjalan pada port 8080 di dalam kontainer, Anda dapat mengaksesnya di http://localhost:8080 dengan perintah berikut:
