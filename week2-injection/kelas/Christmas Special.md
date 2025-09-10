# Christmas Special

Link: https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false

![alt text](<img/Screenshot 2025-09-10 181220.png>)

Karena produk Christmas special offer tidak tersedia di tampilan halaman, maka kita perlu mencari id product tersebut dengan melihat isi database seperti pada soal `Database Schema`. Setelah id product ditemukan, maka dapat dilakukan checkout.

1. Masuk ke halaman produk

![alt text](<img/Screenshot 2025-09-10 182413.png>)

2. Menyalakan intercept pada burpsuite kemudian klik pada produk. Nanti akan ditemukan traffic dengan request **GET** dengan endpoint `/rest/products/search`

Kemudian send to repeater

![alt text](<img/Screenshot 2025-09-10 182552.png>)

![alt text](<img/Screenshot 2025-09-10 182614.png>)

3. Untuk melihat isi database, saya memasukkan `'))--` pada search query. Ini seperti pada soal `Database Schema`. Response menunjukkan bahwa id product Christmas special offer adalah `10`

![alt text](<img/Screenshot 2025-09-10 182649.png>)

4. Mematikan intercept burpsuite. Lalu agar bisa melakukan checkout, user harus login. Di sini saya login sebagai Jim seperti pada soal `Login Jim`. Setelah itu, menyalakan kembali intercept burpsuite dan klik pada _Add to Basket_

![alt text](<img/Screenshot 2025-09-10 183338.png>)

![alt text](<img/Screenshot 2025-09-10 185101.png>)

5. Mencari request **POST** pada burpsuite yang berisi id product. Setelah menemukannya, saya mengganti id ini dengan id product christmas special offer, yaitu 10.

![alt text](<img/Screenshot 2025-09-10 183450.png>)

![alt text](<img/Screenshot 2025-09-10 183519.png>)

6. Jika sudah mengganti id, intercept dimatikan agar produk masuk ke keranjang. Kemudian dilakukan checkout dan berhasil menyelesaikan soal.

![alt text](<img/Screenshot 2025-09-10 183644.png>)

![alt text](<img/Screenshot 2025-09-10 183714.png>)