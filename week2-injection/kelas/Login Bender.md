# Login Bender

Link: https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false

1. Masuk ke halaman login

![alt text](<img/Screenshot 2025-09-10 024310.png>)

2. Email Bender dapat ditemukan pada bagian product review

![alt text](<img/Screenshot 2025-09-10 024043.png>)

3. Memasukkan email Bender pada kolom username dan diikuti dengan manipulasi SQL Injection. Untuk kolom password dapat diisi bebas.

![alt text](<img/Screenshot 2025-09-10 024215.png>)

Penambahan `--` pada `bender@juice-sh.op'--` berfungsi sebagai komentar dalam SQL sehingga seluruh kode setelah tanda tersebut diabaikan oleh database. Dengan cara ini, penyerang bisa menutup string `'` lalu menonaktifkan bagian query berikutnya seperti password check. Hasilnya, query jadi tidak lengkap sesuai logika normal aplikasi, tetapi tetap dieksekusi sehingga autentikasi bisa dilewati.

4. Berhasil masuk sebagai Bender