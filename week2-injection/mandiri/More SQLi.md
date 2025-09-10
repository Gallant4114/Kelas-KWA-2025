# More SQLi

Link: https://play.picoctf.org/practice?page=1&search=More%20SQLi

1. Langkah pertama adalah memasukkan command SQL Injection pada kolom username dan password. Di sini saya menggunakan username bebas dan input password menggunakan `'or 1=1;--`. Input ini bekerja karena menutup string password dengan `'`, lalu menambahkan kondisi `OR 1=1` yang selalu benar. Tanda `--` membuat sisa query diabaikan sebagai komentar. Akibatnya, pengecekan password dilewati dan query tetap mengembalikan hasil valid.


![alt text](<img/Screenshot 2025-09-10 192314.png>)

![alt text](<img/Screenshot 2025-09-10 192347.png>)

2. Di sini akan muncul beberapa data. Kemudian memasukkan input `Algiers' union select sql,1,1 from sqlite_master;--`. Input bekerja dengan cara menutup string input `"Algiers'"` lalu menambahkan query baru menggunakan **UNION SELECT**. Bagian `union select sql,1,1 from sqlite_master` memaksa database menggabungkan hasil pencarian dengan metadata dari tabel sistem `sqlite_master`, sehingga skema dan definisi tabel ikut keluar. Tanda `--` di akhir berfungsi untuk mengabaikan sisa query asli agar tidak menimbulkan error.

![alt text](<img/Screenshot 2025-09-10 192359.png>)

![alt text](<img/Screenshot 2025-09-10 193002.png>)

3. Ditemukan tabel bernama `more_table`. Lalu mencoba input `Algiers' union select flag,id,1 from more_table;--`. Payload ini bekerja dengan cara menutup input string setelah kata **Algiers'**, lalu menambahkan query baru menggunakan **UNION SELECT**. Query tambahan ini memaksa database menggabungkan hasil asli dengan data dari tabel **more\_table**, tepatnya kolom **flag** dan **id**. Tanda `--` di akhir digunakan untuk mengomentari sisa query sehingga hanya bagian injeksi yang dieksekusi, memungkinkan isi tabel (termasuk nilai flag) agar ditampilkan.


![alt text](<img/Screenshot 2025-09-10 192656.png>)

![alt text](<img/Screenshot 2025-09-10 193112.png>)

4. Flag telah ditemukan

![alt text](<img/Screenshot 2025-09-10 192723.png>)

flag: `picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_c8ee9477}`