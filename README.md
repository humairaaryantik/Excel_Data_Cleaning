</p><h1 align="center" = > CLEANING DATA MENGGUNAKAN EXCEL </h1>

### DESKRIPSI

Dokumentasi ini bertujuan untuk membersihkan data mentah (raw data) menggunakan Microsoft Excel agar data menjadi lebih akurat, konsisten, dan siap untuk dianalisis.

Dataset mentah yang digunakan masih memiliki beberapa permasalahan, yaitu : 

1. Format data yang tidak konsisten
2. Missing values (data kosong) atau NULL
3. Data duplikat
4. Inkonsistensi kategori

### INFORMASI DATASET

- Jumlah row data (sebelum cleaning) : 21865
- Jumlah row data (sesudah cleaning) : 21830
- Jumlah kolom orders : 19
- Jumlah kolom region : 2
- Raw data diubah menjadi cleaned data untuk menandai bahwa dataset telah melalui proses pembersihan data

  Sheets orders dan region --> Sheets orders_cleaned dan region_cleaned
  
Berikut merupakan tampilan dataset sebelum dilakukan proses data cleaning
<p align="center">
  <img src="https://github.com/humairaaryantik/Excel_Data_Cleaning/blob/bcd20491badd2f78c5e9e6c1064cbb421a2d85fd/Cleaning%20data%20excel/1.jpg" alt="image" width="800"/>
  

### TAHAPAN DATA CLEANING
1️⃣ **Identifikasi Masalah pada Raw Data (orders dan region)**

Beberapa contoh permasalahan yang ditemukan pada dataset sebelum dilakukan proses data cleaning:
1. Format tanggal tidak konsisten

<p align="center">
  <img src="https://github.com/humairaaryantik/Excel_Data_Cleaning/blob/f4d30ad8c066008759c3f09b8773fca9e68c09e1/Cleaning%20data%20excel/2.png" alt="image" width="800"/>
  
2. Penulisan nama kategori tidak konsisten

<p align="center">
  <img src="https://github.com/humairaaryantik/Excel_Data_Cleaning/blob/4fff13b916cc4dfb8f25ae3407b3b3f62a947953/Cleaning%20data%20excel/3.png" alt="image" width="800"/>

3. Data kosong (NULLS) dan Unknown

<p align="center">
  <img src="https://github.com/humairaaryantik/Excel_Data_Cleaning/blob/4fff13b916cc4dfb8f25ae3407b3b3f62a947953/Cleaning%20data%20excel/4.png" alt="image" width="800"/>

Berikut tabel yang merangkum permasalahan kualitas data yang telah diidentifikasi pada keseluruhan dataset:
| No | Tabel | Kolom | Permasalahan | Penyelesaian |
|----|-------|-------|--------------|--------------|
| 1 | orders | purchase_ts | Format tanggal tidak konsisten |Ya|
| 2 | orders | purchase_ts | Format tanggal hilang (Null) |Tidak|
| 3 | orders | product_name | Nama produk/kategori tidak konsisten |Ya|
| 4 | orders | USD_price | Adanya $0 transaksi dan Null |Tidak|
| 5 | orders | marketing_channel | Data Hilang (Null) |Ya|
| 6 | orders | account_creation_method | Adanya data hilang (Null) dan Unknown |Ya|
| 7 | orders | country_code | Kode negara hilang |Ya|
| 8 | orders | seluruh kolom | Duplikat data |Ya|
| 9 | region | region | Data kode negara tidak konsisten dan Null |Ya|

2️⃣ **Standarisasi Format**
- Format tanggal dan kategori produk diseragamkan
  
  ``` Formula: DATEVALUE, TEXT, UPPER, LOWER, PROPER, IF ```
  
- Spasi berlebih dihapus
  
  ``` Formula: TRIM ```
  
- Format mata uang disesuaikan
  
  ``` Format Cells → Currency ```
  
3️⃣ **Menangani Missing Values (NULL atau Blanks)** 
- Mengganti nilai kosong dengan "Unknown" menggunakan fungsi IF()
- Memerbaiki error #N/A dari proses lookup menggunakan fungsi IFERROR()
- Menghapus baris jika informasi tidak lengkap atau membiarkan nilai tetap Blank jika data tidak tersedia

 4️⃣ **Menghapus Data Duplikat** 
 
   `` All Data → Remove Duplicates ``
 
  <p align="center">
  <img src="https://github.com/humairaaryantik/Excel_Data_Cleaning/blob/4d5fb0141caecdcaae7af434b29ac9e42b826951/Cleaning%20data%20excel/5.jpeg" width="800"/>
  <img src="https://github.com/humairaaryantik/Excel_Data_Cleaning/blob/4d5fb0141caecdcaae7af434b29ac9e42b826951/Cleaning%20data%20excel/6.jpeg" width="800"/>
</p>

Total data duplikat yang diidentifikasi : **35 baris**

5️⃣ **Validasi Dataset Hasil Cleaning**
Melakukan pengecekan akhir untuk memastikan dataset sudah bersih dan siap dianalisis
- Memastikan tidak ada data duplikat menggunakan fitur Remove Duplicates
- Memeriksa missing values menggunakan Filter
- Memastikan format data (tanggal, teks, dan angka) sudah konsisten

### File dataset hasil cleaning dapat diakses di folder berikut
📂 [Dataset Folder](dataset/)
