# Monitoring Polusi Udara Kampus — System Design & Architecture 🍃

Repository ini berisi dokumen analisis dan perancangan sistem untuk proyek **Monitoring Polusi Udara Kampus**. Sistem ini dirancang untuk memantau kualitas udara di berbagai titik area kampus secara real-time. Semua diagram di sini dibuat sebagai cetak biru (*blueprint*) sebelum nanti masuk ke tahap pengembangan aplikasi (*web programming* & *database*).

---

## 📌 Status Proyek & Spesifikasi
* **Fase:** Tahap 1 — Analisis & Perancangan Sistem (*System Design*)
* **Metode:** *Object-Oriented Analysis and Design* (OOAD)
* **Tools:** StarUML

---

## 👥 Aktor & Hak Akses Sistem
Biar pengelolaan data polusi dan hak aksesnya jelas, sistem ini memisahkan peran pengguna menjadi dua aktor utama. Ini detail hak aksesnya:

| Aktor | Peran Utama | Fitur yang Bisa Diakses |
| :--- | :--- | :--- |
| **User (Civitas Akademika)** | Melihat informasi kualitas udara di area kampus. | Lihat dashboard real-time, cek riwayat indeks polusi, dan terima notifikasi peringatan. |
| **Admin (Petugas/Teknisi)** | Mengelola perangkat sensor dan konfigurasi data. | Manajemen data sensor (CRUD), pantau log data masuk, dan atur batasan parameter polusi. |

---

## 📊 Rancangan Diagram Sistem

Ini visualisasi alur bisnis dan interaksi sistem yang sudah dimodelkan pakai StarUML:

### 1. Use Case Diagram
Diagram ini memetakan fungsi utama sistem, mulai dari bagaimana sensor mengirim data, cara user melihat grafik polusi, sampai bagaimana admin mengelola perangkat monitoring di lapangan.

![Use Case Diagram](usecase-monitoring.png)

### 2. Activity Diagram
Diagram ini menggambarkan alur kerja pengguna dan sistem, termasuk proses validasi login admin serta bagaimana sistem otomatis mengirimkan peringatan kalau indeks polusi melebihi batas aman.

> 💡 **Catatan Validasi Sistem:**
> Alur penanganan error dibuat sangat detail. Jika ada kegagalan autentikasi atau kesalahan input pada panel admin, alur "No" secara visual akan langsung mengarahkan kembali ke halaman input awal demi keamanan sistem.

![Activity Diagram](activity-monitoring.png)

---

## 🛠️ Rencana Fitur Utama (Scope of Work)
Mengacu ke hasil analisis diagram, ini beberapa modul utama yang bakal diimplementasikan pas tahap coding nanti:
* **Dashboard Real-Time:** Menampilkan grafik interaktif kualitas udara (seperti parameter PM2.5, CO2, atau suhu).
* **Sistem Notifikasi/Alert:** Otomatis memberikan peringatan di halaman web jika udara berada di kategori tidak sehat.
* **Manajemen Perangkat Sensor:** Halaman khusus admin untuk memantau status aktif atau matinya sensor di titik kampus.
* **Integrasi Database:** Penyimpanan log data polusi harian untuk melihat tren kualitas udara jangka panjang.
