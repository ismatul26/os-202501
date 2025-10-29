
# Laporan Praktikum Minggu 3
Topik: Manajemen File dan Permission di linux

---

## Identitas
- Nama : ISMATUL KHOERIYAH
- NIM  : 250202912 
- Kelas: 1IKRA

---

## Tujuan
Tuliskan tujuan praktikum minggu ini.  
- Menggunakan perintah Is pwd cd cat untuk navigasi file.
- Menggunakan chomd dan chown untuk manajemen hak asas file
- Menjelaskan hsil output dari perintah linux dasar.
- Menyususn laporan praktikum dengan struktur yang benar.
---

## Dasar Teori
Tuliskan ringkasan teori (3–5 poin) yang mendasari percobaan.
  Konsep dasar dari percobaan trsrbut adalah konsep system berkas dalam system operasi, konsep ini penting untuk mempelajarri bagaimana system operasi keamanan, efesiensi.
---

## Langkah Praktikum
1. Langkah-langkah yang dilakukan.  
2. Perintah yang dijalankan.  
3. File dan kode yang dibuat.  
4. Commit message yang digunakan.

---

## Kode / Perintah:
1. Setup Environment
• Gunakan Linux (Ubuntu/WSL).
• Pastikan folder kerja berada di dalam direktori repositori Git praktikum:
 praktikum/week3-linux-fs-permission/

3. Eksperimen 1 – Navigasi Sistem File Jalankan perintah berikut:

pwd
ls -l
cd /tmp
ls -a
• Jelaskan hasil tiap perintah.
• Catat direktori aktif, isi folder, dan file tersembunyi (jika ada).

3. Eksperimen 2 – Membaca File Jalankan perintah:

cat /etc/passwd | head -n 5
• Jelaskan isi file dan struktur barisnya (user, UID, GID, home, shell).

4. Eksperimen 3 – Permission & Ownership Buat file baru:

echo "Hello <NAME><NIM>" > percobaan.txt
ls -l percobaan.txt
chmod 600 percobaan.txt
ls -l percobaan.txt
• Analisis perbedaan sebelum dan sesudah chmod.
• Ubah pemilik file (jika memiliki izin sudo):

sudo chown root percobaan.txt
ls -l percobaan.txt
• Catat hasilnya.

5. Eksperimen 4 – Dokumentasi

• Ambil screenshot hasil terminal dan simpan di:
praktikum/week3-linux-fs-permission/screenshots/
• Tambahkan analisis hasil pada laporan.md.
• Commit & Push

git add .
git commit -m "Minggu 3 - Linux File System & Permission"
git push origin main

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
 Manajemen file memungkinkan pengguna untuk mengelola data dengan efisien serta menjaga keamanan melalui pengaturan hak akses.

---

## Quiz
1. Apa fungsi dari perintah chmod?  
   Jawaban: Perintah chmod digunakan untuk mengubah hak akses (permission) pada file atau direktori di sistem operasi                 Linux/Unix. Hak akses ini menentukan siapa yang dapat membaca (read), menulis (write), atau mengeksekusi                  (execute) file tersebut
2. Apa arti dari kode permission rwxr-xr-?
   Jawaban: •rwx → untuk pemilik (owner) : memiliki hak baca, tulis, dan eksekusi.
            •r-x → untuk grup (group) : hanya bisa membaca dan mengeksekusi.
            •r-- → untuk lainnya (others) : hanya bisa membaca.
3. Jelaskan perbedaan antara chown dan chmod!
   Jawaban: Chmod mengatur siapa yang boleh melakukan apa terhadap file, sedangkan chown mengatur siapa pemilik file                  tersebut.

---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
