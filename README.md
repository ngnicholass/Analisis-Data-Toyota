# Laporan Analisis Data Toyota
### Nicholas_C14250094
---
## 1. Pendahuluan
Tujuan analisis dilakukan untuk:
1. Membersihkan data (outlier dan missing value)
2. Menampilkan visualisasi data
3. Klasifikasi data
4. Mendapatkan insight dan interpretasi
Analisis ini menggunakan workflow KNIME karena platform ini menyediakan antarmuka visual berbasis workflow yang memudahkan penyusunan proses analisis data secara sistematis.
---
## 2. Alur Workflow & Penjelasan
Berikut ringkasan setiap node:
### 1. CSV Reader
Fungsi: Membaca dataset ToyotaCorolla.csv dan mengimpor seluruh isi dataset ke dalam workflow.
### 2. Column Filter
Fungsi: Menghilangkan kolom yang tidak digunakan dan memilih kolom yang ingin digunakan.
### 3. Numeric Outlier
Fungsi: Mendeteksi semua outlier pada dataset dan menggantinya menjadi missing value.
### 4. Missing Value
Fungsi: Mengatasi missing value dan menggantinya, jika tipe data Number(int) akan diganti menjadi median dan jika tipe data string akan diganti menjadi most frequent value .
### 5. Line Correlation
Fungsi: Untuk melihat korelasi variabel data, positif atau negatif.
### 6. Scatter Plot & Box Plot
Fungsi: Memberikan gambaran hubungan antar variabel.
### 7. Rule Engine
Fungsi: Membuat aturan logika untuk menghasilkan kolom baru berdasarkan kondisi tertentu, node ini digunakan untuk klasifikasi data dengan ketentuan:
- Harga <= 10000 masuk ke kelas Murah
- Harga di antara 10000-15000 masuk ke kelas Sedang
- Harga > 15000 masuk ke kelas Mahal.
---
## 3. Insight dan Interpretasi yang didapat
1. Variabel yang mempengaruhi harga mobil adalah HP, Umur mobil, KM mobil, dan Tipe bahan bakar mobil.
2. Variabel HP memiliki korelasi positif dengan variabel harga yang dapat dilihat di scatter plot, yang artinya semakin tinggi HP mobil maka semakin tinggi juga harga mobil.
3. Berbeda dengan variabel HP, variabel umur memiliki korelasi negatif dengan variabel harga mobil. Sehingga semakin umur mobil tua/besar maka harga mobil akan semakin menurun.
4. Variabel KM memiliki korelasi negatif dengan harga mobil, sehingga semakin KM mobil banyak maka harga mobil akan semakin rendah/murah.
5. Setelah mobil diklasifikasi berdasarkan tipe bahan bakarnya, terlihat bahwa mobil dengan bahan bakar Petrol cenderung paling mahal dari tipe bahan bakar lainnya(dilihat dari median). Lalu mobil dengan tipe bahan bakar Diesel dan CNG memiliki nilai median yang sama, tetapi harga mobil dengan bahan bakar CNG cenderung lebih tinggi(dilihat dari Q1 dan Q3).
6. Setelah dilakukan klasifikasi berdasarkan harga, didapatkan insight bahwa mobil kelas mahal memiliki umur yang rendah dan mobil kelas murah memiliki umur yang lebih tua. Mobil kelas mahal juga memiliki KM yang lebih rendah dari kelas sedang dan murah, tetapi mobil dengan kelas murah memiliki KM yang paling tinggi. Terakhir, mobil kelas mahal cenderung memiliki HP yang lebih rendah dari mobil dengan kelas murah dan sedang(dilihat dari median).
---
## 4. Kesimpulan
Workflow ini berhasil melakukan Data preparation dan Visualisasi untuk mendapatkan insight dan interpretasi, serta melakukan klasifikasi data. Dari workflow ini, didapatkan insight bahwa harga mobil dipengaruhi oleh variabel HP, KM, Umur mobil, dan juga tipe bahan bakar. Setelah melakukan klasifikasi berdasarkan harga, mobil dengan kelas mahal, sedang, dan murah memiliki ciri-ciri tertentu berdasarkan variabel tertentu.
