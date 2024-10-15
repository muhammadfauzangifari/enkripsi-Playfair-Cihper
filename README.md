# Enkripsi-Playfair-Cihper
Nama : Muhammad Fauzan Gifari
NIM : 312210428
Kelas : TI.22.A1
Mata kuliah : kriptografi
Dosen : Ahmad Turmudi Zy, S.Kom,M.Kom

Untuk mengenkripsi teks menggunakan Playfair Cipher, kita perlu beberapa langkah:

Langkah 1: Membuat Matriks Kunci
Kita mulai dengan membangun matriks 5x5 menggunakan kata kunci, "TEKNIK INFORMATIKA". Setiap huruf dari kata kunci hanya ditulis sekali, dan huruf I dan J digabungkan menjadi satu tempat.

Kunci: TEKNIK INFORMATIKA

Matriks kunci (tanpa pengulangan huruf dan menggabungkan I dan J):

T  E  K  N  I
F  O  R  M  A
B  C  D  G  H
L  P  Q  S  U
V  W  X  Y  Z

Langkah 2: Menyusun Teks dan Pisah menjadi Pasangan
Sekarang kita pecah teks plaintext menjadi pasangan huruf. Jika ada huruf yang sama dalam satu pasangan, kita tambahkan X di antara mereka. Jika jumlah huruf ganjil, kita tambahkan X di akhir
1.GOOD BROOM SWEEP CLEAN
Pasangan: GO OD BR OM SW EE PC LE AN
Setelah diperbaiki: GO OD BR OM SW EX EP CL EA NX

2.REDWOOD NATIONAL STATE PARK
Pasangan: RE DW OO DN AT IO NA LS TA TE PA RK
Setelah diperbaiki: RE DW OX OD NA TI IO NA LS TA TE PA RK

3.JUNK FOOD AND HEALTH PROBLEMS
Pasangan: JU NK FO OD AN DH EA LT HP RO BL EM S
Setelah diperbaiki: JU NK FO OD AN DH EA LT HP RO BL EX MS

Langkah 3: Aturan Enkripsi
Untuk setiap pasangan huruf, ada tiga aturan yang diterapkan berdasarkan posisi mereka dalam matriks:
1.Jika kedua huruf berada dalam baris yang sama, maka diganti dengan huruf di sebelah kanannya (dengan wrap-around jika di ujung).
2.Jika kedua huruf berada dalam kolom yang sama, maka diganti dengan huruf di bawahnya (dengan wrap-around jika di ujung).
3.Jika berada di baris dan kolom yang berbeda, maka mereka diganti dengan huruf yang berada di sudut persegi panjang yang dibentuk oleh posisi keduanya.

Enkripsi Teks 1: GOOD BROOM SWEEP CLEAN
GO → HO
OD → GD
BR → FC
OM → AM
SW → PY
EX → YX
EP → AL
CL → BP
EA → TA
NX → YZ

Ciphertext: HOGDFCAMPYXYALBPTAYZ

Enkripsi Teks 2: REDWOOD NATIONAL STATE PARK
RE → FM
DW → CW
OX → AZ
OD → GD
NA → KI
TI → NI
IO → AI
NA → KI
LS → QU
TA → NI
TE → NI
PA → FL
RK → FQ

Ciphertext: FMCWAZGDKINI AIKIQUNINIFL FQ

Enkripsi Teks 3: JUNK FOOD AND HEALTH PROBLEMS
JU → LV
NK → PQ
FO → OA
OD → GD
AN → KF
DH → GH
EA → TA
LT → SI
HP → UB
RO → AF
BL → FP
EX → YX
MS → QU

Ciphertext: LVPQOAGDKFGHTASIUBAFPFPYXQU

Hasil Akhir:
1.GOOD BROOM SWEEP CLEAN → HOGDFCAMPYXYALBPTAYZ
2.REDWOOD NATIONAL STATE PARK → FMCWAZGDKINI AIKIQUNINIFL FQ
3.JUNK FOOD AND HEALTH PROBLEMS → LVPQOAGDKFGHTASIUBAFPFPYXQU
Ini adalah hasil enkripsi Playfair Cipher menggunakan kunci "TEKNIK INFORMATIKA".

Untuk dekripsi Playfair Cipher, kita mengikuti prosedur yang mirip dengan enkripsi, namun dengan aturan yang sedikit berbeda untuk mengembalikan teks asli. Berikut adalah langkah-langkah dekripsinya:

Langkah 1: Gunakan Matriks Kunci yang Sama
Kita akan menggunakan matriks kunci yang sama yang digunakan untuk enkripsi:

T  E  K  N  I
F  O  R  M  A
B  C  D  G  H
L  P  Q  S  U
V  W  X  Y  Z

Langkah 2: Pecah Ciphertext Menjadi Pasangan 
Pisahkan ciphertext ke dalam pasangan huruf yang dihasilkan dari enkripsi sebelumnya.

Langkah 3: Aturan Dekripsi
1. Jika kedua huruf berada di baris yang sama, geser ke kiri (wrap-around ke kanan jika di awal baris).
2. Jika kedua huruf berada di kolom yang sama, geser ke atas (wrap-around ke bawah jika di atas).
3. Jika kedua huruf berada di baris dan kolom yang berbeda, tukar mereka dengan huruf yang berada di sudut persegi panjang yang sama (seperti pada enkripsi).

Dekripsi Teks 1: HOGDFCAMPYXYALBPTAYZ
Ciphertext yang dipisahkan: HO GD FC AM PY YX AL BP TA YZ
HO → GO
GD → OD
FC → BR
AM → OM
PY → SW
YX → EX
AL → EP
BP → CL
TA → EA
YZ → NX

Plaintext: GOOD BROOM SWEEP CLEAN (dengan X di antara huruf untuk memperbaiki pasangan saat enkripsi)

Dekripsi Teks 2: FMCWAZGDKINI AIKIQUNINIFL FQ
Ciphertext yang dipisahkan: FM CW AZ GD KI NI AI KI QU NI NI FL FQ
FM → RE
CW → DW
AZ → OX
GD → OD
KI → NA
NI → TI
AI → IO
KI → NA
QU → LS
NI → TA
NI → TE
FL → PA
FQ → RK

Plaintext: REDWOOD NATIONAL STATE PARK (dengan X ditambahkan di antara OX untuk menghindari huruf ganda)

Dekripsi Teks 3: LVPQOAGDKFGHTASIUBAFPFPYXQU
Ciphertext yang dipisahkan: LV PQ OA GD KF GH TA SI UB AF FP YX QU
LV → JU
PQ → NK
OA → FO
GD → OD
KF → AN
GH → DH
TA → EA
SI → LT
UB → HP
AF → RO
FP → BL
YX → EX
QU → MS

Plaintext: JUNK FOOD AND HEALTH PROBLEMS (dengan X ditambahkan di antara beberapa huruf saat enkripsi)

Hasil Akhir Dekripsi:
HOGDFCAMPYXYALBPTAYZ → GOOD BROOM SWEEP CLEAN
FMCWAZGDKINI AIKIQUNINIFL FQ → REDWOOD NATIONAL STATE PARK
LVPQOAGDKFGHTASIUBAFPFPYXQU → JUNK FOOD AND HEALTH PROBLEMS








