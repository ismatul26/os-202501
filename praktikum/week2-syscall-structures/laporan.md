
# Laporan Praktikum Minggu 2
Topik: Struktur system call dan fungsi kernel

---

## Identitas
- Nama : ISMATUL KHOERIYAH
- NIM  : 250202912
- Kelas: 1IKRA

---

## Tujuan
Tuliskan tujuan praktikum: 
 •Memahami konsep dasar system call dan bagaimana proses user berinteraksi dengan kernel dalam sistem operasi.
 •Memecahkan masalah dalam mengamati dan menganalisis log sistem operasi Linux sebagai dasar dalam memahami cara kerja      internal sistem.
 
> 

---

## Dasar Teori
Tuliskan ringkasan teori:
  •System call adalah mekanisme komunikasi antara program pengguna dan kernel untuk mengakses layanan sistem operasi,        seperti membaca file, menulis data, dan membuat proses baru.
  •Dalam Linux, perintah strace digunakan untuk melacak aktivitas system call suatu program, sedangkan dmesg digunakan       untuk melihat pesan log kernel dan aktivitas sistem.


---

## Langkah Praktikum
1. Langkah-langkah yang dilakukan.  
2. Perintah yang dijalankan.  
3. File dan kode yang dibuat.  
4. Commit message yang digunakan.

---

## Kode / Perintah
Tuliskan potongan kode atau perintah utama:
```bash
uname -a
lsmod | head
dmesg | head
```

---

## Hasil Eksekusi
Sertakan screenshot hasil percobaan atau diagram:
![Screenshot hasil](screenshots/example.png)

---

## Analisis
- Jelaskan makna hasil percobaan.  
- Hubungkan hasil dengan teori (fungsi kernel, system call, arsitektur OS).  
- Apa perbedaan hasil di lingkungan OS berbeda (Linux vs Windows)?  

---

## Kesimpulan   
   System call merupakan mekanisme penting yang memungkinkan program pengguna (user program) berinteraksi dengan kernel sistem operasi. Tanpa system call, program tidak bisa mengakses sumber daya seperti file, memori, atau perangkat keras.
   

---
## Tugas
1. Dokumentasi hasil eksperimen straece dan dmesg dalam bentuk tabel obsevasi :
   | strace Is | strace -c Is | strace -p |
   | 


2. Tulis analisis 400-500 kata :
   system cal merupakan mekanisme penting yang memungkinkan program aplikasi (user mode) berinteraksi dengan kernel (system mode) secara amandan terkontrol. tanpa system call, program pengguna tidak akan bisa mengakses sumber daya penting seperti memori, file, perangkat keras, maupun jaringan, karena akses langsung dari user mode ke kernel dapat menyebabkan kerusakan system atau kebocoran data. Oleh karena itu, system call berperan sebagai gerbang penghubung antara pengguna dan sistem operasi yang menjaga keamanan serta stabilitas seluruh sistem komputer. system call penting bagi keamanan OS karena berfungsi sebagai lapisan kontrol antara aplikasi dan sumber daya inti sistem. kernel memiliki hak istimewa tertinggi, sedangkan program pengguna berjala di mode terbatas (user mode). jika program pengguna diizinkan mengakses kernel secara langsung, maka virus atau program berbahaya bisa mengubah data sistem, menghapus file penting, ataumengganggu proses lain.
    Dengan adanya syistem call, setiap permintaan dari user ke kernel harus melalui prosedur yang diawasi. Kernel akan memverifikasi apakh permintaan tersebut sah, dan apakah operasi tersebut aman dilakukan. Selain itu, transisi anatara user mode dan kernel mode juga dijaga ketat agar berjalan aman. saat program melakukan system call, CPU akan berpindah dari user mode ke kernel mode melalui mekanisme yang disebut trap atau interrupt. OS memastikan bahwa hanya intruksi tertentu yang bisa memicu transisi ini, dan alamat kode kernel yang dijalankan sudah sudah ditentukan secara tetap.

## Quiz
1. Apa fungsi utama system call dalam sistem opera
   jawab: Memberikan layanan agar program dapat menggunakan fungsi-fungsi kerneluntuk mengakses sumber daya sistem                 secara aman dan efisien.
3.  Sebutkan 4 kategori system call yang umum digunakan.
   jawab: Manajemen proses, Manajemen berkas, Manajemen memori, Manajemen perangkat I/O.
    
5. Mengapa system call tidak bisa dipanggil langsung oleh user program?
   jawab: Karena berjalan di user mode, sedangkan fungsi system call berada di kernel mode.
 

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?
  Jawaban: Memahami alur kerja system call dan hubungan antara user mode dengan kernel mode. Hal ini karena proses
tersebut terjadi sangat cepat dan tidak terlihat langsung oleh pengguna.
- Bagaimana cara Anda mengatasinya?
  Jawaban: Membandingkan hasil percobaan dengan teori, agar lebih mudah melihat hubungan antara konsep dan praktik.

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
