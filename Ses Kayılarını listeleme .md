Ses Kayıtlarını Listeleme ve Alma

Dosya adları tarih,saat,arayan,aranan,süre gibi bilgileri içermektedir.
*Aşağıdaki api ile ses kayıt klasörleri gelmektedir.

https://ipadresi:9999/cgibin/system_cmd.cgi?cmd=sh%20/etc/scripts/shell_scripts.sh%20list_files%20/var/spool/asterisk/mo
nitor/recording&username=&password=

Çıktı;
trunk-sip-908502591905 

https://ipadresi:9999/cgibin/system_cmd.cgi?cmd=sh%20/etc/scripts/shell_scripts.sh%20list_files%20/var/spool/asterisk/mo
nitor/recording/trunk-sip-908502591905&username=&password=
Çıktı;
20161025-161938-100-903123320404-1477401578.25-4.gsm
20161025-162048-903123320404-100-1477401638.35-15.gsm
*Aşağıdaki api ile filitreli ses kayıt listesini çekebilirsiniz.
Örneğin aşağıdaki api 903123320404 ile ilişkili kayıtları listeler.

iki yıldız arasındaki 903123320404 yerine 100-903123320404 yazarsanız 100 ün aradığı
903123320404 kayıtlarını listeler.
iki yıldız arasındaki 903123320404 yerine 903123320404-100 yazarsanız 903123320404 ün aradığı
100 kayıtlarını listeler.
iki yıldız arasındaki 903123320404 yerine 20161118- yazarsanız 18.11.2016 tarihindeki kayıtları
listeler.
iki yıldız arasındaki 903123320404 yerine 20161118-*-100-903123320404 yazarsanız 18.11.2016
tarihindeki 100 ün aradığı 903123320404 kayıtları listeler. 

