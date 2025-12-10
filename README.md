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

Kolom yang dipakai:
1. Price
2. Age_08_04
3. KM
4. Fuel_Type
5. HP

<img width="442" height="322" alt="image" src="https://github.com/user-attachments/assets/7c341ca9-2ba6-4f58-a4c3-d03ad574a0a5" />

### 3. Numeric Outlier
Fungsi: Mendeteksi semua outlier pada dataset dan menggantinya menjadi missing value.
<img width="478" height="332" alt="image" src="https://github.com/user-attachments/assets/46173195-cc07-4f27-a7a1-e690d347ac90" />

### 4. Missing Value
Fungsi: Mengatasi missing value dan menggantinya, jika tipe data Number(int) akan diganti menjadi median dan jika tipe data string akan diganti menjadi most frequent value.

<img width="484" height="152" alt="image" src="https://github.com/user-attachments/assets/84325ba8-962e-4e8a-bca5-7f3eacf10985" />

### 5. Linear Correlation
Fungsi: Untuk melihat korelasi variabel data, positif atau negatif.

<img width="458" height="277" alt="image" src="https://github.com/user-attachments/assets/bba16085-6507-4785-b26b-d635b67a3413" />

### 6. Scatter Plot & Box Plot
Fungsi: Memberikan gambaran hubungan antar variabel dan mendapatkan insight.
### 7. Rule Engine
Fungsi: Membuat aturan logika untuk menghasilkan kolom baru berdasarkan kondisi tertentu, node ini digunakan untuk klasifikasi data dengan ketentuan:
- Harga <= 10000 masuk ke kelas Murah
- Harga di antara 10000-15000 masuk ke kelas Sedang
- Harga > 15000 masuk ke kelas Mahal.

<img width="469" height="313" alt="image" src="https://github.com/user-attachments/assets/674e9e1c-61bd-4f6c-8bbc-ebed0c6a08c9" />

---
## 3. Insight dan Interpretasi yang didapat
1. Variabel yang mempengaruhi harga mobil adalah HP, Umur mobil, KM mobil, dan Tipe bahan bakar mobil.
2. Variabel HP memiliki korelasi positif dengan variabel harga yang dapat dilihat di scatter plot, yang artinya semakin tinggi HP mobil maka semakin tinggi juga harga mobil.

   Visualisasi:

   <img width="442" height="339" alt="image" src="https://github.com/user-attachments/assets/c06818a2-0038-4d1c-b4c9-441032a7829f" />

3. Berbeda dengan variabel HP, variabel umur memiliki korelasi negatif dengan variabel harga mobil. Sehingga semakin umur mobil tua/besar maka harga mobil akan semakin menurun.

   Visualisasi:

   <img width="478" height="332" alt="image" src="https://github.com/user-attachments/assets/4fb75b96-e945-419f-96d4-c74c4a81991a" />

4. Variabel KM memiliki korelasi negatif dengan harga mobil, sehingga semakin KM mobil banyak maka harga mobil akan semakin rendah/murah.

   Visualisasi:

   <img width="481" height="330" alt="image" src="https://github.com/user-attachments/assets/660a7391-4fe0-42bc-bb97-93b765e37235" />

5. Setelah mobil diklasifikasi berdasarkan tipe bahan bakarnya, terlihat bahwa mobil dengan bahan bakar Petrol cenderung paling mahal dari tipe bahan bakar lainnya(dilihat dari median). Lalu mobil dengan tipe bahan bakar Diesel dan CNG memiliki nilai median yang sama, tetapi harga mobil dengan bahan bakar CNG cenderung lebih tinggi(dilihat dari Q1 dan Q3).

   Visualisasi:

   <img width="449" height="343" alt="image" src="https://github.com/user-attachments/assets/f11aa048-4039-4432-b6d6-637e8a9e2c84" />

6. Setelah dilakukan klasifikasi berdasarkan harga, didapatkan insight bahwa mobil kelas mahal memiliki umur yang rendah dan mobil kelas murah memiliki umur yang lebih tua. Mobil kelas mahal juga memiliki KM yang lebih rendah dari kelas sedang dan murah, tetapi mobil dengan kelas murah memiliki KM yang paling tinggi. Terakhir, mobil kelas mahal cenderung memiliki HP yang lebih rendah dari mobil dengan kelas murah dan sedang(dilihat dari median).

   Visualisasi:

   <img width="484" height="342" alt="image" src="https://github.com/user-attachments/assets/9f85dd8a-6cde-4ebf-9f05-029de4c1159f" />

---
## 4. Kesimpulan
Workflow ini berhasil melakukan Data preparation dan Visualisasi untuk mendapatkan insight dan interpretasi, serta melakukan klasifikasi data. Dari workflow ini, didapatkan insight bahwa harga mobil dipengaruhi oleh variabel HP, KM, Umur mobil, dan juga tipe bahan bakar. Setelah melakukan klasifikasi berdasarkan harga, mobil dengan kelas mahal, sedang, dan murah memiliki ciri-ciri tertentu berdasarkan variabel tertentu.
