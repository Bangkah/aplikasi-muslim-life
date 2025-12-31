
# CatatanHarian - Aplikasi Pencatatan Kegiatan Harian Berbasis Java Swing

## Identitas Kelompok
- **Kelompok:**
    - Ammar
    - Atha
    - Irsan
- **Mata Kuliah:** Pemrograman Berorientasi Objek
- **Dosen:** Buk Suci

---

## Cerita Pembuatan Project

Pada awal pembuatan aplikasi CatatanHarian, saya melihat banyak orang di sekitar saya masih mencatat aktivitas harian di buku tulis atau kertas. Sering kali catatan tersebut hilang, rusak, atau sulit ditemukan kembali. Dari situ, saya ingin membuat sebuah aplikasi sederhana yang bisa membantu siapa saja mencatat kegiatan harian secara digital, agar lebih aman dan mudah diakses.

Langkah pertama yang saya lakukan adalah menyiapkan lingkungan pengembangan. Saya menginstall Java JDK versi 21, karena versi ini stabil dan mendukung fitur-fitur modern Java. Saya juga menginstall Apache Ant agar proses build dan pembuatan file JAR bisa dilakukan secara otomatis. Untuk pemilihan tanggal, saya memilih library eksternal JCalendar, yang sangat membantu dalam membuat input tanggal yang user-friendly.

Setelah semua tools siap, saya mulai membuat struktur folder project. Saya buat folder src untuk source code, lib untuk library eksternal, dan nbproject untuk konfigurasi build dari NetBeans. File utama yang saya buat adalah FormCatatanHarian.java, yang berisi seluruh logika dan tampilan aplikasi.

Dalam proses coding, saya menggunakan Java Swing untuk membangun tampilan antarmuka. Saya memilih Swing karena mudah digunakan dan sudah terintegrasi dengan Java. Saya membuat beberapa komponen utama seperti JLabel, JTextArea, JList, JButton, JSpinner, dan JDateChooser. JDateChooser dari JCalendar sangat memudahkan pengguna dalam memilih tanggal catatan.

Saya juga membuat inner class Catatan sebagai model data, dan menggunakan ArrayList untuk menyimpan semua catatan yang dibuat oleh pengguna. Setiap kali pengguna menambah, mengedit, atau menghapus catatan, saya pastikan tampilan daftar catatan langsung diperbarui agar sinkron dengan data.

Salah satu tantangan terbesar adalah mengatur classpath agar JCalendar bisa digunakan tanpa error, serta memastikan semua dependensi terhubung dengan baik. Saya juga harus menyesuaikan versi JDK agar kompatibel dengan library eksternal. Selain itu, saya berusaha membuat UI yang intuitif dan mudah digunakan, agar aplikasi ini bisa dipakai oleh siapa saja tanpa perlu belajar lama.

Setelah logika dasar selesai, saya menambahkan fitur penyimpanan dan pemuatan data ke file txt. Saya memilih format txt karena mudah dibaca dan dipindahkan. Setiap baris berisi tanggal, waktu, dan isi catatan, dipisahkan dengan tanda '|'. Saya juga menambahkan error handling agar jika terjadi masalah saat membaca atau menulis file, aplikasi bisa memberikan pesan yang jelas kepada pengguna.

Terakhir, saya melakukan pengujian aplikasi secara menyeluruh. Saya mencoba menambah, mengedit, menghapus, menyimpan, dan memuat catatan untuk memastikan semua fitur berjalan dengan baik. Setelah yakin aplikasi stabil, saya membuat file build.xml agar proses build bisa dilakukan dengan satu perintah di terminal.

---

## Alur Kerja Program

Ketika aplikasi dijalankan, pengguna akan melihat tampilan utama yang berisi daftar catatan harian. Jika file catatan.txt sudah ada, data akan otomatis dimuat ke dalam daftar. Pengguna bisa menambah catatan baru dengan memilih tanggal menggunakan JCalendar, memilih waktu dengan JSpinner, dan mengisi isi catatan di JTextArea. Setelah itu, pengguna klik tombol Tambah, dan catatan akan langsung muncul di daftar.

Jika ingin mengedit catatan, pengguna cukup memilih catatan dari daftar, lalu data akan ditampilkan di field input. Pengguna bisa mengubah tanggal, waktu, atau isi catatan, lalu klik tombol Edit untuk menyimpan perubahan. Untuk menghapus catatan, pengguna pilih catatan yang diinginkan dan klik tombol Hapus.

Aplikasi juga menyediakan fitur untuk menyimpan semua catatan ke file txt dengan klik tombol Simpan. File akan disimpan dengan format yang sudah ditentukan, sehingga mudah dibaca dan dipindahkan. Jika ingin memuat data dari file lain, pengguna bisa klik tombol Muat dan memilih file txt yang diinginkan.

Setiap perubahan data langsung diperbarui di tampilan, sehingga pengguna selalu melihat data terbaru. Jika terjadi error saat membaca atau menulis file, aplikasi akan menampilkan pesan error yang jelas agar pengguna tahu apa yang harus dilakukan.

---

## Teknologi yang Digunakan

- **Java JDK 21** sebagai bahasa pemrograman utama.
- **Java Swing** untuk membangun tampilan antarmuka pengguna.
- **JCalendar (com.toedter.calendar)** sebagai library eksternal untuk input tanggal.
- **Apache Ant** untuk build automation dan pembuatan file JAR.
- **NetBeans/VS Code** sebagai editor untuk menulis dan mengelola source code.

---

## Penjelasan OOP dan Implementasi pada Project

Karena aplikasi ini dibuat untuk materi Pemrograman Berorientasi Objek (OOP), berikut penjelasan keempat prinsip utama OOP dan penerapannya pada CatatanHarian:

### 1. Enkapsulasi
Enkapsulasi adalah prinsip OOP yang menyatukan data dan fungsi dalam satu unit (class), serta membatasi akses langsung ke data. Pada aplikasi ini, class `Catatan` menyimpan data tanggal, waktu, dan isi catatan, serta menyediakan konstruktor dan method `toString()` untuk mengakses data tersebut. Data dalam class hanya bisa diakses melalui method yang disediakan, sehingga lebih aman dan terstruktur.

### 2. Inheritance (Pewarisan)
Inheritance memungkinkan sebuah class mewarisi sifat dan method dari class lain. Pada aplikasi ini, class utama `FormCatatanHarian` merupakan turunan dari `javax.swing.JFrame`. Dengan mewarisi JFrame, aplikasi langsung mendapatkan semua fitur dan method dari JFrame, sehingga bisa digunakan untuk membangun tampilan GUI tanpa harus menulis ulang semua kode dasar window.

### 3. Polimorfisme
Polimorfisme adalah kemampuan sebuah objek untuk memiliki banyak bentuk, biasanya melalui method overriding atau interface. Pada aplikasi ini, polimorfisme terlihat pada penggunaan method `toString()` yang dioverride di class `Catatan`. Ketika objek Catatan ditampilkan di JList, yang dipanggil adalah method `toString()` milik Catatan, bukan method default dari Object. Selain itu, event handler pada Swing juga menggunakan polimorfisme, karena objek ActionListener bisa memiliki implementasi berbeda sesuai kebutuhan.

### 4. Abstraksi
Abstraksi adalah proses menyembunyikan detail implementasi dan hanya menampilkan fitur penting kepada pengguna. Pada aplikasi ini, pengguna hanya berinteraksi dengan tombol dan field input, tanpa perlu tahu bagaimana data disimpan atau diproses di belakang layar. Class dan method yang dibuat juga berfungsi untuk menyederhanakan proses, sehingga kode lebih mudah dipahami dan digunakan.

---

## Penutup

Proses pembuatan aplikasi CatatanHarian memberikan banyak pengalaman, mulai dari mengatur struktur project, mengintegrasikan library eksternal, membangun UI yang intuitif, hingga menangani error pada file I/O. Tantangan terbesar adalah memastikan semua fitur berjalan stabil dan aplikasi mudah digunakan oleh siapa saja.

Dengan aplikasi ini, saya berharap pengguna bisa lebih terorganisir dalam mencatat aktivitas harian, dan data yang dicatat bisa lebih aman serta mudah diakses kapan saja. Aplikasi ini juga bisa menjadi dasar untuk pengembangan fitur-fitur lebih lanjut, seperti pencarian catatan, export ke format lain, atau sinkronisasi dengan cloud.

Terima kasih atas perhatiannya.
