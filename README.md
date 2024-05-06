# tutorial10broadcast

1. Try to run one server, and three clients. Try to type something in each client. Capture your
   screen. Put it in your Readme.md. Put some explanation. How to run it, and what happens when
   you type some text in the clients.

<img src="images/Screenshot (453).png">
<img src="images/Screenshot (452).png">
<img src="images/Screenshot (451).png">
<img src="images/Screenshot (450).png">

Projek kali ini menyimulasikan sebuah broadcast channel di mana client dapat mengirimkan sebuah pesan, yang akan ditampilkan
di channel sehingga semua client bisa melihatnya juga. Kita bisa melihat contohnya di foto ketiga, di mana saat client ketiga mengirim tes3, 
maka client pertama dan kedua melihatnya juga. Hal ini bisa terjadi karena server.rs memiliki fungsi yang membuat broadcast channel
untuk terus menerus listen untuk pesan dari klien, yang dilakukan dengan melakukan loop secara concurrent sehingga ia bisa mendengar
dari semua client, tidak hanya satu.

2. Put your explanation in the Readme.md

<img src="images/Screenshot (454).png">
<img src="images/Screenshot (455).png">
<img src="images/Screenshot (456).png">
<img src="images/Screenshot (457).png">

Selain fungsi main di client.rs, yang perlu diubah adalah fungsi main di server.rs untuk memastikan client dan server terkoneksi
di port yang sama. Karena keduanya mendengar port yang sama, maka mereka pasti terhubung koneksi yang sama. Baik client pertama,
kedua, atau ketiga semua terhubung dengan server, sehingga semua client bisa mendengar pesan dari server.

3. Make your own modification. Capture the result, put it in the Readme.md and put some
   explanation why you change it there.

   <img src="images/Screenshot (466).png">
   <img src="images/Screenshot (467).png">
   <img src="images/Screenshot (468).png">

Saya membuat perubahan di server.rs di mana saya menginsert socket address client yang terkoneksi di hadnle_connection agar muncul
di pesan welcome. Selain itu saya membuat global variable client address untuk menyimpan address dari client yang mengirim suatu pesan
sehingga ketika di broadcast di channel maka address tersebut akan ditampilkan bersama message mereka. Client address ini berubah setiap
menerima message.