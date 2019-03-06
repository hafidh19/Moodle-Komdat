# Moodle

## Table of Contents

- [Sekilas Tentang Moodle](#sekilas-tentang-moodle)
- [Instalasi](#instalasi)
	- [Basic Requirements](#basic-requirements)
  - [Langkah-Langkah Instalasi](#langkah-instalasi)
- [Cara Pemakaian](#cara-pemakaian)
- [Pembahasan](#pembahasan)
- [Referensi](#referensi)


# Sekilas Tentang Moodle

**Moodle**  (singkatan dari  **_Modular Object-Oriented Dynamic Learning Environment_**) adalah paket perangkat lunak yang diproduksi untuk kegiatan belajar berbasis internet dan situs yang menggunakan prinsip  _social constructionist pedagogy_. Moodle merupakan salah satu aplikasi dari konsep dan mekanisme belajar mengajar yang memanfaatkan teknologi informasi, yang dikenal dengan konsep e-learning. Moodle dapat digunakan secara bebas sebagai produk sumber terbuka (open source) di bawah lisensi GNUPublic License.

Secara filosofi ada 4 (empat) konsep dari CMS Moodle tersebut terhadap pengembangan pendidikan yaitu,  _constructivisme, constructionism, Social Constructivism,_  dan  _Connected and Separate_. CMS Moodle merupakan aplikasi e-learning berbasis web yang menggunakan open source.

# _Basic Requirements_
-   Kita akan membutuhkan sebuah working web server ([Apache](https://docs.moodle.org/36/en/Apache "Apache")), database ([MySQL](https://docs.moodle.org/36/en/MySQL "MySQL"),  [MariaDB](https://docs.moodle.org/36/en/MariaDB "MariaDB")  atau  [PostgreSQL](https://docs.moodle.org/36/en/PostgreSQL "PostgreSQL")) dan konfigurasi dari  [PHP](https://docs.moodle.org/36/en/PHP "PHP"). Cek [_release notes_](https://docs.moodle.org/dev/Moodle_3.6_release_notes)  pada dokumentasi pengembangan untuk _software requirements_.
-   Moodle membutuhkan beberapa ekstensi dari  [PHP](https://docs.moodle.org/36/en/PHP "PHP") .
## Apache
<h3 align='center'><img src="https://www.prodefence.org/wp-content/uploads/2017/06/apache-web-server.png"><h3>

Apache adalah software web server yang gratis dan bersifat open source. Server ini telah menjadi platform bagi  [46% website di seluruh dunia](https://w3techs.com/technologies/details/ws-apache/all/all). Nama resminya adalah  [Apache HTTP Server](https://httpd.apache.org/), dan software ini dikelola dan dikembangkan oleh Apache Software Foundation. Pada projek ini mengunakan **_Apache2_**.
### Instalasi Apache
#### **Automatic Installation**
Ubuntu

    sudo apt install apache2

## MySQL
<h3 align='center'><img src="https://waterfall-security.com/static/mysql-logo.jpg"><h3>

MySQL  adalah sebuah server basis data SQL multiuser dan multi-threaded. SQL sendiri adalah salah satu bahasa basis data yang paling populer di dunia. Implementasi program server basis data ini adalah program daemon mysqld dan beberapa program lain serta beberapa pustaka.
Projek ini menggunakan MySQL karena lebih mudah dalam proses instalasi dan konfigurasinya.
### Instalasi MySQL
#### **Automatic Installation**
Ubuntu

    sudo apt install mysql-server
## PHP
PHP: Hypertext Preprocessor adalah bahasa skrip yang dapat ditanamkan atau disisipkan ke dalam HTML. PHP banyak dipakai untuk memprogram situs web dinamis. PHP dapat digunakan untuk membangun sebuah CMS.
### Instalasi PHP
#### **Automatic Installation**
Ubuntu

    sudo apt install php
 #### **Ekstensi PHP**
Ekstensi PHP yang dibutuhkan atau direkomendasikan diinstall (beberapa, contoh: iconv, ctype and tokenizer sudah tersedia secara default oleh PHP. Selainnya harus diinstall.

-   The  **iconv**  extension is required.
-   The  **mbstring**  extension is recommended.
-   The  **curl**  extension is required (required for networking and web services).
-   The  **openssl**  extension is recommended (required for networking and web services).
-   The  **tokenizer**  extension is recommended.
-   The  **xmlrpc**  extension is recommended (required for networking and web services).
-   The  **soap**  extension is recommended (required for web services).
-   The  **ctype**  extension is required.
-   The  **zip**  extension is required.
-   The  **gd**  extension is recommended (required for manipulating images).
-   The  **simplexml**  extension is required.
-   The  **spl**  extension is required.
-   The  **pcre**  extension is required.
-   The  **dom**  extension is required.
-   The  **xml**  extension is required.
-   The  **intl**  extension is recommended.
-   The  **json**  extension is required.
-   **The appropriate extension for your chosen database is also required.**

-   Other PHP extensions may be required to support optional Moodle functionality, especially external authentication and/or enrolment (e.g. LDAP extension for LDAP authentication and the sockets extension for Chat server).

# Instalasi Moodle
### Langkah Instalasi:
1. Instalasi LAMP (Linux Apache MySQL PHP)
Untuk langkah instalasinya dapat dilihat diatas pada [Basic Requirements](#basic-requirements) atau sebagai berikut.
```
sudo apt update
sudo apt upgrade
sudo apt install apache2 php mysql-server
```
2. Membuat Database
```
# buat database baru
CREATE DATABASE moodle DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

# Create a user/password combination with appropriate permissions for the database
mysql> GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,CREATE TEMPORARY TABLES,DROP,INDEX,ALTER ON moodle.* TO 'moodleuser'@'localhost' IDENTIFIED BY 'yourpassword';
```
3. Download data Moodle dari source
```
# unduh moodle terbaru
wget https://download.moodle.org/stable36/moodle-latest-36.tgz

# extract ke direktori root
sudo tar -xvzf moodle-latest-36.tgz -C /var/www/html

# ubah kepemilikan ke user www-data
sudo chown -R www-data:www-data /var/www/html/moodle
```
Setelah sudah melakukan langkah diatas, buka laman [http://localhost:8888/moodle](http://localhost:8888/moodle) untuk meneruskan instalasi. 


# Cara Pemakaian
Langkah pertama yang harus dilakukan adalah login sebgai admin, yang mana username dan passwordnya kita buat pada instalasi diatas. Setelah berhasil masuk anda akan diarahkan kehalaman seperti berikut.
<h3 align='center'><img src="https://i.imgur.com/fgcxA6M.png"><h3>

Untuk mengatur moodle kita dapat mengakses nya pada menu yang ada di sebelah kiri laman. 
<h3 align='center'><img src="https://i.imgur.com/fPKacEH.png"><h3>

Pilih pada bagian Site administration, lalu akan muncul seperti berikut.
<h3 align='center'><img src="https://i.imgur.com/scrkgIV.png"><h3>

Berikut fitur-fitur yang disediakan moodle dan kegunaannya.
1.  User Management  
Dengan adanya fitur ini, moodle menyediakan fasilitas yang membagi 7 lapisan user agar administrator tidak terlalu sibuk dengan keterlibatan dalam mengerjakan seluruh tugas dalam situs tersebut. 7 lapisan user tersebut adalah : Administrator, Course Creator, Teacher, Non-editing teacher, Student dan Guest.  
  
2.  Authenticated User  
Secara default seluruh user yang telah login merupakan Authenticated User. Walupun suatu user berperan sebagai teacher pada suatu course, namun di course lain ia hanya berperan sebagi authenticated user yang memiliki kedudukan yang sama dengan guest. Perbedaan guest dengan authenticated user, bila belum terdaftar pada suatu course, maka authenticated user dapat langsung mendaftar pada course tersebut sedangkan guest tidak. 

	Walaupun secara default Moodle hanya memberikan 7 lapisan user seperti yang dijelaskan diatas, namun pengguna Moodle (berperan sebagai admin) dapat secara bebas mengkostumisasi, bahkan menambah, jenis lapisan user sesuai keinginannya.  
  
3.  Course Management  
Pada Moodle, yang dapat memanajemen course yang ada hanyalah user dengan role sebagai teacher, dan tentu saja admin yang dapat melakukan apapun. Walaupun user dengan role course creator dapat memciptakan suatu course, namun user tersebut tidak dapat memodifikasi course yang telah ia ciptakan bila ia tidak mengajar di course tersebut (bukan sebagai teacher). Course pada Moodle memiliki beberapa format, yaitu : LMAS course format, SCORM Format, Social Format, Topics Format, Weekly Format, Weekly Format – CSS-no tables  
  
4.  Assignments  
Dengan aktifitas ini, teacher dapat memberikan tugas yang mengharuskan student mengirim (upload) konten digital, misalnya essay, tugas proyek, laporan, dan lain-lain. Jenis file yang dapat dikirim misalnya ord-processed documents, spreadsheets, images, audio and video clips. Selanjutnya teacher dapat melihat dan menilai tugas yang telah dikirim oleh student.  
  
5.  Chats  
Dengan fitur ini, setiap peserta dapat berdiskusi secara real-time via web.  
  
6.  Choices  
Fitur ini sangat sederhana – teacher memberikan beberapa pertanyaan dan menyediakan berberapa pilihan jawaban. Aktifitas ini dapat digunakan sebagai polling untuk merangsang daya pikir terhadap sebuah topic, misalnya membiarkan sebuah kelas untuk menentukan (vote) arah dari course.  
  
7.  Database Activity  
Dengan fitur ini, teacher dan/atau students dapat membuat, melihat dan mencari bank data mengenai topik apapun. Format dan struktur data yang dimasukkan hamper tidak terbatas, termasuk gambar, file, URL, nomor, dan text.  
  
8.  Forums  
Sama dengan chat, pada forum, student dan teacher dapat berinteraksi satu sama lain secara real-time. Namun tidak seperti chat, pada forum interaksi yang dilakukan secara asinkron. Setiap member yang tergabung dalam forum akan menerima salinan dari posting di email mereka.  
  
9.  Glossary  
Pada fitur ini, pererta dapat membuat kumpulan/daftar pengertian-pengertian kata, seperti kamus. Data yang dimasukkan dapat berasal dari berbagai format dan secara otomatis dapat dibuat link ke materi lain.  
  
10.  Lesson  
Lesson ditujukan agar teacher dapat membuat aktifitas yang berisi konten yang menarik dan fleksibel. Lesson terbagi menjadi beberapa halaman dan diakhir setiap halaman biasanya terdapat pertanyaan yang memiliki beberapa jawaban. Jawaban yang dipilih student akan menentukan halaman mana yang akan diaksesnya.  
  
11.  Quizzes  
Pada fitur ini, teacher dapat mendesain kumpulan soal, yang berisi multiple choice, true-false, dan pertanyaan jawaban singkat. Pertanyaan – pertanyaan tersebut akan tersimpan di bank soal yang dapat dikategorikan dan digunakan ulang.  
  
12.  SCORM/AICC Packages  
Dengan fitur ini, teacher dapat membuat paket yang berisi halaman web, grafis, program Javascript, slide presentasi Flash, video, suara and konten apapun yang dapat dibuka di web browser. Paket ini juga diintegrasikan kumpulan soal yang bila diperlukan dapat dinilai dan kemudian dimasukkan ke rapor student.  
  
13.  Surveys  
Survey merupakan feedback, quisioner ataupun angket yang dapat digunakan sebagai bahan pembelajaran ataupun kritikan bagi teacher ataupun course. Sehingga kinerja teacher dan isi dari course dapat diperbaiki diwaktu mendatang.  
  
14.  Wikis  
Pada aktivitas ini, student dan teacher dapat secara kolaboratif menulis dokumen web tanpa mengetahui bahasa html, langsung dari web browser. Hasilnya dapat berupa hasil kreativitas kelas, kelompok ataupun individu.

# Pembahasan
### Kelebihan-Kekurangan Moodle
-   Pros:
	-   Sistem jaringan dan keamanannya dapat diatur sendiri 
	-   Ruang akses yang dapat dibatasi sesuai dengan jaringan yang dibuat
	-   Sistem pembelajaran yang dapat disesuaikan dengan kebutuhan (karena open source)
	-   Fitur yang lengkap untuk sebuah proses pembelajaran jarak jauh

-   Cons:
	-   Membutuhkan pemahaman lebih tentang sistem
	-   Perlu tenaga ahli untuk membangun sistem e-learning-nya
	-   Memerlukan hardware khusus
	-   Harus meng-install aplikasi khusus

### Perbandingan dengan CMS lainnya
1. eFront
**eFront**  adalah sebuah platform sumber terbuka eLearning (juga dikenal sebagai Sistem Manajemen Course (CMS), atau Learning Management Systems (LMS), atau Virtual Learning Environment (VLE)).

**_Kelebihan_**
•  Mudah digunakan dimana eFront dibangun dengan memperhatikan pengguna akhir. Dengan antar muka yang alami, dan mudah untuk melakukan navigasi.
•  Visually attractive mempunyai fitur-fitur yang menarik.
•  Technologically advanced jadi eFront bersifat Object-oriented, dibangun dengan menggunakan Ajax, Unicode, mendukung LDAP and SCORM (1.2 and 2004/4th edition), multilingual eLearning platform.
•  Konsep Pedagogi dimana eFront dintegrasikan dengan konsep pedagogik yang membuat pengguna termotivasi.
•  Open Source and Professionally Supported dari semua edisi eFront ditawarkan dengan source code. Kita bisa download edisi community secara gratis, melakukan kostumasi sesuai kebutuhan, menambah fungsionalitas baru dan membagikannya kepada komunitas. Meskipun didistribusikan sebagai open source, eFront didukung oleh tim pengembang yang professional.
•  Complete. eFront memasukan bermacam-macam komponen yang membantu kita untuk membuat struktur pelajaran dan menambah konten, membangun ujian online, berkomunikasi dengan anggota lain, melacak sejarah dan kemajua dari siswa, melakukan survei, proyek penugasan, dan membuat sertifikat. Dan itu hanya beberapa dari fasilitas yang ada di eFront.

**_Kekurangan_**
Versi open source gratis eFront tidak memiliki fungsionalitas dan sertifikasi eCommerce, serta integrasi media sosial.

# Referensi
[Moodle](https://moodle.org/)
[wiearthabatch7](https://wiearthabatch7.wordpress.com/2013/01/21/kelebihan-dan-kekurangan-moodle-dan-edmodo/)
 [Alya's Update](http://alyafaba.blogspot.com/2016/05/kelebihan-dan-kekurangan-e-front.html)
