</p><h1 align="center" = > CLEANING DATA MENGGUNAKAN EXCEL </h1>

### DESKRIPSI

Dokumentasi ini bertujuan untuk membersihkan data mentah (raw data) menggunakan Microsoft Excel agar data menjadi lebih akurat, konsisten, dan siap untuk dianalisis.

Dataset mentah yang digunakan masih memiliki beberapa permasalahan, yaitu : 

1. Format data yang tidak konsisten
2. Missing values (data kosong) atau NULLS
3. Data duplikat
4. Inkonsistensi kategori

### INFORMASI DATASET

- Jumlah row data (sebelum cleaning) : 21865
- Jumlah row data (sesudah cleaning) : 21830
- Raw data diubah menjadi cleaned data untuk menandai bahwa dataset telah melalui proses pembersihan data

  Sheets orders dan region --> Sheets orders_cleaned dan region_cleaned
  
Berikut merupakan tampilan dataset sebelum dilakukan proses data cleaning
<p align="center">
  <img src="https://github.com/humairaaryantik-portofolio/Project_Udemy/blob/fa8ee98b1f19f2d493c2d3b29a8b34fe034ff98a/Udemy.jpg" alt="image" width="700"/>
  

### TAHAPAN DATA CLEANING
1️⃣ **Identifikasi Masalah pada Raw Data (orders dan region)**

Beberapa contoh permasalahan yang ditemukan pada dataset sebelum dilakukan proses data cleaning:
1. Format tanggal tidak konsisten
   <p align="center">
  <img src="https://github.com/humairaaryantik-portofolio/Project_Udemy/blob/fa8ee98b1f19f2d493c2d3b29a8b34fe034ff98a/Udemy.jpg" alt="image" width="700"/>
2. Penulisan nama kategori tidak konsisten
  <p align="center">
  <img src="https://github.com/humairaaryantik-portofolio/Project_Udemy/blob/fa8ee98b1f19f2d493c2d3b29a8b34fe034ff98a/Udemy.jpg" alt="image" width="700"/>
3. Data kosong (NULLS) dan Unknown
  <p align="center">
  <img src="https://github.com/humairaaryantik-portofolio/Project_Udemy/blob/fa8ee98b1f19f2d493c2d3b29a8b34fe034ff98a/Udemy.jpg" alt="image" width="700"/>

Berikut tabel yang merangkum permasalahan kualitas data yang telah diidentifikasi pada keseluruhan dataset:
| No | Tabel | Kolom | Permasalahan | Penyelesaian |
|----|-------|-------|--------------|--------------|
| 1 | orders | purchase_ts | Format tanggal tidak konsisten |Ya|
| 2 | orders | purchase_ts | Format tanggal hilang (Nulls) |Tidak|
| 3 | orders | product_name | Nama produk/kategori tidak konsisten |Ya|
| 4 | orders | USD_price | Adanya $0 transaksi dan Nulls |Tidak|
| 5 | orders | marketing_channel | Data Hilang (Nulls) |Ya|
| 6 | orders | account_creation_method | Adanya data hilang (Nulls) dan Unknown |Ya|
| 7 | orders | country_code | Kode negara hilang |Ya|
| 8 | orders | seluruh kolom | Duplikat data |Ya|
| 9 | region | region | Data kode negara tidak konsisten dan Nulls |Ya|
