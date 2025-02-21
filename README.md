# AplikasiPenghitunganHari-PERBAIKAN
 Berikut adalah file `README.md` untuk proyek **Perhitungan Hari** Anda:  

---

## **📅 Aplikasi Perhitungan Hari**  
Aplikasi ini dibuat menggunakan Java dengan **NetBeans JFrameForm**, bertujuan untuk menghitung jumlah hari dalam suatu bulan dan menampilkan informasi tambahan seperti:  
✅ Jumlah hari dalam bulan tertentu.  
✅ Hari pertama dan terakhir dalam bulan tersebut.  
✅ Validasi apakah tahun yang dipilih merupakan **tahun kabisat** atau bukan.  
✅ Menghitung selisih hari antara dua tanggal yang dipilih pengguna.  

---

## **🛠 Fitur Utama**  
### 🎯 **1. Hitung Jumlah Hari dalam Bulan**  
- Pengguna memilih **bulan** dan **tahun** dari **ComboBox** dan **JSpinner**.  
- Aplikasi menghitung jumlah hari dalam bulan tersebut.  

### 📅 **2. Tampilkan Hari Pertama dan Terakhir**  
- Menampilkan **hari pertama** dan **hari terakhir** dalam bulan yang dipilih.  
- Contoh output:  
  ```
  Hari Pertama: MONDAY
  Hari Terakhir: WEDNESDAY
  ```

### 🔍 **3. Validasi Tahun Kabisat**  
- Aplikasi memeriksa apakah tahun yang dipilih adalah **tahun kabisat** atau bukan.  
- Contoh output:  
  ```
  Tahun ini adalah tahun kabisat
  ```

### 🔢 **4. Hitung Selisih Hari antara Dua Tanggal**  
- Pengguna memilih **dua tanggal** menggunakan **JDateChooser**.  
- Aplikasi menghitung dan menampilkan jumlah hari di antara kedua tanggal tersebut.  

---

## **📌 Cara Menjalankan Aplikasi**  
1️⃣ **Buka NetBeans** dan buat **Project Baru**.  
2️⃣ **Tambahkan File Baru** dengan nama `PerhitunganHariForm.java`.  
3️⃣ **Salin kode berikut ke dalam file**:  

```java
// Impor library yang dibutuhkan
import java.time.LocalDate;
import java.time.YearMonth;
import java.util.Date;
import java.time.ZoneId;
import javax.swing.event.ChangeListener;
import com.toedter.calendar.JDateChooser;
import java.time.temporal.ChronoUnit;

public class PerhitunganHariForm extends javax.swing.JFrame {

    public PerhitunganHariForm() {
        initComponents();
    }

    private void hitungButtonActionPerformed(java.awt.event.ActionEvent evt) {                                             
        int tahun = (Integer) spinnerTahun.getValue();
        int bulanIndex = comboBoxBulan.getSelectedIndex() + 1; // Januari = 1, Februari = 2, dst.

        if (tahun <= 0) {
            hasilLabel.setText("Tahun tidak valid!");
            return;
        }

        YearMonth yearMonth = YearMonth.of(tahun, bulanIndex);
        int jumlahHari = yearMonth.lengthOfMonth();
        hasilLabel.setText("Jumlah hari: " + jumlahHari);

        // Hitung hari pertama dan terakhir dalam bulan
        LocalDate tanggalPertama = LocalDate.of(tahun, bulanIndex, 1);
        LocalDate tanggalTerakhir = LocalDate.of(tahun, bulanIndex, jumlahHari);

        hariPertamaLabel.setText("Hari Pertama: " + tanggalPertama.getDayOfWeek());
        hariTerakhirLabel.setText("Hari Terakhir: " + tanggalTerakhir.getDayOfWeek());

        // Cek apakah tahun kabisat
        boolean isKabisat = YearMonth.of(tahun, 2).lengthOfMonth() == 29;
        tahunKabisatLabel.setText(isKabisat ? "Tahun ini adalah tahun kabisat" : "Tahun ini bukan tahun kabisat");
    }
                                 
    private void spinnerTahunStateChanged(javax.swing.event.ChangeEvent evt) {                                          
       hitungButtonActionPerformed(null);
    }
                             
    private void hitungSelisihButtonActionPerformed(java.awt.event.ActionEvent evt) {                                                     
        Date tanggalAwal = dateChooser1.getDate();
        Date tanggalAkhir = dateChooser2.getDate();

        if (tanggalAwal == null || tanggalAkhir == null) {
            selisihHariLabel.setText("Pilih kedua tanggal!");
            return;
        }

        LocalDate awal = tanggalAwal.toInstant().atZone(ZoneId.systemDefault()).toLocalDate();
        LocalDate akhir = tanggalAkhir.toInstant().atZone(ZoneId.systemDefault()).toLocalDate();

        long selisih = ChronoUnit.DAYS.between(awal, akhir);
        selisihHariLabel.setText("Selisih: " + selisih + " hari");
    }       

    public static void main(String args[]) {
        java.awt.EventQueue.invokeLater(new Runnable() {
            public void run() {
                new PerhitunganHariForm().setVisible(true);
            }
        });
    }
}
```

---

## **🛠 Teknologi yang Digunakan**  
✅ **Java SE** (JDK 8+)  
✅ **NetBeans IDE**  
✅ **Java Swing (JFrameForm)**  
✅ **JDateChooser** (Untuk memilih tanggal)  

---

`.  

---

## **📜 Lisensi**  
Aplikasi ini dibuat untuk **tujuan edukasi** dan bebas digunakan. 🚀  

---

