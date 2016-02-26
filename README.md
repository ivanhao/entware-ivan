# Entware-ivan
It's a entware which include lighttpd,php5,php5-cgi,php5-cli,samba,minidlna and also include XunLei Xware.It's support Owncloud,you can download owncloud to `/opt/share/www`.

It's tested in `armv7` device such as some Openwrt device,Raspberry Pi 2,Banana Pi M1+.

##Installation note:
The entware will run in path:`/opt`,you can make directory `/opt` or make soft link from your Hard Driver:
```
ln -s /mnt/sda1/opt /opt
```
Then clone the tar archive to your disk and uncompress tar archive to location:`/opt`.

* Test

```
/opt/bin/opkg list-installed
```

##Owncloud:
It's support [owncloud](https://owncloud.org/install/#instructions-server)8.2.2(latest version) which is tested by me.You can test other version youself.
you can download owncloud to `/opt/share/www`.

##Lighttpd config:
lighttpd's default port is 9001,you can config it by the following method:
```
vi /opt/etc/lighttpd/lighttpd.conf
```
change the `server.port   9001` to other port number you want.

* Start lighttpd: 

```php
/opt/sbin/lighttpd -f /opt/etc/lighttpd/lighttpd.conf
```
you can add this to `/etc/rc.local` to make it auto start after boot.

##Xware:
Xware is a software for [Xunlei](http://luyou.xunlei.com/thread-12545-1-1.html) downloader,you can run it like this:
```
/opt/xware/portal
```



