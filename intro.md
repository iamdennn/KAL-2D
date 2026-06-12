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

# Matriks

## 2.1 Aritmetika Matriks

Matriks memainkan peran dalam membahas tentang sistem linear di **Bab 1**. Dalam bab ini membahas lebih mendalam tentang matriks.

Seperti topik matematika lainnya, matriks dapat digunakan dalam banyak hal. Dengan demikian, penting untuk membahas lebih detail dalam kursus ini.

### Prinsip 2.1.1. Matriks. Tidak setiap matriks harus dianggap sebagai matriks augmented yang terkait dengan sistem linear.

### 2.1.1 Dasar-dasar matriks

Kita mulai dengan beberapa definisi mendasar tentang matriks, kesamaan matriks, dan jenis-jenis matriks khusus. Seperti yang diperjelas oleh definisi berikut ini, matriks hanyalah urutan bilangan yang diatur dengan cara yang sangat khusus.

### Definisi 2.1.2. Matriks. Sebuah *matriks (riil)* adalah susunan persegi panjang dari bilangan riil.
$$A = \begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{bmatrix}$$  *(2.1.1)*

Bilangan $a_{ij}$ yang terletak pada baris ke-$i$ dan kolom ke-$j$ dari $A$ disebut **entri-$(i, j)$** (atau **entri-$ij$**) dari $A$.

Sebuah matriks dengan $m$ baris dan $n$ kolom dikatakan memiliki **ukuran** (atau **dimensi**) $m \times n$.

Matriks biasanya menggunakan huruf kapital awal alfabet (misal: $A, B, C, D$, dll.) untuk menunjukkan matriks.

Matriks yang ditampilkan dalam (2.1.1) sulit dalam ruang yang dibutuhkan untuk menampilkannya, maupun waktu yang dibutuhkan untuk menulis atau mengetiknya. Oleh karena itu kami memperkenalkan dua bentuk notasi yang agak saling melengkapi untuk membantu mendeskripsikan matriks.

### Definisi 2.1.3. Notasi Matriks.
Notasi pembangun matriks:** Notasi $[a_{ij}]_{m \times n}$ menunjukkan matriks $m \times n$ yang entri $ij$-nya (baris ke-$i$, kolom ke-$j$) adalah $a_{ij}$. Ketika tidak ada bahaya kebingungan, notasi ini sering disingkat menjadi $[a_{ij}]$.
 
**Notasi entri matriks:** Diberikan sebuah matriks $A$, notasi $[A]_{ij}$ menunjukkan entri ke-$ij$ dari $A$.

Jadi jika $A = [a_{ij}]_{m \times n}$, maka $[A]_{ij} = a_{ij}$ untuk semua $1 \le i \le m$ dan $1 \le j \le n$.

### Catatan 2.1.4. Notasi untuk menyatakan matriks sering digunakan hanya untuk memberikan nama pada entri-entri dari suatu matriks sembarang. Namun, ini juga dapat digunakan untuk mendeskripsikan matriks yang entri $ij$-nya diberikan oleh aturan atau formula tertentu.

Sebagai contoh, misalkan $A = [a_{ij}]_{2 \times 3}$, dimana $a_{ij} = (i - j)j$. Ini adalah matriks $2 \times 3$ yang entri $ij$-nya adalah $(i - j)j$. Jadi

$$A = \begin{bmatrix} (1 - 1)1 & (1 - 2)2 & (1 - 3)3 \\ (2 - 1)1 & (2 - 2)2 & (2 - 3)3 \end{bmatrix} = \begin{bmatrix} 0 & -2 & -6 \\ 1 & 0 & -3 \end{bmatrix}$$

Dalam contoh ini kita memiliki $[A]_{23} = -3$ dan $[A]_{ii} = 0$ untuk $i = 1, 2$.

### Definisi 2.1.5. Kesamaan Matriks. Misalkan $A$ dan $B$ adalah matriks dengan dimensi $m \times n$ dan $m' \times n'$, masing-masing. Dua matriks tersebut *sama* jika:
1. $m = m'$ dan $n = n'$;
2. $[A]_{ij} = [B]_{ij}$ untuk semua $1 \le i \le m$ dan $1 \le j \le n$.

Dengan kata lain, kita memiliki $A = B$ jika dan hanya jika $A$ dan $B$ memiliki bentuk yang sama, dan setiap entri dari $A$ sama dengan entri yang bersesuaian dari $B$.

### Contoh 2.1.6. Kesamaan Matriks. 

Matriks
  $$A = \begin{bmatrix} 1 & 2 & 3 & 4 \end{bmatrix} \quad B = \begin{bmatrix} 1 \\ 2 \\ 3 \\ 4 \end{bmatrix}$$
 
tidak sama satu sama lain, meskipun mereka memiliki entri yang sama yang muncul kira-kira dalam urutan yang sama. Dalam kasus ini kesamaan tidak berlaku karena $A$ dan $B$ memiliki bentuk yang berbeda: $A$ adalah $1 \times 4$, dan $B$ adalah $4 \times 1$.
 
Matriks $A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}$ dan $B = \begin{bmatrix} 1 & 2 \\ 5 & 4 \end{bmatrix}$ memiliki dimensi yang sama, tetapi tidak sama karena $[A]_{21} = 3 \ne 5 = [B]_{21}$.

### Definisi 2.1.7. Matriks persegi, vektor baris, vektor kolom, matriks nol.

Sebuah matriks $A$ adalah *bujur sangkar (persegi)* jika dimensinya adalah $n \times n$. *Diagonal* dari sebuah matriks persegi $A = [a_{ij}]_{n \times n}$ terdiri dari entri-entri $a_{ii}$ untuk $1 \le i \le n$.
 
Sebuah matriks $1 \times n$
$$\mathbf{a} = \begin{bmatrix} a_1 & a_2 & \cdots & a_n \end{bmatrix}$$
disebut **vektor baris**. Entri ke-$j$ dari sebuah vektor baris $\mathbf{a}$ dilambangkan $[\mathbf{a}]_j$.
Sebuah matriks $n \times 1$
$$\mathbf{b} = \begin{bmatrix} b_1 \\ b_2 \\ \vdots \\ b_m \end{bmatrix}$$
disebut **vektor kolom**. Entri ke-$i$ dari sebuah vektor kolom $\mathbf{b}$ dilambangkan $[\mathbf{b}]_i$.
**$m \times n$ matriks nol**, dilambangkan $\mathbf{0}_{m \times n}$, adalah matriks dengan dimensi tersebut, yang semua entrinya adalah nol; yaitu, $(\mathbf{0}_{m \times n})_{ij} = 0$ untuk semua $1 \le i \le m$ dan $1 \le j \le n$.
Ketika ukuran dimensi tidak dibutuhkan untuk ditampilkan, kita akan menghapus subskrip dan menulis cukup $\mathbf{0}$ untuk sebuah matriks nol.

### Catatan 2.1.8. Matriks sebagai kumpulan kolom/baris.

Misalkan $A$ adalah sebuah matriks $m \times n$. Kita akan sering memikirkan $A$ sebagai kumpulan kolom, dalam hal ini kita menulis 
$$A = \begin{bmatrix} | & | & & | \\ \mathbf{c}_1 & \mathbf{c}_2 & \cdots & \mathbf{c}_n \\ | & | & & | \end{bmatrix}$$  *(2.1.2)*
dimana $\mathbf{c}_j$ adalah vektor kolom yang terdiri dari entri-entri dari kolom ke-$j$ dari $A$: yaitu, 
$$\mathbf{c}_j = \begin{bmatrix} a_{1j} \\ a_{2j} \\ \vdots \\ a_{mj} \end{bmatrix}$$ 
Demikian pula, ketika kita memikirkan $A$ sebagai kumpulan baris, kita menulis 
$$A = \begin{bmatrix} — & \mathbf{r}_1 & — \\ — & \mathbf{r}_2 & — \\ & \vdots & \\ — & \mathbf{r}_m & — \end{bmatrix}$$  *(2.1.3)*
dimana $\mathbf{r}_i$顶级 adalah vektor baris yang terdiri dari entri-entri dari baris ke-$i$ dari $A$: yaitu, 
$$\mathbf{r}_i = \begin{bmatrix} a_{i1} & a_{i2} & \cdots & a_{in} \end{bmatrix}$$
Garis vertikal dan horizontal digunakan untuk menekankan bahwa $\mathbf{c}_j$ adalah vektor kolom dan $\mathbf{r}_i$ adalah vektor baris.

## 2.1.2 Penjumlahan, pengurangan dan perkalian skalar

Kita sekarang membahas berbagai operasi aljabar yang akan kita gunakan untuk menggabungkan dan mengubah matriks; kita merujuk pada penggunaan operasi sebagai *aritmetika matriks*. Beberapa operasi ini menyerupai operasi aritmetika dalam hal notasi dan definisinya. Secara khusus, perhatikan dengan seksama (a) jenis objek matematika apa yang berfungsi sebagai input untuk setiap operasi (bahan operasi), dan (b) jenis objek matematika apa yang dikeluarkan.

### Definisi 2.1.9. Penjumlahan dan pengurangan matriks.

**Penjumlahan Matriks** adalah operasi yang didefinisikan sebagai berikut: diberikan dua matriks $m \times n$ $A = [a_{ij}]_{m \times n}$ dan $B = [b_{ij}]_{m \times n}$, kita mendefinisikan **jumlah** mereka menjadi matriks
$$A + B := [a_{ij} + b_{ij}]_{m \times n}$$
Dengan kata lain $A + B$ adalah matriks $m \times n$ yang memenuhi
$$[A + B]_{ij} = [A]_{ij} + [B]_{ij} = a_{ij} + b_{ij}$$

untuk semua $1 \le i \le m$ dan $1 \le j \le n$.
 
**Pengurangan Matriks** adalah operasi yang didefinisikan sebagai berikut: diberikan dua matriks $m \times n$ $A = [a_{ij}]_{m \times n}$ dan $B = [b_{ij}]_{m \times n}$, kita mendefinisikan **selisih** mereka menjadi matriks 
$$A - B := [a_{ij} - b_{ij}]_{m \times n}$$
Dengan kata lain $A - B$ adalah matriks $m \times n$ yang memenuhi 
$$[A - B]_{ij} = [A]_{ij} - [B]_{ij} = a_{ij} - b_{ij}$$
untuk semua $1 \le i \le m$ dan $1 \le j \le n$

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
