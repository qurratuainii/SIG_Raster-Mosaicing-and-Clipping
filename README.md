# SIG_Raster-Mosaicing-and-Clipping

*Tutorial Raster Mosaicing and Clipping

1. Download terlebih dahulu file berikut ini: N05E080.SRTMGL1.hgt.zip, N06E079.SRTMGL1.hgt.zip, N06E080.SRTMGL1.hgt.zip, N06E081.SRTMGL1.hgt.zip, N07E079.SRTMGL1.hgt.zip, N07E080.SRTMGL1.hgt.zip, N07E081.SRTMGL1.hgt.zip
N08E079.SRTMGL1.hgt.zip, N08E080.SRTMGL1.hgt.zip, N08E081.SRTMGL1.hgt.zip
N09E080.SRTMGL1.hgt.zip, ne_10m_admin_0_countries.zip

2. Buka QGIS dan cari file yang sudah di download pada panel browser. Perluas file zip individual untuk menampilkan file .hgt. Tahan tombol Ctrl dan pilih semua file individual. Setelah dipilih, seret ke kanvas (*Gambar 1*)

3. Selanjutnya kita akan melihat 11 layer individu dimuat di panel Layers dan ditampilkan di kanvas. Kita akan menggabungkan ubin individu ini menjadi satu mosaik. Klik Processing lalu pilih Toolbox (*Gambar 2*)

4. Cari dan temukan GDAL Raster miscellaneous Merge toll. Klik dua kali untuk meluncurkannya (*Gambar 3*)

5. Dalam Merge dialog, klik tombol ... di sebelah Input Layers. Klik pilih semua layer individu (*Gambar 4*)

6. pada dataset layer tdi tipe data input adalah integer bertanda 16-bit. Untuk menjaga integritas data, kita harus menjaga tipe data yang sama untuk layer gabungan. Pilih Int16 sebagi tipe data output. Juga format data keluaran default adalah GeoTiff. File GeoTiff bisa menjadi sangat besar jika tidak dikompresi. Pilih HIgh Compression sebagai profil setelah itu klik run (*Gambar 5*)

7. Setelah pemrosesan selesai, Merged layer baru akan ditambahkan ke panel Layers. Jika layer tidak berada di bagin atas tumpukan, pilih dan seret ke bagian atas panel lapisan, tetapi jika sudah berada di atas biarkan saja (*Gambar 6*)

8. Kita dapat melihat bahwa Merged berisi data elevasi gabungan dari ubin masukan individual. Visualisasi default hanya menampilkan nilai pixel dalam kisaran 0-255. Namun data kami berisi nilai -14 hingga 2371, menghasilkan rendering kontras yang rendah. Kita dapat mengubah menjadi visualisasi yang lebih baik. Klik Open the layer Styling panel pada panel Layers (*Gambar 7*)

9. Pada Layer Styling panel, klik dropdown render type dan pilih Hillshade renderer. Opsi rendering ini sangat cocok untuk data elevasi (*Gambar 8*)

10. Operasi umum lainnya sat bekerja dengan raster adalah untuk memotong raster ke area yang diminati. Untuk tutorial ini, kami akan memotong layer gabungan ke batas negara untuk Sri Lanka. Pilih file ne_10m_admin_0_countries.shp lalu seret file ke kanvas (*Gambar 9*)

11. Pilih layer ne_10m_admin_0_countries yang baru ditambahkan di panel Layers. Klik tombol Select Features by area atau satu klik pada attributes Toolbar. Setelah itu klik poligon untuk Sri Lanka untuk memilihnya (*Gambar 10*)

12. Selanjutnya klik Processing lalu pilih Toolbox. Cari dan temukan GDAL Ekstrasksi raster lalu pilih Clip raster by mask layer tool. Klik untuk dua kali untuk menampilkannya  (*Gambar 11*)

13. Pada Clip Raster by Mask Layer atur Merged sebagai input layer. Pilih ne_10m_admin_0_countries sebagai layer Mask, dan centang kotak Selected features only. Masukkan 0,000000 sebagai niala nodata yang ditentukan ke pita keluaram. Pilih High compression sebagai profil dan Klik run (*Gambar 12*)

14. Sebuah merged baru akan ditambahkan ke panel Layers. Pada titik ini, mungkinsulit untuk melihat hasilnya karena kita memiliki terlalu banyak lapisan tumpang tindih yang terlihat. Klik tombol Manage Map Themes dan pilih Hide all Layers (*Gambar 13*)

15. Nyalakan hanya layer Merged terbaru dan gayakan dengan renderer Hilshade seperti yang dilakukan sebelumnya (*Gambar 14*)

16. Lapisan elevasi keluaran gabungan dan subset untuk Sri Lanka sudah siap (*Gambar 15*)
