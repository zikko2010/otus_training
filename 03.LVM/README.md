# otus_training

02. RAID
ДЗ:
	mdadm --create --verbose /dev/md0 -l 5 -n 3 /dev/sd{b,c,d}
	mkdir /etc/mdadm
	echo "DEVICE partitions" > /etc/mdadm/mdadm.conf
	mdadm --detail --scan --verbose | awk '/ARRAY/ {print}' >> /etc/mdadm/mdadm.conf
	parted -s /dev/md0 mklabel gpt
	parted /dev/md0 mkpart primary ext4 0% 40%
	parted /dev/md0 mkpart primary ext4 40% 70%
	parted /dev/md0 mkpart primary ext4 70% 100%
	for i in $(seq 1 3); do sudo mkfs.ext4 /dev/md0p$i; done
	mkdir -p /raid/part{1,2,3}
	or i in $(seq 1 3); do mount /dev/md0p$i /raid/part$i; done

ДЗ* - см. Vagrantfile. По сути добавила все тоже, что выше + прописала в /etc/fstab инфу, чтобы разделы оставались примонтированными после перезагрузки.



