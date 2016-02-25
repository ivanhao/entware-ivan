# Entware-ivan
It's a entware which include lighttpd,php5,php5-cgi,php5-cli,samba,dlna and also include XunLei Xware.It's support Owncloud,you can download owncloud to /opt/share/www.

##Installation note:
The entware will run in path:`/opt`,you can make directory `/opt` or make soft link from your Hard Driver.etc:
```
ln -s /mnt/sda1/opt /opt
```
Then clone the tar archieve to your disk and uncompress tar archieve to location:`/opt`.

*Test
```
/opt/bin/opkg list-installed
```

##Lighttpd config:
lighttpd's default port is 9001,you can config it by follow method:
```
vi /opt
```
