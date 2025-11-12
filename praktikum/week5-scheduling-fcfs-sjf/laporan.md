
# Laporan Praktikum Minggu 5
Topik: Penjadwalan CPU – FCFS dan SJF

---

## Identitas
- Nama  : ISMATUL KHOERIYAH   
- NIM   : 250202912
- Kelas : 1IKRA
---

## Tujuan
Setelah menyelesaikan tugas ini, mahasiswa mampu:
1. Menghitung waiting time dan turnaround time untuk algoritma FCFS dan SJF.
2. Menyajikan hasil perhitungan dalam tabel yang rapi dan mudah dibaca.
3. Membandingkan performa FCFS dan SJF berdasarkan hasil analisis.
4. Menjelaskan kelebihan dan kekurangan masing-masing algoritma.
5. Menyimpulkan kapan algoritma FCFS atau SJF lebih sesuai digunakan.

---

## Dasar Teori

1. FCFS (First Come, First Served)
  - FCFS merupakan algoritma penjadwalan paling sederhana.
  - Proses yang datang terlebih dahulu akan dieksekusi terlebih dahulu (antrian FIFO – First In, First Out).
  - Tidak ada preemption; proses yang sedang berjalan akan terus dieksekusi sampai selesai.
   Kelebihan: Mudah diterapkan dan adil terhadap proses yang datang lebih dulu.
   Kekurangan: Dapat menyebabkan convoy effect — proses kecil menunggu proses besar selesai.
3. SJF (Shortest Job First)
  - Algoritma ini memilih proses dengan waktu eksekusi (burst time) paling pendek untuk dieksekusi terlebih dahulu.
  - Dapat bersifat: Non-preemptive: proses tidak dihentikan sampai selesai.
                     Preemptive (Shortest Remaining Time First – SRTF): jika ada proses baru dengan waktu lebih pendek, CPU berpindah ke                        proses tersebut.
   Kelebihan: Memberikan waktu tunggu rata-rata yang paling rendah.
   Kekurangan: Sulit diterapkan karena waktu eksekusi proses biasanya tidak diketahui sebelumnya.

---

## Langkah Praktikum
1. Siapkan Data Proses Gunakan tabel proses berikut sebagai contoh (boleh dimodifikasi dengan data baru):
| Proses |	Burst Time |	Arrival Time |
   P1         	6	            0
   P2          	8            	1
   P3         	7           	2
   P4	          3           	3

2. Eksperimen 1 – FCFS (First Come First Served)
   - Urutkan proses berdasarkan Arrival Time.
   - Hitung nilai berikut untuk tiap proses:
     Waiting Time (WT) = waktu mulai eksekusi - Arrival Time
     Turnaround Time (TAT) = WT + Burst Time
  - Hitung rata-rata Waiting Time dan Turnaround Time.
  - Buat Gantt Chart sederhana:
    | P1 | P2 | P3 | P4 |
    0    6    14   21   24
    
3. Eksperimen 2 – SJF (Shortest Job First)
 - Urutkan proses berdasarkan Burst Time terpendek (dengan memperhatikan waktu kedatangan).
 - Lakukan perhitungan WT dan TAT seperti langkah sebelumnya.
 - Bandingkan hasil FCFS dan SJF pada tabel berikut:

| Algoritma |	Avg Waiting Time | Avg Turnaround Time |	          Kelebihan            |	         Kekurangan                      |
    FCFS        	...                 	...	            Sederhana dan mudah diterapkan    	Tidak efisien untuk proses panjang
    SJF         	...	                  ...           	Optimal untuk job pendek          	Menyebabkan starvation pada job panjang
    
4. Eksperimen 3 – Visualisasi Spreadsheet (Opsional)
- Gunakan Excel/Google Sheets untuk membuat perhitungan otomatis:
  Kolom: Arrival, Burst, Start, Waiting, Turnaround, Finish.
  Gunakan formula dasar penjumlahan/subtraksi.
- Screenshot hasil perhitungan dan simpan di:
  praktikum/week5-scheduling-fcfs-sjf/screenshots/
  
5. Analisis
- Bandingkan hasil rata-rata WT dan TAT antara FCFS & SJF.
- Jelaskan kondisi kapan SJF lebih unggul dari FCFS dan sebaliknya.
- Tambahkan kesimpulan singkat di akhir laporan.
  
6. Commit & Push
git add .
git commit -m "Minggu 5 - CPU Scheduling FCFS & SJF"
git push origin main

---
## Tugas
1. Hitung waiting time dan turnaround time dari minimal 2 skenario FCFS dan SJF.
2. Sajikan hasil perhitungan dalam tabel perbandingan (FCFS vs SJF).
3. Analisis kelebihan dan kelemahan tiap algoritma.
4. Simpan seluruh hasil dan analisis ke laporan.md.

---

## Quiz
1.  Apa perbedaan utama antara FCFS dan SJF?
    Jawaban: Perbedaan utama antara FCFS dan SJF adalah sebagai berikut:
           - FCFS (First Come, First Served) menjadwalkan proses berdasarkan urutan kedatangan. Proses yang datang lebih dulu akan                    dieksekusi lebih dulu. Algoritma ini non-preemptive dan mudah diterapkan, tetapi dapat menyebabkan convoy effect, yaitu                   proses kecil harus menunggu proses besar selesai.
          - SJF (Shortest Job First) menjadwalkan proses berdasarkan lama waktu eksekusi paling pendek. Algoritma ini dapat bersifat non-             preemptive atau preemptive (SRTF). SJF menghasilkan waktu tunggu rata-rata lebih kecil, tetapi sulit diterapkan karena                    membutuhkan informasi lama eksekusi dan dapat menyebabkan starvation bagi proses yang lebih panjang.

2.  Mengapa SJF dapat menghasilkan rata-rata waktu tunggu minimum?
    Jawaban: Karena, algoritma ini selalu menjalankan proses dengan waktu eksekusi paling singkat terlebih dahulu.
             Dengan cara ini, proses-proses kecil cepat selesai dan tidak menunggu lama di antrian. Proses yang lebih panjang baru                     dijalankan setelah proses-proses pendek selesai, sehingga total waktu tunggu semua proses menjadi lebih efisien. 

3. Apa kelemahan SJF jika diterapkan pada sistem interaktif?
    Jawaban: 1. Sulit mengetahui waktu eksekusi proses sebelumnya, pada sistem interaktif, lama waktu proses tidak bisa diprediksi                        karena tergantung pada input pengguna.
             2. Tidak responsif terhadap proses baru, proses yang panjang bisa membuat proses interaktif (yang butuh respon cepat) harus                  menunggu.
             3. Dapat menyebabkan starvation, proses dengan waktu eksekusi panjang bisa tertunda terus jika selalu ada proses pendek                      yang masuk lebih dulu.

---

##Output yang Diharapkan
- Hasil observasi dan perhitungan dimasukkan ke dalam laporan.md.
- Screenshot tabel atau Gantt Chart disimpan di screenshots/.
- Laporan lengkap berada di laporan.md.
- Semua hasil telah di-commit ke GitHub tepat waktu.


---
##Referensi
- Abraham Silberschatz, Peter Baer Galvin, Greg Gagne. Operating System Concepts, 10th Edition, Wiley, 2018.
- Andrew S. Tanenbaum, Herbert Bos. Modern Operating Systems, 4th Edition, Pearson, 2015.
- OSTEP – Operating Systems: Three Easy Pieces, 2018.
- Linux Manual Pages – Scheduling & Process Control.

