# CatatanHarian

CatatanHarian adalah aplikasi desktop sederhana berbasis Java Swing untuk mencatat kegiatan harian. Aplikasi ini memungkinkan pengguna menambah, mengedit, menghapus, dan melihat daftar catatan harian dengan tanggal dan waktu.

## Fitur Utama
- Menambah catatan harian dengan tanggal, waktu, dan isi catatan
- Mengedit dan menghapus catatan yang sudah ada
- Menyimpan dan memuat catatan ke/dari file `catatan.txt`
- Tampilan GUI berbasis Java Swing
- Pemilihan tanggal menggunakan komponen JCalendar

## Struktur Project

```
CatatanHarian/
├── build.xml                # File build Ant
├── catatan.txt              # File penyimpanan data catatan
├── lib/
│   └── jcalendar-1.4.jar    # Library eksternal JCalendar
├── manifest.mf              # File manifest JAR
├── nbproject/               # Konfigurasi NetBeans/Ant
├── src/
│   └── FormCatatanHarian.java # Source code utama aplikasi
└── ...
```

## Dependensi
- Java JDK 21 atau lebih baru
- JCalendar 1.4 (`lib/jcalendar-1.4.jar`)

## Cara Build
1. Pastikan JDK sudah terpasang (disarankan JDK 21)
2. Pastikan file `lib/jcalendar-1.4.jar` sudah ada (otomatis jika mengikuti instruksi ini)
3. Jalankan perintah berikut di terminal:
   ```
   ant -buildfile build.xml
   ```
   Hasil build akan berada di folder `dist/CatatanHarian.jar`

## Cara Menjalankan
### Dari Source (direktori build/classes)
```
java -cp build/classes:lib/jcalendar-1.4.jar FormCatatanHarian
```

### Dari File JAR
Jika JAR sudah berisi manifest Main-Class yang benar:
```
java -jar dist/CatatanHarian.jar
```
Jika belum, gunakan classpath manual:
```
java -cp dist/CatatanHarian.jar:lib/jcalendar-1.4.jar FormCatatanHarian
```

## Format File catatan.txt
Setiap baris: `YYYY-MM-DD|HH:mm|isi catatan`
Contoh:
```
2025-11-12|09:32|kampus
2025-11-11|10:32|pulang
```

## Author
UTS - Muhammad Rezkyan Noor (2310010087)
