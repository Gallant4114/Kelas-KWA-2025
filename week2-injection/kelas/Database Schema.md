# Database Schema

Link: https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false

![alt text](<img/Screenshot 2025-09-10 060223.png>)

1. Pada soal ini saya menggunakan burpsuite. Masuk ke bagian proxy burpsuite, open browser, dan mengakses challenge.

![alt text](<img/Screenshot 2025-09-10 090251.png>)

![alt text](<img/Screenshot 2025-09-10 090336.png>)

2. Lalu masuk ke bagian kolom search product dan mengaktifkan intercept pada burpsuite.

![alt text](<img/Screenshot 2025-09-10 090111.png>)

![alt text](<img/Screenshot 2025-09-10 090425.png>)

3. Memasukkan input pada kolom search, misalnya apple. Selain itu juga bisa dengan refresh halaman

![alt text](<img/Screenshot 2025-09-10 090126.png>)

4. Mencari request GET search product yang ada pada burpsuite.

![alt text](<img/Screenshot 2025-09-10 083804.png>)

5. Send to repeater

![alt text](<img/Screenshot 2025-09-10 083824.png>)

6. Ubah payload dan send. Di sini saya mencoba melihat response yang dihasilkan.

![alt text](<img/Screenshot 2025-09-10 083926.png>)

7. Memasukkan payload berikut kemudian send

```bash
'))UNION%20SELECT%20sql,2,3,4,5,6,7,8,9%20FROM%20sqlite_master--
```

Payload bekerja karena memanfaatkan **SQL Injection dengan UNION** untuk menggabungkan hasil query normal dengan query buatan penyerang. Bagian `UNION SELECT sql,2,3,4,5,6,7,8,9%20FROM%20sqlite_master` memaksa database mengembalikan isi kolom `sql` dari tabel sistem `sqlite_master`, yang berisi definisi struktur tabel dan query pembuatan database. Dengan begitu, penyerang bisa membocorkan skema database, termasuk nama tabel maupun kolom sensitif yang ada di dalamnya.

![alt text](<img/Screenshot 2025-09-10 084635.png>)

![alt text](<img/Screenshot 2025-09-10 084649.png>)

8. Soal berhasil diselesaikan

![alt text](<img/Screenshot 2025-09-10 084946.png>)