
# Laporan Praktikum Minggu 10
Topik: Manajemen Memori – Page Replacement (FIFO & LRU) 

---

# Identitas
 Nama  : ISMATUL KHOERIYAH 
 NIM   : 250202912  
 Kelas : IKRA

---

# Tujuan
Setelah menyelesaikan tugas ini, mahasiswa mampu:

- Mengimplementasikan algoritma page replacement FIFO dalam program.
- Mengimplementasikan algoritma page replacement LRU dalam program.
- Menjalankan simulasi page replacement dengan dataset tertentu.
- Membandingkan performa FIFO dan LRU berdasarkan jumlah page fault.
- Menyajikan hasil simulasi dalam laporan yang sistematis.


---

# Dasar Teori

Memori virtual adalah mekanisme sistem operasi yang memungkinkan program menggunakan ruang memori lebih besar dari memori fisik dengan cara menyimpan sebagian data di secondary storage. Data dikelola dalam satuan page dan ditempatkan pada frame di memori utama.

Page fault terjadi ketika proses mengakses halaman yang belum ada di memori. Jika memori penuh, sistem harus melakukan page replacement, yaitu memilih halaman yang akan diganti agar halaman baru dapat dimuat. Tujuan utama mekanisme ini adalah mengurangi jumlah page fault dan meningkatkan kinerja sistem.

Algoritma FIFO (First-In First-Out) mengganti halaman yang pertama kali masuk ke memori. Algoritma ini sederhana, namun tidak mempertimbangkan frekuensi akses dan dapat menimbulkan anomali Belady.

# Langkah Praktikum

Langkah-langkah yang dilakukan.
Perintah yang dijalankan.
File dan kode yang dibuat.
Commit message yang digunakan.

---

# Kode / Perintah
import os

def fifo_page_replacement(reference_string, frames_count):
    frames = []
    page_faults = 0
    page_hits = 0

    print("=== FIFO Page Replacement ===")
    for page in reference_string:
        if page in frames:
            page_hits += 1
            print("Page", page, "= HIT | Frame:", frames)
        else:
            page_faults += 1
            if len(frames) < frames_count:
                frames.append(page)
            else:
                frames.pop(0)
                frames.append(page)
            print("Page", page, "= FAULT | Frame:", frames)

    print("Total Page Fault (FIFO):", page_faults)
    print("Total Page Hit (FIFO):", page_hits)
    print()


def lru_page_replacement(reference_string, frames_count):
    frames = []
    page_faults = 0
    page_hits = 0

    print("=== LRU Page Replacement ===")
    for page in reference_string:
        if page in frames:
            page_hits += 1
            frames.remove(page)
            frames.append(page)
            print("Page", page, "= HIT | Frame:", frames)
        else:
            page_faults += 1
            if len(frames) < frames_count:
                frames.append(page)
            else:
                frames.pop(0)
                frames.append(page)
            print("Page", page, "= FAULT | Frame:", frames)

    print("Total Page Fault (LRU):", page_faults)
    print("Total Page Hit (LRU):", page_hits)
    print()


def read_reference_string(file_path):
    with open(file_path, "r") as file:
        return [int(x.strip()) for x in file.read().split(",")]

---

# Hasil Eksekusi
Sertakan screenshot hasil percobaan atau diagram:
![Screenshot hasil](screenshots/example.png)

---

# Analisis
- Jelaskan makna hasil percobaan.  
- Hubungkan hasil dengan teori (fungsi kernel, system call, arsitektur OS).  
- Apa perbedaan hasil di lingkungan OS berbeda (Linux vs Windows)?  

---

# Kesimpulan

Page replacement berperan penting dalam memori virtual untuk menangani page fault saat memori penuh. Algoritma FIFO sederhana tetapi kurang efisien pada beberapa pola akses, sedangkan LRU lebih adaptif dan umumnya menghasilkan jumlah page fault yang lebih sedikit. Oleh karena itu, pemilihan algoritma yang tepat berpengaruh langsung pada kinerja dan efisiensi sistem memori.

---

# TUGAS DAN QUIZ
#TUGAS
1. Buat program simulasi page replacement FIFO dan LRU.
2. Jalankan simulasi dengan dataset uji.
3. Sajikan hasil simulasi dalam tabel atau grafik.
4. Tulis laporan praktikum pada laporan.md.
#QUIZ
1. Apa perbedaan utama FIFO dan LRU?
   JAWAB: Perbedaan utamanya ada pada dasar pemilihan halaman yang diganti:
          -FIFO (First-In First-Out)
          Mengganti halaman yang paling dulu masuk ke memori — seperti antrian. Tidak melihat apakah halaman tersebut masih            sering dipakai atau tidak.
          
          -LRU (Least Recently Used)
          Mengganti halaman yang paling lama tidak digunakan. Mempertimbangkan riwayat akses sehingga lebih sesuai dengan              pola penggunaan memori.
2. Mengapa FIFO dapat menghasilkan Belady’s Anomaly?
   JAWAB: FIFO dapat menyebabkan Belady’s Anomaly karena algoritma ini hanya berdasarkan urutan kedatangan halaman dan tidak           mempertimbangkan apakah halaman masih sering digunakan. Akibatnya, penambahan frame bisa membuat halaman penting             ikut terganti sehingga jumlah page fault justru bertambah.
3. Mengapa LRU umumnya menghasilkan performa lebih baik dibanding FIFO?
   JAWAB: LRU umumnya lebih baik daripada FIFO karena memilih halaman berdasarkan riwayat pemakaian — halaman yang paling              lama tidak digunakan dianggap paling kecil kemungkinan dipakai kembali. Dengan begitu, halaman yang masih sering             diakses tetap dipertahankan di memori, sehingga jumlah page fault biasanya lebih sedikit dibanding FIFO yang hanya           mengikuti urutan kedatangan halaman tanpa melihat pola akses.
   
---

## Refleksi Diri
Tuliskan secara singkat:
- Apa bagian yang paling menantang minggu ini?  
- Bagaimana cara Anda mengatasinya?  

---

**Credit:**  
_Template laporan praktikum Sistem Operasi (SO-202501) – Universitas Putra Bangsa_
