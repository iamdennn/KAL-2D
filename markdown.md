# Tugas
---
## **A. Perhitungan Determinan (Ekspansi Baris)**

Rumus Umum: $det(A) = \sum_{k=1}^{n} (-1)^{i+k} a_{ik} M_{ik}$

### **1. Matriks 2x2**
$A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$

*   **Langkah (Ekspansi Baris 1):**
    $det(A) = (-7 \times 4) - (-5 \times 1)$
    $det(A) = -28 - (-5)$
    $det(A) = -28 + 5$
*   **Hasil:** **-23**

### **2. Matriks 3x3**
$A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$

*   **Langkah (Ekspansi Baris 3 - Paling Mudah karena banyak nol):**
    $det(A) = a_{31}C_{31} + a_{32}C_{32} + a_{33}C_{33}$
    $det(A) = 0 + 0 + (1) \times (-1)^{3+3} \begin{vmatrix} 0 & 2 \\ 1 & -2 \end{vmatrix}$
    $det(A) = 1 \times (0 - 2)$
*   **Hasil:** **-2**

### **3. Matriks 4x4**
$A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}$

*   **Langkah:** Menggunakan operasi baris (OBE) untuk membuat nol atau ekspansi kofaktor secara bertahap.
*   **Hasil Akhir:** **-128**

---

## **B. Perhitungan Invers (Matriks Adjoin)**

Rumus: $A^{-1} = \frac{1}{det(A)} adj(A)$

### **4. Invers Matriks 2x2**
$A = \begin{bmatrix} -7 & -5 \\ 1 & 4 \end{bmatrix}$, $det(A) = -23$

*   **Adjoin A:** Tukar elemen diagonal utama, kali negatif diagonal samping.
    $adj(A) = \begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix}$
*   **Invers:**
    $A^{-1} = \frac{1}{-23} \begin{bmatrix} 4 & 5 \\ -1 & -7 \end{bmatrix}$
*   **Hasil:** **$\begin{bmatrix} -4/23 & -5/23 \\ 1/23 & 7/23 \end{bmatrix}$**

### **5. Invers Matriks 3x3**
$A = \begin{bmatrix} 0 & 2 & -3 \\ 1 & -2 & -1 \\ 0 & 0 & 1 \end{bmatrix}$, $det(A) = -2$

*   **Matriks Kofaktor:**
    $C_{11} = -2, C_{12} = -1, C_{13} = 0$
    $C_{21} = -2, C_{22} = 0, C_{23} = 0$
    $C_{31} = -8, C_{32} = -3, C_{33} = -2$
*   **Adjoin A (Transpose Kofaktor):**
    $adj(A) = \begin{bmatrix} -2 & -2 & -8 \\ -1 & 0 & -3 \\ 0 & 0 & -2 \end{bmatrix}$
*   **Hasil ($A^{-1} = adj(A) / -2$):**
    **$\begin{bmatrix} 1 & 1 & 4 \\ 0.5 & 0 & 1.5 \\ 0 & 0 & 1 \end{bmatrix}$**

### **6. Invers Matriks 4x4**
$A = \begin{bmatrix} 1 & -3 & 1 & 1 \\ -3 & 1 & 1 & 1 \\ 1 & 1 & -3 & 1 \\ 1 & 1 & 1 & -3 \end{bmatrix}$, $det(A) = -128$

*   **Hasil Akhir:**
    **$A^{-1} = \begin{bmatrix} -3/8 & -1/8 & -1/8 & -1/8 \\ -1/8 & -3/8 & -1/8 & -1/8 \\ -1/8 & -1/8 & -3/8 & -1/8 \\ -1/8 & -1/8 & -1/8 & -3/8 \end{bmatrix}$**
    *(Atau $-1/8 \times$ matriks yang elemen diagonalnya 3 dan sisanya 1)*

---

# Tugas Operasi Baris Elementer (OBE)

## **A. Perhitungan Matriks dengan Coding Python**

Berikut adalah implementasi kode Python menggunakan library NumPy untuk menyelesaikan soal-soal matriks yang telah dibahas.

### **1. Penyelesaian Soal 1**
**Persamaan:**
$ \begin{cases} x + 2y + z = 9 \\ 2x + 3y + 4z = 20 \\ 3x + y + 3z = 13 \end{cases} $
```python
import numpy as np

# Membuat matriks augmented
A = np.array([
    [1, 2, 1, 9],
    [2, 3, 4, 20],
    [3, 1, 3, 13]
], dtype=float)

n = len(A)

# Proses Eliminasi Gauss
for i in range(n):
    if A[i][i] != 0:
        A[i] = A[i] / A[i][i]
    for j in range(i+1, n):
        A[j] = A[j] - A[j][i] * A[i]

# Substitusi Mundur
x = np.zeros(n)
for i in range(n-1, -1, -1):
    x[i] = A[i][-1] - np.dot(A[i, i+1:n], x[i+1:n])

print("Solusi Soal 1:")
for i in range(n):
    print(f"x{i+1} = {x[i]}")
```
---

### **Soal 2: Sistem Persamaan Linear**
Selesaikan sistem berikut menggunakan metode Eliminasi Gauss:
$$ \begin{cases} 2x - y + 3z = 7 \\ 4x + 2y - z = 1 \\ -2x + y + 2z = 4 \end{cases} $$

#### **Penyelesaian Secara Markdown (Langkah Detail)**
1. **Matriks Augmented:**
   $$\left( \begin{array}{ccc|c} 2 & -1 & 3 & 7 \\ 4 & 2 & -1 & 1 \\ -2 & 1 & 2 & 4 \end{array} \right)$$
2. **Hasil OBE (Eselon Baris):**
   $$\left( \begin{array}{ccc|c} 1 & -0.5 & 1.5 & 3.5 \\ 0 & 1 & -1.75 & -3.25 \\ 0 & 0 & 1 & 2.2 \end{array} \right)$$
3. **Solusi Akhir:**
   * $x = 0.5$
   * $y = 0.6$
   * $z = 2.2$

```python
import numpy as np

# Matriks augmented untuk Soal 2
A = np.array([
    [2, -1, 3, 7],
    [4, 2, -1, 1],
    [-2, 1, 2, 4]
], dtype=float)

n = len(A)

# Eliminasi Gauss (OBE)
for i in range(n):
    # Normalisasi pivot menjadi 1
    if A[i][i] != 0:
        A[i] = A[i] / A[i][i]
        
    # Eliminasi elemen di bawah pivot
    for j in range(i+1, n):
        A[j] = A[j] - A[j][i] * A[i]

# Substitusi Mundur
x = np.zeros(n)
for i in range(n-1, -1, -1):
    x[i] = A[i][-1] - np.dot(A[i, i+1:n], x[i+1:n])

print("Solusi Soal 2:")
print("x =", x[0])
print("y =", x[1])
print("z =", x[2])
```
---

### **Soal PPT: Latihan Implementasi**
Selesaikan sistem persamaan linear berikut menggunakan metode Eliminasi Gauss:
$$ \begin{cases} 8x_1 + x_2 + x_3 = 19 \\ x_1 + 2x_2 + 3x_3 = 9 \\ 2x_1 + x_2 - x_3 = 5 \end{cases} $$

#### **1. Bentuk Matriks Augmented**
Berdasarkan koefisien dari persamaan di atas, kita peroleh matriks berikut:
$$\left( \begin{array}{ccc|c} 8 & 1 & 1 & 19 \\ 1 & 2 & 3 & 9 \\ 2 & 1 & -1 & 5 \end{array} \right)$$

#### **2. Proses Eliminasi Gauss (Python)**
Kode berikut melakukan normalisasi pivot menjadi 1 dan mengeliminasi elemen di bawahnya untuk mendapatkan bentuk eselon baris:
```python
import numpy as np

# Matriks augmented Soal PPT
A = np.array([
    [8, 1, 1, 19],
    [1, 2, 3, 9],
    [2, 1, -1, 5]
], dtype=float)

n = len(A)

# Eliminasi Gauss
for i in range(n):
    # Normalisasi pivot ke 1
    if A[i][i] != 0:
        A[i] = A[i] / A[i][i]
    
    # Eliminasi baris di bawahnya
    for j in range(i+1, n):
        A[j] = A[j] - A[j][i] * A[i]

# Menampilkan matriks setelah eliminasi
print("Matriks Eselon Baris:")
print(A)

# Substitusi Mundur
x = np.zeros(n)
for i in range(n-1, -1, -1):
    x[i] = A[i][-1] - np.dot(A[i, i+1:n], x[i+1:n])

print("\nSolusi Akhir:")
print(f"x1 = {x[0]}")
print(f"x2 = {x[1]}")
print(f"x3 = {x[2]}")
```
---

# Matrix Transformasi

## **A.Implementasi menggunakan GeoGebra**
<iframe src="https://www.geogebra.org/calculator/ykfwhnys?embed" width="800" height="600" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

### Penjelasan Logika Matriks Transformasi (Translasi)

#### 1. Rumus Dasar Translasi
Untuk memindahkan titik awal $(x, y)$ ke titik baru $(x', y')$, kita menggunakan vektor atau matriks translasi $T = \begin{bmatrix} a \\ b \end{bmatrix}$. Hubungannya adalah:

$$x' = x + a$$
$$y' = y + b$$

Untuk mencari nilai matriks $T$, rumusnya dibalik: **$T = \text{Tujuan} - \text{Awal}$**.

#### 2. Analisis Kasus Per Kasus
Berdasarkan koordinat yang diinput di GeoGebra:

*   **A ke B:**
    *   Titik $A = (2, 3)$, Titik $B = (2, 1)$.
    *   Sumbu $x$: $2 - 2 = 0$.
    *   Sumbu $y$: $1 - 3 = -2$.
    *   **Hasil:** Matriks $T = \begin{bmatrix} 0 \\ -2 \end{bmatrix}$.
*   **B ke C:**
    *   Titik $B = (2, 1)$, Titik $C = (4, 1)$.
    *   Sumbu $x$: $4 - 2 = 2$.
    *   Sumbu $y$: $1 - 1 = 0$.
    *   **Hasil:** Matriks $T = \begin{bmatrix} 2 \\ 0 \end{bmatrix}$.
*   **D ke E:**
    *   Titik $D = (2, 4)$, Titik $E = (2, 0)$.
    *   Sumbu $x$: $2 - 2 = 0$.
    *   Sumbu $y$: $0 - 4 = -4$.
    *   **Hasil:** Matriks $T = \begin{bmatrix} 0 \\ -4 \end{bmatrix}$.
*   **E ke F:**
    *   Titik $E = (2, 0)$, Titik $F = (4, 0)$.
    *   Sumbu $x$: $4 - 2 = 2$.
    *   Sumbu $y$: $0 - 0 = 0$.
    *   **Hasil:** Matriks $T = \begin{bmatrix} 2 \\ 0 \end{bmatrix}$.

#### 3. Mekanisme di GeoGebra
Saat mengetik perintah `Translate(A, (0, -2))`, GeoGebra melakukan operasi berikut:
1.  Koordinat $x$ dari $A$ ($2$) ditambah $0 = 2$.
2.  Koordinat $y$ dari $A$ ($3$) ditambah $-2 = 1$.
Hasilnya muncul titik baru di **$(2, 1)$**, tepat di posisi titik **B**.

---

## **B.Implementasi Menggunakan Python**

```python
import numpy as np

# Definisi koordinat titik sesuai gambar
points = {
    'A': np.array([2, 3]),
    'B': np.array([2, 1]),
    'C': np.array([4, 1]),
    'D': np.array([2, 4]),
    'E': np.array([2, 0]),
    'F': np.array([4, 0])
}

# Fungsi untuk menghitung matriks translasi
def hitung_translasi(awal, tujuan, nama):
    matriks = points[tujuan] - points[awal]
    print(f"Matriks Transformasi {nama} ({awal} ke {tujuan}):")
    print(f"T = {matriks}\n")

# Jalankan tugasnya
hitung_translasi('A', 'B', 'T1')
hitung_translasi('B', 'C', 'T2')
hitung_translasi('D', 'E', 'T3')
hitung_translasi('E', 'F', 'T4')
```
---

## Citations

You can also cite references that are stored in a `bibtex` file. For example,
the following syntax: `` {cite}`holdgraf_evidence_2014` `` will render like
this: {cite}`holdgraf_evidence_2014`.

Moreover, you can insert a bibliography into your page with this syntax:
The `{bibliography}` directive must be used for all the `{cite}` roles to
render properly.
For example, if the references for your book are stored in `references.bib`,
then the bibliography is inserted with:

```{bibliography}
```

## Learn more

This is just a simple starter to get you started.
You can learn a lot more at [jupyterbook.org](https://jupyterbook.org).
