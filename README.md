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

## Data Preparation 
Pada bagian ini Anda menjelaskan teknik yang digunakan pada tahapan data preparation.
- Terapkan minimal satu teknik data preparation dan jelaskan proses yang dilakukan.
- Jelaskan alasan mengapa Anda perlu menerapkan teknik tersebut pada tahap data preparation

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan.

Jelaskan bagaimana Anda melakukan proses modeling dalam proyek. Misalnya, anda menggunakan satu algoritma kemudian melakukan improvement dari baseline model atau anda menggunakan dua atau lebih algoritma kemudian membandingkan performanya.

Sajikan model terbauk anda sebagai solusi.
Jelaskan pula hasil dari model anda (misal, hasil prediksi)

## Evaluation
Bagian ini menjelaskan mengenai metrik evaluasi yang digunakan untuk mengukur kinerja model. Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan dan bagaimana formulanya
- Kelebihan dan kekurangan metrik
- Bagaimana cara menerapkannya ke dalam kode.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
_Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
