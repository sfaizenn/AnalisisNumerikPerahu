# Analisis Numerik : Integrasi Numerik pada Studi Kasus Volume Lambung Perahu Katamaran

**Nama :** Sandi Fadia Aizena

**NPM :** 25083010009

**Mata Kuliah :** Analisis Numerik


### **Deskripsi Tugas**
Tugas ini menghitung volume kedua lambung perahu katamaran fiberglass untuk wisata pancing berdasarkan gambar tampak atas dan tampak samping yang diberi grid.

Metode yang digunakan yaitu:
1. **Pengukuran dimensi dari gambar** untuk memperoleh lebar lambung (tampak atas) dan tinggi lambung (tampak samping) pada setiap jarak 10 cm.
2. **Integrasi Numerik (aturan Simpson 1/3)** untuk menjumlahkan luas penampang sepanjang lambung menjadi volume.

### **Tujuan**
1. Menentukan lebar dan tinggi lambung dari gambar bergrid dengan skala satu kotak grid = 10 cm.
2. Menghitung luas penampang lambung pada setiap titik memanjang, dengan anggapan lantai kapal datar (tanpa keel) sehingga tampak depan berbentuk persegi panjang.
3. Menerapkan integrasi numerik dengan aturan Simpson 1/3 untuk menghitung volume satu lambung, tanpa memasukkan volume reserve buoyancy.
4. Menghitung volume kedua lambung dan mengimplementasikan seluruh proses menggunakan Python.

### **Objek yang Dianalisis**
| Bagian | Keterangan |
|--------|------------|
| Lambung kiri dan kanan | Identik, sehingga V_total = 2 × V_satu lambung |
| Reserve buoyancy | Ujung buritan dan ujung haluan, tidak dihitung |
| Bagian yang dihitung | Antara sekat buritan dan sekat haluan (x = 20 sampai 180 cm) |

### Data dan Ketentuan
Gambar yang digunakan adalah **perahu.pdf** yang memuat tampak atas dan tampak samping perahu katamaran.

Sumber gambar:
https://www.researchgate.net/publication/342077926_Desain_dan_Konstruksi_Perahu_Katamaran_Fiberglass_untuk_Wisata_Pancing

Ketentuan soal:
- Satu kotak grid = 10 cm (satu dash-kosong = 5 + 5 cm).
- Lantai kapal dianggap datar (tanpa keel), sehingga tampak depan semuanya persegi panjang.
- Volume reserve buoyancy tidak dihitung.

Variabel yang digunakan dalam analisis antara lain:
- `x` : posisi memanjang lambung (cm)
- `B` : lebar lambung dari tampak atas (cm)
- `H` : tinggi lambung dari tampak samping (cm)
- `A = B × H` : luas penampang (cm²)

### Metodologi
1. Kalibrasi Skala
Satu kotak grid ditetapkan sebesar 10 cm. Lebar grid 200 cm dibagi menjadi 20 interval dengan jarak antar titik h = 10 cm.
2. Pengukuran Dimensi
Lebar `B` diukur dari tampak atas dan tinggi `H` diukur dari tampak samping (garis geladak sampai dasar datar) pada x = 0, 10, 20, ..., 200 cm.
3. Luas Penampang
Karena tampak depan berbentuk persegi panjang, luas penampang pada setiap titik adalah `A = B × H`.
4. Batas Integrasi
Reserve buoyancy (x = 0 sampai 20 cm dan x = 180 sampai 200 cm) tidak dihitung, sehingga integrasi hanya dilakukan pada x = 20 sampai 180 cm (n = 16 interval).
5. Integrasi Numerik
Volume satu lambung dihitung dengan aturan Simpson 1/3:
```
V_satu  = (h/3) × [ A0 + An + 4 × (A ganjil) + 2 × (A genap) ]
V_total = 2 × V_satu
```
dengan h = 10 cm dan n = 16.

### Library yang Digunakan
1. `pandas` untuk menyusun tabel data pengukuran
2. `numpy` untuk operasi numerik dan integrasi Simpson
3. `matplotlib` untuk visualisasi profil lebar dan tinggi lambung

### Cara Menjalankan
1. Clone atau download repository ini.
2. Buka notebook menggunakan Google Colab atau Jupyter Notebook.
3. Pastikan berkas `perahu.pdf` tersedia di folder yang sama dengan notebook.
4. Jalankan setiap cell secara berurutan.
