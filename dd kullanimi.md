dd kullanimi
============

# Dvd veya CD 'den Iso dosyasi olusturma

dd if=/dev/dvd of=dvd.iso

# Iso dosyasini cd veya dvd 'ye yazdirma

dd if=dvd.iso of=/dev/cdrom obs=32k seek=0

#Badblock olan dosyayi kurtarma

dd if=movie.avi of=rescued_movie.avi conv=noerror

# Disk klonlama

dd if=/dev/sda of=sda.img

#Klonlu diski acma

dd if=sda.img of=/dev/sdb

#Klonu transfer etme

dd if=/dev/sdb | ssh root@target "(cat > backup.img)"

#DD kolunu mount etme

fdisk -u -l sda.img

Hangi partitionu mount etmek istiyorsak onun sektor start degerini 512 ile carpariz 

512 x 6096 = 3121152

mount -o loop,offset=3121152 -t auto /root/sda.img /mnt/sda




