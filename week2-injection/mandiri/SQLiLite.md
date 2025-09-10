# SQLiLite

Link: https://play.picoctf.org/practice?page=1&search=SQLiLite

1. Memasukkan input username = `admin` dan password = `password`

![alt text](<img/Screenshot 2025-09-10 225904.png>)

![alt text](<img/Screenshot 2025-09-10 230025.png>)

2. Mengganti password dengan input `' OR '1'='1`

![alt text](<img/Screenshot 2025-09-10 230402.png>)

![alt text](<img/Screenshot 2025-09-10 230300.png>)

3. Setelah berhasil login, view page source untuk menemukan flagnya

![alt text](<img/Screenshot 2025-09-10 230443.png>)

flag: `picoCTF{L00k5_l1k3_y0u_solv3d_it_ec8a64c7}`