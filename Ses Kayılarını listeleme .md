Ses Kayıtlarını Listeleme ve Alma
Dosya adları tarih,saat,arayan,aranan,süre gibi bilgileri içermektedir.
*Aşağıdaki api ile ses kayıt klasörleri gelmektedir.

https://ipadresi:9999/cgibin/system_cmd.cgi?cmd=sh%20/etc/scripts/shell_scripts.sh%20list_files%20/var/spool/asterisk/mo
nitor/recording&username=&password=

Çıktı;
trunk-sip-908502591905
*Aşağıdaki api ile ses kayıt listesini çekebilirsiniz.

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

https://ipadresi:9999/cgibin/system_cmd.cgi?cmd=find%20/var/spool/asterisk/monitor/recording/%20-
name%20*903123320404*&username=&password=

Çıktı;
/var/spool/asterisk/monitor/recording/trunk-sip-903123320404/20161118-110332-100-
903123320404-1479456211.1297-69.wav

*Aşağıdaki api ile ses kayıt dosyasını indirebilirsiniz.

https://ipadresi:9999/cgi-bin/fileget.cgi?action=rcdownload&filename=recording/trunk-sip908502591905/20161027-163425-100-905412535962-1477575265.426-
5.gsm&username=&password=

Örnek get adresi;

https://ipadresi:9999/cgi-
bin/autocalls.cgi?action=call&number=903123320404&mr=2&rt=10&dp=1&dest=1&detail=&datetim

e=-1&username=&password=

*Veriyi alma
işem sırasında sonucu direk size get edeceğimiz bir adres vermelisiniz.
örn;
http://www.siteniz.com/santral/bilgigonder.php?sonuc=&telefon=&son=

telefon= aranan numara bilgisi başında 90 olarak gelir örneğin 903123320404
sonuc= arama sırasında oluşabilecek durumları döner.
son= aramanın sonlanıp sonlanmadığını söyler

Dönen Değerler

Arama bilgileri dönerken aşağıdaki şekilde değerler gelebilir.

1..9
ANSWER
NOANSWER
BUSY
FAILED
CANCEL
CONGESTION
CHANUNAVAIL
DONTCALL
TORTURE
INVALIDARGS

ANSWER: Call is answered. A successful dial. The caller reached the callee.
BUSY: Busy signal. The dial command reached its number but the number is busy.
NOANSWER: No answer. The dial command reached its number, the number rang for too long, then
the dial timed out.
CANCEL: Call is cancelled. The dial command reached its number but the caller hung up before the
callee picked up.
CONGESTION: Congestion. This status is usually a sign that the dialled number is not recognised.
CHANUNAVAIL: Channel unavailable. On SIP, peer may not be registered.
DONTCALL: Privacy mode, callee rejected the call
TORTURE: Privacy mode, callee chose to send caller to torture menu
INVALIDARGS: Error parsing Dial command arguments
