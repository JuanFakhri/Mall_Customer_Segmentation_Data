# Mall Customer Segmentation Data

## Inspirasi
Pada akhir kasus ini, akan dapat menjawab pertanyaan-pertanyaan di bawah ini.

- Bagaimana mencapai segmentasi pelanggan menggunakan algoritma pembelajaran mesin (KMeans Clustering) dengan Python dengan cara yang paling sederhana.
- Siapa target pelanggan Anda dengan siapa Anda dapat memulai strategi pemasaran [mudah dibicarakan]
- Bagaimana strategi pemasaran bekerja di dunia nyata

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

#### 2.4 Apa korelasi antara skor pengeluaran, usia, dan pendapatan?
![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/8fd3b25f-94de-4bec-bb0f-0123cd8679b2)

<b>Observation:</b>

Dari ringkasan di atas, kita dapat melihat koefisien Pearson antara variabel yang berbeda. Kami tidak melihat korelasi linier yang kuat antara usia, pendapatan, dan skor pengeluaran.

![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/744d815f-4242-46c4-a48e-840b08be6348)
![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/391a2e19-8be0-4b35-9c8a-eabbf05d7c14)
<b>Observation:</b>

Dari visualisasi di atas, kita melihat hubungan non-linear antara usia, pendapatan, dan skor pengeluaran. Kita tidak bisa hanya menyesuaikan model linier untuk memodelkan skor pengeluaran. Namun, kita dapat menggunakan algoritma pengelompokan tanpa pengawasan seperti K-mean untuk mengelompokkan pelanggan ke dalam segmen yang berbeda.

### 3. MENEMUKAN DAN MENGGANTI PENCILAN(Outliers)
![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/6dccf645-d011-4ba5-a1fc-748379f3664b)
<b>Observation:</b>

Terlihat jelas pendapatan tahunan pelanggan kisaran $135-$139 terdapat outlier, outlier tersebut  di hapus supaya hasil prediksi berjalan dengan baik

![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/caef8428-c5be-4634-b925-41a46add42a8)
<b>Observation:</b>

Data outlier sudahh di bersihkan tahan selanjut pemodelan data

#### 6. Pemodelan K-mean untuk segmentasi anggota supermarket
![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/0ccb336b-3df7-4cd4-98b0-d58dafeba669)

Menentukan k dari k-mean untuk pengelompokan:

Saya akan menggunakan metode siku di sini: melihat jumlah jarak intra-cluster, yang juga disebut sebagai inersia. Jarak intra-cluster adalah jarak antara setiap pusat cluster dan titik-titik di dalam cluster.

![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/8f1bab6f-2e06-4b39-bd2f-cc99561244d3)

Mana
<b>C1, C2, C3</b> adalah sentroid <b>Pi</b> s adalah titik dalam  <b>jarak</b> cluster itu adalah jarak Euclidean yang biasa.

Inersia menurun saat K meningkat. Kita bisa hanya memilih k yang meminimalkan inersia karena inersia dapat diminimalkan menjadi 0 sebagai k menuju ukuran dataset.

Intuisinya adalah bahwa meningkatkan jumlah cluster akan meningkatkan kecocokan (menjelaskan lebih banyak variasi), karena ada lebih banyak parameter (lebih banyak cluster) untuk digunakan, maka perlu dilakukan penilaian yang cermat untuk memastikan bahwa peningkatan jumlah cluster benar-benar membantu dalam memperbaiki kualitas klasterisasi. 

Peningkatan jumlah cluster dapat meningkatkan kecocokan pada klasterisasi yang tidak terlalu optimal, tetapi dapat juga menurunkan kualitas klasterisasi pada data yang tidak memerlukan jumlah cluster yang lebih banyak. Selain itu, meningkatkan jumlah cluster juga dapat meningkatkan kompleksitas model dan berdampak pada peningkatan waktu komputasi serta sulitnya interpretasi hasil klasterisasi. Oleh karena itu, peningkatan jumlah cluster harus dilakukan secara hati-hati dan disesuaikan dengan jumlah data yang tersedia serta dengan melakukan validasi model secara berkelanjutan.

<b>Observation:</b>

Dari plot di atas, kita dapat berpendapat bahwa 4 cluster (titik infleksi pada kurva) sudah cukup.

![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/b68aa179-d9c8-4ca1-b589-bc281b046b2c)

Saya akan mencoba memecahnya menjadi plot 2D untuk analisis lebih lanjut.
![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/ec0ff3c5-82bb-49bb-a5c3-afb57041196e)
![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/2f5a0be6-d4d7-48fa-a26f-b66e9b12b9ee)
![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/576bbefd-2eb1-4c28-b058-113ea33b3007)

##### Interpretasi segmentasi:
Dari hasil model pengelompokan K-mean di atas dengan k optimal yang dipilih menggunakan metode siku, dapat diamati 4 klaster menarik yang diwarnai dengan warna jingga, biru, kuning, dan ungu.

Menganalisis cluster, kita dapat melihat apa yang diwakili oleh setiap cluster:


Cluster 0: kelompok pelanggan dengan inti pengeluaran rata-rata 84, pendapatan tahunan rata-rata 78.5k, dan usia rata-rata 32.
Klaster 1: kelompok pelanggan dengan inti pengeluaran rata-rata 47, pendapatan tahunan rata-rata 54k, dan usia rata-rata 47.

Klaster 2: kelompok pelanggan dengan inti pengeluaran rata-rata 75.5, pendapatan tahunan rata-rata 26.5k, dan usia rata-rata 23.
Klaster 3: kelompok pelanggan dengan inti pengeluaran rata-rata 16, pendapatan tahunan rata-rata 79k, dan usia rata-rata 42.


Dengan kata lain mengenai visualisasi segmentasi:

Pelanggan Cluster 0 berusia 32-an, berpenghasilan rata-rata 78.5k, mereka paling sering berbelanja dengan skor pengeluaran tinggi kisaran 84k.
Pelanggan Cluster 1 adalah pelanggan yang lebih tua di usia akhir 40 hingga 50-an, memiliki pendapatan rata-rata 54k dan menghabiskan lebih sedikit dari klaster .

Pelanggan Cluster 2 berusia 32-an, berpenghasilan rendah rata-rata 26.5k, akan tetapi mereka sering berbelanja dengan skor pengeluaran kisaran 75.5k.
Pelanggan Cluster 3 berusia 16-an dan memiliki banyak pendapatan sekitar 79k dan sayang sekali mereka tidak sering berbelanja di supermarket.

<b> jumlah pelanggan di setiap cluster </b>
![image](https://github.com/JuanFakhri/Mall_Customer_Segmentation_Data/assets/61308533/9537fd68-01ce-49e6-b0f1-29094e67f0ac)

##### Pengamatan:

Berdasarkan data cluster yang dianalisis, terlihat bahwa terdapat perbedaan karakteristik antara kelompok pelanggan. Pelanggan di Cluster 0 memiliki usia yang relatif muda dan penghasilan yang cukup tinggi, serta cenderung berbelanja dengan pengeluaran yang tinggi. Sedangkan pelanggan di Cluster 1 memiliki usia yang lebih tua, dengan penghasilan yang lebih rendah dan pengeluaran yang cenderung lebih sedikit dibandingkan dengan Cluster 0. Pelanggan di Cluster 2 juga memiliki usia yang relatif muda, namun memiliki penghasilan yang rendah, tetapi cenderung berbelanja dengan pengeluaran yang cukup tinggi. Sementara itu, pelanggan di Cluster 3 memiliki pendapatan yang tinggi, namun tidak aktif berbelanja di supermarket. Hal ini menunjukkan bahwa segmentasi pelanggan dapat memberikan gambaran yang jelas mengenai kebiasaan belanja pelanggan dan dapat membantu dalam merancang strategi pemasaran yang lebih efektif dan efisien.

##### Saran:
- Untuk pelanggan Cluster 0 yang berusia 32-an dan berpenghasilan rata-rata 78.5k, supermarket dapat mempertimbangkan untuk menawarkan produk-produk dengan harga yang lebih tinggi dan berkualitas baik karena mereka cenderung memiliki skor pengeluaran yang tinggi.

- Pelanggan Cluster 1 yang lebih tua di usia akhir 40 hingga 50-an, dengan pendapatan rata-rata 54k dan menghabiskan lebih sedikit dari klaster lainnya, supermarket dapat mencoba menawarkan diskon khusus atau promosi yang menarik untuk menarik minat mereka untuk berbelanja lebih sering.

- Pelanggan Cluster 2 yang berusia 32-an dan berpenghasilan rendah rata-rata 26.5k, meskipun sering berbelanja dengan skor pengeluaran kisaran 75.5k, supermarket dapat menawarkan produk-produk yang lebih terjangkau untuk mempertahankan minat mereka untuk berbelanja.

- Pelanggan Cluster 3 yang berusia 16-an dan memiliki banyak pendapatan sekitar 79k namun tidak sering berbelanja di supermarket, supermarket dapat mencoba menarik minat mereka dengan menawarkan produk-produk atau promosi yang lebih sesuai dengan kebutuhan dan minat mereka.







