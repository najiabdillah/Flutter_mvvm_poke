# Sampel MVVM Arsitektur Flutter
 Contoh flutter menggunakan Arsitektur Bersih dan MVVM.
# Dalam artikel ini, kami menunjukkan kepada Anda bagaimana tampilan MVVM dengan Flutter.
 Kami akan membuat ViewModel reaktif fungsional menggunakan Darts Stream API.
#MVVM
 Sebelum kita melihat kode apa pun, kita harus mendapatkan pemahaman dasar tentang MVVM (Model-View-ViewModel).
# Bagaimana tampilan proyek Android saya?
# Struktur Modul
Ada 3 modul utama untuk membantu memisahkan kode. Yaitu Data, Domain, dan Aplikasi.

- **Data** berisi Penyimpanan Lokal, API, objek Data (objek Permintaan/Respons, objek DB), dan implementasi repositori.

- **Domain** berisi UseCase, Objek/Model Domain (Kelas Data Pojos/Kotlin), dan Antarmuka Repositori

- **Aplikasi** berisi UI, Objek Tampilan, komponen Android, dll. Dapat dipecah menjadi modul terpisah jika diperlukan. Misalnya, kita dapat memiliki modul yang disebut Perangkat yang menangani hal-hal seperti kamera, lokasi, dll.

# Repositori
 - Jembatan antara lapisan Data dan lapisan Domain
 - Menghubungkan ke sumber data dan mengembalikan data yang dipetakan
 - Sumber data termasuk DB, Api, dan RxCache (Cache data yang terus-menerus memancarkan pembaruan ke pelanggan. Lebih lanjut tentang ini di posting lain).
 - Selalu simpan data yang dipetakan. Misalnya. Simpan objek domain di file RxCache.
# UseCase
 - Bertanggung jawab untuk menghubungkan ke repositori untuk mengambil data yang diperlukan. Dapat mengembalikan Flowable yang akan memancarkan setiap pembaruan (dari RxCache), atau Single/Completable yang selesai setelah hasil diambil.
 - Di sinilah logika bisnis terjadi.
 - Mengembalikan data ke hilir.
 - Sekali pakai.
 - Tinggal di Domain (Tidak ada ketergantungan Android. Sangat dapat diuji).
# LihatModel
 - Mengatur data dan menahan status Tampilan.
 - Pembicaraan untuk menggunakan kasus.
 - Tidak tahu tentang View.
# Lihat
 - Perbarui UI
 - Tahu tentang ViewModel
 - Mengamati perubahan pada ViewModel.
# Router
 - Saya membiarkan ini terbuka untuk memenuhi setiap kebutuhan proyek. Poin utama di sini adalah penting untuk mengkonsolidasikan logika navigasi ke satu tempat. Ini membantu dengan pemeliharaan dan pengujian unit.
# Fitur baru
 - Banyak bahasa


 naji abdillah