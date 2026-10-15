# Klasifikasi Kondisi Tanah untuk Smart Irrigation Berbasis Machine Learning

## 1. Deskripsi Proyek

Proyek ini bertujuan mengklasifikasikan kondisi kelembapan media tanam jeruk purut menggunakan Machine Learning berdasarkan data suhu, kelembapan udara, dan pembacaan analog sensor kelembapan tanah.

Tiga algoritma yang digunakan adalah Decision Tree, Random Forest, dan Support Vector Machine (SVM) dengan kernel RBF. Ketiga model dilatih dan dibandingkan menggunakan fitur sensor yang tersedia.

Pada tahap UAS ini, fokus proyek adalah pengolahan data sensor, pelatihan model, evaluasi hasil klasifikasi, dan pengujian prediksi. Implementasi kendali aktuator fisik belum menjadi fokus pengerjaan.

## 2. Tujuan

- Mengolah dan mengeksplorasi data hasil pembacaan sensor.
- Melatih model untuk mengklasifikasikan kondisi media tanam.
- Membandingkan performa Decision Tree, Random Forest, dan SVM.
- Mengevaluasi model menggunakan data testing dan cross-validation.
- Menguji prediksi kondisi tanah berdasarkan data sensor.

## 3. Dataset

Dataset yang digunakan adalah `Dataset_Smart_Irrigation_300_Data_Terpilih_1.xlsx`, dengan total 300 sampel yang dibaca dari tiga sheet Excel:

- `Kering`
- `Optimal`
- `Terlalu Basah`

Ketiga kategori tersebut digunakan sebagai kelas target klasifikasi.

### Fitur input

- **Suhu (°C):** data suhu udara.
- **Kelembapan udara (%RH):** data kelembapan udara.
- **ADC tanah:** nilai pembacaan analog sensor kelembapan tanah.

Target klasifikasi adalah kondisi tanah, yaitu Kering, Optimal, dan Terlalu Basah.

## 4. Tahapan Pengolahan Data

Tahapan yang dilakukan dalam notebook meliputi:

1. Mengimpor library Python dan scikit-learn.
2. Membaca dan menggabungkan data dari tiga sheet Excel.
3. Memeriksa dan mengeksplorasi dataset.
4. Menentukan fitur input dan target klasifikasi.
5. Membagi data menjadi 80% data training dan 20% data testing menggunakan stratifikasi.
6. Melakukan evaluasi tambahan dengan Stratified 5-fold Cross-Validation.

## 5. Model Machine Learning

### Decision Tree

Algoritma berbasis pohon keputusan yang dapat divisualisasikan untuk membantu memahami aturan klasifikasi.

### Random Forest

Algoritma ensemble yang menggabungkan sejumlah pohon keputusan untuk menghasilkan prediksi klasifikasi.

### Support Vector Machine (SVM)

Algoritma klasifikasi dengan kernel Radial Basis Function (RBF). StandardScaler digunakan dalam pipeline untuk melakukan penskalaan fitur sebelum klasifikasi.

## 6. Skenario Pengujian

Pengujian menggunakan **Skenario A**, yaitu klasifikasi dengan tiga fitur sensor:

- Suhu
- Kelembapan udara
- ADC tanah

Ketiga model diuji menggunakan skenario fitur yang sama agar hasil evaluasinya dapat dibandingkan.

## 7. Hasil Evaluasi

Berdasarkan hasil pengujian pada data testing, diperoleh hasil berikut:

| Model | Akurasi |
|---|---:|
| Decision Tree | 100% |
| Random Forest | 100% |
| SVM (RBF) | 100% |

Hasil tersebut menunjukkan bahwa ketiga model memperoleh akurasi 100% pada pembagian data testing yang digunakan dalam eksperimen ini.

Akurasi tersebut belum menjamin performa yang sama pada data sensor baru. Validitas label kondisi tanah dan kemampuan generalisasi model tetap perlu diperhatikan.

## 8. Dokumentasi Output

File `hasil.zip` berisi dokumentasi hasil eksperimen, seperti grafik eksplorasi data, confusion matrix, perbandingan model, visualisasi pohon keputusan, feature importance, tabel hasil evaluasi, dan file model tersimpan sesuai isi arsip final.

## 9. Struktur Repository

- `Training_Smart_Irrigation_3_Model (1).ipynb` — notebook utama untuk eksplorasi data, pelatihan, evaluasi, dan pengujian prediksi.
- `hasil.zip` — dokumentasi output eksperimen.

## 10. Batasan Proyek

Proyek berfokus pada pengambilan dan pengolahan data sensor serta klasifikasi kondisi tanah. Pengendalian pompa atau aktuator otomatis belum diimplementasikan pada tahap UTS ini.

## 11. Kesimpulan

Decision Tree, Random Forest, dan SVM dibandingkan untuk mengklasifikasikan kondisi media tanam berdasarkan tiga fitur sensor. Pada pengujian yang dilakukan, ketiga model memperoleh akurasi 100% pada data testing. Pengujian lanjutan menggunakan data sensor yang benar-benar terpisah diperlukan untuk menilai kemampuan model pada kondisi baru.

