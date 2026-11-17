# Algoritma Penyelesaian SPL Tiga Variabel dengan Metode Gauss-Jordan

## 1. Tujuan

Menentukan nilai tiga variabel (`x`, `y`, dan `z`) dari tiga persamaan linear dengan mengubah matriks augmented menjadi bentuk eselon baris tereduksi.

## 2. Bentuk umum

Sistem persamaan linear tiga variabel dapat ditulis sebagai:

```text
a1*x + b1*y + c1*z = d1
a2*x + b2*y + c2*z = d2
a3*x + b3*y + c3*z = d3
```

Matriks augmented-nya adalah:

```text
| a1  b1  c1 | d1 |
| a2  b2  c2 | d2 |
| a3  b3  c3 | d3 |
```

## 3. Langkah algoritma

1. Mulai.
2. Masukkan koefisien tiga persamaan dan konstanta di ruas kanan.
3. Susun semua nilai tersebut ke dalam matriks augmented berukuran 3 × 4.
4. Untuk setiap kolom variabel, pilih elemen pivot dari baris aktif sampai baris terakhir dengan nilai mutlak terbesar. Pemilihan ini disebut pivot parsial.
5. Tukar baris aktif dengan baris yang memiliki pivot terpilih apabila diperlukan.
6. Periksa pivot. Jika nilainya mendekati nol, matriks tidak memiliki solusi tunggal sehingga proses dihentikan.
7. Bagi seluruh elemen pada baris pivot dengan nilai pivot agar elemen pivot menjadi 1.
8. Untuk setiap baris selain baris pivot, hilangkan elemen pada kolom pivot dengan operasi baris: `baris_target = baris_target - faktor × baris_pivot`.
9. Ulangi langkah 4–8 untuk kolom variabel berikutnya sampai semua kolom variabel memiliki pivot.
10. Baca tiga nilai pada kolom terakhir matriks augmented sebagai nilai `x`, `y`, dan `z`.
11. Substitusikan hasil ke persamaan awal untuk memeriksa ketepatan jawaban.
12. Selesai.

## 4. Contoh data pengujian

```text
2x +  y -  z =   8
-3x -  y + 2z = -11
-2x +  y + 2z =  -3
```

Solusi yang diharapkan dari data pengujian ini adalah `x = 2`, `y = 3`, dan `z = -1`.

## 5. Keterangan

- Operasi baris elementer digunakan untuk mengubah matriks tanpa mengubah himpunan solusinya.
- Pivot parsial membantu mengurangi risiko pembagian dengan bilangan yang sangat kecil.
- Implementasi ini ditujukan untuk matriks persegi 3 × 3 yang mempunyai solusi tunggal.
- Jika matriks singular, program menghentikan proses dan memberi pesan bahwa solusi tunggal tidak dapat ditentukan oleh prosedur tersebut.
