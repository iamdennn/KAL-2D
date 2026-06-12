# SISTEM PERSAMAAN LINIER

---

# 1.1 Sistem Persamaan Linear

## 1.1.1. Definisi Sistem Persamaan Linear

Suatu sistem persamaan linear (*system of linear equations* atau *linear system*) adalah suatu himpunan persamaan-persamaan linear. Sistem linear homogen adalah himpunan persamaan linear yang semuanya berbentuk homogen (ruas kanannya nol).

Jika kita menuliskan suatu sistem yang terdiri atas $m$ persamaan dalam $n$ peubah $x_1, x_2, \dots, x_n$, biasanya setiap persamaan ditulis dalam bentuk standar dan suku-suku yang bersesuaian disejajarkan dalam kolom sebagai berikut:

$$
\begin{aligned}
a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n &= b_1 \\
a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n &= b_2 \\
\vdots \\
a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n &= b_m
\end{aligned}
$$

Sistem linear homogen biasanya dituliskan sebagai:

$$
\begin{aligned}
a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n &= 0 \\
a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n &= 0 \\
\vdots \\
a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n &= 0
\end{aligned}
$$

## 1.1.2 Tujuan Dari Operasi Persamaan Linear

Operasi persamaan linear bertujuan untuk menemukan solusi dengan cara menyederhanakan persamaan tanpa mengubah nilai kebenarannya, seperti contoh di bawah ini:
Diberikan persamaan:
$2x + 4 = 10$
Tujuan kita adalah mencari $x$, langkah operasi yang bisa kita lakukan dengan menggunakan cara:

1. Kita kurangi kedua sisi dengan 4:
   $2x + 4 - 4 = 10 - 4$
   $2x = 6$
2. Kita bagi kedua sisi dengan 2:
   $x = 3$

---

## 1.1.2. Persamaan Linear dan Nonlinear

### 1. Persamaan Linear
Persamaan linear adalah persamaan yang variabelnya memiliki pangkat tertinggi **satu (derajat satu)** dan grafiknya berbentuk **garis lurus**.

**Contoh Bentuk Umum (dua bentuk)**

1. **Satu variabel**
   $[ ax + b = 0 ]$
   Keterangan:
   * 0 = konstanta
   * a, b = koefisien
   * x = variabel
   Contoh: $[ 2x + 5 = 0 ]$

2. **Dua variabel**
   $[ ax + by + c = 0 ]$
   Keterangan:
   * (a, b, c) = konstanta
   * (x, y) = variabel
   Contoh: $[ 2x + y - 4 = 0 ]$

**Ciri-ciri Persamaan Linear:**
* Pangkat variabel = 1
* Tidak ada perkalian antar variabel
* Tidak ada akar atau pangkat lebih dari satu

---

### 2. Persamaan Nonlinear
Persamaan nonlinear adalah persamaan yang memiliki variabel dengan pangkat **lebih dari satu**, berada dalam akar, atau saling dikalikan sehingga grafiknya **bukan garis lurus**.

**Bentuk Umum (dua bentuk)**

1. **Persamaan kuadrat**
   $[ ax^2 + bx + c = 0 ]$
   Keterangan:
   * Pangkat tertinggi variabel adalah 2.
   Contoh: $[ x^2 + 3x - 4 = 0 ]$

2. **Persamaan dengan perkalian variabel**
   $[ xy + x + y = 0 ]$
   Contoh: $[ xy + 2x - y = 3 ]$

**Ciri-ciri Persamaan Nonlinear:**
* Pangkat variabel lebih dari 1 atau berbentuk akar
* Bisa terdapat perkalian antar variabel ($xy$)
* Grafik berupa kurva (parabola, lingkaran, dll.)

---

## 1.1.3. Definisi Solusi Sistem Persamaan Linear

**Pengertian Solusi dalam persamaan linear** adalah nilai variabel yang membuat persamaan menjadi **benar** ketika nilai tersebut disubstitusikan ke dalam persamaan.
Dengan kata lain, solusi adalah nilai yang menyebabkan **ruas kiri = ruas kanan**.

**Penjelasan**: Pada persamaan linear, tujuan utama adalah mencari nilai variabel (misalnya $x, y, z$) yang memenuhi persamaan.
Jika suatu nilai dimasukkan ke dalam persamaan dan menghasilkan kesamaan yang benar, maka nilai tersebut disebut **solusi**.

**Jenis solusi pada persamaan linear diantaranya:**
1. **Solusi tunggal**: Hanya ada satu set nilai variabel yang memenuhi semua persamaan.
2. **Tidak ada solusi**: Tidak ada nilai variabel yang memenuhi semua persamaan (sistem inkonsisten).
3. **Solusi tak terhingga**: Ada tak terhingga banyaknya solusi (sistem dependen).

**Contoh grafis (2D) dalam solusi persamaan linear:**
* Garis berpotongan $\to$ Solusi tunggal
* Garis sejajar $\to$ Tidak ada solusi
* Garis berimpit $\to$ Solusi tak terhingga

```{code-cell} python
from IPython.display import IFrame

IFrame(
    "[https://www.geogebra.org/classic/ekkrznta?embed](https://www.geogebra.org/classic/ekkrznta?embed)",
    width=800,
    height=600
)
```
---

# Operasi Baris Elementer Pada Matriks 

## 2.1 Operasi Baris Elementer Pada Matriks

### 2.1.1 Definisi Operasi Baris Pada Matriks
Operasi Baris Elementer (OBE) adalah operasi dasar yang dilakukan terhadap baris-baris suatu matriks dengan tujuan mengubah bentuk matriks menjadi lebih sederhana tanpa mengubah solusi sistem persamaan linear yang direpresentasikan oleh matriks tersebut.

Dengan kata lain, operasi ini hanya mengubah tampilan matriks, tetapi nilai solusi tetap sama (ekuivalen).

Operasi baris elementer banyak digunakan dalam:
* Penyelesaian Sistem Persamaan Linear (SPL),
* Metode eliminasi Gauss,
* Metode Gauss-Jordan,
* Pencarian invers matriks,
* Menentukan rank matriks.

Proses mengubah suatu matriks menggunakan operasi baris elementer disebut **reduksi baris (row reduction)**. Dua matriks disebut **ekuivalen baris (row equivalent)** jika salah satunya dapat diperoleh dari yang lain melalui sejumlah hingga operasi baris elementer.

---

### Jenis-Jenis Operasi Baris Elementer

#### 1. Pertukaran Dua Baris (Row Switching)
Menukar posisi dua baris dalam matriks.
* **Notasi:** $R_i \leftrightarrow R_j$
* **Makna:** Baris ke-$i$ ditukar dengan baris ke-$j$.
* **Contoh:** 
  $$\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} \xrightarrow{R_1 \leftrightarrow R_2} \begin{bmatrix} 3 & 4 \\ 1 & 2 \end{bmatrix}$$

#### 2. Perkalian Baris dengan Konstanta (Row Scaling)
Mengalikan semua elemen dalam satu baris dengan suatu bilangan bukan nol.
* **Notasi:** $R_i \to kR_i, \quad k \neq 0$
* **Makna:** Setiap elemen pada baris ke-$i$ dikalikan konstanta $k$.
* **Contoh:**
  $$\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} \xrightarrow{R_1 \to 2R_1} \begin{bmatrix} 2 & 4 \\ 3 & 4 \end{bmatrix}$$

#### 3. Penjumlahan Baris (Row Replacement)
Menambahkan kelipatan suatu baris ke baris lainnya.
* **Notasi:** $R_i \to R_i + kR_j$
* **Makna:** Baris ke-$i$ diganti dengan hasil penjumlahan baris ke-$i$ dan kelipatan baris ke-$j$.
* **Contoh:**
  $$\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} \xrightarrow{R_2 \to R_2 - 3R_1} \begin{bmatrix} 1 & 2 \\ 0 & -2 \end{bmatrix}$$

---

### 2.1.2 Notasi Operasi Bilangan Elementer
Notasi operasi baris elementer digunakan untuk menunjukkan perubahan yang dilakukan pada baris suatu matriks tanpa menuliskan seluruh proses perhitungan. Biasanya huruf $R$ digunakan sebagai singkatan dari **Row (baris)**.

1. **Notasi Pertukaran Baris**
   * Bentuk notasi: $R_i \leftrightarrow R_j$
   * Arti: Baris ke-$i$ ditukar dengan baris ke-$j$.

2. **Notasi Perkalian Baris Dengan Konstanta**
   * Bentuk notasi: $R_i \to kR_i, \quad k \neq 0$
   * Arti: Baris ke-$i$ diganti menjadi $k$ kali baris ke-$i$.

3. **Notasi Penjumlahan Baris (Penggantian Baris)**
   * Bentuk notasi: $R_i \to R_i + kR_j$
   * Arti: Baris $i$ diganti hasil penjumlahan Baris $i$ lama ditambah kelipatan baris $j$.

---

### 2.1.3 Langkah-Langkah Menjalankan Operasi Baris Elementer
Eliminasi Gauss (Gaussian elimination) adalah algoritma yang digunakan untuk mengubah suatu matriks menjadi bentuk eselon baris (row echelon form) dengan menggunakan operasi baris elementer.

**Langkah-Langkah Eliminasi Gauss:**
1. **Menentukan Pivot Pertama:** Temukan kolom paling kiri yang memiliki elemen tak nol. Jika perlu, lakukan **pertukaran baris (row swap)** untuk memindahkan baris dengan elemen tak nol tersebut ke posisi paling atas.
2. **Membuat Leading 1:** Kalikan baris teratas (baris pivot) dengan suatu skalar sehingga elemen utama (pivot) menjadi 1. Elemen utama ini disebut **leading one**.
3. **Membuat Nol di Bawah Pivot:** Untuk setiap baris di bawah baris pivot, lakukan operasi $R_i \to R_i + kR_{pivot}$ agar semua elemen di bawah pivot menjadi nol.
4. **Ulangi Proses:** Ulangi langkah 1-3 pada submatriks yang berada di bawah baris pivot terakhir sampai seluruh matriks berada dalam bentuk eselon baris.

---

### 2.1.4 Contoh Proses Eliminasi Gauss
Selesaikan sistem persamaan berikut:
$$\begin{cases} x + 2y + z = 9 \\ 2x + 3y + 4z = 20 \\ 3x + y + 3z = 13 \end{cases}$$

**1. Bentuk Matriks Augmented**
$$\left( \begin{array}{ccc|c} 1 & 2 & 1 & 9 \\ 2 & 3 & 4 & 20 \\ 3 & 1 & 3 & 13 \end{array} \right)$$

**2. Eliminasi Kolom Pertama**
Operasi: $R_2 \to R_2 - 2R_1$ dan $R_3 \to R_3 - 3R_1$
Hasil:
$$\left( \begin{array}{ccc|c} 1 & 2 & 1 & 9 \\ 0 & -1 & 2 & 2 \\ 0 & -5 & 0 & -14 \end{array} \right)$$

**3. Eliminasi Kolom Kedua**
Operasi: $R_3 \to R_3 - 5R_2$
Hasil:
$$\left( \begin{array}{ccc|c} 1 & 2 & 1 & 9 \\ 0 & -1 & 2 & 2 \\ 0 & 0 & -10 & -24 \end{array} \right)$$

**4. Substitusi Mundur**
* **Dari baris ketiga:**
  $-10z = -24 \implies z = \frac{12}{5}$
* **Baris kedua:**
  $-y + 2z = 2 \implies -y + 2(\frac{12}{5}) = 2 \implies -y = -\frac{14}{5} \implies y = \frac{14}{5}$
* **Baris pertama:**
  $x + 2y + z = 9 \implies x + 2(\frac{14}{5}) + \frac{12}{5} = 9 \implies x + 8 = 9 \implies x = 1$

**Hasil Akhir:**
$x = 1, \quad y = \frac{14}{5}, \quad z = \frac{12}{5}$