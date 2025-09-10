# NoSQL Manipulation

Link: https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false 

![alt text](<img/Screenshot 2025-09-10 221703.png>)

1. Di sini saya login sebagai Jim

![alt text](<img/Screenshot 2025-09-10 222550.png>)

2. Buka pada product review. Kemudian saya mencoba menulis 1 review. Sebelum send review, perlu dilakukan intercept burpsuite.

![alt text](<img/Screenshot 2025-09-10 222717.png>)

3. Mencari request **PUT** pada packet yang berisi review kemudian send to repeater.

![alt text](<img/Screenshot 2025-09-10 222734.png>)

4. Mengubah request **PUT** menjadi **PATCH**. Kemudian mengubah review menjadi input berikut.
Request untuk memperbarui ulasan perlu menggunakan PATCH. Saya menggunakan ID dan akan diatur agar tidak sama dengan -1 yang membuat pembaruan semua ulasan dengan pesan yang sama.

![alt text](<img/Screenshot 2025-09-10 223332.png>)

![alt text](<img/Screenshot 2025-09-10 223000.png>)

![alt text](<img/Screenshot 2025-09-10 223336.png>)

Selanjutnya send packet.

5. Terlihat bahwa banyak review yang diupdate secara bersamaan. Soal berhasil diselesaikan

![alt text](<img/Screenshot 2025-09-10 223412.png>)

![alt text](<img/Screenshot 2025-09-10 223421.png>)

![alt text](<img/Screenshot 2025-09-10 223442.png>)