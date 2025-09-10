# Login Jim

Link: https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false

![alt text](<img/Screenshot 2025-09-10 022742.png>)

1. Langkah pertama adalah masuk ke halaman login di tab Account

![alt text](<img/Screenshot 2025-09-10 023222.png>)

2. Mencari email Jim pada product review

![alt text](<img/Screenshot 2025-09-10 023145.png>)

3. Memasukkan email Jim pada kolom username dan diikuti dengan manipulasi SQL Injection. Untuk kolom password dapat diisi bebas.

![alt text](<img/Screenshot 2025-09-10 023412.png>)

Penambahan `--` pada `jim@juice-sh.op'--` berfungsi sebagai komentar dalam SQL sehingga seluruh kode setelah tanda tersebut diabaikan oleh database. Dengan cara ini, penyerang bisa menutup string `'` lalu menonaktifkan bagian query berikutnya seperti password check. Hasilnya, query jadi tidak lengkap sesuai logika normal aplikasi, tetapi tetap dieksekusi sehingga autentikasi bisa dilewati.

4. Berhasil masuk sebagai Jim

![alt text](<img/Screenshot 2025-09-10 023619.png>)