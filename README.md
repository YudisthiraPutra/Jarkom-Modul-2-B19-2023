# Jarkom-Modul-2-B19-2023

Anggota Kelompok
1. Mohammad Ahnaf Fauzan 5025211170 <br>
2. Al-Ferro Yudisthira Putra 5025211176<br>

# LAPORAN RESMI

## Nomor 1
### Soal
Yudhistira akan digunakan sebagai DNS Master, Werkudara sebagai DNS Slave, Arjuna merupakan Load Balancer yang terdiri dari beberapa Web Server yaitu Prabakusuma, Abimanyu, dan Wisanggeni. Buatlah topologi dengan pembagian sebagai berikut. Folder topologi dapat diakses pada drive berikut 
### Hasil
### Konfigurasi
## Nomor 2
### Soal
Buatlah website utama pada node arjuna dengan akses ke arjuna.yyy.com dengan alias www.arjuna.yyy.com dengan yyy merupakan kode kelompok.
### Hasil
### Konfigurasi
## Nomor 3
### Soal
Dengan cara yang sama seperti soal nomor 2, buatlah website utama dengan akses ke abimanyu.yyy.com dan alias www.abimanyu.yyy.com.
### Hasil
### Konfigurasi
## Nomor 4
### Soal
Kemudian, karena terdapat beberapa web yang harus di-deploy, buatlah subdomain parikesit.abimanyu.yyy.com yang diatur DNS-nya di Yudhistira dan mengarah ke Abimanyu.
### Hasil
### Konfigurasi
## Nomor 5
### Soal
Buat juga reverse domain untuk domain utama. (Abimanyu saja yang direverse)
### Hasil
### Konfigurasi
## Nomor 6
### Soal
Agar dapat tetap dihubungi ketika DNS Server Yudhistira bermasalah, buat juga Werkudara sebagai DNS Slave untuk domain utama.
### Hasil
### Konfigurasi
## Nomor 7
### Soal
Seperti yang kita tahu karena banyak sekali informasi yang harus diterima, buatlah subdomain khusus untuk perang yaitu baratayuda.abimanyu.yyy.com dengan alias www.baratayuda.abimanyu.yyy.com yang didelegasikan dari Yudhistira ke Werkudara dengan IP menuju ke Abimanyu dalam folder Baratayuda.
### Hasil
### Konfigurasi
## Nomor 8
### Soal
Untuk informasi yang lebih spesifik mengenai Ranjapan Baratayuda, buatlah subdomain melalui Werkudara dengan akses rjp.baratayuda.abimanyu.yyy.com dengan alias www.rjp.baratayuda.abimanyu.yyy.com yang mengarah ke Abimanyu.
### Hasil
### Konfigurasi
## Nomor 9
### Soal
Arjuna merupakan suatu Load Balancer Nginx dengan tiga worker (yang juga menggunakan nginx sebagai webserver) yaitu Prabakusuma, Abimanyu, dan Wisanggeni. Lakukan deployment pada masing-masing worker.
### Hasil
### Konfigurasi
## Nomor 10
### Soal
Kemudian gunakan algoritma Round Robin untuk Load Balancer pada Arjuna. Gunakan server_name pada soal nomor 1. Untuk melakukan pengecekan akses alamat web tersebut kemudian pastikan worker yang digunakan untuk menangani permintaan akan berganti ganti secara acak. Untuk webserver di masing-masing worker wajib berjalan di port 8001-8003. Contoh <br>
    - Prabakusuma:8001 <br>
    - Abimanyu:8002 <br>
    - Wisanggeni:8003 <br>
### Hasil
### Konfigurasi
## Nomor 11
### Soal
Selain menggunakan Nginx, lakukan konfigurasi Apache Web Server pada worker Abimanyu dengan web server www.abimanyu.yyy.com. Pertama dibutuhkan web server dengan DocumentRoot pada /var/www/abimanyu.yyy
### Hasil

<img width="594" alt="Screenshot 2023-10-16 at 22 15 58" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/75ca47fe-a46d-439c-8514-3303c2715d3b">

### Konfigurasi
```
<VirtualHost *:80>
        # The ServerName directive sets the request scheme, hostname and port t$
        # the server uses to identify itself. This is used when creating
        # redirection URLs. In the context of virtual hosts, the ServerName
        # specifies what hostname must appear in the request's Host: header to
        # match this virtual host. For the default virtual host (this file) this
        # value is not decisive as it is used as a last resort host regardless.
        # However, you must set it for any further virtual host explicitly.
        #ServerName www.example.com

        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/abimanyu.b19
        ServerName abimanyu.b19.com
        ServerAlias www.abimanyu.b19.com

        # Available loglevels: trace8, ..., trace1, debug, info, notice, warn,
        # error, crit, alert, emerg.
        # It is also possible to configure the loglevel for particular
        # modules, e.g.
        #LogLevel info ssl:warn

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        # For most configuration files from conf-available/, which are
        # enabled or disabled at a global level, it is possible to
        # include a line for only one particular virtual host. For example the
        # following line enables the CGI configuration for this host only
        # after it has been globally disabled with "a2disconf".
        #Include conf-available/serve-cgi-bin.conf
</VirtualHost>
```
## Nomor 12
### Soal
Setelah itu ubahlah agar url www.abimanyu.yyy.com/index.php/home menjadi www.abimanyu.yyy.com/home.
### Hasil

<img width="578" alt="Screenshot 2023-10-16 at 22 29 56" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/5b58ed9a-736a-4b22-add2-e2dcc1cb3dc1">
<br>
<img width="313" alt="Screenshot 2023-10-16 at 22 30 19" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/f9922e89-43dc-4530-b6a5-25ead6350370">


### Konfigurasi

```
<VirtualHost *:80>
        # The ServerName directive sets the request scheme, hostname and port t$
        # the server uses to identify itself. This is used when creating
        # redirection URLs. In the context of virtual hosts, the ServerName
        # specifies what hostname must appear in the request's Host: header to
        # match this virtual host. For the default virtual host (this file) this
        # value is not decisive as it is used as a last resort host regardless.
        # However, you must set it for any further virtual host explicitly.
        #ServerName www.example.com

        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/abimanyu.b19
        ServerName abimanyu.b19.com
        ServerAlias www.abimanyu.b19.com

        Alias "/home" "/var/www/abimanyu.b19/index.php"

        # Available loglevels: trace8, ..., trace1, debug, info, notice, warn,
        # error, crit, alert, emerg.
        # It is also possible to configure the loglevel for particular
        # modules, e.g.
        #LogLevel info ssl:warn

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        # For most configuration files from conf-available/, which are
        # enabled or disabled at a global level, it is possible to
        # include a line for only one particular virtual host. For example the
        # following line enables the CGI configuration for this host only
        # after it has been globally disabled with "a2disconf".
        #Include conf-available/serve-cgi-bin.conf
</VirtualHost>
```
## Nomor 13
### Soal
Selain itu, pada subdomain www.parikesit.abimanyu.yyy.com, DocumentRoot disimpan pada /var/www/parikesit.abimanyu.yyy
### Hasil

<img width="576" alt="Screenshot 2023-10-16 at 22 33 15" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/1dc2027d-ec82-44b3-8137-48738902e235">

### Konfigurasi

```
<VirtualHost *:80>
   DocumentRoot /var/www/parikesit.abimanyu.b19
   ServerName parikesit.abimanyu.b19.com
   ServerAlias www.parikesit.abimanyu.b19.com
</VirtualHost>
```
## Nomor 14
### Soal
Pada subdomain tersebut folder /public hanya dapat melakukan directory listing sedangkan pada folder /secret tidak dapat diakses (403 Forbidden).
### Hasil
#### /public

<img width="736" alt="Screenshot 2023-10-16 at 22 36 21" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/41b1eeaa-1fb0-4c80-9819-731fce909d46">

#### /secret

<img width="755" alt="Screenshot 2023-10-16 at 22 36 55" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/b8721917-6e6c-4696-bc83-ba8db51d03db">

### Konfigurasi
```
<VirtualHost *:80>
   DocumentRoot /var/www/parikesit.abimanyu.b19
   ServerName parikesit.abimanyu.b19.com
   ServerAlias www.parikesit.abimanyu.b19.com

        <Directory /var/www/parikesit.abimanyu.b19/public>
                Options +Indexes
         </Directory>
         <Directory /var/www/parikesit.abimanyu.b19/secret>
                Require all denied
         </Directory>
</VirtualHost>
```
## Nomor 15
### Soal
Buatlah kustomisasi halaman error pada folder /error untuk mengganti error kode pada Apache. Error kode yang perlu diganti adalah 404 Not Found dan 403 Forbidden.
### Hasil

<img width="737" alt="Screenshot 2023-10-16 at 22 38 38" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/b3067427-7d80-40b9-a466-b82a12e0fa62">

### Konfigurasi

```
<VirtualHost *:80>
   DocumentRoot /var/www/parikesit.abimanyu.b19
   ServerName parikesit.abimanyu.b19.com
   ServerAlias www.parikesit.abimanyu.b19.com

        <Directory /var/www/parikesit.abimanyu.b19/public>
                Options +Indexes
         </Directory>
         <Directory /var/www/parikesit.abimanyu.b19/secret>
                Require all denied
         </Directory>

    ErrorDocument 404 /error/404.html
    ErrorDocument 403 /error/403.html
</VirtualHost>
```
## Nomor 16
### Soal
Buatlah suatu konfigurasi virtual host agar file asset www.parikesit.abimanyu.yyy.com/public/js menjadi 
www.parikesit.abimanyu.yyy.com/js 
### Hasil

<img width="737" alt="Screenshot 2023-10-16 at 22 39 24" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/06b8320e-2267-409b-8928-6d648b2b6704">

### Konfigurasi
```
<VirtualHost *:80>
   DocumentRoot /var/www/parikesit.abimanyu.b19
   ServerName parikesit.abimanyu.b19.com
   ServerAlias www.parikesit.abimanyu.b19.com

        <Directory /var/www/parikesit.abimanyu.b19/public>
                Options +Indexes
         </Directory>
         <Directory /var/www/parikesit.abimanyu.b19/secret>
                Require all denied
         </Directory>

    Alias "/js" "/var/www/parikesit.abimanyu.b19/public/js"
    ErrorDocument 404 /error/404.html
    ErrorDocument 403 /error/403.html
</VirtualHost>
```
## Nomor 17
### Soal
Agar aman, buatlah konfigurasi agar www.rjp.baratayuda.abimanyu.yyy.com hanya dapat diakses melalui port 14000 dan 14400.
### Hasil

<img width="735" alt="Screenshot 2023-10-16 at 22 42 58" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/dd4f4877-3e58-47c5-87ec-1df834c114db">

### Konfigurasi

```
<VirtualHost *:14000 *:14400>
   DocumentRoot /var/www/rjp.baratayuda.abimanyu.b19
   ServerName rjp.baratayuda.abimanyu.b19.com
   ServerAlias www.rjp.baratayuda.abimanyu.b19.com
        <Directory /var/www/rjp.baratayuda.abimanyu.b19>
        AllowOverride All
    </Directory>
</VirtualHost>
```

## Nomor 18
### Soal
Untuk mengaksesnya buatlah autentikasi username berupa “Wayang” dan password “baratayudayyy” dengan yyy merupakan kode kelompok. Letakkan DocumentRoot pada /var/www/rjp.baratayuda.abimanyu.yyy.
### Hasil

<img width="732" alt="Screenshot 2023-10-16 at 22 49 57" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/05598c97-fc42-446d-9c4f-090c2eb76743">

### Konfigurasi
#### setup .htaccess
```
AuthType Basic
AuthName "Restricted Area"
AuthUserFile /etc/apache2/.htpasswd
Require valid-user
```
#### setup .htpasswd
```
Wayang:$apr1$vwbkex0Q$6gUtw4ezJDaz28Sv5YMkB1
```
## Nomor 19
### Soal
Buatlah agar setiap kali mengakses IP dari Abimanyu akan secara otomatis dialihkan ke www.abimanyu.yyy.com (alias)
### Hasil

<img width="734" alt="Screenshot 2023-10-16 at 22 53 03" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/078c2e5f-f200-4af6-9e02-b339168c5a8d">

### Konfigurasi
## Nomor 20
### Soal
Karena website www.parikesit.abimanyu.yyy.com semakin banyak pengunjung dan banyak gambar gambar random, maka ubahlah request gambar yang memiliki substring “abimanyu” akan diarahkan menuju abimanyu.png.
### Hasil

<img width="566" alt="Screenshot 2023-10-16 at 22 58 58" src="https://github.com/YudisthiraPutra/Jarkom-Modul-2-B19-2023/assets/114007340/e445d611-1dd2-4f35-9ceb-17b4deb7d6b5">

### Konfigurasi
```
<VirtualHost *:80>
   DocumentRoot /var/www/parikesit.abimanyu.b19
   ServerName parikesit.abimanyu.b19.com
   ServerAlias www.parikesit.abimanyu.b19.com

        <Directory /var/www/parikesit.abimanyu.b19/public>
                Options +Indexes
         </Directory>
         <Directory /var/www/parikesit.abimanyu.b19/secret>
                Require all denied
         </Directory>

    Alias "/js" "/var/www/parikesit.abimanyu.b19/public/js"
    ErrorDocument 404 /error/404.html
    ErrorDocument 403 /error/403.html

        RewriteEngine On
        RewriteCond %{REQUEST_URI} abimanyu
        RewriteRule ^.abimanyu.\.(jpg|jpeg|png|gif)$ /public/images/abimanyu.$
</VirtualHost>
```



