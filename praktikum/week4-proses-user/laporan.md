
# Laporan Praktikum Minggu 4
Topik: Manajemen Proses dan User di Linux

---

## Identitas
- Nama  : Ismatul Khoeriyah
- NIM   : 250202912 
- Kelas : 1IKRA

---

## Tujuan
Tujuan praktikum: 
Menjelaskan konsep proses dan user dalam sistem operasi Linux.
Menampilkan daftar proses yang sedang berjalan dan statusnya.
Menggunakn perintah untuk membuat dan megelola user.
Menghentikan atau mengontrl proses tertentu menggunakan PID.
Menjelaskan kaitan antara manajemen user dan keamanan sistem.
  

---

## Dasar Teori
Tuliskan ringkasan teori (3–5 poin) yang mendasari percobaan.

---

## Langkah Praktikum
1. Setup Environment

Gunakan Linux (Ubuntu/WSL).
Pastikan Anda sudah login sebagai user non-root.
Siapkan folder kerja:
praktikum/week4-proses-user/
2. Eksperimen 1 – Identitas User Jalankan perintah berikut:

whoami
id
groups
Jelaskan setiap output dan fungsinya.
Buat user baru (jika memiliki izin sudo):
sudo adduser praktikan
sudo passwd praktikan
Uji login ke user baru.
3. Eksperimen 2 – Monitoring Proses Jalankan:

ps aux | head -10
top -n 1
Jelaskan kolom penting seperti PID, USER, %CPU, %MEM, COMMAND.
Simpan tangkapan layar top ke:
praktikum/week4-proses-user/screenshots/top.png
Eksperimen 3 – Kontrol Proses

Jalankan program latar belakang:
sleep 1000 &
ps aux | grep sleep
Catat PID proses sleep.
Hentikan proses:
kill <PID>
Pastikan proses telah berhenti dengan ps aux | grep sleep.
4. Eksperimen 4 – Analisis Hierarki Proses Jalankan:

pstree -p | head -20
Amati hierarki proses dan identifikasi proses induk (init/systemd).
Catat hasilnya dalam laporan.

5. Commit & Push

git add .
git commit -m "Minggu 4 - Manajemen Proses & User"
git push origin main

D. Tugas & Quiz
Tugas
Dokumentasikan hasil semua perintah dan jelaskan fungsi tiap perintah.
Gambarkan hierarki proses dalam bentuk diagram

---

## Kode / Perintah
-whoami
 id
 groups
 Jelaskan setiap output dan fungsinya.
 Buat user baru (jika memiliki izin sudo):
 sudo adduser praktikan
 sudo passwd praktikan
- ps aux | head -10
 top -n 1
-sleep 1000 &
 ps aux | grep sleep
 kill <PID>
 -pstree -p | head -20




---


## Hasil Eksekusi
Sertakan screenshot hasil percobaan atau diagram:
![Screenshot hasil](screenshots/example.png)

---

## Analisis
 Pada praktikum Manajemen Proses dan Linux, dilakukan serangkaian percobaan untuk memahami cara kerja dan pengelolaan proses dalam sistem operasi berbasis Linux. Hasil praktikum menunjukkan bagaimana Linux menangani berbagai proses secara simultan, serta bagaimana pengguna dapat memonitor, mengatur prioritas, dan mengontrol proses-proses tersebut menggunakan perintah terminal.  

---

## Kesimpulan
Berdasarkan hasil praktikum manajemen proses pada sistem operasi Linux, dapat disimpulkan bahwa Linux memiliki sistem pengelolaan proses yang sangat efisien dan terstruktur. Setiap proses yang berjalan memiliki identitas unik berupa PID, status, serta prioritas yang dapat diatur sesuai kebutuhan pengguna.
---

## Quiz
1. Apa fungsi dari proses init atau systemd dalam sistem Linux?
  Jawaban: Dalam sistem operasi Linux, init atau systemd adalah proses pertama yang dijalankan oleh kernel saat sistem mulai booting. Proses ini memiliki PID = 1, dan berperan sebagai induk dari semua proses lain di sistem.
  
2. Apa perbedaan antara kill dan killall?
  Jawaban: - kill digunakan untuk menghentikan proses berdasarkan PID (Process ID).
             Contoh: kill 1234 → menghentikan proses dengan PID 1234.
           - killall digunakan untuk menghentikan semua proses berdasarkan nama program.
             Contoh: killall firefox → menghentikan semua proses bernama firefox.
           - Perbedaan utama: kill pakai PID, sedangkan killall pakai nama proses.
3. Mengapa user root memiliki hak istimewa di sistem Linux?
  Jawaban: Karena User root memiliki hak istimewa karena ia adalah administrator utama sistem, yang berfungsi untuk mengontrol, mengatur, dan memelihara seluruh aspek sistem Linux agar berjalan dengan aman dan stabil.   

---


---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
