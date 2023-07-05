### Import library yang diperlukan
import cv2 as cv
import numpy as np
import matplotlib.pyplot as plt

### Mengambil citra (gambar) dengan nama 'd.jpg' menggunakan OpenCV
img = cv.imread('d.jpg')

### Menampilkan citra img dalam sebuah jendela dengan judul "contour". Menutup semua jendela (window) yang terbuka menggunakan OpenCV. Parameter 0 menunjukkan bahwa jendela akan tetap terbuka hingga pengguna menekan tombol.
cv.imshow("contour", img)
cv.waitKey(0)
cv.destroyAllWindows()

### Mengubah citra dari format BGR (Blue-Green-Red) ke format RGB (Red-Green-Blue) menggunakan OpenCV
gray = cv.cvtColor(img, cv.COLOR_BGR2RGB)

### Kode ini menggunakan metode Canny untuk mendeteksi tepi dalam citra menggunakan fungsi cv.Canny(). Parameter 30 dan 150 adalah nilai ambang bawah dan ambang atas yang digunakan dalam deteksi tepi.
edges = cv.Canny(img, 30, 150)

### Kode ini menggunakan transformasi Hough probabilistik (cv.HoughLinesP()) untuk mendeteksi garis dalam citra tepi. Parameter-parameter yang digunakan adalah 1 (resolusi rho), np.pi/180 (resolusi sudut theta dalam radian), 30 (nilai ambang batas minimum untuk panjang garis), dan maxLineGap=250 (jarak maksimum antara dua titik dalam garis yang dianggap sebagai bagian dari garis yang sama).
lines = cv.HoughLinesP(edges, 1, np.pi/180, 30, maxLineGap=250)

### Membuat salinan citra asli untuk menampilkan hasil deteksi garis
img_line = img.copy()

### Mengubah semua piksel menjadi putih (255), kecuali garis tepi
img_line = np.ones_like(img) * 255  

### Menggambar garis pada citra salinan sesuai dengan koordinat yang terdeteksi
### Menampilkan garis dengan warna merah (0, 0, 255) dan ketebalan 6 piksel
for line in lines:
    x1, y1, x2, y2, = line[0]
    cv.line(img_line, (x1, y1), (x2, y2), (0, 0, 225), 6)

### Konversi citra salinan yang telah diubah dengan garis-garis ke format RGB
gray1 = cv.cvtColor(img_line, cv.COLOR_BGR2RGB)

### Tampilan citra menggunakan indeks
fig, axs = plt.subplots(1, 2, figsize=(10, 10))
ax = axs.ravel()

### Tampilan Citra Asli
ax[0].imshow(gray, cmap='gray')
ax[0].set_title('Citra Asli')

### Tampilan Citra dengan Deteksi Tepi dan Garis
ax[1].imshow(gray1, cmap='gray')
ax[1].set_title('Setelah Edges')

### Menampilkan plot citra
plt.show()