# Airline Customer Value Analysis

## Domain Project

Dalam industri penerbangan yang dinamis dan kompetitif, pemahaman yang mendalam tentang pelanggan menjadi kunci untuk kesuksesan bisnis jangka panjang. Melalui proyek segmentasi pelanggan, maskapai penerbangan bertujuan untuk membagi basis pelanggan menjadi segmen yang lebih kecil dan lebih terdefinisi dengan jelas. Tujuan utama dari segmentasi ini adalah untuk mengidentifikasi pola perilaku yang berbeda di antara pelanggan, memahami preferensi pelanggan, dan mengenali kebutuhan yang spesifik dari setiap segmen.

Dengan pemahaman yang lebih baik tentang berbagai segmen pelanggan, maskapai penerbangan akan dapat menyesuaikan strategi pemasaran secara lebih efektif. Ini mungkin meliputi penawaran promosi yang disesuaikan, pengembangan program loyalitas yang lebih relevan, atau penyediaan layanan tambahan yang sesuai dengan kebutuhan masing-masing segmen. Selain itu, segmentasi pelanggan juga membantu maskapai penerbangan untuk mengidentifikasi peluang untuk pertumbuhan bisnis, seperti menargetkan segmen yang belum dimanfaatkan sepenuhnya atau mengembangkan produk atau layanan baru yang sesuai dengan kebutuhan pasar.

## Business Understanding

**Problem Statement:** Maskapai penerbangan menghadapi lingkungan bisnis yang dinamis dan kompetitif, di mana pemahaman mendalam tentang pelanggan menjadi krusial untuk kesuksesan jangka panjang. Namun, dengan basis pelanggan yang besar dan beragam, sulit bagi maskapai penerbangan untuk secara efektif memahami preferensi, kebutuhan, dan pola perilaku pelanggan mereka.

**Goals:**
1. Memahami secara mendalam pola perilaku, preferensi, dan kebutuhan pelanggan maskapai penerbangan.
2. Memecah basis pelanggan menjadi segmen yang lebih kecil dan lebih terdefinisi untuk memungkinkan penyesuaian strategi pemasaran yang lebih efektif.
3. Mengidentifikasi peluang untuk peningkatan pertumbuhan bisnis melalui segmentasi pelanggan yang lebih baik.
4. Mengembangkan strategi pemasaran yang disesuaikan, program loyalitas yang lebih relevan, dan layanan tambahan yang sesuai dengan kebutuhan masing-masing segmen.

**Solution Statement:** Melalui proyek segmentasi pelanggan, kami akan menganalisis data historis dan fitur pelanggan untuk membagi basis pelanggan maskapai penerbangan menjadi segmen yang lebih kecil dan lebih terdefinisi. Kami akan menggunakan teknik analisis data yang canggih untuk mengidentifikasi pola perilaku yang berbeda di antara pelanggan, memahami preferensi mereka, dan mengenali kebutuhan yang spesifik dari setiap segmen. Dengan demikian, kami akan memberikan wawasan yang lebih dalam kepada maskapai penerbangan tentang profil pelanggan mereka, memungkinkan mereka untuk mengambil keputusan yang lebih tepat dan berbasis data dalam upaya untuk memperkuat hubungan dengan pelanggan dan meningkatkan kinerja bisnis mereka secara keseluruhan.

## Data Understanding

Datasets yang digunakan adalah [flight.csv](https://drive.google.com/uc?id=14G4xOWK5e-QQ9S7GmBwULChNdeJZXs2U) dengan terdiri dari 23 fitur yang secara rinci terdapat 15 fitur numerik dan 8 fitur non-numerik. Berikut adalah fitur-fitur pada dataset Flight.

| Column Name       | Description                                                     |
|-------------------|-----------------------------------------------------------------|
| MEMBER_NO         | ID Member                                                       |
| FFP_DATE          | Frequent Flyer Program Join Date                                |
| FIRST_FLIGHT_DATE | Tanggal Penerbangan pertama                                     |
| GENDER            | Jenis Kelamin                                                   |
| FFP_TIER          | Tier dari Frequent Flyer Program                                |
| WORK_CITY         | Kota Asal                                                       |
| WORK_PROVINCE     | Provinsi Asal                                                   |
| WORK_COUNTRY      | Negara Asal                                                     |
| AGE               | Umur Customer                                                   |
| LOAD_TIME         | Tanggal data diambil                                            |
| FLIGHT_COUNT      | Jumlah penerbangan Customer                                     |
| BP_SUM            | Rencana Perjalanan                                              |
| SUM_YR_1          | Fare Revenue                                                    |
| SUM_YR_2          | Votes Prices                                                    |
| SEG_KM_SUM        | Total jarak(km) penerbangan yg sudah dilakukan                  |
| LAST_FLIGHT_DATE  | Tanggal penerbangan terakhir                                    |
| LAST_TO_END       | Jarak waktu penerbangan terakhir ke pesanan penerbangan paling akhir |
| AVG_INTERVAL      | Rata-rata jarak waktu                                           |
| MAX_INTERVAL      | Maksimal jarak waktu                                            |
| EXCHANGE_COUNT    | Jumlah penukaran                                                |
| avg_discount      | Rata rata discount yang didapat customer                        |
| Points_Sum        | Jumlah poin yang didapat customer                               |
| Point_NotFlight   | point yang tidak digunakan oleh members                         |

Dengan statistika deskriptif pada data numerik sebagai berikut:

| Column Name       | Count   | Mean    | Std     | Min   | 25%     | 50%     | 75%      | Max       |
|-------------------|---------|---------|---------|-------|---------|---------|----------|-----------|
| member_no         | 62988   | 31494.5 | 18183.2 | 1     | 15747.75| 31494.5 | 47241.25 | 62988     |
| ffp_tier          | 62988   | 4.102   | 0.374   | 4     | 4       | 4       | 4        | 6         |
| age               | 62568   | 42.476  | 9.886   | 6     | 35      | 41      | 48       | 110       |
| flight_count      | 62988   | 11.839  | 14.049  | 2     | 3       | 7       | 15       | 213       |
| bp_sum            | 62988   | 10925.08| 16339.49| 0     | 2518    | 5700    | 12831    | 505308    |
| sum_yr_1          | 62437   | 5355.38 | 8109.45 | 0     | 1003    | 2800    | 6574     | 239560    |
| sum_yr_2          | 62850   | 5604.03 | 8703.36 | 0     | 780     | 2773    | 6845.75  | 234188    |
| seg_km_sum        | 62988   | 17123.88| 20960.84| 368   | 4747    | 9994    | 21271.25 | 580717    |
| last_to_end       | 62988   | 176.12  | 183.82  | 1     | 29      | 108     | 268      | 731       |
| avg_interval      | 62988   | 67.75   | 77.52   | 0     | 23.37   | 44.67   | 82       | 728       |
| max_interval      | 62988   | 166.03  | 123.40  | 0     | 79      | 143     | 228      | 728       |
| exchange_count    | 62988   | 0.32    | 1.14    | 0     | 0       | 0       | 0        | 46        |
| avg_discount      | 62988   | 0.72    | 0.19    | 0     | 0.61    | 0.71    | 0.81     | 1.5       |
| points_sum        | 62988   | 12545.78| 20507.82| 0     | 2775    | 6328.5  | 14302.5  | 985572    |
| point_notflight   | 62988   | 2.73    | 7.36    | 0     | 0       | 0       | 1        | 140       |

Dengan statistika deskriptif pada data non-numerik sebagai berikut:

| Column Name          | Count  | Unique | Top         | Frequency |
|----------------------|--------|--------|-------------|-----------|
| ffp_date             | 62988  | 3068   | 1/13/2011   | 184       |
| first_flight_date    | 62988  | 3406   | 2/16/2013   | 96        |
| gender               | 62985  | 2      | Male        | 48134     |
| work_city            | 60719  | 3234   | guangzhou   | 9386      |
| work_province        | 59740  | 1165   | guangdong   | 17509     |
| work_country         | 62962  | 118    | CN          | 57748     |
| load_time            | 62988  | 1      | 3/31/2014   | 62988     |
| last_flight_date     | 62988  | 731    | 3/31/2014   | 959       |

## Exploratory Data Analysis

Berikut beberapa EDA yang dilakukan:

<img src="https://github.com/mfathul21/airline-customer-value/blob/main/assets/category1.jpg?raw=true" alt="category1_plot" width="800">

Gambar 1. Category1 Features Plot 

<img src="https://github.com/mfathul21/airline-customer-value/blob/main/assets/category2.jpg?raw=true" alt="category2_plot" width="800">

Gambar 2. Category2 Features Plot 

<img src="https://github.com/mfathul21/airline-customer-value/assets/94775806/70429894-932f-4ddf-a0b4-d4b3fce5eee2" alt="numeric_plot" width="800">

Gambar 3. Numerical Features Plot

<img src="https://github.com/mfathul21/airline-customer-value/blob/main/assets/corr_plot.jpg?raw=true" alt="corr_plot" width="800">

Gambar 4. Correlation Plot

## Data Preprocessing

**Handlin Missing Value**

Dengan menggunakan method `.isna().sum()` diperoleh bahwa pada dataset flight terdapat beberapa data yang hilang dengan rincian sebagai berikut:

- work_city: 3.6% nilai kosong
- work_province: 5.2% nilai kosong
- age: 0.67% nilai kosong
- sum_yr_1: 0.87% nilai kosong
- sum_yr_2: 0.22% nilai kosong
- gender: 0.005% nilai kosong
- work_country: 0.04% nilai kosong

Perhatikan, untuk nilai yang hilang (missing value) pada setiap fitur memiliki persentase yang rendah (dibawah 10%) sehingga melakukan drop missing value menjadi suatu pilihan dalam menangani kasus missing value tersebut. Akan tetapi, untuk fitur sum_yr_1 dan sum_yr_2 akan dilakukan imputasi dengan 0 dengan dasar bahwa untuk setiap nilai yang hilang pada fitur sum_yr_1 diikuti dengan sum_yr_2 yang memiliki nilai 0 dan begitupula sebaliknya.

**Handling Date Features**

Pada dataset flight terdapat 4 fitur date, yaitu fpp_date, first_flight_date, last_flight_date, dan load_time dengan tipe data object. Oleh karena itu, dilakukan konversi ke datetime sehingga mempermudah nantinya dalam proses feature engineering. Sebelum itu, dikarenakan terdapat perbedaan format tanggal antara fitur last_flight_date dengan fitur lainnya yang menggunakan format %m/%d/%Y. Selain itu, format pada fitur last_flight_date tidak konsisten karena ada beberapa baris dengan format %m/%d/%Y dan beberapa baris lainnya dengan format %Y/%m/%d %H:%m:%s. Sebelum melakukan konversi tipe data dari objek menjadi datetime, perlu dilakukan manipulasi terlebih dahulu untuk memastikan formatnya menjadi konsisten dan sesuai.

**Feature Engineering**

Dalam proses ini, dilakukan seleksi fitur yang akan digunakan untuk melakukan klasterisasi terhadap pelanggan. Salah satu pendekatan yang umum digunakan adalah RFM (Recency, Frequency, Monetary), di mana fitur-fitur ini merepresentasikan tiga dimensi utama dari metode RFM, yaitu:

1. Recency (R): Mewakili seberapa baru pelanggan terakhir kali melakukan interaksi atau melakukan perjalanan udara dengan pesawat dari data yang diambil. Semakin kecil nilai recency, semakin baru interaksi tersebut. Contohnya adalah jumlah hari sejak pelanggan terakhir kali melakukan penerbangan.

2. Frequency (F): Mewakili seberapa sering pelanggan melakukan interaksi atau transaksi dalam jangka waktu tertentu. Semakin tinggi nilai frequency, semakin sering pelanggan berinteraksi. Contohnya adalah total penerbangan pelanggan dalam periode waktu yang ditentukan.

3. Monetary (M): Mewakili seberapa banyak uang yang dihabiskan oleh pelanggan dalam bisnis dalam jangka waktu tertentu. Semakin tinggi nilai monetary, semakin besar nilai transaksi yang dilakukan pelanggan. Contohnya adalah total nilai pembelian yang dilakukan pelanggan dalam periode waktu yang ditentukan.

Berikut adalah penggunaan fitur RFM dalam proses feature engineering:

```python
customers = pd.DataFrame()

customers['recency'] = airline['load_time'] - airline['last_flight_date']
customers['frequency'] = airline['flight_count']
customers['monetary'] = airline['sum_yr_1'] + airline['sum_yr_2']
```

Dengan menggunakan fitur RFM, dapat dilakukan pengelompokkan pelanggan ke dalam segmen-segmen yang berbeda berdasarkan perilaku belanja mereka. Hal ini dapat membantu bisnis untuk lebih memahami pelanggan mereka, mengidentifikasi peluang-peluang pemasaran, serta merancang strategi pemasaran yang lebih tersegmentasi dan efektif.

Berikut masing-masing distribusi dari fitur RFM:

<img src="https://github.com/mfathul21/airline-customer-value/blob/main/assets/rfm_plot.jpg?raw=true" alt="corr_plot" width="800">

Gambar 5. Distribution of RFM Features

Dari Gambar 5, terlihat bahwa distribusi dari fitur-fitur pelanggan seperti recency, frequency, dan monetary memiliki kecenderungan positive skew (condong ke kanan). Oleh karena itu, akan dilakukan transformasi untuk mengubah bentuk distribusi tersebut dengan menggunakan Box-Cox transformasi, sehingga diperoleh distribusi setelah dilakukan transformasi sebagai berikut:

<img src="https://github.com/mfathul21/airline-customer-value/blob/main/assets/bcox_rfm_plot.jpg?raw=true" alt="corr_plot" width="800">

Gambar 6. Distribution of RFM Features Transform

Berdasarkan Gambar 6 diperoleh setelah dilakukan transformasi menggunakan metode Box-Cox, distribusi dari ketiga fitur RFM tersebut menjadi lebih simetris dan mendekati distribusi normal.

**Standarization**

Setelah melakukan feature engineering dan mendapatkan fitur RFM, langkah selanjutnya adalah standarisasi data. Standarisasi adalah proses untuk mengubah skala atau rentang nilai dari fitur-fitur dalam dataset sehingga memiliki skala yang seragam atau mendekati distribusi normal. Hal ini penting karena beberapa algoritma machine learning seperti SVM, KNN, dan regresi bergantung pada skala fitur yang seragam. Metode standarisasi yang digunakan adalah StandardScaler dengan implemntasi sebagai berikut.

```python
scaler = StandardScaler()
scaler.fit(customers_fix)
customers_std = scaler.transform(customers_fix)
```

Dengan menggunakan StandardScaler, skala fitur RFM dapat diubah sehingga memiliki mean = 0 dan standar deviasi = 1. Hal ini membantu dalam mempersiapkan data untuk proses klasterisasi dengan algoritma seperti K-Means atau DBSCAN, serta memastikan bahwa seluruh fitur memiliki dampak yang seimbang terhadap hasil klasterisasi.

Setelah melakukan standarisasi, data siap untuk digunakan dalam proses klasterisasi untuk mengelompokkan pelanggan ke dalam segmen-segmen yang lebih homogen berdasarkan perilaku belanja mereka. Langkah-langkah selanjutnya termasuk pemilihan jumlah klaster yang optimal, pelatihan model klasterisasi, dan interpretasi hasil klasterisasi untuk mengambil wawasan bisnis yang berguna.

## Modelling

Dengan menggunakan algoritma K-Means untuk proses klasterisasi pelanggan penerbangan dilakukan evaluasi dengan elbow method dalam menentukan k (jumlah klaster) yang optimal, berikut hasil evaluasi dengan elbow method:

<img src="https://github.com/mfathul21/airline-customer-value/blob/main/assets/elbow_plot.jpg?raw=true" alt="corr_plot" width="800">

Gambar 7. Evaluation Plot of Elbow Method

Berdasarkan gambar 7 diperoleh nilai k atau jumlah klaster yang optimal adalah 4 klaster. Oleh karena itu, dilakukan proses modelling dengan algoritma K-Means dengan 4 klaster sehingga diperoleh untuk nilai rata-rata masing-masing sebagai berikut:

| Cluster | Recency (mean) | Frequency (mean) | Monetary (mean) | Count |
|---------|----------------|------------------|-----------------|-------|
| 0       | 185.20         | 10.27            | 9496.37         | 16613 |
| 1       | 365.74         | 3.00             | 2472.48         | 17935 |
| 2       | 42.32          | 5.18             | 4060.77         | 10840 |
| 3       | 25.67          | 28.26            | 26922.81        | 16216 |

Selain itu, berikut untuk visualiasi segmentasi pelanggan dengan algoritma K-Means dan 4 klaster

<img src="https://github.com/mfathul21/airline-customer-value/blob/main/assets/segment_plot.jpg?raw=true" alt="corr_plot" width="800">

Gambar 8. Segmentation of Customers

Perhatikanlah, berdasarkan tabel nilai rata-rata masing-masing klaster dan Gambar 8 dapat diambil beberapa kesimpulan dan rekomendasi sebagai berikut:

**Cluster 0**

- Recency (Mean): 185 hari
- Frequency (Mean): 10 kali
- Monetary (Mean): $9496.37
- Jumlah Observasi: 16613

Rekomendasi: Klaster ini terdiri dari pelanggan yang telah menggunakan layanan pesawat baru-baru ini, sering melakukan perjalanan dengan pesawat, dan memiliki pengeluaran yang tinggi dalam layanan pesawat. Rekomendasi untuk klaster ini adalah menawarkan program loyalitas eksklusif, upgrade kelas penerbangan, diskon khusus, akses ke lounge bandara, atau pelayanan tambahan yang dapat meningkatkan pengalaman perjalanan mereka.

**Cluster 1**

- Recency (Mean): 365 hari
- Frequency (Mean): 3 kali
- Monetary (Mean): $2472.48
- Jumlah Observasi: 17935

Rekomendasi: Klaster ini terdiri dari pelanggan yang jarang menggunakan layanan pesawat dan memiliki pengeluaran yang rendah dalam layanan pesawat. Rekomendasi untuk klaster ini adalah mengidentifikasi penyebab rendahnya frekuensi perjalanan dan upaya untuk meningkatkan kesadaran atau menawarkan promosi khusus, diskon, atau pelayanan tambahan untuk mendorong mereka untuk melakukan perjalanan lebih sering.

**Cluster 2**

- Recency (Mean): 42 hari
- Frequency (Mean): 5 kali
- Monetary (Mean): $4060.77
- Jumlah Observasi: 10840

Rekomendasi: Klaster ini terdiri dari pelanggan yang baru-baru ini menggunakan layanan pesawat, melakukan perjalanan dengan pesawat dengan frekuensi yang sedang, dan memiliki pengeluaran yang cukup tinggi dalam layanan pesawat. Rekomendasi untuk klaster ini adalah menawarkan paket perjalanan atau promosi yang dapat meningkatkan frekuensi perjalanan mereka, program loyalitas dengan reward menarik, atau pelayanan tambahan yang sesuai dengan kebutuhan perjalanan mereka.

**Cluster 3**

- Recency (Mean): 25 hari
- Frequency (Mean): 28 kali
- Monetary (Mean): $26922.81
- Jumlah Observasi: 16216

Rekomendasi: Klaster ini terdiri dari pelanggan yang baru-baru ini menggunakan layanan pesawat, sering melakukan perjalanan dengan pesawat dengan frekuensi yang tinggi, dan memiliki pengeluaran yang sangat tinggi dalam layanan pesawat. Rekomendasi untuk klaster ini adalah memberikan perhatian khusus kepada pelanggan VIP, menawarkan layanan premium eksklusif, program loyalitas dengan reward premium, akses prioritas di bandara, atau layanan khusus untuk meningkatkan pengalaman perjalanan mereka.
