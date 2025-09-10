# SQL Direct

Link: https://play.picoctf.org/practice?page=1&search=SQL%20Direct

1. Masuk ke webshell dan menjalankan command `psql -h saturn.picoctf.net -p 59676 -U postgres pico` dan password `postgres`

![alt text](<img/Screenshot 2025-09-10 231019.png>)

2. Menjalankan command `\dt` untuk show table yang tersedia

![alt text](<img/Screenshot 2025-09-10 231153.png>)

3. Menjalankan command `select * from flags;` untuk mengetahui isi tabel

![alt text](<img/Screenshot 2025-09-10 231230.png>)

flag: `picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}`