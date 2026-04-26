# JejakAktif

JejakAktif adalah Progressive Web App (PWA) berbasis lokasi (GPS) yang melacak rute pergerakan Anda, menghitung estimasi jumlah langkah, dan kalori yang terbakar.

## Fitur Utama
* **Filter Kendaraan Otomatis:** Sistem mendeteksi kecepatan real-time. Jika Anda bergerak di atas 7 km/jam (naik sepeda/motor/mobil/kereta), perhitungan langkah dan kalori otomatis dijeda hingga Anda kembali ke kecepatan berjalan normal.
* **Presisi GPS Tinggi:** Menggunakan algoritma Haversine formula dan parameter `enableHighAccuracy: true` dari HTML5 Geolocation API.
* **Peta Interaktif:** Terintegrasi dengan Leaflet.js dengan animasi pergerakan penanda lokasi (marker) dan penggambaran rute jejak (polyline) secara langsung.
* **PWA Ready:** Mendukung manifest dan Service Worker untuk di-install ke layar utama *smartphone* seperti aplikasi native.

## Cara Menggunakan
1. Pastikan file di-*hosting* melalui **HTTPS**. HTML5 Geolocation API tidak akan berfungsi pada koneksi HTTP biasa (kecuali di environment `localhost`).
2. Buka di browser *smartphone*. Setujui akses Lokasi (GPS).
3. Klik tombol **Mulai**. Berjalanlah, dan aplikasi akan menggambar rute Anda di atas peta.
4. Klik **Selesai** untuk meninjau keseluruhan metrik dan tampilan jauh peta rute Anda.

## Teknologi
* HTML, CSS, JavaScript (Vanilla)
* Leaflet.js & OpenStreetMap
