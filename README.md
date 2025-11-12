# TUGAS-RAHMAT
# PRAKTIKUM SISTEM OPERASI

# 1 Membuat Struktur Direktori dan File di Terminal Linux


🪐 Tujuan:

Belajar membuat direktori dan file menggunakan terminal Linux, serta menyiapkan hasil kerja agar dapat diunggah ke GitHub.


# LANGKAH-LANGKAH


---

# BUAT STRUKTUR DIREKTORI UTAMA
```
rahmat@Rahmat2:~$ mkdir latihan1_sistemOperasi
```
📝 Penjelasan: Perintah mkdir (make directory) digunakan untuk membuat folder baru bernama latihan1_sistemOperasi di direktori home (~).


---

# MASUK KE DIREKTORI YANG TELAH DIBUAT
```
rahmat@Rahmat2:~$ cd latihan1_sistemOperasi
```
📝 Penjelasan: Perintah cd (change directory) digunakan untuk berpindah ke folder latihan1_sistemOperasi.


---

# BUAT SUBDIREKTORI TAMBAHAN
```
rahmat@Rahmat2:~/latihan1_sistemOperasi$ mkdir documents images archives logs
```
📝 Penjelasan: Perintah ini membuat empat folder di dalam latihan1_sistemOperasi, yaitu:

documents → menyimpan file teks

images → menyimpan file gambar

archives → menyimpan file arsip

logs → menyimpan catatan aktivitas



---

# BUAT BEBERAPA FILE TEKS DI DALAM DIREKTORI documents
```
rahmat@Rahmat2:~/latihan1_sistemOperasi$ cd documents
rahmat@Rahmat2:~/latihan1_sistemOperasi/documents$ touch file1.csv file2.csv file3.csv file4.csv file5.csv
```
📝 Penjelasan:

cd documents → berpindah ke folder documents.

touch file1.csv file2.csv ... → membuat lima file teks kosong sekaligus.



---

# BUAT FILE GAMBAR (SIMULASI) DI DALAM DIREKTORI images
```
rahmat@Rahmat2:~/latihan1_sistemOperasi$ cd ../images
rahmat@Rahmat2:~/latihan1_sistemOperasi/images$ touch files6.jpg files7.jpg files8.jpg files9.jpg files10.jpg
```
📝 Penjelasan:

../ digunakan untuk naik satu tingkat dari direktori sebelumnya (documents ke latihan1_sistemOperasi).

Lalu masuk ke images.

touch digunakan untuk membuat 5 file gambar kosong (sebagai contoh).



---

# CEK HASIL STRUKTUR DIREKTORI
```
rahmat@Rahmat2:~/latihan1_sistemOperasi$ ls
```
📝 Penjelasan: Perintah ls menampilkan daftar isi dari direktori saat ini. Kamu akan melihat folder documents, images, archives, dan logs.


---

# KEMBALI KE DIREKTORI UTAMA
```
rahmat@Rahmat2:~/latihan1_sistemOperasi/images$ cd ..
```
📝 Penjelasan: cd .. digunakan untuk kembali ke direktori induk (dalam hal ini dari images ke latihan1_sistemOperasi).

# DESKRIPSI GAMBAR
(https://drive.google.com/file/d/19mnUmAzlFfj2ZYz8vmUN7DkAJ5w_WlDj/view?usp=drive_link)



# 2 SCRIPT ORGANISASI FILE


---

🪐 Tujuan:

Mempelajari cara mengelompokkan (mengorganisasi) file berdasarkan tipe ekstensi menggunakan perintah terminal Linux (find, exec, mv, dan cp).


---
# LANGKAH-LANGKAH

# MASUK KE DIREKTORI PROYEK
```
rahmat@Rahmat2:~$ cd latihan1_sistemOperasi
```
📝 Penjelasan: Perintah cd digunakan untuk berpindah ke direktori latihan1_sistemOperasi yang sudah dibuat pada latihan sebelumnya.


---

# CEK ISI DIREKTORI
```
rahmat@Rahmat2:~/latihan1_sistemOperasi$ ls
```
📝 Penjelasan: Perintah ls digunakan untuk menampilkan daftar folder di dalam direktori tersebut.
Hasilnya kemungkinan seperti:

archives  documents  images  logs


---

# BUAT DIREKTORI UNTUK FILE YANG TELAH DIURUTKAN
```
rahmat@Rahmat2:~/latihan1_sistemOperasi$ mkdir sorted_files
```
📝 Penjelasan: Perintah mkdir digunakan untuk membuat folder baru bernama sorted_files.
Folder ini akan menjadi tempat hasil pengelompokan file berdasarkan jenisnya.


---

# PINDAHKAN SEMUA FILE .txt KE FOLDER sorted_files
```
rahmat@Rahmat2:~/latihan1_sistemOperasi$ find . -type f -name "*.txt" -exec mv {} sorted_files/ \;
```
📝 Penjelasan:

find . → mencari mulai dari direktori saat ini (. berarti current directory)

-type f → mencari hanya file (bukan folder)

-name "*.txt" → mencari semua file yang berakhiran .txt

-exec mv {} sorted_files/ \; → menjalankan perintah mv (move) untuk memindahkan setiap file yang ditemukan ke folder sorted_files/


# Catatan: Jika muncul pesan seperti:
```
mv: 'sorted_files/file1.txt' and 'sorted_files/file1.txt' are the same file
```
itu berarti file dengan nama yang sama sudah ada di folder tujuan, jadi tidak perlu dipindahkan lagi.


---

# SALIN (BUKAN PINDAH) SEMUA FILE GAMBAR .jpg DAN .png KE FOLDER sorted_files
```
rahmat@Rahmat2:~/latihan1_sistemOperasi$ find . -type f \( -name "*.jpg" -o -name "*.png" \) -exec cp {} sorted_files/ \;
```
📝 Penjelasan:

find . → mencari di seluruh subdirektori dari lokasi sekarang

-type f → hanya mencari file

\( -name "*.jpg" -o -name "*.png" \) → mencari file yang berakhiran .jpg atau .png (-o berarti OR)

-exec cp {} sorted_files/ \; → menyalin (copy) semua file hasil pencarian ke folder sorted_files


# Perbedaan mv dan cp:

mv → memindahkan file dari lokasi lama ke baru

cp → menyalin file, sehingga file aslinya tetap ada di lokasi semula



---

# CEK HASILNYA
```
rahmat@Rahmat2:~/latihan1_sistemOperasi$ ls sorted_files
```
📝 Penjelasan: Perintah ls di dalam sorted_files akan menampilkan semua file .txt, .jpg, dan .png yang sudah berhasil dikumpulkan dalam satu folder.

DESKRIPSI GAMBAR
(https://drive.google.com/file/d/1XB3u3fUgSTZbQXyBgQwWpGdw1hl6gCW3/view?usp=drive_link)



# 3 Fungsi Pencarian di Linux 

# Masuk ke folder latihan1_sistemOperasi
```
rahmat@Rahmat2:~$ cd latihan1_sistemOperasi
```
📝 Penjelasan: cd (change directory) digunakan untuk berpindah ke folder yang sudah dibuat sebelumnya agar kita bisa menjalankan perintah di dalamnya.


---

# Menjalankan Perintah Pencarian File Berdasarkan Nama

Mencari file bernama doc1.txt di dalam folder ini dan subfolder-nya
rahmat@Rahmat2:~/latihan1_sistemOperasi$ find . -name "doc1.txt"

📝 Penjelasan:

find adalah perintah untuk mencari file atau folder.

. artinya pencarian dilakukan mulai dari direktori saat ini.

-name "doc1.txt" berarti mencari file yang namanya tepat doc1.txt.


✨ Hasil output:

# ./sorted_files/doc1.txt

Artinya file doc1.txt ditemukan di dalam folder sorted_files.


---

# Menjalankan Pencarian Berdasarkan Ukuran File

Mencari file yang ukurannya lebih dari 1 kilobyte
rahmat@Rahmat2:~/latihan1_sistemOperasi$ find . -size +1k

📝 Penjelasan:

-size digunakan untuk mencari file berdasarkan ukuran.

+1k berarti mencari file yang lebih besar dari 1 kilobyte.

Simbol + berarti lebih dari, - berarti kurang dari, dan tanpa tanda berarti tepat sama.


✨ Contoh output:

./images
./documents
./logs
./sorted_files
./archives

Beberapa folder atau file yang berukuran lebih dari 1KB akan ditampilkan.


---

# Menjalankan Pencarian Isi Teks Dalam File

Mencari teks 'Log' di dalam file yang ada di folder documents
rahmat@Rahmat2:~/latihan1_sistemOperasi$ grep 'Log' documents/

📝 Penjelasan:

grep digunakan untuk mencari teks tertentu di dalam file.

'Log' adalah kata kunci yang dicari.

documents/ adalah folder tempat pencarian dilakukan.


✨ Hasil output:
```
grep: documents/: Is a directory
```
Artinya perintah grep gagal karena yang disebut adalah folder, bukan file.
Untuk mencari di seluruh file di dalam folder documents, gunakan perintah:

# grep -r 'Log' documents/

💯 -r berarti recursive, yaitu mencari ke semua file di dalam subfolder juga.

DESKRIPSI GAMBAR
(https://drive.google.com/file/d/1W5E3LqOs9t1mJsxkFR9i3yqg5PuuDsnT/view?usp=drive_link)




# 4.GENERATE LAPORAN SISTEM

# Masuk ke Direktori Proyek
```
rahmat@Rahmat2:~$ cd Latihan1_sistemOperasi
```
🧠Penjelasan:
Masuk ke direktori yang baru saja dibuat agar semua perintah berikutnya dijalankan di dalam folder tersebut.


---

# Membuat File Laporan Awal
```
rahmat@Rahmat2:~/Latihan1_sistemOperasi$ echo "=== LAPORAN FILE SISTEM ===" > report.txt
```
🧠Penjelasan:
Membuat file report.txt dan menuliskan judul laporan di dalamnya.
Simbol > digunakan untuk menulis baru (overwrite) ke dalam file.


---

# Menambahkan Informasi Jumlah File
```
rahmat@Rahmat2:~/Latihan1_sistemOperasi$ echo "Jumlah file:" >> report.txt
rahmat@Rahmat2:~/Latihan1_sistemOperasi$ find . -type f | wc -l >> report.txt
```
🧠Penjelasan:

echo "Jumlah file:" >> report.txt menambahkan label "Jumlah file" ke file laporan.

find . -type f | wc -l menghitung berapa banyak file biasa (bukan folder) di direktori saat ini dan subdirektorinya.

Simbol >> digunakan untuk menambahkan hasil ke dalam report.txt (append mode).



---
# Menambahkan Informasi Jumlah Folder
```
rahmat@Rahmat2:~/Latihan1_sistemOperasi$ echo "Jumlah folder:" >> report.txt
rahmat@Rahmat2:~/Latihan1_sistemOperasi$ find . -type d | wc -l >> report.txt
```
🧠Penjelasan:

find . -type d mencari semua direktori.

wc -l menghitung jumlah baris (jumlah direktori yang ditemukan).

Hasilnya ditambahkan ke laporan.



---

# Menambahkan Informasi Ukuran Total Direktori
```
rahmat@Rahmat2:~/Latihan1_sistemOperasi$ echo "Ukuran total direktori:" >> report.txt
rahmat@Rahmat2:~/Latihan1_sistemOperasi$ du -sh >> report.txt
```
🧠Penjelasan:

du -sh menampilkan ukuran total dari direktori saat ini dalam format yang mudah dibaca (contoh: 12K, 1.3M, 2.1G).

Hasilnya ditambahkan ke dalam report.txt.



---
# Menambahkan Daftar Semua File
```
rahmat@Rahmat2:~/Latihan1_sistemOperasi$ echo "Daftar file:" >> report.txt
rahmat@Rahmat2:~/Latihan1_sistemOperasi$ ls -lRh >> report.txt
```
🧠Penjelasan:

ls -lRh menampilkan daftar file dan folder secara rinci (-l), rekursif (-R), dan ukuran manusiawi (-h).

Output daftar file ini kemudian ditambahkan ke report.txt.



---

✨ HASIL AKHIR

Setelah semua langkah dijalankan, kamu akan mendapatkan file bernama report.txt yang berisi informasi seperti berikut:

=== LAPORAN FILE SISTEM ===
Jumlah file:
5
Jumlah folder:
3
Ukuran total direktori:
20K
Daftar file:
(total 12K)
-rw-rw-r-- 1 vboxuser vboxuser  120 Nov 11 08:05 report.txt

DEKRIPSI GAMBAR
(https://drive.google.com/file/d/1r-g3qWzZp21oOSopnosv_kRXnqb8gWhH/view?usp=drive_link)

TEKS GAMBAR
(https://drive.google.com/file/d/1gVZaUzqADPcHLzist1X9CZSsuWFCCYjy/view?usp=drive_link)


