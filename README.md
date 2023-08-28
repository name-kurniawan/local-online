## pointing subdomain ke pc modem atau device local
### Kebutuhan
* Server atau vps
* Domain aktif
* account zerotier
  
### Bagian server atau vps
* install zerotier.\
lihat situs aslinya di https://zerotier.com

* install apache2.\
`sudo apt install apache2` \
atau search di google untuk caranya.

* buat file point ip.\
`sudo nano /etc/apache2/sites-available/stb.conf` \

* pastekan config seperti berikut :\
`<VirtualHost *:80>`\
`ProxyPreserveHost On`\
`ProxyPass / http://192.168.194.4/ `\
`ProxyPassReverse / http://192.168.194.4/ `\
`ServerName stb.legends-studio.eu.org `\
`</VirtualHost>`\
save perubahan stb.conf.\

* aktifkan stb.conf dengan perintah \
`a2ensite stb.conf` \

* restart apache \
`/etc/init.d/apache2 restart` \

* Edit host di vps \
`nano /etc/hosts` \

* Tambahkan ip dan subdomain \
`192.168.194.4   stb.legends-studio.eu.org` \

#### Bagian dns seting
* add cname record
`stb.legends-studio.eu.org ` \
Tunggu sampai subdomain online kira-kira 15 - 30 menit
  
