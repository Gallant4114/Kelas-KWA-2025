# User Credentials

Link: https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false 

![alt text](<img/Screenshot 2025-09-10 221655.png>)

1. Masuk ke kolom search product, misalnya mencari `apple`. Sebelum search, aktifkan intercept pada burpsuite.

![alt text](<img/Screenshot 2025-09-10 232124.png>)

![alt text](<img/Screenshot 2025-09-10 233124.png>)

2. Mencari request **GET** pada burpsuite yang berisi search product. Lalu send to repeater.

![alt text](<img/Screenshot 2025-09-10 232152.png>)

3. Menambahkan input `apple')) UNION SELECT id, email, password, '4','5','6','7','8','9' FROM USERS --`

![alt text](<img/Screenshot 2025-09-10 232738.png>)

Karena input tersebut belum berhasil memberikan output response, maka perlu dilakukan encode to URL.

![alt text](<img/Screenshot 2025-09-10 233012.png>)

4. Paste hasil encode dan ganti input tersebut

![alt text](<img/Screenshot 2025-09-10 232856.png>)

Data user credential muncul pada bagian response. Soal berhasil diselesaikan.

![alt text](<img/Screenshot 2025-09-10 232910.png>)

![alt text](<img/Screenshot 2025-09-10 232958.png>)