# otus_training

07. Systemd

1. Watchlog

Move the following files to dirs:
/usr/lib/systemd/system/watchlog.timer 
/usr/lib/systemd/system/watchlog.service
/usr/lib/systemd/system/watchlog.timer 
/usr/lib/systemd/system/watchlog.service

Run systemctl start watchlog.timer 


2. Spawn

Move the following files to dirs:
/usr/lib/systemd/system/spawn-fcgi.service
/etc/sysconfig/spawn-fcgi

Run systemctl start spawn-fcgi.service


3. Apache
Move the following files to dirs:
/usr/lib/systemd/system/httpd@.service
/etc/sysconfig/httpd-first
/etc/sysconfig/httpd-second
/etc/httpd/conf/first.conf
/etc/httpd/conf/second.conf

Run:
systemctl start httpd@first
systemctl start httpd@second


 
[root@bash vagrant]# ss -tnulp | grep httpd
tcp    LISTEN     0      128    [::]:8080               [::]:*                   users:(("httpd",pid=3390,fd=4),("httpd",pid=3389,fd=4),("httpd",pid=3388,fd=4),("httpd",pid=3387,fd=4),("httpd",pid=3386,fd=4),("httpd",pid=3385,fd=4),("httpd",pid=3384,fd=4))
tcp    LISTEN     0      128    [::]:80                 [::]:*                   users:(("httpd",pid=3376,fd=4),("httpd",pid=3375,fd=4),("httpd",pid=3374,fd=4),("httpd",pid=3373,fd=4),("httpd",pid=3372,fd=4),("httpd",pid=3371,fd=4),("httpd",pid=3370,fd=4))


 


