# myportofolio_mobile

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Learn Flutter](https://docs.flutter.dev/get-started/learn-flutter)
- [Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Flutter learning resources](https://docs.flutter.dev/reference/learning-resources)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
### Tugas 7

1. Widget tree adalah struktur hierarki berbentuk pohon yang menggambarkan seluruh wiget yang tersusun dan terbungkus antara satu dengan yang lain, dari root sampai leaf.

Hubungan child-parent -- satu parent bungkus anak lewat properti child:, kalau banyak anak jadi properti children:

Widget induk membatasi ukuran si child agar tidak lebih besar dari parent
2. MyApp: membungkus seluruh aplikasi, mengatur judul aplikasi, mendefinisikan warna Material3, dan menentukan MyHomePage sebagai halaman pertama

MyHomePage: Beranda utama, judul, baris kartu info pemilik portofolio

InfoCard: menampilkan informasi informasi identitas pemilik seperti card NPM, nama, dan kelas PBP

ItemCard: Lihat Proyek, Tambah Proyek, Logout, untuk menu aksi

MaterialApp: widget standar untuk setting global theme, judul, navigasi, sama home

Scaffold: kerangka tata letak halaman, termasuk appBar, body, dan juga SnackBar

AppBar: Menampilakn bagian atas halaman yang berisi judul dengan warna sesuai theme

Padding: Jarak atau ruang kosng agak tidak seperti AI dan agak para widget lebih leluasa. Elemen tidak saling berhimpit

COlumn: menyusun daftar widget secara kolom, atas ke bawah

Row: menyusun daftar widget Kiri ke kanan, horizontal, 

SizedBox: Membuat kotak pembatas untuk jarak vertikal anta elemen

Center: posisikan widget anak agar di tengah.

Text: Menampilkan teks ke layar, ada juga styling text seperti bold, ukuran font, dan justify text

GridView.count: menyusun kumpulan widget anak dalam grid dua dimensi, jumlah kolom tetap(3) untuk menampilkan daftar tombol itemcard

Card: Menampilkan elemen kartu yang sudutnya tidak tajam dan ada efek bayangan

COntainer: Widget pembungkus yang digunakan untuk mengatur dimensi lebar responsif serta padding dalam InfoCard dan Itemcard

Material: Menyediakan kanvas berbasis Material Design pada ItemCard sehingga dapat diberikan item.color, sudut melengkung, dan efek sentuhan.

InkWell: Membuat area ItemCard interkatif jika ada sentuhan pengguna

Icon: Menampilkan ikon seperti folder, add_circle, logout pada Itemcard

SnackBar: Menampilkan pesan notif jika ItemCard ditekan, yang dipicu melalui ScaffoldMessenger


3. Fungsi MaterialApp: membungkus seluruh aplikasi dan konfigurasi berbagai layanan tingkat aplikasi sesuai standar desain Material Design. 
Kenapa di root? Karena untuk konfigurasi ThemeData sepeprti warna utama indigo dan sekunder amber bisa tersedia untuk anak-anaknya.
Banyak komponen seperti Scaffold, AppBar, Card, InkWell, dan SnackBar bergantung pada konteks yang disediakan oleh MaterialApp. Jadi MaterialApp ditaruh paling root agar semua jalan tanpa error
4. Stateless: statis dan tidak punya objek State yang dapat dimutasi, semua properti di dalam bersifat final, tidak dapat diubah.
Stateful: dinamis dan terhubung dengan sebuah objek State terpisah untuk menyimpan data yang dapat berubah selama aplikasi berjalan, misalnya counter. 
Kapan pakai dan mana yang harus didahulukan?
Pakai stateless untuk tampilan final seperti nama, npm, kelas, dan tombol tombol aksi.
Interaktif pakai stateful misal minta input atau counter sesuatu.
5. BuildCOntext adalah objek pegangan yang merepresentasikan lokasi spesifik sebuah widget di dalam struktur widget tree. BuildCOntext sangat penting karena di flutter, data konfigurasi global dan layanan bersama disimpan pada widget leluhur di bagian atas pohon. Dengan BuildCOntext, sebuah widget anak dapat menelusuri hierarki pohon ke atas untuk akses data atau layanan ari leluhur terdekat secara langsung tanpa harus oper parameter secara berantai dari induk ke anak.
Penggunaan dalam build:
parameter context diteruskan secara otomatis oleh framework Flutter. Dalam proyek ini, context dimanfaatkan untuk:
- Akses tema warna
- Ukur dimensi layar
- Menampilkan notif SnackBar
6. Hot reload: Fitur pada mode debug yang memanfaatkan kompilasi Just-In-Time yang menyuntikkan berkas kode Dart yang baru saja diubah langsung ke dalam Dart VM yang sedang berjalan. Setelah kode baru, Flutter bangun ulang widget tree dengan cepat sambil mempertahankan state yang sedang aktif

Hot Restart: kompilasi ulang semuanya jadi state yang sedang aktif juga kena reset.

Kapan tidak hanya pakai Hot Reload:
- ubah variabel global, static, atau inisialisasi state di dalam metode intState()
- ubah fungsi main
- ubah jenis kelas misal dari stateful jadi stateless

Kapan Full Restart:
- Tambah paket atau dependensi baru di berkas pubspec.yaml yang menyertakan kode native platform
- Modifikasi konfigurasi atau kode pada lapisan native masing-masing sistem operasi

AI Discolure Tugas 7: 
Chat: https://gemini.google.com/share/d/1_NVJ4OIqEf0jvD3Lejn34ilWLsnBFule?usp=sharing

Peran: Membantu langkah demi langkah
Kekurangan: Kadang chat balasan terlalu panjang

Catatan terkait satu commit sebelum ini:
Harusnya tadi pake docs, bukan feat...sorry my bad

### Tugas 8
1. Beda Navigator.push(), Navigator.pop(), Navigator.pushReplacement()

push digunakan agar route baru ada di puncak stack, jadi halaman lama tetap tersimpan di bawahnya

pushReplacement digunakan untuk mengganti stack teratas, tapi bawahnya tidak berubah.

pop digunakan untuk menghapus halaman tearatas. berguna untuk kembali ke halaman sebelumnya, misal tombol Batal atau OK

Metode yang digunakan formulir adalah push. Ketika user menekan misalkan Tambah Proyek, maka form Tambah Proyek akan terpush dan menimpa MyHomePage. Ketika selesai mengisi formulir maka tekan OK atau kalau tidak jadi tekan Batal. Metode yang digunakan untuk kembali ke laman utama adalah pop

Opsi Home membawa user kembali ke MyHomePage, halaman pertama ketika aplikasi berjalan. 
Saat menekan Home, maka jendela yang sekarang terbuka akan beralih ke tampilan utama MyHomePage

2. Sususan Scaffold, Appbar, dan Drawer membantu menjaga halaman strukrut tetap konsisten
Scaffold merupakan kerangka halaman atau page layout, yang isinya ada appBar dan drawer. Di sini Scaffold bertujuan untuk membungkus seluruh halaman agar memiliki satu warna yang sama.

appBar untuk bilah judul dan kontrol navigasi

drawer itu navigas yang samping kiri (di proyek ini kita sebut left drawer) yang  isinya ada menu navigasi seperti Home, Add Music, Add Project

Ketiga komponen ini menjaga agar struktur halaman konsisten.

Untuk warna tema sudah terjaga di main.dart menggunakan ThemeData. Sehingga setiap halaman mengakses warna primer lewar Theme.of(contect).colorScheme.primary pada AppVar, DrawerHeader, dan tombol aksi. Dengan begitu tampilan aplikasi memiliki identitas yang seragam.

3. Tata letak tersebut dipilih untuk formulir karena sudah menyelesaikan masalah-masalah untuk elemen-elemen dalam formulir. SigleChildScrollView digunakan karena ini aplikasi mobile jadi jika kepenuhan bisa lanjut di bawah untuk widget widgetnya.

Jadi secara keseluruhan kegunaannya adalah untuk menjaga fleksibilitas dan untuk kenyamanan user mobile, di mana mobile/handphone ya ruangnya terbatas jadi kita pakai tata letak yang seperti itu.

Lalu pengaturan jarak juga dilakukan agar elemen tidak saling berimpitan, kegunaannya untuk agar tidak salah pencet(misal jari user terlalu besar) dan untuk kenyamanan mata user. Kadang kalau berimpitan gitu user tidak nyaman melihatnya.

4. 
GlobalKey<FormState> menjadi pengenal unik untuk mengakses objek FormState dari luar widget Form, menjalankna validasi, serta reset formulir.

validator tugasnya mengecek setiap masukan agar valid dan sesuai permintaan. Kalau tidak sesuai akan kirim pesan error.

validate dipakai saat onpressed Save. Ini digunakan untuk memastikan seluruh validator tereksekusi. Jika ada satu saja validator yang salah maka akan kembalikan pesan error