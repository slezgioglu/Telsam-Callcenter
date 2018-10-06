myTelefonSendAPI

Versiyon

JSON =  {"data":{"actions": "version"}}

Register

JSON =  {"data":{"actions": "register","parameters":[{"server":"serverTest","user": "userTest","pass": "passTest"}]}}

UnRegister

JSON =  {"data":{"actions": "unregister"}}

Ara

JSON =  {"data":{"actions": "callstart","parameters":[{"line": "1","number": "12345678901"}]}}

Cevapla

JSON =  {"data":{"actions": "answercall","parameters":[{"line": "1"}]}}

Aramayı Reddet

JSON =  {"data":{"actions": "rejectcall","parameters":[{"line": "1"}]}}

Aramayı Sonlandır

JSON =  {"data":{"actions": "hangupcall","parameters":[{"line": "1"}]}}

Aktar

JSON =  {"data":{"actions": "blindtransfercall","parameters":[{"line": "1","to": "12345678900"}]}}

Aramayı Beklet

JSON =  {"data":{"actions": "holdretrievecall","parameters":[{"line": "1"}]}}

Tuş Sesi

JSON =  {"data":{"actions": "sendtone","parameters":[{"tone": "Number"}]}}

Last Message

JSON =  {"data":{"actions": "lastmessage"}}

Register Status

JSON =  {"data":{"actions": "registerstatus"}}

KULLANIMI

myTelefonSendTransfer(dönüş,JSON)

myTelefonSendTransfer

Gözetimli Aktarma

myTelefonSendTransfer(dönüş,false);

Kör Aktarma

myTelefonSendTransfer(dönüş,true


NOT: Her saniye Last Message fonksiyonu çağırmalıdır. Eğer çağırılmazsa 10 sn. sonra sistem kendini otomatik UnRagister eder. 

