# TUGAS-RAHMAT
# PRAKTIKUM SISTEM OPERASI

Project Based Learning 1 (latihan 2)

LATIHAN 2

Berikut langkah-langkah penulisan syntax nya:

# 1. Masuk ke Folder Proyek

```
cd latihan2_sistemOperasi

```

Penjelasan:

Perintah cd berarti change directory — digunakan untuk masuk ke folder proyek kamu yang bernama latihan2_sistemOperasi.


Pastikan folder ini sudah ada di direktori home kamu sebelumnya (~/).





# 2. Membuat Struktur Folder Proyek

```
mkdir src doc data
```


Penjelasan:




mkdir (make directory) digunakan untuk membuat folder baru.


Di sini kamu membuat tiga folder:



src → tempat menyimpan source code (kode program utama).


doc → tempat menyimpan dokumentasi.


data → tempat menyimpan data atau file pendukung.









# 3. Membuat File Baru


```
touch README.MD src main.sh
```


Penjelasan:




touch digunakan untuk membuat file kosong.


Tapi di sini ada sedikit kesalahan kecil: touch README.MD src main.sh akan mencoba membuat file bernama src, bukan menambah isi folder src.

Yang benar seharusnya:

touch README.MD main.sh


agar hanya membuat dua file kosong:



README.MD → file dokumentasi utama proyek (biasanya berisi deskripsi proyek di GitHub).


main.sh → file shell script utama (kode yang bisa dijalankan di terminal Linux).









# 4. Melihat Struktur Folder


tree



Penjelasan:




Menampilkan struktur folder dan file secara hierarkis.


Output-nya menunjukkan:

.
├── data
├── doc
├── main.sh
├── README.MD
└── src


Artinya proyek sudah memiliki struktur direktori dan file yang rapi.






Jika perintah tree belum ada di sistem kamu, install dengan:


sudo apt install tree






# 5. Melihat Ukuran Folder


```
du -h --max-depth=1

```

Penjelasan:




du = disk usage, untuk melihat ukuran setiap folder.


-h = human-readable, agar ukuran ditampilkan dalam format seperti KB, MB, GB.


--max-depth=1 = hanya menampilkan ukuran di tingkat pertama direktori (tidak masuk ke subfolder).


Output-nya memperlihatkan ukuran masing-masing folder (data, src, doc) dan total ukuran keseluruhan.


 
# BERIKUT LINK DESKRIPSI HASIL DOKUMENTASI PEMBUATAN :
(https://drive.google.com/file/d/1D39oAdIV_OS8t9exBZkKQ-fp17wS6kdz/view?usp=drive_link)
