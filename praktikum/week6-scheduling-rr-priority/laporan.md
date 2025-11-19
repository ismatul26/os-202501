
# Laporan Praktikum Minggu 6
Topik: Penjadwalan CPU – Round Robin (RR) dan Priority Scheduling


---

## Identitas
- Nama  : ISMATUL KHOERIYAH    
- NIM   : 250202912 
- Kelas : 1IKRA

---

## Tujuan
1. Menghitung waiting time dan turnaround time pada algoritma RR dan Priority.
2. Menyusun tabel hasil perhitungan dengan benar dan sistematis.
3. Membandingkan performa algoritma RR dan Priority.
4. Menjelaskan pengaruh time quantum dan prioritas terhadap keadilan eksekusi proses.
5. Menarik kesimpulan mengenai efisiensi dan keadilan kedua algoritma.

---

## Dasar Teori
Pada praktikum minggu ini, mahasiswa akan mempelajari dua algoritma lanjutan penjadwalan CPU, yaitu:
- Round Robin (RR)
- Priority Scheduling
Kedua algoritma ini banyak digunakan pada sistem modern karena mempertimbangkan keadilan waktu eksekusi (time quantum) dan tingkat prioritas proses.
Mahasiswa akan melakukan simulasi perhitungan manual untuk menghitung waiting time dan turnaround time, serta menganalisis efek perbedaan time quantum dan prioritas terhadap performa CPU scheduling.


---

## Langkah Praktikum
1. Siapkan Data Proses Gunakan contoh data berikut (boleh dimodifikasi sesuai kebutuhan):
Proses	Burst Time	Arrival Time	Priority
P1      	5            	0	          2
P2      	3           	1	          1
P3      	8	            2           4
P4	      6	            3         	3

2. Eksperimen 1 – Round Robin (RR)
Gunakan time quantum (q) = 3.
Hitung waiting time dan turnaround time untuk tiap proses.
Simulasikan eksekusi menggunakan Gantt Chart (manual atau spreadsheet).
| P1 | P2 | P3 | P4 | P1 | P3 | ...
0    3    6    9   12   15   18  ...
Catat sisa burst time tiap putaran.

3. Eksperimen 2 – Priority Scheduling (Non-Preemptive)
Urutkan proses berdasarkan nilai prioritas (angka kecil = prioritas tinggi).
Lakukan perhitungan manual untuk:
WT[i] = waktu mulai eksekusi - Arrival[i]
TAT[i] = WT[i] + Burst[i]
Buat tabel perbandingan hasil RR dan Priority.

4. Eksperimen 3 – Analisis Variasi Time Quantum (Opsional)
Ubah quantum menjadi 2 dan 5.
Amati perubahan nilai rata-rata waiting time dan turnaround time.
Buat tabel perbandingan efek quantum.

5. Eksperimen 4 – Dokumentasi
Simpan semua hasil tabel dan screenshot ke:

praktikum/week6-scheduling-rr-priority/screenshots/
Buat tabel perbandingan seperti berikut:

Algoritma 	Avg Waiting Time  	Avg Turnaround Time	      Kelebihan                              	Kekurangan
RR           	...                  	...             	Adil terhadap semua proses	    Tidak efisien jika quantum tidak tepat
Priority    	...	                  ...             	Efisien untuk proses penting  	Potensi starvation pada prioritas rendah

6. Commit & Push
git add .
git commit -m "Minggu 6 - CPU Scheduling RR & Priority"
git push origin main

---

##Tugas
1. Hitung waiting time dan turnaround time untuk algoritma RR dan Priority.
   jawab:    Proses	       Arrival (ms)  	     Burst (ms)	       Priority (angka kecil = prioritas lebih tinggi)
               P1             	0	                  5                   	2
               P2              	1	                  3                   	1
               P3	              2                  	8                   	4
               P4             	3	                  6                   	3
Rumus singkat:
Turnaround time (TAT) = Completion time − Arrival time
Waiting time (WT) = Turnaround time − Burst time

2. Sajikan hasil perhitungan dan Gantt Chart dalam laporan.md.
Algoritma    	Avg TAT    	Avg WT
RR          	15.25 ms	  9.75 ms
Priority    	10.75 ms  	5.25 ms

3. Bandingkan performa dan jelaskan pengaruh time quantum serta prioritas
   jawab: pengaruh time quantum:
          a. Prioritas Menentukan Urutan Eksekusi
            Proses dengan prioritas lebih tinggi selalu dijalankan lebih dulu
            Efeknya:
            Turnaround time proses prioritas tinggi → kecil
            Turnaround time proses prioritas rendah → besar
         b. Risiko Starvation
            Jika selalu datang proses prioritas tinggi, proses prioritas rendah bisa tidak pernah diproses
            Sering diatasi dengan:
            Aging (menaikkan prioritas proses semakin lama dia menunggu)
        c. Cocok untuk Sistem Real-Time.
   
## Quiz
   1. Apa perbedaan utama antara Round Robin dan Priority Scheduling?
    Jawaban: 1. Cara Menentukan Urutan Eksekusi
              -Round Robin: Berdasarkan giliran dengan time quantum.
              -Priority: Berdasarkan tingkat prioritas proses.
             2. Urutan Eksekusi
              -RR: Semua proses diperlakukan sama dan dieksekusi bergantian.
              -Priority: Proses dengan prioritas tertinggi dijalankan terlebih dahulu.
            3. Keadilan
              -RR: Paling adil—tidak ada proses yang menunggu terlalu lama.
              -Priority: Bisa tidak adil—proses prioritas rendah dapat mengalami starvation.
            4. Responsivitas
             -RR: Sangat responsif, cocok untuk sistem interaktif.
             -Priority: Responsivitas bergantung pada nilai prioritas.
            5. Overhead
             -RR: Tinggi karena banyak context switching.
             -Priority: Rendah karena proses jarang berganti-ganti.
  2.Apa pengaruh besar/kecilnya time quantum terhadap performa sistem?
   Jawaban: 1. Time Quantum Terlalu Kecil
             CPU sering melakukan context switching → overhead meningkat.
             Kinerja sistem menjadi kurang efisien.
             Tapi responsivitas sangat baik karena proses cepat mendapat giliran kembali.
             Gantt chart menjadi sangat terfragmentasi.
           2. Time Quantum Terlalu Besar
             RR menjadi mirip FCFS, proses panjang mendominasi CPU.
             Proses pendek menunggu lebih lama → responsivitas menurun.
             Overhead kecil karena context switching jarang.
           3. Time Quantum Ideal
            Dipilih mendekati rata-rata burst time.
            Menghasilkan keseimbangan antara:
            - Fairness
            - Responsiveness
            - Efisiensi context switching   
 3.Mengapa algoritma Priority dapat menyebabkan starvation?
  Jawaban: Karena CPU selalu memilih proses dengan priorits tinggi, sehingga proses berprioritas rendah trs tertunda dan tidak mendapat giliran eksekusi apabila proses berprioritas tinggi datang terus meberus.  

---

F. Referensi
- Abraham Silberschatz, Peter Baer Galvin, Greg Gagne. Operating System Concepts, 10th Edition, Wiley, 2018.
- Andrew S. Tanenbaum, Herbert Bos. Modern Operating Systems, 4th Edition, Pearson, 2015.
- OSTEP – Operating Systems: Three Easy Pieces, 2018.
- Linux Manual Pages – Scheduling & Process Control

_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
