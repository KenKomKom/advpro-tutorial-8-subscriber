# advpro-tutorial-8-subscriber


7.Try to answer the following questions, and write the answer in the and new file readme.md in 
you repository.

a. what is amqp?

Amqp adalah singkatan untuk Advanced Message Queuing Protocol. Dimana artinya aplikasi-aplikasi client dibuat untuk bisa berkomunikasi dengan aplikasi sumber yang mengirimkan informasi/data. Data ini akan dikirimkan menggunakan messaging middleware dimana client akan mendapatkan data yang mereka perlukan dari middleware ini.

Pada link amqp://guest:guest@localhost:567. amqp merupakan protocol yang digunakan untuk melakukan transaksi data.

b. guest:guest merupakan username dan juga password yang digunakan untuk agar terautentikasi oleh server. Untuk 'localhost:5672', localhost merujuk terhadap hostname dari server dimana host nya sekarang adalah perangkat kita sendiri dan untuk 5672 merupakan port yang digunakan untuk AMQP.
############################################
![alt text](image-3.png)
Pada gambar diatas dapat dilihat kalau pada suatu saat sempat terdapat 15 message pada queue. Ini terjadi akibat subscribernya perlu waktu lebih lama untuk mengelola tiap event yang berada di message queue sehingga terjadi penumpukkan message karena lebih cepat publisher meng-publish message daripada subscriber membuat message.
###########################################
![alt text](image.png)
![alt text](image-4.png)
Pada image tersebut dapat dilihat kalau pada tiap subscriber mendapatkan data yang berbeda-beda saat publisher mengirimkan banyak data ke message queue. Ini karena tiap subscriber berfungsi seperti aplikasi nya masing-masing sehingga terpisah saat mengambil data dari message queue. Ketika data sudah terambil dari message queue, maka message akan hilang dan aplikasi lain tidak bisa menggunakannya.

Selain itu, menurut saya, cara untuk meningkatkan performa dari aplikasi subscriber adalah dengan membuatnya menjadi multithreading sehingga bisa mengolah banyak event dari publisher sekaligus.