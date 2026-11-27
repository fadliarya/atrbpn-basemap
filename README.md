# ATR BPN Basemap (QGIS Plugin)

> ⚠️ **Plugin ini dihentikan (27 November 2026).**
> Atas permintaan pengelola layanan Peta Dasar ATR/BPN, plugin ini tidak lagi dikembangkan maupun didistribusikan, karena layanan tersebut diperuntukkan bagi kementerian/lembaga dan pemakaian tanpa izin resmi membebani server mereka. Mohon uninstall plugin ini dari QGIS (**Plugins > Manage and Install Plugins > Installed > ATR BPN Basemap > Uninstall**). Foto udara tetap bisa dilihat langsung di https://petadasar.atrbpn.go.id.
>
> **This plugin has been discontinued (27 November 2026)** at the request of the ATR/BPN Peta Dasar service operator. Please uninstall it from QGIS.

**[Bahasa Indonesia](#bahasa-indonesia) | [English](#english)**

Plugin QGIS untuk menampilkan dan mengekspor foto udara Peta Dasar ATR/BPN.
A QGIS plugin to display and export ATR/BPN Peta Dasar aerial imagery.

---

## Bahasa Indonesia

Plugin QGIS untuk menambahkan foto udara Peta Dasar ATR/BPN ([petadasar.atrbpn.go.id](https://petadasar.atrbpn.go.id)) sebagai basemap XYZ. URL tile diperbarui secara otomatis dari situs ATR/BPN, sehingga Anda tidak perlu mencari dan menyalin URL secara manual setiap kali alamatnya berubah. Foto udara juga dapat diekspor menjadi GeoTIFF.

### Fitur

- Menambahkan foto udara ATR/BPN sebagai layer XYZ dengan satu klik, lengkap dengan header Referer yang dibutuhkan server.
- Mendeteksi URL tile terbaru dari skrip peta di situs ATR/BPN, lalu menguji tile contoh sebelum dipakai.
- Memperbarui layer di proyek yang sedang terbuka dan koneksi XYZ di panel Browser.
- Pengecekan otomatis di latar belakang, paling sering sekali sehari (dapat dimatikan).
- Bila situs ATR/BPN berubah, plugin memakai URL cadangan dari konfigurasi di GitHub dan memberi tahu bila ada versi baru.
- Ekspor foto udara ke GeoTIFF dengan pilihan:
  - extent (canvas, layer, draw on canvas, atau koordinat manual),
  - pemotongan mengikuti poligon (opsional, bisa hanya fitur terpilih),
  - zoom level 16 sampai 21 (zoom 20 setara resolusi asli ±15 cm),
  - CRS output, ukuran piksel, dan metode resampling,
  - kompresi JPEG, DEFLATE, atau LZW, serta overview internal.
- Ekspor berjalan di latar belakang dan dapat dibatalkan dari panel Task.

### Persyaratan

- QGIS 3.22 atau lebih baru (diuji pada QGIS 3.44).
- Koneksi internet.

### Cara Pakai

Semua perintah ada di menu **Plugins > ATR BPN Basemap**:

| Menu | Fungsi |
|---|---|
| Tambahkan Foto Udara ATR/BPN | Menambahkan layer foto udara ke proyek (juga tersedia sebagai tombol di toolbar Plugins) |
| Ekspor foto udara ke GeoTIFF... | Mengunduh tile pada extent dan zoom level tertentu lalu menyimpannya sebagai GeoTIFF |
| Cek & perbarui URL dari situs ATR/BPN | Mencari URL tile terbaru secara manual |
| Atur URL secara manual... | Mengisi URL tile sendiri bila deteksi otomatis gagal |
| Cek otomatis saat QGIS dibuka | Menyalakan atau mematikan pengecekan otomatis |
| Tentang plugin | Informasi plugin, URL yang sedang dipakai, dan kredit data |

Catatan:
- Foto udara baru tampil mulai **zoom 16** (sekitar skala 1:8.000). Saat di-zoom out lebih jauh, layer memang terlihat kosong.
- Pada ekspor, perhatikan **estimasi** jumlah tile dan ukuran berkas sebelum menekan **Ekspor**. Untuk area satu desa, zoom 19 dengan kompresi JPEG biasanya sudah memadai.
- Ekspor pertama pada suatu area bisa terasa lambat karena server ATR/BPN membuat tile saat itu juga.

### Batasan

- Cakupan data hanya wilayah Indonesia yang tersedia di Peta Dasar ATR/BPN. Di luar area tersebut tile akan kosong.
- Ketersediaan data sepenuhnya bergantung pada layanan ATR/BPN.
- Gunakan fitur ekspor secara wajar (extent kecil, jumlah unduhan paralel rendah) agar tidak membebani server penyedia.

### Kredit Data

Foto udara dan Peta Dasar yang ditampilkan plugin ini bersumber dari **Kementerian Agraria dan Tata Ruang/Badan Pertanahan Nasional (ATR/BPN) Republik Indonesia** melalui layanan [Peta Dasar ATR/BPN](https://petadasar.atrbpn.go.id). Seluruh hak atas data tetap milik Kementerian ATR/BPN. Kredit ini juga ditampilkan pada menu **Tentang plugin**.

### Penafian

Plugin ini dikembangkan secara independen dan **tidak berafiliasi** dengan Kementerian Agraria dan Tata Ruang/Badan Pertanahan Nasional. Pengguna bertanggung jawab mematuhi ketentuan penggunaan data dari penyedia.

### Laporan Masalah

Laporkan bug atau saran melalui halaman [Issues](https://github.com/fadliarya/atrbpn-basemap/issues).

---

## English

A QGIS plugin that adds aerial imagery from the ATR/BPN Peta Dasar service ([petadasar.atrbpn.go.id](https://petadasar.atrbpn.go.id)) as an XYZ basemap. The tile URL is updated automatically from the ATR/BPN website, so you no longer need to find and copy the URL by hand every time it changes. The imagery can also be exported to GeoTIFF.

### Features

- Adds ATR/BPN aerial imagery as an XYZ layer in one click, including the Referer header required by the server.
- Detects the latest tile URL from the map script on the ATR/BPN website and tests a sample tile before using it.
- Updates layers in the open project and the XYZ connection in the Browser panel.
- Automatic background check, at most once a day (can be turned off).
- If the ATR/BPN website changes, the plugin falls back to a URL from the configuration on GitHub and notifies you when a new version is available.
- Export imagery to GeoTIFF with options for:
  - extent (canvas, layer, draw on canvas, or manual coordinates),
  - clipping to a polygon layer (optional, selected features only if needed),
  - zoom level 16 to 21 (zoom 20 matches the native resolution of about 15 cm),
  - output CRS, pixel size, and resampling method,
  - JPEG, DEFLATE, or LZW compression, plus internal overviews.
- Exports run in the background and can be cancelled from the Task panel.

### Requirements

- QGIS 3.22 or later (tested on QGIS 3.44).
- Internet connection.

### Usage

All commands are under **Plugins > ATR BPN Basemap** (menu labels are in Indonesian):

| Menu | Function |
|---|---|
| Tambahkan Foto Udara ATR/BPN | Add the aerial imagery layer to the project (also available as a Plugins toolbar button) |
| Ekspor foto udara ke GeoTIFF... | Download tiles for a given extent and zoom level and save them as GeoTIFF |
| Cek & perbarui URL dari situs ATR/BPN | Check for the latest tile URL manually |
| Atur URL secara manual... | Enter a tile URL yourself if automatic detection fails |
| Cek otomatis saat QGIS dibuka | Turn the automatic check on or off |
| Tentang plugin | Plugin information, the URL in use, and data credits |

Notes:
- Imagery is only shown from **zoom 16** (about 1:8,000 scale). When zoomed out further, the layer appears empty by design.
- When exporting, check the **estimate** of tile count and file size before clicking **Ekspor**. For a village-sized area, zoom 19 with JPEG compression is usually enough.
- The first export of an area can be slow because the ATR/BPN server generates the tiles on demand.

### Limitations

- Coverage is limited to the parts of Indonesia available in ATR/BPN Peta Dasar. Tiles outside that area are empty.
- Data availability depends entirely on the ATR/BPN service.
- Please use the export feature responsibly (small extents, few parallel downloads) to avoid overloading the provider's server.

### Data Credits

The aerial imagery and base maps shown by this plugin are provided by the **Ministry of Agrarian Affairs and Spatial Planning/National Land Agency (Kementerian ATR/BPN) of the Republic of Indonesia** through the [Peta Dasar ATR/BPN](https://petadasar.atrbpn.go.id) service. All rights to the data remain with Kementerian ATR/BPN. This credit is also shown in the **Tentang plugin** (About) dialog.

### Disclaimer

This plugin is developed independently and is **not affiliated** with the Ministry of Agrarian Affairs and Spatial Planning/National Land Agency. Users are responsible for complying with the data provider's terms of use.

### Issues

Report bugs or suggestions on the [Issues](https://github.com/fadliarya/atrbpn-basemap/issues) page.

---

## Lisensi / License

GNU General Public License v2.0 atau lebih baru / or later. Lihat / See [LICENSE](LICENSE).

Pengembang / Developer: Fadli Arya Wisnu Baradi
