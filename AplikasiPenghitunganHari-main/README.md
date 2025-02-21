# AplikasiPenghitunganHari
Tugas 4 - (Muhammad Fajar Fitrianto_2210010748)

kelas : 5B NonReg Banjarmasin

Form Perhitungan Hari

# Deskripsi

PerhitunganHariForm adalah aplikasi berbasis Java yang menggunakan JFrame untuk membuat antarmuka grafis. Aplikasi ini bertujuan untuk menghitung jumlah hari dalam bulan tertentu, dengan input berupa tahun dan bulan. Proyek ini menggunakan komponen JFrame dan pustaka java.time untuk pengolahan tanggal.

# Fitur

Input tahun dan bulan untuk menghitung jumlah hari.

Tombol untuk menghitung hasil.

Antarmuka yang user-friendly menggunakan Java Swing.

 # Panduan Membuat JFrame Form
1.Desain Form di NetBeans:

-Buka NetBeans IDE.

-Buat proyek Java baru.

-Klik kanan pada package, `pilih New` > `JFrame Form.`

-Gunakan Drag and Drop untuk menambahkan komponen seperti `JLabel`, `JTextField`, dan `JButton.`

2.Edit Kode Manual:

-Klik dua kali pada tombol untuk membuat event handler.

-Tambahkan logika koding pada metode yang dihasilkan seperti hitungHari.


# Penjelasan Koding
Berikut adalah penjelasan singkat mengenai struktur kode dalam file PerhitunganHariForm.java:

Import Library

`import java.time.LocalDate;`

`import java.time.YearMonth;`

"Kode ini mengimpor pustaka java.time untuk manipulasi tanggal yang modern dan aman."

Deklarasi Kelas Utama


`public class PerhitunganHariForm extends javax.swing.JFrame {`

"Kelas ini memperluas JFrame, yang berarti antarmuka pengguna dibangun menggunakan komponen Swing."

# Konstruktor dan Komponen



public PerhitunganHariForm() {    
        
        initComponents();
    hitungButton.addActionListener(new java.awt.event.ActionListener() {
        public void actionPerformed(java.awt.event.ActionEvent evt) {
            hitungHari(evt);
        }
    });
    }


"Konstruktor memanggil metode `initComponents()` untuk menginisialisasi semua komponen yang dirancang di GUI. Tombol `hitungButton` dihubungkan dengan event listener yang memicu metode `hitungHari().`"

# Metode Penghitungan


private void hitungButtonActionPerformed(java.awt.event.ActionEvent evt) {                                             
  
   
   
   
   String bulanDipilih = (String) comboBoxBulan.getSelectedItem();
    
    int tahun = (Integer) spinnerTahun.getValue();
   
    int bulanIndex = comboBoxBulan.getSelectedIndex() + 1; // Indeks ke-0 untuk Januari
    
    YearMonth yearMonth = YearMonth.of(tahun, bulanIndex);
    int jumlahHari = yearMonth.lengthOfMonth();
    
    hasilLabel.setText("Jumlah hari: " + jumlahHari);
    }                                            

Metode ini membaca input tahun dan bulan dari `TextField`, lalu menghitung jumlah hari di bulan tersebut menggunakan `YearMonth`. Hasilnya ditampilkan di `Label`.


# Cara Menjalankan Proyek

-Kloning atau unduh repositori ini.

-Buka proyek di NetBeans.

-Jalankan dengan menekan tombol Run atau Shift + F6.

