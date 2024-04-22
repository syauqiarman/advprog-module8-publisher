**Syauqi Armanaya Syaki**<br/>
**2206829010**<br/>
**Pemrograman Lanjut C**<br/>

a. How many data your publisher program will send to the message broker in one run?

Pada program publisher ini terdapat lima pesan ke message broker dalam sekali dijalankan karena terdapat lima fungsi call `publish_event` yang mengirim pesan berupa `UserCreatedEventMessage`. Isi dari pesan tersebut adalah `user_id` dan `user_name` yang berbeda di tiap fungsi call nya. Adapun isi pesan yang dikirimkan adalah sebagai berikut:
1. user_id: "1", user_name: "2206829010-Amir" 
2. user_id: "2", user_name: "2206829010-Budi" 
3. user_id: "3", user_name: "2206829010-Cica" 
4. user_id: "4", user_name: "2206829010-Dira" 
5. user_id: "5", user_name: "2206829010-Emir" 

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?

Maksud dari URL tersebut adalah sebagai alamat dari message broker yang digunakan. URL yang sama antara program publisher dan subscriber karena kedua program di konfigurasi untuk saling terhubung dan berkomunikasi lewat message broker yang sama, yaitu RabbitMQ. Jadi saat publisher mengirim pesan ke queue di RabbitMQ, subscriber akan mengatur listener untuk menerima dan memproses pesan dari queue tadi.

Bukti running RabbitMQ:
![alt text](image.png)

Bukti console screen dan RabbitMQ:
![alt text](image-1.png)

Setelah melakukan run di subscriber dan publisher, maka data dari publisher akan dikirim ke message queue yang ada, setelah itu subscriber akan menerima data dari message queue tersebut dan ditampilkan seperti bukti diatas.

Bukti browser capture untuk monitoring chart berdasarkan publisher:
![alt text](image-2.png)

Berdasarkan bukti yang terlampir diatas, terdapat peningkatan message rates di waktu tertentu yang dilihat dari spikenya. Peningkatan message rates tersebut dapat terjadi karena ketika melakukan run yang berulang pada publisher yang berupa pengiriman message, maka message rates di RabbitMQ akan meningkat berdasarkan message queue nya.