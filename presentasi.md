# Presentasi UAS - CatatanHarian


## 1. Judul & Identitas
- **Judul:** CatatanHarian - Aplikasi Pencatatan Kegiatan Harian Berbasis Java Swing
- **Kelompok:**
    - Ammar
    - Atha
    - Irsan
- **Mata Kuliah:** Pemrograman Berorientasi Objek
- **Dosen:** Buk Suci

---

## 2. Latar Belakang
- Banyak orang membutuhkan media sederhana untuk mencatat aktivitas harian.
- Catatan manual di kertas rentan hilang dan tidak praktis.
- Aplikasi desktop sederhana memudahkan pencatatan, pencarian, dan pengelolaan catatan harian.

---

## 3. Tujuan Aplikasi
- Membantu pengguna mencatat, mengedit, dan menghapus catatan harian.
- Menyimpan catatan secara digital agar mudah diakses dan dikelola.
- Memberikan pengalaman pengguna yang mudah dan intuitif.

---

## 4. Fitur Utama
- Menambah catatan harian (tanggal, waktu, isi)
- Edit dan hapus catatan
- Menyimpan & memuat catatan ke/dari file `catatan.txt`
- Tampilan GUI modern dengan Java Swing
- Pemilihan tanggal menggunakan JCalendar

---

## 5. Teknologi & Tools
- Bahasa Pemrograman: Java (JDK 21)
- GUI: Java Swing
- Library Eksternal: JCalendar (com.toedter.calendar)
- Build Tool: Apache Ant
- Editor: NetBeans/VS Code

---

## 6. Struktur Project
```
CatatanHarian/
├── build.xml
├── catatan.txt
├── lib/jcalendar-1.4.jar
├── manifest.mf
├── nbproject/
├── src/FormCatatanHarian.java
└── ...
```

---

## 7. Penjelasan Alur Program
1. **Tampilan Awal:**
   - Form utama menampilkan daftar catatan.
2. **Menambah Catatan:**
   - User memilih tanggal, waktu, dan mengisi catatan, lalu klik Simpan.
3. **Edit/Hapus Catatan:**
   - Pilih catatan dari daftar, edit atau hapus sesuai kebutuhan.
4. **Penyimpanan:**
   - Data disimpan ke file `catatan.txt` dengan format: `YYYY-MM-DD|HH:mm|isi catatan`.
5. **Memuat Data:**
   - Saat aplikasi dibuka, data dari file otomatis dimuat ke daftar.

---

## 8. Contoh Kode Penting
### a. Model Data Catatan
```java
public class Catatan {
    String tanggal, waktu, isi;
    public Catatan(String tanggal, String waktu, String isi) {
        this.tanggal = tanggal;
        this.waktu = waktu;
        this.isi = isi;
    }
    public String toString() {
        return tanggal + " " + waktu + " - " + isi;
    }
}
```

### b. Menyimpan ke File
```java
PrintWriter writer = new PrintWriter("catatan.txt");
for (Catatan c : daftar) {
    writer.println(c.tanggal + "|" + c.waktu + "|" + c.isi);
}
writer.close();
```

### c. Memuat dari File
```java
BufferedReader reader = new BufferedReader(new FileReader("catatan.txt"));
String line;
while ((line = reader.readLine()) != null) {
    String[] parts = line.split("\\|");
    if (parts.length == 3) daftar.add(new Catatan(parts[0], parts[1], parts[2]));
}
reader.close();
```

---

## 9. Demo Aplikasi (Live/Video)
- Tunjukkan proses menambah, mengedit, menghapus, dan menyimpan catatan.
- Tampilkan file `catatan.txt` hasil penyimpanan.

---

## 10. Kelebihan & Kekurangan
### Kelebihan:
- Sederhana, ringan, mudah digunakan
- Data mudah dicadangkan (file txt)
- Bisa dikembangkan lebih lanjut (misal: export ke PDF, sinkronisasi cloud)

### Kekurangan:
- Belum ada fitur pencarian/penyaringan catatan
- Data belum terenkripsi
- Tampilan masih sederhana

---

## 11. Rencana Pengembangan
- Menambah fitur pencarian catatan
- Export/import data ke format lain (CSV, PDF)
- Sinkronisasi dengan cloud atau aplikasi mobile
- Penambahan autentikasi user

---

## 12. Penutup
- CatatanHarian membantu pengguna lebih produktif dan terorganisir.
- Terima kasih atas perhatiannya.

---

## 13. Tanya Jawab
- Silakan ajukan pertanyaan terkait aplikasi atau pengembangan lebih lanjut.
