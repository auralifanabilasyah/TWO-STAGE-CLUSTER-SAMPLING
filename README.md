# ESTIMASI TINGKAT KEPUASAN MAHASISWA PROGRAM STUDI STATISTIKA UNIVERSITAS MATARAM TERHADAP KONEKSI INTERNET DI LINGKUNGAN KAMPUS MENGGUNAKAN TWO-STAGE CLUSTER SAMPLING

## Deskripsi Proyek

Proyek ini bertujuan untuk mengestimasi tingkat kepuasan mahasiswa Program Studi Statistika Universitas Mataram terhadap kualitas koneksi internet di lingkungan kampus. Penelitian dilakukan menggunakan pendekatan survei dengan instrumen kuesioner skala Likert 1–4 yang terdiri atas 12 indikator kepuasan.

Analisis dilakukan menggunakan dua metode sampling, yaitu Simple Random Sampling (SRS) dan Two-Stage Cluster Sampling. Kedua metode dibandingkan berdasarkan nilai estimasi rata-rata, standard error, relative standard error (RSE), interval kepercayaan, serta design effect untuk menentukan metode yang lebih efisien dalam mengestimasi tingkat kepuasan mahasiswa pada populasi.

Bahasa pemrograman yang digunakan adalah R dengan bantuan beberapa package statistik seperti readxl, dplyr, dan psych.

---

# Daftar Isi

1. Deskripsi Proyek
2. Latar Belakang
3. Tujuan Penelitian
4. Metodologi Penelitian
5. Langkah-Langkah Analisis Menggunakan R Studio
6. Hasil dan Pembahasan
7. Kesimpulan
8. Daftar Pustaka

---

# Latar Belakang

Perkembangan teknologi informasi telah mengubah proses pembelajaran di perguruan tinggi menjadi semakin bergantung pada internet. Berbagai aktivitas akademik seperti pengisian KRS, akses Sistem Informasi Akademik (SIA), pembelajaran daring melalui SPADA, pengumpulan tugas, pencarian referensi ilmiah, hingga pelaksanaan perkuliahan menggunakan Zoom atau Google Meet membutuhkan koneksi internet yang baik dan stabil.

Kualitas layanan internet menjadi salah satu faktor yang dapat memengaruhi efektivitas proses pembelajaran mahasiswa. Internet yang lambat, tidak stabil, atau sering mengalami gangguan dapat menghambat akses informasi dan menurunkan kenyamanan mahasiswa dalam mengikuti kegiatan akademik.

Menurut Parasuraman, Zeithaml, dan Berry (1988), kepuasan pengguna terhadap suatu layanan dipengaruhi oleh persepsi pengguna terhadap kualitas layanan yang diterima. Semakin baik kualitas layanan yang diberikan, maka semakin tinggi tingkat kepuasan pengguna.

Dalam konteks pendidikan tinggi, evaluasi terhadap kualitas layanan internet perlu dilakukan secara berkala untuk mengetahui tingkat kepuasan mahasiswa sebagai pengguna utama layanan tersebut. Hasil evaluasi dapat digunakan sebagai dasar pengambilan keputusan dalam meningkatkan kualitas infrastruktur jaringan kampus.

Oleh karena itu dilakukan penelitian mengenai estimasi tingkat kepuasan mahasiswa Program Studi Statistika Universitas Mataram terhadap koneksi internet di lingkungan kampus menggunakan metode Two-Stage Cluster Sampling dan dibandingkan dengan metode Simple Random Sampling.

---

# Tujuan Penelitian

1. Mengukur tingkat kepuasan mahasiswa terhadap koneksi internet di lingkungan kampus.
2. Menguji validitas instrumen kuesioner yang digunakan.
3. Menguji reliabilitas instrumen penelitian.
4. Mengestimasi rata-rata tingkat kepuasan mahasiswa menggunakan metode Simple Random Sampling.
5. Mengestimasi rata-rata tingkat kepuasan mahasiswa menggunakan metode Two-Stage Cluster Sampling.
6. Membandingkan efisiensi kedua metode sampling berdasarkan nilai standard error dan design effect.

---

# Metodologi Penelitian

## Jenis Penelitian

Penelitian ini merupakan penelitian kuantitatif menggunakan metode survei.

## Populasi

Populasi penelitian adalah seluruh mahasiswa Program Studi Statistika Universitas Mataram yang menjadi responden pada survei.

Jumlah populasi yang tersedia dalam data adalah sebanyak 30 mahasiswa.

## Teknik Pengumpulan Data

Data dikumpulkan menggunakan Google Form dengan skala Likert 1–4.

Kategori jawaban:

| Skor | Kategori |
|--------|--------|
| 1 | Sangat Tidak Puas |
| 2 | Tidak Puas |
| 3 | Puas |
| 4 | Sangat Puas |

## Variabel Penelitian

Terdapat 12 indikator kepuasan yang digunakan untuk mengukur kualitas koneksi internet kampus.

## Software

Analisis dilakukan menggunakan:

- R Studio
- Package readxl
- Package dplyr
- Package psych

---

# Langkah-Langkah Analisis Menggunakan R Studio

## 1. Import Data

Data hasil survei diimpor dari file Excel menggunakan package readxl.

## 2. Pemeriksaan Struktur Data

Struktur data diperiksa menggunakan fungsi str() dan names() untuk memastikan tipe data setiap variabel telah sesuai.

## 3. Pengambilan Variabel Kuesioner

Variabel kuesioner diambil dari kolom 6 sampai kolom 17 karena kolom tersebut berisi seluruh indikator kepuasan.

## 4. Uji Validitas

Validitas dilakukan menggunakan korelasi Product Moment antara masing-masing item dengan skor total.

Kriteria:

- p-value < 0,05 → Valid
- p-value ≥ 0,05 → Tidak Valid

## 5. Uji Reliabilitas

Reliabilitas dilakukan menggunakan Cronbach Alpha.

Kriteria:

| Alpha | Interpretasi |
|---------|---------|
| > 0,90 | Sangat Reliabel |
| 0,80–0,90 | Reliabel |
| 0,70–0,80 | Cukup Reliabel |

## 6. Cleaning Data

Dilakukan pemeriksaan missing value menggunakan fungsi:

```r
colSums(is.na(data))
```

## 7. Visualisasi Data

Distribusi skor kepuasan divisualisasikan menggunakan boxplot untuk mendeteksi adanya nilai ekstrem (outlier).

## 8. Pembentukan Skor Kepuasan

Skor kepuasan setiap responden diperoleh dari rata-rata seluruh item kuesioner.

## 9. Kategorisasi Tingkat Kepuasan

Kategori tingkat kepuasan ditentukan berdasarkan interval:

| Interval | Tingkat Kepuasan |
|-----------|-----------|
| 1,00 – 1,75 | Sangat Tidak Puas |
| 1,76 – 2,50 | Tidak Puas |
| 2,51 – 3,25 | Puas |
| 3,26 – 4,00 | Sangat Puas |

## 10. Analisis Simple Random Sampling

Tahapan meliputi:

- Menentukan sampel acak sederhana
- Menghitung peluang pemilihan
- Menghitung bobot sampling
- Mengestimasi rata-rata populasi
- Menghitung Standard Error
- Menghitung Interval Kepercayaan
- Menghitung Relative Standard Error

## 11. Analisis Two-Stage Cluster Sampling

Tahap pertama:

- Memilih cluster (kelas)

Tahap kedua:

- Memilih mahasiswa dalam setiap cluster

Selanjutnya dihitung:

- Peluang pemilihan
- Bobot sampling
- Estimasi rata-rata
- Standard Error
- Relative Standard Error
- Interval Kepercayaan

## 12. Perbandingan Efisiensi

Perbandingan dilakukan menggunakan nilai Design Effect (Deff).

Kriteria:

- Deff < 1 → Cluster lebih efisien
- Deff = 1 → Sama efisien
- Deff > 1 → SRS lebih efisien

---

# Hasil dan Pembahasan

## Hasil Pemeriksaan Struktur Data

Data yang digunakan terdiri atas 30 responden dan 17 variabel.

Lima variabel pertama merupakan identitas responden, sedangkan 12 variabel berikutnya merupakan indikator kepuasan terhadap koneksi internet kampus.

Seluruh item kuesioner bertipe numerik sehingga dapat langsung digunakan dalam analisis statistik.

---

## Hasil Uji Validitas

Hasil pengujian menunjukkan seluruh item memiliki nilai p-value di bawah 0,05.

Nilai korelasi item-total berada pada rentang:

- Minimum = 0,5631
- Maksimum = 0,9295

Karena seluruh nilai p-value lebih kecil dari 0,05 maka seluruh indikator dinyatakan valid.

Hal ini menunjukkan bahwa setiap pertanyaan dalam kuesioner mampu mengukur konsep yang sama yaitu kepuasan mahasiswa terhadap koneksi internet kampus.

Item dengan korelasi tertinggi adalah:

**"Secara keseluruhan, saya puas terhadap koneksi internet di lingkungan Program Studi Statistika Universitas Mataram"**

dengan nilai korelasi sebesar 0,9295.

Sedangkan korelasi terendah terdapat pada indikator:

**"Saya puas karena koneksi internet jarang mengalami gangguan saat digunakan"**

dengan nilai korelasi sebesar 0,5631.

Meskipun merupakan nilai terendah, angka tersebut masih berada di atas batas minimal validitas sehingga item tetap dinyatakan valid.

---

## Hasil Uji Reliabilitas

Nilai Cronbach Alpha yang diperoleh adalah:

**α = 0,9539**

Nilai tersebut berada di atas 0,90 sehingga instrumen termasuk kategori sangat reliabel.

Artinya seluruh item memiliki konsistensi internal yang sangat baik dan mampu memberikan hasil pengukuran yang stabil apabila digunakan kembali pada kondisi yang serupa.

Hasil ini menunjukkan bahwa instrumen layak digunakan untuk melakukan estimasi tingkat kepuasan mahasiswa.

---

## Hasil Cleaning Data

Pemeriksaan missing value menunjukkan seluruh variabel memiliki nilai nol.

Dengan demikian tidak terdapat data yang hilang sehingga seluruh data dapat digunakan dalam proses analisis tanpa memerlukan imputasi atau penghapusan observasi.

---

## Hasil Visualisasi Data

Visualisasi menggunakan boxplot menunjukkan distribusi skor kepuasan relatif terkonsentrasi pada rentang nilai 2,5 hingga 3,5.

Tidak ditemukan outlier yang ekstrem sehingga data dianggap cukup representatif untuk menggambarkan kondisi populasi.

Hal ini menunjukkan bahwa mayoritas mahasiswa memberikan penilaian yang cenderung positif terhadap kualitas koneksi internet di lingkungan kampus.

---

## Hasil Kategorisasi Tingkat Kepuasan Responden

Distribusi tingkat kepuasan responden diperoleh sebagai berikut:

| Tingkat Kepuasan | Jumlah | Persentase |
|------------------|---------|------------|
| Sangat Tidak Puas | 2 | 6,67% |
| Tidak Puas | 5 | 16,67% |
| Puas | 18 | 60,00% |
| Sangat Puas | 5 | 16,67% |

Hasil tersebut menunjukkan bahwa mayoritas responden berada pada kategori **Puas**.

Sebanyak 60% mahasiswa merasa puas terhadap kualitas koneksi internet yang tersedia di lingkungan kampus. Hanya sebagian kecil responden yang berada pada kategori tidak puas maupun sangat tidak puas.

Temuan ini mengindikasikan bahwa layanan internet kampus secara umum telah mampu memenuhi kebutuhan akademik mahasiswa.

---

## Estimasi Tingkat Kepuasan Menggunakan Simple Random Sampling

Hasil estimasi menunjukkan:

- Estimasi rata-rata = 2,8542
- Standard Error = 0,0800
- RSE = 2,80%
- CI 95% = (2,6973 ; 3,0111)

Berdasarkan interval kategori yang digunakan, nilai rata-rata sebesar 2,8542 termasuk dalam kategori **Puas**.

Artinya apabila hasil sampel digeneralisasikan ke populasi mahasiswa Program Studi Statistika Universitas Mataram, maka tingkat kepuasan mahasiswa terhadap koneksi internet kampus diperkirakan berada pada kategori Puas.

Nilai RSE sebesar 2,80% menunjukkan tingkat presisi yang sangat baik karena berada jauh di bawah batas 25%.

---

## Estimasi Tingkat Kepuasan Menggunakan Two-Stage Cluster Sampling

Hasil estimasi menunjukkan:

- Estimasi rata-rata = 3,0000
- Standard Error = 0,1459
- RSE = 4,86%
- CI 95% = (2,7140 ; 3,2860)

Nilai estimasi sebesar 3,0000 juga berada dalam kategori **Puas**.

Dengan demikian, berdasarkan pendekatan Two-Stage Cluster Sampling dapat disimpulkan bahwa mahasiswa Program Studi Statistika Universitas Mataram secara umum merasa puas terhadap kualitas koneksi internet di lingkungan kampus.

Meskipun menghasilkan nilai rata-rata yang sedikit lebih tinggi dibandingkan SRS, tingkat kepuasan yang diperoleh tetap berada pada kategori yang sama yaitu Puas.

---

## Perbandingan Metode Sampling

| Metode | Estimasi | Tingkat |
|---------|---------|---------|
| SRS | 2,8542 | Puas |
| Two-Stage Cluster Sampling | 3,0000 | Puas |

Kedua metode menghasilkan kesimpulan yang sama yaitu tingkat kepuasan mahasiswa berada pada kategori **Puas**.

Namun terdapat perbedaan pada tingkat presisi.

Nilai Standard Error metode SRS sebesar 0,0800 lebih kecil dibandingkan metode Cluster sebesar 0,1459.

Selain itu diperoleh:

**Design Effect = 3,324**

Karena nilai Deff lebih besar dari 1, maka metode SRS lebih efisien dibandingkan Two-Stage Cluster Sampling pada data ini.

---

# Kesimpulan

Berdasarkan hasil analisis terhadap 30 responden mahasiswa Program Studi Statistika Universitas Mataram diperoleh bahwa seluruh item kuesioner valid dan instrumen penelitian memiliki reliabilitas yang sangat tinggi dengan nilai Cronbach Alpha sebesar 0,9539.

Distribusi tingkat kepuasan menunjukkan bahwa 60% responden berada pada kategori Puas. Hasil estimasi menggunakan Simple Random Sampling menghasilkan rata-rata kepuasan sebesar 2,8542, sedangkan Two-Stage Cluster Sampling menghasilkan rata-rata sebesar 3,0000.

Kedua metode memberikan kesimpulan yang sama, yaitu tingkat kepuasan mahasiswa terhadap koneksi internet di lingkungan kampus berada pada kategori **Puas**.

Dengan demikian dapat disimpulkan bahwa kualitas koneksi internet di lingkungan Program Studi Statistika Universitas Mataram secara umum telah mampu mendukung kegiatan akademik mahasiswa, meskipun masih terdapat beberapa mahasiswa yang memberikan penilaian kurang puas sehingga peningkatan kualitas layanan internet tetap perlu dilakukan.

---

# Daftar Pustaka

Parasuraman, A., Zeithaml, V. A., & Berry, L. L. (1988). SERVQUAL: A Multiple-Item Scale for Measuring Consumer Perceptions of Service Quality. Journal of Retailing, 64(1), 12–40.

Cochran, W. G. (1977). Sampling Techniques. Third Edition. New York: John Wiley & Sons.

Lohr, S. L. (2019). Sampling: Design and Analysis. Second Edition. Boca Raton: CRC Press.

Groves, R. M., Fowler, F. J., Couper, M. P., Lepkowski, J. M., Singer, E., & Tourangeau, R. (2009). Survey Methodology. New Jersey: John Wiley & Sons.

Sugiyono. (2022). Metode Penelitian Kuantitatif. Bandung: Alfabeta.
