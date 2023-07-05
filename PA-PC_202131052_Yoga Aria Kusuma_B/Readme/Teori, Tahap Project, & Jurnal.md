202131052_Yoga Aria Kusuma_Project D
1. Teori yang mendukung project

    Deteksi bentuk gambar menggunakan kontur merujuk pada proses penggunaan metode pengolahan citra untuk mengidentifikasi dan memisahkan bentuk atau objek dalam sebuah gambar dengan menganalisis kontur atau tepi objek tersebut.
   
    Kontur merupakan garis atau tepi yang membatasi objek dalam citra. Dalam konteks deteksi bentuk gambar, deteksi kontur dilakukan dengan mengidentifikasi perubahan intensitas piksel yang signifikan di sekitar tepi objek. Metode deteksi tepi seperti operator Canny, Sobel, atau Laplacian sering digunakan untuk menghasilkan kontur dengan meningkatkan perubahan intensitas di sekitar tepi objek.
   
    Setelah kontur objek dideteksi, langkah selanjutnya adalah merepresentasikan kontur tersebut dalam bentuk yang dapat digunakan untuk analisis lebih lanjut. Representasi kontur dapat dilakukan dalam beberapa cara, seperti representasi berbasis piksel seperti chain code atau Freeman chain code, atau representasi berbasis kurva seperti spline atau Fourier descriptor. Representasi ini menggambarkan garis tepi objek dalam bentuk serangkaian titik atau kurva yang mencerminkan bentuk dan struktur objek tersebut.
   
    Setelah kontur direpresentasikan, fitur-fitur kontur dapat diekstraksi untuk menggambarkan karakteristik unik dari objek. Fitur-fitur ini dapat meliputi panjang kontur, luas area terbentuk oleh kontur, jumlah sudut, rasio aspek, atau fitur-fitur bentuk lainnya. Ekstraksi fitur membantu dalam mengenali bentuk objek dengan membedakan karakteristik mereka.
    
    Pengenalan bentuk adalah langkah akhir dalam deteksi bentuk gambar menggunakan kontur. Fitur-fitur kontur yang diekstraksi dapat digunakan dalam metode pengenalan pola untuk mengenali bentuk objek. Metode pengenalan bentuk dapat melibatkan penggunaan klasifikasi berbasis aturan, pembelajaran mesin, atau jaringan saraf tiruan untuk membandingkan fitur-fitur kontur dengan pola yang telah diketahui sebelumnya dan mengenali bentuk objek yang sesuai.

    Dalam keseluruhan, deteksi bentuk gambar menggunakan kontur melibatkan tahapan deteksi kontur, representasi kontur, ekstraksi fitur, dan pengenalan bentuk. Metode ini digunakan untuk mengidentifikasi dan memisahkan objek dalam sebuah gambar berdasarkan analisis kontur atau tepi mereka.

2. Menjelaskan tahapan cara menyelesaikan project
    Untuk menyelesaikan proyek yang terkait dengan deteksi garis menggunakan Transformasi Hough Probabilistik dapat mengikuti langkah-langkah berikut:
   
A.	Import Library:
•	Pastikan telah menginstal library OpenCV, NumPy, dan matplotlib. 
•	Import library yang diperlukan: import cv2 as cv, import numpy as np, import matplotlib.pyplot as plt.

B.	Baca dan Tampilkan Gambar:
•	Gunakan fungsi cv.imread() untuk membaca gambar dari file.
•	Tampilkan gambar menggunakan plt.imshow() untuk memastikan gambar telah terbaca dengan benar.

C.	Konversi Warna dan Deteksi Tepi:
•	Ubah format warna gambar menggunakan cv.cvtColor() agar sesuai dengan kebutuhan, seperti dari BGR ke RGB.
•	Gunakan algoritma deteksi tepi, misalnya Canny, menggunakan fungsi cv.Canny() untuk menghasilkan gambar dengan efek tepi.

D.	Deteksi Garis menggunakan Transformasi Hough:
•	Gunakan fungsi cv.HoughLinesP() untuk mendeteksi garis-garis pada gambar yang sudah diberi efek tepi.
•	Tentukan parameter-parameter yang diperlukan, seperti resolusi rho, resolusi theta, dan threshold. Sesuaikan parameter ini sesuai dengan gambar dan kebutuhan.
•	Simpan garis-garis yang terdeteksi dalam suatu variabel.

E.	Gambar Garis pada Gambar Asli:
•	Buat salinan gambar asli menggunakan img_line = img.copy().
•	Iterasi melalui setiap garis yang terdeteksi.
•	Gambar setiap garis pada salinan gambar menggunakan cv.line() dengan warna dan ketebalan yang diinginkan.

F.	Tampilkan Gambar Hasil:
•	Konversi gambar yang telah diubah dengan cv.cvtColor() ke format RGB agar kompatibel dengan matplotlib.
•	Buat plot menggunakan plt.subplots() dengan jumlah subplot sesuai kebutuhan.
•	Gunakan plt.imshow() untuk menampilkan gambar asli dan gambar hasil deteksi garis.
•	Tambahkan judul untuk setiap subplot menggunakan plt.title().
•	Panggil plt.show() untuk menampilkan plot.

G.	Eksekusi dan Evaluasi Hasil:
•	Jalankan kode tersebut dan lihat hasilnya.
•	Evaluasi hasilnya dan sesuaikan parameter atau metode deteksi garis jika diperlukan.

3. Jurnal Terkait
   Link : https://ejournal3.undip.ac.id/index.php/bfd/article/view/5936
   Link : https://ejournal.gunadarma.ac.id/index.php/infokom/article/view/1527/1286
   Link : https://doi.org/10.33084/jsakti.v4i1.2545
