# Login Admin

Link: https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false 

![alt text](img/image.png)

1. Langkah pertama adalah masuk ke halaman login di tab Account

![alt text](<img/Screenshot 2025-09-10 021921.png>)

2. Mencoba memasukkan username ' dan password bebas

![alt text](<img/Screenshot 2025-09-10 021720.png>)

3. Terdapat text [object Object]

![alt text](<img/Screenshot 2025-09-10 022041.png>)

4. Di sini perlu melakukan manipulasi berupa input SQL Injection sebagai berikut

![alt text](<img/Screenshot 2025-09-10 022241.png>)

Input `' OR 1 = 1 -- -` bisa memicu SQL Injection karena memanipulasi query asli dengan menambahkan kondisi logika yang selalu benar. Bagian `OR 1=1` membuat sistem mengabaikan validasi username yang diminta, sementara `-- -` berfungsi sebagai komentar untuk mengabaikan sisa query. Akibatnya, database akan mengembalikan data tanpa benar-benar memverifikasi kredensial, sehingga penyerang bisa melewati autentikasi.

5. Berhasil login sebagai Admin

![alt text](<img/Screenshot 2025-09-10 022550.png>)