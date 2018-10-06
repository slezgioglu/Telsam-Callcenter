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
