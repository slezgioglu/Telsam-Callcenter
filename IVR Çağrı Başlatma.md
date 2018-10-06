IVR Aratma

*Veriyi gönderme işlemi;
veriyi bir url get olarak bekleyeceğiz.
örn;

https://ipadresi:9999/cgibin/autocalls.cgi?action=call&number=&mr=&rt=&dp=&dest=&detail=&datetime=&username=&pas
sword=

Açıklama;

number= aranacak numara başında 90 olmalı 

mr= kaç adet deneme yapacağı

rt= başarısız çağrıların ardından beklenecek süre saniye cinsinden

dp= arama planı

dest= senaryo numarası

detail= senaryonun detay bilgileri (isim,sayitek,sayitam,lira,tarih)

datetime= arama zamanı cinsi yyMMddHmm olmalı, -1 zaman yok hemen ara

username=&password= doğrulama bilgileri

Örnekte decode edilmiş detay bilgisi;

#mst#|isim{Mesut ALTÜRK}|;|sayitek{1234}|;|lira{87.06}|#mst#

Örnekte encode edilmiş detay bilgisi;

%23mst%23%7Cisim%7BMesut%20ALT%C3%9CRK%7D%7C%3B%7Csayitek%7B1234%7D%7C%3B%7
Clira%7B87.06%7D%7C%23mst%23

Örnek get adresi;

https://ipadresi:9999/cgibin/autocalls.cgi?action=call&number=903123320404&mr=2&rt=10&dp=1&dest=1&detail=&datetim
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
