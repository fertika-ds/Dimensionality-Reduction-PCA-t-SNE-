# Dimensionality-Reduction-PCA-t-SNE-
# Visualisasi Data Berdimensi Tinggi pada Dataset Handwritten Digits
Proyek ini mengeksplorasi teknik **Dimensionality Reduction** (Reduksi Dimensi) menggunakan dataset angka tulisan tangan (Optical Recognition of Handwritten Digits). Tujuan utamanya adalah untuk memvisualisasikan data dari 64 dimensi menjadi 2 dimensi agar pola pengelompokan (cluster) angka dapat dianalisis secara visual.
## Deskripsi Masalah
Dalam analisis data, seringkali kita berhadapan dengan dataset yang memiliki banyak fitur. Pada dataset **Digits**, setiap gambar angka diwakili oleh **64 fitur** (piksel 8x8). Manusia memiliki keterbatasan dalam memvisualisasikan data di atas 3 dimensi. Oleh karena itu, diperlukan teknik reduksi dimensi untuk:
1. Menemukan struktur tersembunyi dalam data.
2. Membedakan kemiripan antar angka (0-9) dalam grafik 2D.
3. Mengurangi beban komputasi sebelum proses pemodelan AI.
##  Dataset
* **Sumber:** `sklearn.datasets.load_digits`
* **Jumlah Sampel:** 1.797 gambar.
* **Fitur:** 64 kolom (nilai intensitas piksel 0-16).
* **Target:** Label angka 0 hingga 9.
##  Metodologi
1. **Preprocessing (Standardisasi):** Menyeragamkan skala data menggunakan `StandardScaler` agar setiap piksel memiliki pengaruh yang adil dalam perhitungan varians.
2. **PCA (Principal Component Analysis):** Teknik linear untuk menangkap varians terbesar dalam data.
3. **t-SNE (t-Distributed Stochastic Neighbor Embedding):** Teknik non-linear yang handal dalam menjaga hubungan lokal antar data (clustering).
### Analisis Hasil:
* **PCA:** Menunjukkan pemisahan yang cukup baik namun masih banyak terjadi tumpang tindih (*overlap*) antar angka karena keterbatasan transformasi linear.
* **t-SNE:** Berhasil memisahkan angka 0-9 menjadi 10 "pulau" atau *cluster* yang sangat jelas. Hal ini membuktikan bahwa hubungan antar piksel pada gambar angka bersifat non-linear dan kompleks.

##  Kesimpulan
Metode **t-SNE jauh lebih unggul** dalam kasus visualisasi gambar tulisan tangan karena mampu mempertahankan struktur data yang rumit, sehingga kita bisa membedakan jenis angka hanya dengan melihat sebaran titik di grafik 2D.
