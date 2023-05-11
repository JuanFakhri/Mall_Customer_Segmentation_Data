# Mall Customer Segmentation Data

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

From the above box plots, we can observe that the distributions of the two gender groups share similar pattern for the two age groups of 20-29 and 30-39. The median spending scores of 30-39 are the highest comparing to other age groups.


