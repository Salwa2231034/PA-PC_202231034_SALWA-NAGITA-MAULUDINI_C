
# Penjelasan Project Akhir
1. Teori yang mendukung

Gambar digital direpresentasikan sebagai matriks dua dimensi dari nilai piksel. Dalam gambar berwarna, setiap piksel diwakili oleh tiga komponen warna: merah, hijau, dan biru (RGB). Dalam pustaka OpenCV, format default untuk gambar berwarna adalah BGR (biru, hijau, merah). Ketika bekerja dengan gambar, kita sering perlu mengkonversi format ini ke RGB, terutama jika kita ingin menampilkan gambar menggunakan pustaka seperti Matplotlib yang mengharapkan format RGB.

- Konversi Warna
OpenCV secara default memuat gambar dalam format BGR. Namun, pustaka visualisasi seperti Matplotlib menggunakan format RGB. Oleh karena itu, langkah pertama yang sering dilakukan dalam pemrosesan gambar adalah mengkonversi gambar dari BGR ke RGB menggunakan fungsi cv2.cvtColor(). Konversi ini memastikan bahwa warna gambar ditampilkan dengan benar saat divisualisasikan.

- Transformasi Gambar
Beberapa transformasi dasar yang umum digunakan dalam pemrosesan gambar termasuk rotasi, pengubahan ukuran, pemotongan, pembalikan, dan translasi. Masing-masing transformasi ini memiliki aplikasi dan pentingnya sendiri dalam analisis gambar dan visi komputer.

- Rotasi Gambar:
Rotasi gambar melibatkan memutar gambar sekitar titik pusatnya. Dalam implementasi ini, matriks transformasi afine digunakan. Matriks ini menggabungkan translasi ke titik pusat, rotasi, dan translasi kembali. Fungsi cv2.getRotationMatrix2D() digunakan untuk membuat matriks rotasi, dan cv2.warpAffine() untuk menerapkan rotasi pada gambar. Rotasi digunakan dalam berbagai aplikasi, termasuk koreksi orientasi gambar dan analisis fitur yang berorientasi.

- Pengubahan Ukuran Gambar:
Mengubah ukuran gambar mengubah dimensi gambar, baik memperbesar maupun memperkecil. Fungsi cv2.resize() digunakan untuk tujuan ini. Mengubah ukuran gambar penting dalam berbagai konteks, seperti memperkecil ukuran gambar untuk mempercepat pemrosesan atau memperbesar gambar untuk analisis lebih detail. Pengubahan ukuran juga berguna dalam standarisasi input untuk model pembelajaran mesin.

- Pemotongan Gambar:
Pemotongan melibatkan pengambilan subset dari gambar asli. Dalam proyek ini, area pusat gambar dipotong. Pemotongan digunakan untuk memperbesar area minat tertentu dalam gambar, mengabaikan bagian yang tidak relevan. Ini sering digunakan dalam aplikasi seperti deteksi objek dan segmentasi gambar.

- Pembalikan Gambar:
Pembalikan gambar mencerminkan gambar di sepanjang sumbu tertentu. Fungsi cv2.flip() digunakan untuk mencerminkan gambar secara horizontal. Pembalikan sering digunakan dalam augmentasi data untuk memperbanyak dataset pelatihan dalam pembelajaran mesin, membantu model untuk lebih menggeneralisasi dengan melihat variasi data yang lebih banyak.

- Translasi Gambar:
Translasi menggeser gambar dengan jarak tertentu di sepanjang sumbu x dan y. Ini dilakukan dengan menggunakan matriks translasi dalam fungsi cv2.warpAffine(). Translasi penting dalam menguji robusta model terhadap perubahan posisi objek dalam gambar. Ini juga digunakan dalam pembuatan mosaik gambar dan panorama.

- Visualisasi Hasil
Setelah melakukan berbagai transformasi, penting untuk memvisualisasikan hasilnya untuk memahami efek dari setiap transformasi. Matplotlib digunakan untuk menampilkan gambar-gambar ini dalam satu jendela, dengan judul yang menjelaskan setiap transformasi. Fungsi plt.imshow() digunakan untuk menampilkan gambar, dan plt.subplot() digunakan untuk menata beberapa gambar dalam satu figure.



2. Tahapan cara menyelesaikan projek

Proyek ini melibatkan operasi dasar pemrosesan gambar menggunakan OpenCV dan NumPy, serta visualisasi hasilnya dengan Matplotlib.

- Representasi Gambar:
Gambar digital direpresentasikan sebagai matriks nilai piksel. Pada gambar berwarna, setiap piksel biasanya direpresentasikan oleh tiga nilai yang sesuai dengan saluran Merah (Red), Hijau (Green), dan Biru (Blue) atau RGB.

- Memuat dan Konversi Warna:
Memuat Gambar: cv2.imread() memuat gambar ke dalam array NumPy dalam format BGR (standar default OpenCV).
Konversi Warna: cv2.cvtColor() digunakan untuk mengubah gambar dari format BGR ke RGB agar warna ditampilkan dengan benar menggunakan Matplotlib.

- Transformasi Gambar:
Rotasi: Rotasi dilakukan menggunakan matriks transformasi afine, yang dibuat dengan cv2.getRotationMatrix2D(). Matriks ini menerapkan rotasi sekitar titik pusat yang ditentukan.
Mengubah Ukuran: cv2.resize() mengubah dimensi gambar. Mengubah ukuran sering diperlukan untuk penskalaan gambar untuk berbagai tujuan, seperti pembuatan thumbnail atau penyesuaian resolusi.
Memotong: Memotong melibatkan ekstraksi area persegi panjang dari gambar. Ini dilakukan dengan menentukan koordinat awal dan akhir untuk baris dan kolom.
Membalik: cv2.flip() mencerminkan gambar di sepanjang sumbu yang ditentukan (horizontal, vertikal, atau keduanya). Membalik secara horizontal sering digunakan dalam augmentasi data untuk pembelajaran mesin.
Translasi: Translasi menggeser gambar dengan jumlah piksel yang ditentukan di sepanjang sumbu x dan y. Ini adalah bentuk lain dari transformasi afine, yang dicapai menggunakan cv2.warpAffine() dengan matriks translasi.

- Transformasi Afine:
Transformasi afine adalah pemetaan linier yang mempertahankan titik, garis lurus, dan bidang. Mereka termasuk rotasi, translasi, penskalaan, dan pencukuran. 

- Menampilkan Gambar:
Matplotlib: plt.imshow() digunakan untuk menampilkan gambar. Sumbu dapat diaktifkan atau dinonaktifkan tergantung pada apakah informasi koordinat diperlukan atau tidak. Fungsi display_images() membantu menampilkan beberapa gambar dalam tata letak grid dengan judul untuk setiap gambar

