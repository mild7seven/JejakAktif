# JejakAktif - OpenLayers Edition

Progressive Web App (PWA) untuk navigasi kebugaran yang digerakkan oleh **OpenLayers**, pustaka GIS (*Geographic Information System*) standar industri untuk pemetaan yang presisi dan arsitektur data vektor yang solid.

## Paradigma OpenLayers dalam Proyek Ini
Jika Anda membandingkan kode ini dengan Leaflet atau MapLibre, Anda akan menyadari beberapa fondasi kuat OpenLayers:
1. **Pemisahan Data dan Tampilan (Source vs Layer):** Penanda (Marker) dan garis rute (Path) dimasukkan ke dalam `ol.source.Vector` sebagai `Feature`. Sumber data ini kemudian di-render oleh `ol.layer.Vector`. Ini membuat pemrosesan ribuan titik GPS sangat ringan karena tidak mengotori DOM browser secara langsung.
2. **Proyeksi Koordinat (EPSG:3857 vs EPSG:4326):** OpenLayers sangat ketat secara kartografi. Koordinat murni dari GPS diubah menggunakan `ol.proj.fromLonLat()` sebelum digambar ke kanvas, memastikan geometri tidak mengalami distorsi visual.
3. **Auto-Fit Ekstensif:** Saat menekan tombol selesai, fungsi `vectorSource.getExtent()` langsung menghitung kotak pembatas (Bounding Box) dari seluruh garis rute, dan `map.getView().fit()` membuat kamera mundur menyesuaikan layar secara mulus dengan tambahan `padding` bawah agar tidak tertutup oleh antarmuka *dashboard* statistik.
