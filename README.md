# Gas-Usage-Prediction

## Latar Belakang
Gas alam merupakan salah satu sumber energi utama di Amerika Serikat yang digunakan dalam berbagai sektor seperti perumahan, komersial, industri, bahan bakar kendaraan, dan pembangkit listrik. Memahami pola konsumsi gas alam dapat membantu dalam pengambilan keputusan energi, perencanaan infrastruktur, serta kebijakan energi yang lebih efisien. Oleh karena itu, proyek ini bertujuan untuk membangun model prediktif yang mampu memperkirakan konsumsi gas alam berdasarkan data historis.

## Dataset
Dataset ini diambil dari sumber open source Kaggle dengan judul "Natural Gas Usage (2014-Now)". Dataset yang digunakan dalam proyek ini berasal dari U.S. Energy Information Administration (EIA) dan mencakup data bulanan konsumsi gas alam dari Januari 2014 hingga Januari 2024. Dataset ini berisi informasi mengenai:
1. duoarea: Singkatan negara bagian
2. area-name: Nama negara bagian
3. product: Produk energi (semua baris memiliki "EPG0" untuk Gas Alam)
4. sector: Sektor konsumsi (misalnya, "VRS" untuk perumahan, "VCS" untuk komersial)
5. process: Proses konsumsi spesifik dalam sektor
6. value: Konsumsi bulanan dalam juta kaki kubik (MMcf)

## Metode
### Preprocessing Data
Sebelum melakukan prediksi, dilakukan beberapa tahapan preprocessing untuk memastikan data siap digunakan:
1. Menghapus kolom yang tidak relevan untuk menghindari informasi yang tidak diperlukan dalam model.
2. Mengisi nilai kosong pada kolom "value" dengan rata-rata data agar tidak kehilangan informasi penting yang dapat memengaruhi hasil prediksi.
3. Melakukan encoding pada data bertipe object menggunakan target encoding untuk mengubah variabel kategori menjadi bentuk numerik yang lebih sesuai untuk model regresi.

### Modelling
Tiga model regresi digunakan untuk membandingkan performa dalam memprediksi konsumsi gas alam:
1. Linear Regression
2. XGBoost Regression
3. Random Forest Regression

### Evaluasi Model
Evaluasi model dilakukan dengan membandingkan akurasi (R2) masing-masing algoritma:
1. XGBoost Regression: 99%
2. Random Forest Regression: 99%
3. Linear Regression: 95%
Hasil menunjukkan bahwa XGBoost dan Random Forest memiliki performa terbaik dengan akurasi 99%, sementara Linear Regression memiliki performa yang lebih rendah dengan akurasi 95%.

## Kesimpulan
Dari hasil perbandingan model, dapat disimpulkan bahwa model berbasis pohon keputusan seperti XGBoost dan Random Forest lebih unggul dalam memprediksi konsumsi gas alam dibandingkan Linear Regression. Hal ini disebabkan oleh kemampuan mereka dalam menangkap pola non-linear dan interaksi antar variabel.

Dengan model prediksi ini, berbagai pihak seperti analis energi, pembuat kebijakan, dan perusahaan utilitas dapat lebih mudah memahami tren konsumsi gas alam dan membuat keputusan yang lebih tepat berdasarkan data historis.
