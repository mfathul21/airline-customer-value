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

**THandling Date Features**

Pada dataset flight terdapat 4 fitur date, yaitu fpp_date, first_flight_date, last_flight_date, dan load_time dengan tipe data object. Oleh karena itu, dilakukan konversi ke datetime sehingga mempermudah nantinya dalam proses feature engineering. Sebelum itu, dikarenakan terdapat perbedaan format tanggal antara fitur last_flight_date dengan fitur lainnya yang menggunakan format %m/%d/%Y. Selain itu, format pada fitur last_flight_date tidak konsisten karena ada beberapa baris dengan format %m/%d/%Y dan beberapa baris lainnya dengan format %Y/%m/%d %H:%m:%s. Sebelum melakukan konversi tipe data dari objek menjadi datetime, perlu dilakukan manipulasi terlebih dahulu untuk memastikan formatnya menjadi konsisten dan sesuai.

## Feature Engineering
