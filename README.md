# Analisis Pilihan Aplikasi Belanja Online Mahasiswa

Analisis regresi logistik multinomial untuk mengkaji faktor yang berhubungan dengan pilihan aplikasi belanja online mahasiswa. Proyek ini disusun oleh kelompok **OTW Perjalanan** untuk mata kuliah **Statistika Regresi**, Desember 2025.

## Tujuan

- Menggambarkan karakteristik responden dan pilihan aplikasi belanja online.
- Mengidentifikasi variabel yang berhubungan dengan pilihan platform dibandingkan kategori referensi.
- Membandingkan dua spesifikasi model regresi logistik multinomial.
- Menginterpretasikan hubungan antarvariabel melalui odds ratio.

## Ringkasan Data

Presentasi mencatat **133 responden**, terdiri atas 69 laki-laki dan 64 perempuan.

Variabel dependen adalah pilihan aplikasi belanja online dengan kategori berikut:

| Kode | Aplikasi | Peran dalam model |
|---|---|---|
| 0 | Shopee | Kategori referensi |
| 1 | Tokopedia | Dibandingkan dengan Shopee |
| 2 | TikTok Shop | Dibandingkan dengan Shopee |
| 3 | Bukalapak | Dibandingkan dengan Shopee |

Presentasi menampilkan variabel independen dengan kode `X1` hingga `X11`. Definisi lengkap dan pengkodean setiap variabel belum tersedia dalam bahan yang diperiksa.

## Metode Analisis

1. Statistik deskriptif dan visualisasi distribusi responden serta kategori aplikasi.
2. Eksplorasi korelasi Spearman dan pemeriksaan multikolinearitas menggunakan Variance Inflation Factor (VIF).
3. Estimasi regresi logistik multinomial dengan Shopee sebagai kategori referensi.
4. Pengujian simultan menggunakan likelihood ratio test dan pengujian parsial menggunakan uji Wald, dengan taraf signifikansi **0,10**.
5. Perbandingan model menggunakan log-likelihood, pseudo R², AIC, dan BIC.
6. Interpretasi koefisien melalui odds ratio.

Dua spesifikasi yang dibandingkan dalam presentasi adalah:

| Model | Spesifikasi menurut presentasi |
|---|---|
| Model 1 | Tanpa pengkodean dummy pada variabel independen |
| Model 2 | Menggunakan pengkodean dummy pada variabel independen |

## Hasil yang Dilaporkan

> Angka berikut disalin dari presentasi dan belum dihitung ulang menggunakan dataset serta kode analisis.

| Ukuran | Model 1 | Model 2 |
|---|---:|---:|
| Log-likelihood | -71.617 | -72.337 |
| Log-likelihood model null | -92.4 | -92.4 |
| LLR p-value | 0.02719 | 0.0283 |
| Pseudo R² | 0.2249 | 0.2139 |
| AIC | 201.2335 | 200.6733 |
| BIC | 285.0537 | 281.6013 |

Presentasi melaporkan bahwa kedua model signifikan secara simultan pada taraf 0,10. Model 1 memiliki log-likelihood dan pseudo R² lebih tinggi, sedangkan Model 2 memiliki AIC dan BIC lebih rendah. Penulis presentasi memilih **Model 1 sebagai model final**.

Pseudo R² digunakan sebagai ukuran kecocokan model; nilainya tidak diartikan sebagai persentase variasi target yang dijelaskan seperti R² pada regresi linear.

### Hasil Uji Parsial

Variabel yang dilaporkan signifikan pada taraf 0,10, dengan Shopee sebagai kategori referensi:

| Perbandingan | Model 1 | Model 2 |
|---|---|---|
| Tokopedia terhadap Shopee | `X2`, `X3`, `X7` | `X2`, `X6`, `X7` |
| TikTok Shop terhadap Shopee | `X8` | `X8` |
| Bukalapak terhadap Shopee | Tidak ada yang dilaporkan signifikan | Tidak ada yang dilaporkan signifikan |

Kesimpulan presentasi mengaitkan pilihan platform dengan frekuensi pembelian, pengeluaran, kualitas produk, serta harga dan promosi. Pemetaan faktor tersebut ke kode variabel belum terverifikasi. Temuan ini diperlakukan sebagai hubungan statistik, bukan bukti sebab-akibat.

## Keterbatasan dan Reproduksibilitas

- README ini disusun dari presentasi; dataset, skrip, dan notebook analisis belum diperiksa.
- Prosedur pengambilan sampel, penanganan missing value dan duplikat, definisi variabel, serta pengkodean dummy belum terverifikasi.
- Tabel estimasi Bukalapak memuat p-value `NaN`; konvergensi dan validitas estimasi perlu diperiksa sebelum menarik kesimpulan. Hasil tidak signifikan tidak membuktikan tidak adanya hubungan.
- Pembagian data, validasi di luar sampel, seed, dan versi dependensi belum tersedia. Hasil yang dilaporkan belum menunjukkan kemampuan prediksi pada data baru.
- Petunjuk instalasi dan menjalankan analisis belum dicantumkan karena berkas kode serta dependensinya belum tersedia untuk diperiksa.

## Anggota Kelompok

**OTW Perjalanan**

- Dani Shofi Nur Izza
- Nino Ahmadiy
- M. Rafly Wahyudi

**Dosen pengampu:** Shindi Shella May Wara, M.Stat.

## Sumber

Presentasi *Analisis Regresi Logistik Multinomial untuk Mengetahui Faktor yang Mempengaruhi Mahasiswa dalam Memilih Aplikasi Belanja Online*, Desember 2025.

Berkas sumber: `PPT OTW PERJALNAN SUDAH SAMPAI LOKASI.pdf`. Ringkasan data merujuk halaman 3, spesifikasi dan uji parsial halaman 5-7, perbandingan model halaman 7-8, serta pemilihan model final halaman 12.
