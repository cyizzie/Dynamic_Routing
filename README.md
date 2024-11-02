# Praktikum Jaringan - Konfigurasi Dynamic Routing dengan RIP v2

## Hasil Praktikum

### 1. Konfigurasi Router dan IP
- Setiap router (R1, R2, R3) dikonfigurasi dengan alamat IP sesuai tabel pengalamatan, dan konfigurasi disimpan di NVRAM.
- Banner dan pengaturan jaringan dibuat pada masing-masing router menggunakan **RIP versi 2** untuk memastikan dynamic routing berjalan.

### 2. Dynamic Routing dengan RIP
- **RIP v2** dikonfigurasi untuk mendukung protokol routing dinamis pada setiap router. Setiap router memiliki network yang ditetapkan, seperti 192.168.2.0 pada R1 dan 10.20.10.0 pada R3.

### 3. Pengujian Tabel Routing
- Perintah `show ip route` digunakan untuk memverifikasi bahwa konfigurasi dynamic routing berhasil. Rute bertanda "D" menandakan rute dinamis yang berhasil dikonfigurasi.

### 4. Pengujian Koneksi ICMP
- Ping diuji antara berbagai PC dalam jaringan untuk memastikan konektivitas. Hasil menunjukkan apakah koneksi berhasil atau tidak untuk kombinasi PC yang berbeda, seperti PC1 ke PC5 dan PC7 ke PC3. Koneksi yang berhasil menunjukkan bahwa routing berhasil menghubungkan jaringan yang berbeda, sedangkan kegagalan koneksi mungkin disebabkan oleh kendala teknis atau pengaturan yang perlu diperiksa kembali.


## Analisa

- **Penggunaan RIP v2**  
  Penggunaan RIP versi 2 memungkinkan setiap router berbagi informasi routing secara otomatis, sehingga setiap router dapat mengenali jaringan tetangga tanpa pengaturan rute manual. Protokol ini menggunakan hop count sebagai metrik utama untuk menentukan jalur terpendek, yang efektif untuk jaringan kecil atau menengah.

- **Evaluasi Koneksi Antar PC**  
  Sebagian besar koneksi ICMP (ping) berhasil, menunjukkan bahwa jalur antarjaringan terbentuk dengan baik melalui dynamic routing. Beberapa kegagalan koneksi dapat disebabkan oleh kesalahan konfigurasi atau keterbatasan rentang alamat IP.

- **Efektivitas RIP v2**  
  RIP v2 terbukti efektif untuk jaringan dengan ukuran terbatas namun terbatas oleh batas maksimum hop count sebesar 15. Protokol ini cocok untuk topologi sederhana, namun kurang optimal untuk jaringan yang lebih besar.


## Kesimpulan

Hasil pengujian menunjukkan bahwa **konfigurasi RIP v2** memungkinkan setiap router untuk mengenali jaringan yang terhubung ke router tetangganya dan mengisi tabel routing tanpa intervensi manual. Koneksi ICMP yang berhasil antara PC di jaringan yang berbeda menjadi bukti bahwa **RIP v2 berfungsi dengan baik untuk jaringan sederhana hingga menengah**.

Namun, keterbatasan RIP dalam mendukung jumlah hop yang terbatas menjadi perhatian penting ketika mempertimbangkan penggunaan di jaringan yang lebih luas. Oleh karena itu, meskipun RIP v2 merupakan solusi praktis untuk jaringan kecil, jaringan yang lebih besar atau kompleks sebaiknya mempertimbangkan protokol lain yang lebih efisien, seperti **OSPF** atau **EIGRP**, untuk mendukung skala dan stabilitas yang lebih baik.
