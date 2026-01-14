
# Laporan Praktikum Minggu 10
Topik: Docker – Resource Limit (CPU & Memori) 

---

## Identitas
- Nama  : ISMATUL KHOERIYAH 
- NIM   : 250202912 
- Kelas : IKRA

---

## Tujuan
Setelah menyelesaikan tugas ini, mahasiswa mampu:
1. Menulis Dockerfile sederhana untuk sebuah aplikasi/skrip.
2. Membangun image dan menjalankan container.
3. Menjalankan container dengan pembatasan CPU dan memori.
4. Mengamati dan menjelaskan perbedaan eksekusi container dengan dan tanpa      limit resource.
5. Menyusun laporan praktikum secara runtut dan sistematis.

---

## Dasar Teori

---

## Langkah Praktikum
1. Persiapan Lingkungan
Pastikan Docker terpasang dan berjalan.
Verifikasi:
docker version
docker ps
2. Membuat Aplikasi/Skrip Uji

Buat program sederhana di folder code/ (bahasa bebas) yang:
-Melakukan komputasi berulang (untuk mengamati limit CPU), dan/atau
-Mengalokasikan memori bertahap (untuk mengamati limit memori).

3. Membuat Dockerfile
-Tulis Dockerfile untuk menjalankan program uji.
-Build image
docker build -t week13-resource-limit .

4. Menjalankan Container Tanpa Limit
-Jalankan container normal
 docker run --rm week13-resource-limit
- Catat output/hasil pengamatan.
  
5. Menjalankan Container Dengan Limit Resource
-Jalankan container dengan batasan resource (contoh):
docker run --rm --cpus="0.5" --memory="256m" week13-resource-limit
  Catat perubahan perilaku program (mis. lebih lambat, error saat memori tidak cukup, dll.).

6. Monitoring Sederhana
-Jalankan container (tanpa --rm jika perlu) dan amati penggunaan resource:
docker stats
-Ambil screenshot output eksekusi dan/atau docker stats.

8. Commit & Push
git add .
git commit -m "Minggu 13 - Docker Resource Limit"
git push origin main
 
---

## TUGAS & QUIZ
#TUGAS
1. Buat Dockerfile sederhana dan program uji di folder code/.
2. Build image dan jalankan container tanpa limit.
3. Jalankan container dengan limit CPU dan memori.
4. Sajikan hasil pengamatan dalam tabel/uraian singkat di laporan.md.
   
## QUIZ
1. Mengapa container perlu dibatasi CPU dan memori?
   JAWAB: Container perlu dibatasi CPU dan memori karena container berjalan di atas satu sistem operasi yang sama dan menggunakan sumber daya (resource) yang terbatas. Jika tidak diberi batasan, satu container dapat menggunakan CPU dan memori secara berlebihan sehingga mengganggu kinerja container lain bahkan menyebabkan sistem operasi host menjadi tidak stabil atau mengalami crash. 
2. Apa perbedaan VM dan container dalam konteks isolasi resource?
   JAWAB: VM memberikan isolasi resource yang lebih kuat dan aman karena setiap VM memiliki OS sendiri, sedangkan container memberikan isolasi yang lebih ringan dan efisien dengan berbagi kernel host, namun tetap memerlukan pembatasan resource agar tidak saling mengganggu. 
3. Apa dampak limit memori terhadap aplikasi yang boros memori?
   JAWAB: Dampak limit memori terhadap aplikasi yang boros memori adalah aplikasi dapat mengalami penurunan kinerja, gagal memproses data, atau berhenti secara paksa (OOM kill) ketika penggunaan memori melebihi batas yang ditetapkan.

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
Tuliskan 2–3 poin kesimpulan dari praktikum ini.


---
