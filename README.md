# Maze Generation using Genetic Algorithm

### Final Project – Algoritma Genetika

Repository ini berisi implementasi lengkap algoritma genetika (Genetic Algorithm, GA) untuk menghasilkan labirin solvable berukuran 12×12 dengan tingkat kesulitan yang terkendali. Sistem ini menggunakan dua jenis fitness function, dua metode seleksi, dua operator crossover, serta opsi elitisme, sehingga total terdapat delapan konfigurasi eksperimen yang dievaluasi.

## 1. Deskripsi Proyek

Proyek ini bertujuan mengembangkan generator labirin otomatis yang mampu menghasilkan struktur labirin yang valid, memiliki jalur solusi, dan memiliki tingkat kompleksitas tertentu. GA digunakan untuk mengevolusi populasi labirin dari generasi ke generasi melalui proses seleksi, crossover, mutasi, dan elitisme.

Setiap individu dalam populasi direpresentasikan sebagai grid 12×12, di mana setiap sel memiliki empat-bit encode yang menyatakan keberadaan dinding kiri, atas, kanan, dan bawah.

Project ini dikembangkan sebagai tugas akhir mata kuliah Algoritma Genetika.

## 2. Fitur Utama

Beberapa fitur penting dari sistem ini adalah:

### Representasi Labirin

Setiap sel direpresentasikan dengan empat bit (1–15) yang melambangkan dinding di empat sisi. Proses normalisasi dan repair menjaga konsistensi struktur dan memastikan labirin solvable.

### Dua Fitness Function

1. BFS-based fitness
   Mengukur kompleksitas struktural labirin berdasarkan:

   * panjang shortest path
   * jumlah belokan
   * percabangan samping
   * dead-end
   * jumlah shortest path alternatif

2. DFS-based fitness
   Meniru perilaku manusia melalui simulasi DFS acak berulang untuk menghitung rata-rata langkah.

### Mekanisme GA

* Dua seleksi: Roulette, Tournament
* Dua crossover: Uniform biased, Simple arithmetic
* Mutasi bit-flip dengan peluang mutasi besar dan kecil
* Elitisme untuk mempertahankan individu terbaik pada setiap generasi

### Eksperimen

Terdapat delapan kombinasi operator GA yang diuji, masing-masing menghasilkan metrik:

* Best Fitness
* Different Shortest Paths
* Avg Steps Taken

## 3. Struktur Folder

```
.
├── Maze.h
├── Maze.cpp
├── Util.h
├── Util.cpp
├── main.cpp
├── cc.sh
└── README.md
```

## 4. Cara Menjalankan

Pastikan Anda menggunakan compiler C++ dengan dukungan C++20.

### Kompilasi

Gunakan perintah berikut atau langsung jalankan `cc.sh`:

```
g++ *.cpp -o main -Wall -Wextra -Wshadow -std=c++20
```

### Menjalankan Program

```
./main
```

### Output

Program akan menampilkan:

* Fitness terbaik di setiap generasi
* Maze terbaik dalam bentuk ASCII
* Statistik jalur dan langkah DFS
* Ringkasan evolusi pada akhir generasi

## 5. Hasil Eksperimen (Ringkasan)

Semua konfigurasi GA menunjukkan konsistensi pada nilai best fitness akhir sekitar 0.000708717, namun menghasilkan variasi berbeda pada:

* jumlah jalur terpendek
* pola cabang
* kestabilan konvergensi
* langkah DFS manusiawi

Uniform biased crossover dengan tournament selection dan elitisme memberikan evolusi paling stabil.

## 6. Dependensi

* C++ Standard Library (queue, vector, array, algorithm, random, chrono, dll.)
* Tidak ada third-party dependencies tambahan.

## 7. Kontributor

Proyek dikerjakan oleh:

* Bagus Cipta Pratama
* David Neilleen Irvinne
* Syafran Abdillah Erdin
* Muhammad Dhiwaul Akbar

Departemen Ilmu Komputer dan Elektronika, Universitas Gadjah Mada.

## 8. Lisensi

Proyek ini dibuat untuk keperluan akademik dan tidak memiliki lisensi khusus. Anda bebas memodifikasi untuk pembelajaran atau penelitian lanjutan.

---

Jika Anda ingin README dengan badge, contoh gambar maze, flowchart GA, atau penjelasan tambahan seperti grafik hasil evolusi, beritahu saya.
