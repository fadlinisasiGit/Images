# Laporan Proyek Machine Learning - Muhammad Fadli Ramadhan

## Domain Proyek
Teknik adalah penggunaan prinsip-prinsip ilmiah untuk merancang dan membangun mesin, struktur, dan barang-barang lainnya, termasuk jembatan, terowongan, jalan, kendaraan, dan bangunan. Disiplin teknik mencakup berbagai bidang teknik yang lebih khusus, masing-masing dengan penekanan yang lebih spesifik pada bidang tertentu matematika terapan, ilmu terapan, dan jenis aplikasi.
Teknik adalah disiplin yang luas yang sering dipecah menjadi beberapa sub-disiplin. Meskipun seorang insinyur biasanya akan dilatih dalam disiplin tertentu, ia dapat menjadi multi-disiplin melalui pengalaman. Teknik sering dicirikan memiliki empat cabang utama: teknik kimia, teknik sipil, teknik elektro, dan teknik mesin. [Wikipedia](https://en.wikipedia.org/wiki/Engineering).
India memiliki total 6.214 Institusi Teknik dan Teknologi di mana sekitar 2,9 juta siswa terdaftar. Setiap tahun rata-rata 1,5 juta siswa mendapatkan gelar di bidang teknik, tetapi karena kurangnya keterampilan yang dibutuhkan untuk melakukan pekerjaan teknis, kurang dari 20 persen mendapatkan pekerjaan di domain inti mereka. [BWEDUCATION](http://bweducation.businessworld.in/article/Employability-Of-Engineering-Graduates-In-India-A-Challenge-Needs-To-Address/01-06-2019-171291).
Pertanyaan yang relevan adalah apa yang menentukan gaji dan pekerjaan yang ditawarkan para insinyur ini setelah lulus. Berbagai faktor seperti nilai perguruan tinggi, keterampilan kandidat, kedekatan perguruan tinggi dengan pusat industri, spesialisasi yang dimiliki, kondisi pasar untuk industri tertentu menentukan hal ini. Berdasarkan berbagai faktor ini, diperlukan solusi dengan cara analisa menggunakan algoritma machine learning untuk mnegatasi pertanyaan ini.

## Business Understanding
### Problem Statements
Berdasarkan kondisi yang telah diuraikan sebelumnya, perusahaan akan mengembangkan sebuah sistem prediksi gaji lulusan teknik di India untuk Mempertimbangkan gaji para insinyur pada perusahaan agar dapat optimal. Solusi permasalahan menggunakan algoritma regresi, karena hasil prediksi dipengaruhi oleh variabel fitur dan label pada dataset.

### Goals
Membuat prediksi regresi untuk menentukan gaji dan pekerjaan yang ditawarkan para insinyur ini setelah lulus dan pertimbangan suatu perusahaan untuk menentukan gaji karyawan lulusan teknik.

### Solution statements
Tujuan proyek ini adalah Prediksi gaji lulusan teknik di India agar dapat menjadi pertimbangan suatu perusahaan untuk menentukan gaji karyawan lulusan teknik dan data ini merupakan data regresi. Berikut penjelasan model-model machine learning yang akan digunakan untuk masalah ini :

- **K-Nearest Neighbor :** Algoritma yang relatif sederhana dibandingkan dengan algoritma lain. Algoritma KNN menggunakan 'Kesamaan fitur' untuk memprediksi dari setiap data yang baru. Dengan kata lain, setiap data baru diberi nilai berdasarkan seberapa mirip titik tersebut dalam set pelatihan. 
- **Random Forest :** Salah satu algoritma supervised learning. Dapat digunakan untuk menyelesaikan masalah klasifikasi dan regresi. Ini juga merupakan algoritma yang sering digunakan karena cukup sederhana tetapi memiliki stabilitas yang mumpuni.
- **Boosting :** Algoritma ini bekerja dengan membangun model dari data latih. Kemudian membuat model kedua yang bertugas memperbaiki kesalahan model pertama. Model ditambahkan sampai data laatih terprediksi dengan baik atau telah mecapai maksimum model untuk ditambahkan. Algoritma ini bertujuan untuk meningkatkan performa atau akurasi prediksi  dengan menggabungkan beberapa model sederhana dan dianggap lemah (weak learners) sehingga membentuk suatu model yang kuat (strong ensemble learner). 


## Data Understanding
Dataset yang dipakai didapat dari sebuah platform penyedia dataset untuk data science, yaitu [Kaggle](https://www.kaggle.com/). Untuk proyek ini, dataset yang saya pakai yaitu [Dataset](https://www.kaggle.com/manishkc06/engineering-graduate-salary-prediction) 

Berikut adalah keterangan mengenai maksud dari variabel - variabel atau kolom dataset yang saya pakai :
- ID: ID unik untuk mengidentifikasi kandidat
- Salary: CTC tahunan ditawarkan kepada kandidat (dalam INR)
- Gender: Jenis kelamin kandidat
- DOB: Tanggal lahir kandidat
- 10percentage: Nilai keseluruhan diperoleh dalam ujian kelas 10
 -10board: Dewan sekolah yang kurikulumnya diikuti kandidat di kelas 10
- 12graduation: Tahun kelulusan - sekolah menengah atas
- 12percentage: Nilai keseluruhan diperoleh dalam ujian kelas 12
- 12board: Dewan sekolah yang kurikulumnya diikuti kandidat
- CollegeID:  ID unik yang mengidentifikasi universitas/perguruan tinggi tempat kandidat menghadiri untuk sarjananya
- CollegeTier: Setiap perguruan tinggi telah dianotasi sebagai 1 atau 2. Anotasi telah dihitung dari rata-rata skor AMCAT yang diperoleh siswa di perguruan tinggi/universitas. Perguruan tinggi dengan skor rata-rata di atas ambang batas ditandai sebagai 1 dan lainnya sebagai 2.
- Degree: Gelar yang diperoleh / dikejar oleh kandidat
- Specialization: Spesialisasi yang dikejar oleh kandidat
- CollegeGPA: IPK Agregat saat kelulusan
- CollegeCityID: ID unik untuk mengidentifikasi kota tempat perguruan tinggi berada.
- CollegeCityTier: Tingkat kota tempat perguruan tinggi berada. Ini dianotasi berdasarkan populasi kota.
- CollegeState: Nama negara bagian di mana perguruan tinggi berada
- GraduationYear: Tahun kelulusan (gelar Sarjana)
- English : Skor di bagian Bahasa Inggris AMCAT
- Logical: Score in AMCAT Logical ability section
- Quant: Score in AMCAT's Quantitative ability section
- Domain: Scores in AMCAT's domain module
- ComputerProgramming: Score in AMCAT's Computer programming section
- ElectronicsAndSemicon: Score in AMCAT's Electronics & Semiconductor Engineering section
- ComputerScience: Score in AMCAT's Computer Science section
- MechanicalEngg: Score in AMCAT's Mechanical Engineering section
- ElectricalEngg: Score in AMCAT's Electrical Engineering section
- TelecomEngg: Score in AMCAT's Telecommunication Engineering section
- CivilEngg: Score in AMCAT's Civil Engineering section
- conscientiousness: Scores in one of the sections of AMCAT's personality test
- agreeableness: Scores in one of the sections of AMCAT's personality test
- extraversion: Scores in one of the sections of AMCAT's personality test
- nueroticism: Scores in one of the sections of AMCAT's personality test
- openesstoexperience: Scores in one of the sections of AMCAT's personality test
**Note: **Untuk memberi Anda lebih banyak konteks, AMCAT adalah portal pekerjaan.

Dalam Proyek ini, terdapat beberapa bentuk visualisasi data yang diberikan, seperti penggunaan sns.boxplot untuk mengetahui adanya outliers atau data yang berada di luar batas atas dan batas bawah data sehingga bisa diatasi nantinya menggunakan Metode IQR.
![images](https://github.com/fadlinisasiGit/Images/blob/main/sns%20boxplot%20collegeGPA.png?raw=true).

Selain menggunakan sns.bloxplot, saya juga menggunakan visualisasi data berupa count.plot.
![images](https://github.com/fadlinisasiGit/Images/blob/main/countplot%20specialization.png?raw=true).

Seperti pada gambar diatas, visualisasi data menunjukkan banyaknya jumlah sampel dan persentase pada fitur kategori Specialization. Ini menunjukkan banyaknya spesialisasi kerja lulusan teknik di India.

Selain itu, saya menggunakan teknik sns.catplot untuk mempertimbangkan Fitur Salary dengan fitur kategorikal, 
![images](https://github.com/fadlinisasiGit/Images/blob/main/catplot%20.png?raw=true).

sns.pairplot untuk melihat semua grafik fitur numerik,
![images](https://github.com/fadlinisasiGit/Images/blob/main/pairplot.png?raw=true).

dan  sns.heatmap untuk melihat matrik korelasi fitur numerik.
![images](https://github.com/fadlinisasiGit/Images/blob/main/heatmap.png?raw=true).


Setelah dibuat grafik ini, kita telah mendapat banyak data yang telah di visualisasikan sehingga mempermudah untuk proses analisa data.

## Data Preparation 
Untuk data preparation, saya menggunakan beberapa teknik yang diperlukan dalam tahapan data preparation, yaitu :
- **One Hot Encoding fitur kategori :** metode ini dilakukan karena model machine learning akan semakin baik bila data tersebut berupa angka atau biner, bukan kategori/kata-kata, seperti pada gambar di bawah ini. 
![images](https://miro.medium.com/max/700/1*ggtP4a5YaRx6l09KQaYOnw.png).

- **Reduksi dimensi :** Dengan teknik ini, kita bisa mengurangi jumlah fitur dengan tetap mempertahankan informasi pada data sehingga dapat mengurangi fitur atau kolom yang banyak menjadi lebih sedikit. Seperti pada gambar di bawah ini, saya mereduksi 11 fitur yang berkaitan menjadi 1 fitur bernama AMCATscore. 
![images](https://github.com/fadlinisasiGit/Images/blob/main/reduksiPCA.png?raw=true).

- **Train Test Split :** Teknik ini membagi dataset menjadi data train dan data test . teknik ini dilakukan untuk mempermudah proses modeling atau membuat model regresi. 
- **Standarisasi :** Dengan teknik ini dapat membantu untuk membuat fitur data menjadi bentuk yang lebih mudah diolah oleh algoritma.

## Modeling
Pada penjelasan sebelumnya, saya menggunakan 3 model machine learning yang saya gunakan untuk mencari solusi, yaitu K-Nearest Neighbor, Random Forest, dan Boosting. Selanjutnya Ketiga model prediksi ini dibuat dengan parameter acak dan telah diuji beberapa kali.

Dari hasil prediksi ketiga model ini, saya mendapatkan salah satu model terbaik dan peforma baik yang bisa dijadikan solusi proyek ini. Model prediksi tersebut adalah model K-Nearest Neighbor. Hal ini dikarenakan hasil prediksi K-Nearest Neighbor ini mendekati nilai sebenarnya (Salary atau Gaji) sebagai tujuan proyek ini.

![images](https://github.com/fadlinisasiGit/Images/blob/main/3%20model%20prediksi.png?raw=true)

## Evaluation
Dalam bagian Evaluasi, karena masalah di proyek ini adalah masalah regresi, maka saya menguji performa model ini dengan metrik evaluasi MSE atau Mean Squared Error.
MSE didefinisikan dalam persamaan berikut.
![images](https://github.com/fadlinisasiGit/Images/blob/main/mse.png?raw=true).

Keterangan : N = jumlah dataset, yi = nilai sebenarnya, y_pred = nilai prediksi
Berdasarkan [Sumber](https://en.wikipedia.org/wiki/Mean_squared_error), MSE
mengukur rata - rata kuadrat kesalahan yaitu, selisih kuadrat rata-rata antara nilai taksiran dan nilai sebenarnya. MSE adalah fungsi risiko , sesuai dengan nilai yang diharapkan dari kerugian kesalahan kuadrat. Dalam amalisis regresi, melakukan plotting adalah cara yang lebih alami untuk melihat tren dari keseluruhan data. Rata-rata jarak dari setiap titik ke model regresi yang diprediksi dapat dihitungkan, dan ditampilkan sebagai MSE. Kuadrat sangat penting untuk mengurangi kompleksitas dengan tanda-tanda negatif. Untuk meminimalkan MSE, model bisa lebih akurat, yang berarti model lebih dekat dengan data sebenarnya.  

Jadi, MSE menghitung selisih rata-rata nilai sebenarnya dengan nilai prediksi. Jika prediksi mendekati nilai sebenarnya, maka performa model baik. Jika tidak, performa model buruk.

Sebelum menghitung nilai MSE dalam model, kita perlu melakukan proses scaling fitur numerik pada data test. Kita perlu melakukan scaling terhadap data uji. Hal ini harus dilakukan agar skala antara data train dan data test sama dan kita bisa melakukan evaluasi.
Untuk proses scaling, masukkan kode berikut : 
*X_test.loc[:, numerik_fitur] = scaler.transform(X_test[numerik_fitur])*
Setelah itu ketiga model bisa di evaluasi dengan metrik MSE.


## Penutup
Sekian dari laporan proyek machine learning, predicitive analytics. Terima kasih telah membaca laporan ini. Semoga dapat menjadi manfaat bagi yang membaca laporan ini.
