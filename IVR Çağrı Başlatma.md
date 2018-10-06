IVR Aratma
*Veriyi gönderme işlemi;
veriyi bir url get olarak bekleyeceğiz.
örn;

https://ipadresi:9999/cgi-
bin/autocalls.cgi?action=call&number=&mr=&rt=&dp=&dest=&detail=&datetime=&username=&pas

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
