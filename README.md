# Mall Customer Segmentation Data

## Inspirasi
Pada akhir kasus ini, akan dapat menjawab pertanyaan-pertanyaan di bawah ini.

- Bagaimana mencapai segmentasi pelanggan menggunakan algoritma pembelajaran mesin (KMeans Clustering) dengan Python dengan cara yang paling sederhana.

## Deskripsi dataset:
Saat ini, kami memiliki 200 entri data demografi pelanggan supermarket. Berikut adalah gambaran singkat tentang kolom dataset:

1. CustomerID: ID pelanggan yang diindeks oleh sistem keanggotaan
2. Gender: jenis kelamin pelanggan supermarket
3. Age: usia anggota supermarket
4. Annual Income (k$): pendapatan tahunan pelanggan dengan satuan ribu dolar
S. pending Score (1-100): skor pengeluaran dari 1-100. 100 berarti pelanggan adalah pembeli yang aktif.

### 2. Analisis data eksploratori dari data anggota

#### 2.0 Bagaimana distribusi skor pengeluaran?

![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/81b57208-70c5-4da0-b359-63074c43ee2a)
<b>Observasi:</b>

Dari histogram distribusi skor pengeluaran yang dikemas dengan penambahan 10, kita dapat melihat ada 3 puncak di sekitar skor pengeluaran 10-19, 40-49, dan 70-79 dengan jumlah pelanggan maksimal sebesar 39 jatuh ke dalam rentang skor pengeluaran 40-49. Data ini berpusat di sekitar rentang skor pengeluaran 40-49.

#### 2.1 Bagaimana distribusi skor pengeluaran dari pelanggan pria dan wanita?

![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/cb88116c-b4ae-431d-adf1-eab800a1c635)

<b>Observasi:</b>
 
Dari visualisasi di atas, kita dapat mengamati bahwa tidak ada perbedaan yang jelas antara median dan kuartil atas dari skor pengeluaran pelanggan pria dan wanita. Kuartil pertama dari skor pengeluaran pria lebih rendah sebesar 10,5 unit dibandingkan dengan kuartil pertama dari skor pengeluaran wanita. Skor pengeluaran maksimum (99) untuk wanita lebih tinggi dari skor pengeluaran maksimum (97) untuk pria. Skor pengeluaran minimum (5) untuk wanita lebih tinggi dari skor pengeluaran minimum (1) untuk pria.

#### 2.2 Bagaimana distribusi skor pengeluaran dari kelompok usia yang berbeda?
![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/2473fe05-7346-43ff-bfbb-07fbe36eb21d)


<b>Observasi:</b>

Distribusi data usia pelanggan relatif normal dengan berpusat pada rentang usia 30-39 dengan total jumlah 61 pelanggan.

![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/07639def-e169-43c4-a819-04d4dc7ee85e)

<b>Observation:</b>

Dari plot kotak di atas, kita dapat mengamati bahwa distribusi kedua kelompok gender memiliki pola yang sama untuk dua kelompok usia 20-29 dan 30-39. Skor pengeluaran rata-rata 30-39 adalah yang tertinggi dibandingkan dengan kelompok usia lainnya.

#### 2.3 Apa distribusi pendapatan tahunan dari berbagai kelompok umur?

![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/67942ed6-44e0-472f-abb8-2160beff4c28)
<b>Observation:</b>

Dari plot kotak di atas, kita dapat mengamati bahwa pendapatan tahunan rata-rata tertinggi untuk pelanggan pria adalah 78K untuk kelompok usia 30-39 dan pendapatan tahunan medina tertinggi untuk pelanggan wanita adalah 74K untuk kelompok usia 30-39. Kelompok usia 30-39 juga merupakan kelompok usia dengan skor pengeluaran tertinggi dari plot kotak di bagian sebelumnya.



