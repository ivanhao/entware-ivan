# Entware-ivan

>It's a entware which include lighttpd,php5,php5-cgi,php5-cli,samba,minidlna and also include XunLei Xware.It's support Owncloud.

>It's tested in `armv7` device such as some Openwrt device,Raspberry Pi 2,Banana Pi M1+.

##Installation note:
The entware will run in path:`/opt`,you can make directory `/opt` or make soft link from your Hard Driver.For example:
```
ln -s /mnt/sda1/opt /opt
```
Then clone the tar archive to your disk and uncompress tar archive to location:`/opt`.

* Test

```
/opt/bin/opkg list-installed
```
If nothing goes wrong,it will show the installed packages list.

##Lighttpd config:
#### Default port and default document-root:

lighttpd's default port is 9001,default document-root is `/opt/share/www` you can config it by the following method:
```
vi /opt/etc/lighttpd/lighttpd.conf
```
change the `server.port   = 9001` to other port number you want.

change the `server.document-root  = "/opt/share/www"` to other path you want.

#### Start lighttpd: 

```php
/opt/sbin/lighttpd -f /opt/etc/lighttpd/lighttpd.conf
```
you can add this to `/etc/rc.local` to make it auto start after boot.

##Owncloud:
It's support [owncloud](https://owncloud.org/install/#instructions-server)8.2.2(latest version) which is tested by me.You can test other version youself.

you can download owncloud to `document-root` then start lighttpd.

##Xware:
Xware is a software for [Xunlei](http://luyou.xunlei.com/thread-12545-1-1.html) downloader,you can run it like this:
```
/opt/xware/portal
```
##Samba:
The samba config file in `/opt/etc/samba/smb.conf`

your can change `path = /opt/share/www` to other path you want.

* config samba password

`smbpasswd -a root` |input your password twice.

`/opt/sbin/samba/smbpasswd -a root` |if it's not working up,input this.

`/opt/etc/init.d/samba start` |start samba server. you can add this to `/etc/rc.local` to make it auto start after boot.

##minidlna:
The default minidlna config file in `/opt/etc/minidlna.conf`

change configs below:
```
port=8200
media_dir=/opt/media
db_dir=/opt/var/minidlna
log_dir=/opt/var/minidlna
```
your can change the `media_dir` to the multi-media path.if you want to restrict a media_dir to specific content types, you can prepend the types, followed by a comma, to the directory:
```
+ "A" for audio  (eg. media_dir=A,/home/jmaggard/Music)
+ "V" for video  (eg. media_dir=V,/home/jmaggard/Videos)
+ "P" for images (eg. media_dir=P,/home/jmaggard/Pictures)
+ "PV" for pictures and video (eg. media_dir=PV,/home/jmaggard/digital_camera)
```

* start minidlna:

```
service minidlna start
```
