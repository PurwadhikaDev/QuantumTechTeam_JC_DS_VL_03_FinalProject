# QuantumTechTeam_JC_DS_VL_03_FinalProject
QuantumTech repository was made by three people in order to complete the final project assigned by Purwadhika Digital Technology School.

QuantumTech team contributors:
1. Andika Virdian (andika.virdian@gmail.com)
2. Yogi Wibowo Agusta (yogiwibowoagusta@gmail.com)
3. Rachenda Pandu Purwakusuma (timoepandoe@gmail.com)

[Sumber data City of Philadelphia](https://www.kaggle.com/adebayo/philadelphia-buildings-database) 

### **Contents**

1. Business Problem Understanding

   **Context**

   OPA (Office of Property Assesstment) merupakan lembaga pemerintahan Kota Philadelphia yang memiliki wewenang dalam penentuan harga properti di Philadephia. Sejatinya properti di Philadelphia adalah salah satu sektor sumber pendapatan untuk Kota Phialdephia. Melansir dari web Reclaim Philadelphia (https://www.reclaimphiladelphia.org/blog/2019/2/17/how-are-our-schools-funded), pemasukan dari properti adalah pemasukan yang digunakan untuk sektor pendidikan di Kota Philadelphia. Pada tahun 2019 alokasi dana Pendidikan sebesar $877 dolar atau setara 54% dari total pendapatan pajak properti kota Philadelphia. 

   Pada tahun 2020, OPA menerapkan kebijakan penghentian dan pengurangan pembayaran pajak properti dalam menghadapi pandemi Covid-19. Kebijakan tersebut antara lain:

      1.  Penghentian pembayaran pajak 100% untuk properti baru dan properti yang direhabilitasi (residential/single family) selama 10     tahun kedepan khusus untuk pemilik properti yang telah mengajukan properti nya kepada OPA sebelum 31 Desember 2021, jika mendata setelah 1 Januari 2022 maka tetap dapat 100% pengehentian pembayaran pajak 100% untuk 1 tahun pertama, 9 tahun selanjutnya hanya pengurangan pajak 10%.
      2. Pengurangan pajak properti industrial dan komersial sebesar 10%  selama 10 tahun.

   Sumber (https://nochumson.com/what-you-need-to-know-about-philadelphia-tax-abatement-program/#:~:text=Under%20Philadelphia's%20residential%20tax%20abatement,tax%20abatement%20for%2010%20years.)

   Mengingat sektor properti dalah pendapatan Kota Philadelphia untuk dana pendidikan, kebijakan OPA tentu ada keuntungan dan kerugiannya, dimana OPA tentu pendapatan sektor properti akan berkurang dan untungnya menarik para penduduk untuk dapat memperoleh properti / rehabilitasi propertinya.

   **Problem Statement**

   Berdasarkan penjelasan OPA overview of Trending Methodology March 2019 sumber (https://www.phila.gov/documents/assessment-methodologies/). Dalam penentuan harga properti, OPA merumuskan metode penilaian pajak yaitu "mass appraisal" dan "ratio trend method", 

      1. Mass Appraisal: Menentukan harga properti pasaran berdasarkan variable dan karakteristik properti berbasis Computer Assisted Mass Appraisal (CAMA).
      2. Ratio Trend Method: Menentukan tren kenaikan harga properti yang dikelompokan berdasarkan lokasi dan tipe properti. Ratio diperoleh berdasarkan perbandingan Harga properti pasaran dengan harga jual. 

   Akan tetapi, OPA belum mempunyai tim yang berkompeten dalam menyelesaikan reformasi penilaian harga properti dengan metode Mass Appraisal berbasis CAMA. Untuk itu OPA menggunakan metode Ratio Trend untuk menentukan harga properti. Namun, metode Ration Trend ini memiliki kelemahan, yaitu terbatas waktu dan perlu dilakukan revaluasi trend setiap tahun serta sangat berpengaruh terhadap harga jual properti. Jika properti memiliki variable dan karakteristik properti sama namun harga jual berbeda tentunya timbul ketidak adilan penilaian harga. Sebaliknya, jika properti memiliki variable dan karakteristik berbeda namun harga jual sama tentunya harga properti pendapatan OPA dari harga properti tidak maksimal.

   Target : Harga Pasaran / Market Value

   **Goals**

   Berdasarkan permasalahan tersebut, OPA tentu perlu memiliki model yang dapat memprediksi untuk dapat 

   **Menentukan Harga Pasaran Properti Berdasarkan Variable dan Karaktersitik Properti**. 

   Goal kami adalah Membantu OPA dalam mengatasi permasalahan penentuan harga pasaran / market value. Dimana market value yang nantinya akan ditujukan untuk penentuan nilai pajak pendapatan Kota Phialdephia. 

   Kami memberikan asumsi, bobot presentasi komponen pajak ditentukan sesuai regulasi OPA sehingga yang akan kami lakukan hanya menentukan Market value berdasarkan variable dan karakteristik properti saja agar market value dapat dijadikan OPA sebagai dasar perhitungan pendapatan dari sektor properti

   Kami mengasumsikan Market Value sebagai NJOP dan PBB adalah pajak yang ditetapkan oleh pemerintah setempat

   **Analytic Approach**

   Setelah kami mempelajari dataset ini, untuk menentukan harga pasaran / market value dalam model, berikut prosesnya
      - Kami membagi properti berdasarkan jumlah data tipe katagori properti nya (6 tipe kategori properti). (Jumlah data : 581,456 dengan persebaran data, Single family: 79.39 %, multi family: 7.67%, mixed use: 2.47%, commercial: 2.41% , industry: 0.74% dan vacant land: 7.67%). 
        Kami membagi berdasarkan data berdasarkan kategorinya dikarenakan rentang data yang terlalu besar sehingga nanti akan diperoleh 6 model regressi.
      - Kemudian kami mengelompokkan variable dan karateristik dari properti yang akan ditentukan berdasarkan domain knowledge dan laporan OPA assessment
      - Kemudian kami melakukan modelling secara regressi untuk menentukan prediksi harga pasaran / market value

   **Metric Evaluation**

   Evaluasi metrik yang akan digunakan adalah RMSE, MAE, di mana RMSE adalah nilai rataan akar kuadrat dari error, MAE adalah rataan nilai absolut dari error. Semakin kecil nilai RMSE, dan MAE, berarti model semakin akurat dalam memprediksi harga sewa sesuai dengan limitasi fitur yang digunakan. 

   Selain itu, kita juga bisa menggunakan nilai R-squared atau adj. R-squared jika model yang nanti terpilih sebagai final model adalah model linear. Nilai R-squared digunakan untuk mengetahui seberapa baik model dapat merepresentasikan varians keseluruhan data. Semakin mendekati 1, maka semakin fit pula modelnya terhadap data observasi. Namun, metrik ini tidak valid untuk model non-linear.

2. Data Understanding
   - Dataset merupakan data listing OPA Properti di kota Philadelphia pada tahun 2019
   - Setiap baris data merepresentasikan informasi terkait properti dan pemiliknya.
   - Dataset merupakan data OPA dari kota Philadelphia tahun 2019.
   - Setiap baris data merepresentasikan informasi terkait properti dan detailnya.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| assessment_date | Integer | Tanggal dilakukan penilaian properti terakhir |
| basements | Object | Ketersedian basement dan jenis basementnya |
| beginning_point | Object | Alamat properti |
| book_and_page | Integer | Nomor dokumen penilaian properti yang tercatat di OPA |
| building_code | Object | Kode properti |
| building_code_description | Object | Deskripsi mengenai properti |
| category_code | Integer | 1,2,3,4,5,6 |
| category_code_description | Object | 1. Single Family, 2. Multi Family , 3. Mixed Use, 4. Commercial, 5. Industrial, 6. Vacant Land |
| census_tract | Integer | Kode sub wilayah sensus OPA |
| central_air | Object | Y. Memiliki central air N. Tidak memiliki central air |
| cross_reference | Integer | Nomor akun yang tercatat pada transaski terakhir |
| date_exterior_condition | Date | Usia properti bangunan  |
| depth | float | Posisi elevasi properti terhadap badan jalan. Kedalaman dalam satuan ft..  |
| exempt_building | Integer | Harga properti bangunan yang tidak kena pajak. Dalam satuan dollar |
| exempt_land | Integer | Harga properti tanah yang tidak kena pajak. Dalam satuan dollar |
| exterior_condition | Integer | Kondisi properti. 0. Not Applicable -  Tidak dapat dilakukan renovasi, **1. ..**, 2. Newer construction / Rehabbed - Properti dalam pembangunan / renovasi, 3. Aboce average - Properti yang terawat dan renovasi tidak dibutuhkan, 4. Average - Properti yang membutuhkan renovasi ringan, 5. Below average - Dibutuhkan renovasi, 6. Vacant - area tidak ditempati, 7. Sealed / Structural compromised - properti yang di segel   |
| fireplaces | integer | Jumlah perapian |
| frontage | float | lebar properti dilihat dari posisi jalan akses utama. dalam satuan ft. |
| fuel | Object | Kategori bahan bakar perapian. A. Natural Gas, B. Oil Heat, C. Electric, D. Coal, E. Solar, F. Wood, G. Other, H. None |
| garage_spaces | Integer | Jumlah kapasitas parkiran |
| garage_type | Object | Tipe garasi. 0. Tidak ada, A. Basement, B. Attached Garage - connected with dwelling, C. Detached garage - separate building, F. Converted, S. Self park, T. Attendant |
| **general construction** | Object | - Undescribed - |
| geographic_ward | Integer | - Undescribed -  |
| homestead_exemption | Integer | Pembebasan pajak bangunan |
| house_extension | Integer | Detail alamat rumah |
| house_number | Integer | Nomor rumah |
| interior_condition | Integer | Kondisi properti. 0. Not Applicable -  Tidak dapat dilakukan renovasi, **1. ..**, 2. Newer construction / Rehabbed - Properti dalam pembangunan / renovasi, 3. Aboce average - Properti yang terawat dan renovasi tidak dibutuhkan, 4. Average - Properti yang membutuhkan renovasi ringan, 5. Below average - Dibutuhkan renovasi, 6. Vacant - area tidak ditempati, 7. Sealed / Structural compromised - properti yang di segel |
| location | Object | Alamat properti |
| mailing_address_1 | Object | alamat email 1 |
| mailing_address_2 | Object | alamat email 2 |
| mailing_care_of | Object | alamat email care of |
| mailing_city_state | Object | nama kota dalam surat menyurat |
| mailing_street | Object | nama jalan dalam surat menyurat |
| mailing_zip | Integer | kode ZIP surat menyurat |
| market_value | Integer | Harga properti dasar yang ditetapkan OPA |
| market_value_date | Object | Tanggal penetapan harga properti dasar oleh OPA |
| number_of_bathrooms | Integer | Jumlah kamar mandi |
| number_of_bedrooms | Integer | Jumlah kamar tidur |
| number_of_rooms | Integer | Jumlah kamar |
| number_stories | Integer | Jumlah lantai |
| off_street_open | - Undescribed - | - Undescribed - |
| other_building | Object | Ketersediaan bangunan lain yang terdapat dalam 1 lokasi properti yang sama |
| owner_1 | Object | Pemilik 1 |
| owner_2 | Object | Pemilik 2 |
| parcel_number | Integer | Kode unik sertifikat properti |
| parcel_shape | Object | Bentuk bidang properti. A. Irregular, B. Grossly Irregular, C. Tringular, D. Right of way, E. Rectangular |
| quality_grade | Object | Kualitas bahan bangunan. 1. low, 2. Below average, 3. Average, 4. Above average, 5. Superior, 6. Highest, 0. None |
| recording_date | Date | Tanggal pencatatan yang tercantum pada sertifkat properti |
| registry_number | Object | Nomer id untuk ploting pada peta |
| sale_date | Date | Tanggal dilakukan transaski jual beli  |
| sale_price | Integer | Harga jual properti / harga yang sudah ditetapkan antar kesepakatan |
| separate_utilities | Object | Hanya untuk 2 - 4 unit apartment. A. Central (one heater, hot water tank, electrical service and gas serivce, B. Part separate - not central or all separate, C. All separate (except water), all utilities such as cooking gas, gas for hot water, gas for heat, electric) |
| sewer | Object | Ketersediaan selokan |
| site_type | Object | - Undescribed - |
| state_code | Integer | Kode kota |
| street code | Integer | Kode Angka Jalan |
| street_designation | Object | Singkatan Nama Jalan |
| street_direction | Object | Arah jalan |
| street_name | Object | Nama Jalan |
| suffix | Object | Ekstensi alamat |
| taxable_building | Integer | Nilai Harga properti bangunan di sertifikat |
| taxable_land | | Nilai Harga propert tanah di sertifikat |
| topography | Object | Most of properti at street level., A. Above street level, B. Below Street level, C. Flood Pain, D. Rocky, E. Relates to anything not identified here that may be observed that may have some effect  on valu, F. Level  |
| total_area | integer | Luas Properti. sq ft.|
| total_liveable_area | Integer | Luas properti yang dapat dihuni. sq ft. |
| type_heater | Object | Tipe pemanas. A. Hot air (ducts), B. How water (radiators or baseboards), C. Electrict baseboard, D. Heat pump (outside unit), E. Other, G.Radiant, H. Undertermined |
| unfinished | Object | Status U, bangunan belum selesai / under construction |
| unit | Object | Nomor unit kondominium |
| utility | Object | Utilitas. Undefined. |
| view_type | Object | Pemandangan dari jendela. 0. Not applicable, A. Cityscape / Skyline, B. Flowing water, C. Park?Green, D. Commercial, E. Industrial, H.Edifice/ landmark, I. Other |
| year_built | Object | Tahun pembuatan properti |
| year_built_estimate | Object | Estimasi tahun pembuatan properti |
| zip code | Integer | Kode Zip |
| zoning | Object | Properti Zoning |
| objectid | Integer | - Undescribed - |

   
3. Data Cleaning dan Data Preprocessing
    - EDA
        1. Load Dataset
        2. Menghitung Missing data
        3. Data Prepocessing
Drop Data
Mengisi NaN dengan Data Lain
Mengisi NaN dengan Median
Mengisi NaN dengan Modus
        4. Feature Enginering
        5. Data Preprocessing
        6. Normalized Price
            melakukakan Normalisai market value - Kolom market value ditransform menggunakan log
        7. Output
        8. Data Nominal
        9. Data Visualization
4. Modeling
5. Conclusion
6. Recommendation

****
