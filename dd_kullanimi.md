DD Kullanımı
============

# DD klonunu mount etme

fdisk -u -l sda.img

Hangi partitionu mount etmek istiyorsak onun sektor start degerini 512 ile carpariz 

512 x 6096 = 3121152

mount -o loop,offset=3121152 -t auto /root/sda.img /mnt/sda

# Disk klonlama

dd if=/dev/sda of=sda.img

# Klonu alınmış diski başka diske açma

dd if=sda.img of=/dev/sdb

# Klonu ağ üzerinden gönderme

dd if=/dev/sda | ssh root@ip "(cat > sda.img)"


# Dvd veya CD 'den Iso dosyası oluşturma

dd if=/dev/dvd of=dvd.iso

# Iso dosyasını cd veya dvd 'ye yazdırma

dd if=dvd.iso of=/dev/cdrom obs=32k seek=0

# Badblock olan dosyayı kurtarma

dd if=test.avi of=test_yeni.avi conv=noerror








