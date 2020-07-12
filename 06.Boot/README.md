# otus_training

06. Boot


1. Войти без пароля по инструкции в файле "Практика_Загрузка_Linux" не получилось. 1 и 3 способ - не загружался. 2 способ - загружался, но требовал пароль.
Также пробовала указывать init=/sysroot/bin/sh (вместо init=/bin/sh)

Получилось войти без пароля вот по этой статье: https://www.servers.ru/knowledge/linux-administration/how-to-reset-root-password-on-centos-6-and-centos-7#setting_new_password

- Заменила ro на rw
- Добавила rd.break enforcing=0
- Удалила console=tty0 console=ttyS0, 115200n8

Нажала Ctrl x для загрузки. 

После загрузки поменяла рутовый пароль:
      chroot /sysroot
      passwd root
      touch /.autorelabel
      exit
      reboot
	  

2. Установить систему с LVM, после чего переименовать VG  - в отдельном файле typescript

3. Добавить модуль в initrd - в отдельном файле typescript2