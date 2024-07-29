# PREDIKSI BIAYA PENGIRIMAN BARANG

| Nama Anggota Kelompok          |
| ------------------------------ |
| Ade Ilham Permadi              |
| Agita Nurfadillah              |
| Al Novianti Ramdhani Sulaksono |
| Muhammad Farhan Faridz Sofyan  |

### Business Understanding

**Latar Belakang:**
Biaya pengiriman merupakan komponen biaya yang sangat signifikan dan dapat sangat bervariasi tergantung pada beberapa faktor seperti berat barang, dimensi, jarak pengiriman, dan jenis layanan yang dipilih. Mengingat variasi ini, penting bagi perusahaan untuk dapat memperkirakan biaya pengiriman dengan lebih akurat guna memperkuat proses pengambilan keputusan dalam operasional sehari-hari.

**Tujuan:**
Tujuan dari proyek ini adalah untuk memperkuat proses pengambilan keputusan dengan menyediakan estimasi biaya pengiriman yang lebih akurat. Estimasi ini diharapkan dapat memudahkan perusahaan dalam membuat keputusan yang berkaitan dengan alokasi kapasitas dan strategi pengiriman, serta mengoptimalkan harga jual produk dan meningkatkan kepuasan pelanggan.

### Analytic Approach

**Metodologi:**
Metodologi yang digunakan dalam proyek ini adalah sebagai berikut:

1. **Business Understanding**: Memahami masalah bisnis dan menentukan tujuan analitik.
2. **Data Understanding**: Mengumpulkan dan memahami data yang relevan.
3. **Data Preparation**: Menyiapkan data untuk analisis dengan mengatasi missing values dan melakukan encoding variabel kategorikal.
4. **Modeling**: Membangun model regresi linear untuk memprediksi biaya pengiriman.
5. **Evaluation**: Mengevaluasi kinerja model menggunakan metrik seperti MSE, RMSE, R², MAE, MAPE, dan Adjusted R².

### Data Requirements

**Sumber Data:**
Data yang digunakan dalam prediksi biaya pengiriman ini mencakup informasi berikut:

1. City: Kota pengiriman.
2. Ship Mode: Mode pengiriman.
3. Order Priority: Prioritas pesanan.
4. Product Container: Jenis kemasan produk.
5. Cost Price: Harga biaya barang.
6. Retail Price: Harga jual barang.
7. Order Quantity: Jumlah pesanan.
8. Total: Total setelah pengiriman.
9. Shipping Cost: Biaya pengiriman aktual.

### Persiapan Data

**Langkah-Langkah:**
Langkah-langkah persiapan data yang dilakukan adalah sebagai berikut:

1. Mengonversi kolom mata uang menjadi numerik: Kolom seperti Cost Price, Retail Price, Profit Margin, Sub Total, Discount $, Order Total, Shipping Cost, dan Total dikonversi dari format string ke format numerik.
2. Menangani nilai yang hilang: Nilai yang hilang pada kolom numerik diisi dengan nilai rata-rata kolom tersebut.
3. Mengidentifikasi dan mengonversi kolom non-numerik: Kolom non-numerik diubah menjadi string, lalu dilakukan encoding menggunakan LabelEncoder.
4. Normalisasi data: Kolom fitur dinormalisasi menggunakan MinMaxScaler agar berada dalam rentang 0-1.

### Hasil Evaluasi Model

1. **Mean Squared Error (MSE)**:

   - **Definisi**: Mean Squared Error (MSE) adalah rata-rata kuadrat perbedaan antara nilai aktual dan nilai prediksi. MSE mengukur seberapa jauh prediksi model dari nilai sebenarnya dengan memberikan penalti yang lebih besar untuk kesalahan yang lebih besar karena mengkuadratkan selisih.
   - **Hasil**: MSE = 26.79.
   - **Interpretasi**: Rata-rata kuadrat kesalahan menunjukkan bahwa rata-rata kuadrat perbedaan antara nilai prediksi biaya pengiriman dan nilai aktual adalah sekitar 26.79. Ini berarti bahwa kesalahan prediksi model memiliki variabilitas yang cukup besar.

2. **Root Mean Squared Error (RMSE)**:

   - **Definisi**: Root Mean Squared Error (RMSE) adalah akar kuadrat dari Mean Squared Error (MSE). RMSE memberikan ukuran rata-rata besar kesalahan dalam satuan yang sama dengan variabel target, dalam hal ini, biaya pengiriman.
   - **Hasil**: RMSE = 5.17.
   - **Interpretasi**: Nilai RMSE sebesar 5.17 menunjukkan bahwa rata-rata kesalahan prediksi biaya pengiriman oleh model adalah sekitar 5.17 unit biaya pengiriman. Artinya, prediksi model cenderung meleset sekitar 5.17 unit dari nilai aktualnya, secara rata-rata.

3. **R-squared (R²)**:

   - **Definisi**: R-squared (R²) adalah proporsi variansi dalam variabel dependen (biaya pengiriman) yang bisa dijelaskan oleh variabel independen (fitur-fitur yang digunakan dalam model).
   - **Hasil**: R² = 0.59.
   - **Interpretasi**: Nilai R² sebesar 0.59 menunjukkan bahwa sekitar 59.09% variabilitas dalam biaya pengiriman dapat dijelaskan oleh fitur-fitur dalam model. Ini berarti model mampu menjelaskan lebih dari setengah variabilitas yang ada dalam data target.

4. **Mean Absolute Error (MAE)**:

   - **Definisi**: Mean Absolute Error (MAE) adalah rata-rata dari kesalahan absolut antara nilai aktual dan nilai prediksi. MAE mengukur seberapa besar kesalahan prediksi model tanpa memperhitungkan arah kesalahan (positif atau negatif).
   - **Hasil**: MAE = 3.38.
   - **Interpretasi**: Nilai MAE sebesar 3.38 menunjukkan bahwa rata-rata kesalahan prediksi biaya pengiriman adalah sekitar 3.38 unit. Ini berarti bahwa prediksi model cenderung meleset sekitar 3.38 unit dari nilai aktualnya, secara rata-rata.

5. **Mean Absolute Percentage Error (MAPE)**:

   - **Definisi**: Mean Absolute Percentage Error (MAPE) mengukur rata-rata kesalahan absolut dalam bentuk persentase dari nilai aktual. MAPE memberikan gambaran tentang besar kesalahan relatif terhadap nilai aktual.
   - **Hasil**: MAPE = 144.98%.
   - **Interpretasi**: Nilai MAPE sebesar 144.98% menunjukkan bahwa rata-rata kesalahan prediksi adalah sekitar 144.98% dari nilai aktual biaya pengiriman. Ini berarti bahwa kesalahan prediksi sangat besar relatif terhadap ukuran nilai yang diprediksi.

6. **Adjusted R-squared (Adjusted R²)**:
   - **Definisi**: Adjusted R-squared mengukur proporsi variansi dalam variabel dependen (biaya pengiriman) yang dapat dijelaskan oleh variabel independen dalam model, dengan mempertimbangkan jumlah variabel independen yang digunakan. Adjusted R² memberikan penyesuaian untuk R² yang dapat menjadi bias terhadap model dengan lebih banyak variabel.
   - **Hasil**: Adjusted R² = 0.58.
   - **Interpretasi**: Nilai Adjusted R² sebesar 0.58 menunjukkan bahwa sekitar 58.51% variabilitas dalam biaya pengiriman dapat dijelaskan oleh fitur-fitur dalam model, setelah menyesuaikan untuk jumlah variabel yang digunakan.
