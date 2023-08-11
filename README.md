# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

1. DevOps (“development” and “operations”) adalah kombinasi dari filosofi budaya, praktik, dan alat yang meningkatkan kemampuan organisasi untuk meningkatkan kemampuan organisasi untuk mengirimkan aplikasi dan layanan lebih cepat daripada proses pengembangan perangkat lunak tradisional dan proses manajemen infrastruktur.
2. Infrastruktur adalah sekumpulan fasilitas dan sistem yang melayani suatu negara, kota, atau area lain, dan mencakup layanan dan fasilitas yang diperlukan agar ekonomi, rumah tangga, dan perusahaan berfungsi.
3. Server adalah komputer atau sistem yang menyediakan sumber daya, data, layanan, atau program ke komputer lain, yang dikenal sebagai klien, melalui jaringan. Secara teori, setiap kali komputer berbagi sumber daya dengan mesin klien, mereka dianggap sebagai server.

    Istilah server dapat merujuk ke Physical Machine,  Virtual Machine, atau perangkat lunak yang menjalankan layanan server. Cara kerja server sangat bervariasi tergantung pada bagaimana server kata digunakan.  
•	Server fisik hanyalah sebuah komputer yang digunakan untuk menjalankan perangkat lunak server.  
•	Server virtual adalah representasi virtual dari server fisik. Seperti server fisik, server virtual menyertakan sistem operasi dan aplikasinya sendiri. Ini disimpan terpisah dari server virtual lain yang mungkin berjalan di server fisik.

    Contohnya;  
•	Web Servers - Internet didasarkan pada server web yang menanggapi permintaan dari klien seperti web browser  
•	API - Server yang mengimplementasikan fungsionalitas untuk perangkat lunak lain dengan menawarkan API  
•	File Server - Menyediakan akses ke file

4. High Performance: Server dengan kinerja yang tinggi dapat membantu meningkatkan kecepatan situs web dengan lebih baik

    Instant response for web development company: Perusahaan pengembang aplikasi web perlu memeriksa dan memverifikasi hasil script mereka secara real time di Internet. Pentingnya untuk memiliki server web yang kuat, responsif, dan andal yang dapat membantu Anda dalam situasi pengembangan yang kompleks.

    Flexibility and control over website: Paket hosting bersama dan VPS hanya mengizinkan sejumlah kecil perubahan pada konfigurasi perangkat lunak server. Tidak cukup hak istimewa server yang diberikan kepada pengguna sehingga mereka tidak dapat menginstal perangkat lunak baru. Sedangkan, server khusus memungkinkan pengguna untuk mengubah setiap aspek konfigurasi perangkat lunak server bersama dengan sistem operasinya. Perusahaan pengembang perangkat lunak dapat memaksimalkan potensinya dengan menggunakan server khusus.

    Security: Server dapat menyediakan lingkungan yang jauh lebih aman dan tahan resiko, anda tidak diharuskan juga membagikan sumber daya anda dengan pemilik web lain di server tertentu. Dengan demikian, anda lebih terlindung dari peretas dan pelanggaran keamanan yang ada.

5. Virtualisasi adalah proses yang memungkinkan komputer untuk berbagi sumber daya perangkat kerasnya dengan beberapa lingkungan yang terpisah secara digital. Setiap lingkungan tervirtualisasi berjalan dalam sumber daya yang dialokasikan, seperti memori, daya pemrosesan, dan penyimpanan. Ini juga mendukung layanan komputasi awan yang membantu organisasi mengelola infrastruktur dengan lebih efisien.

    Container adalah paket perangkat lunak yang berisi semua elemen yang diperlukan untuk dijalankan di lingkungan apa pun. Dengan cara ini, container memvirtualisasikan sistem operasi dan berjalan di mana saja, dari pusat data pribadi hingga cloud publik atau bahkan di laptop pribadi pengembang.

6. Container menjadi populer karena menyediakan alat yang ampuh untuk mengatasi beberapa masalah penting pengembang aplikasi, termasuk kebutuhan pengiriman yang lebih cepat, ketangkasan, portabilitas, modernisasi, dan manajemen siklus hidup.

7. Orchestration Container System secara otomatis menyediakan, menerapkan, menskalakan, dan mengelola aplikasi dalam container tanpa mengkhawatirkan infrastruktur yang mendasarinya. Pengembang dapat mengimplementasikan orchestration container di mana pun container berada, memungkinkan mereka mengotomatiskan manajemen siklus hidup container.

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

