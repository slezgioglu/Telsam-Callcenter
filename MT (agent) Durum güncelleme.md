DURUM GETİRME

cm.telsam.com.tr/?supervisor=domain.com.tr&password=pass&action=getstatus&phone=100

Supervisor: Domain adresiniz
Password: Supervisor şifreniz
Action: getstatus durum getirir
Phone: Durumu getirilecek agentin telefon numarası

Çıktısı:
{"100":[{"nickname":"Agent Name","statusid":"1","status":"Hazır"}]}

DURUM DEĞİŞTİRME

cm.telsam.com.tr/?supervisor=telsam.com.tr&password=123&action=sendstatus&phone=100&statusid=2

Supervisor: Domain adresiniz
Password: Supervisor şifreniz
Action: sendstatus durum günceller
Phone: Durumu güncellenecek agentin telefon numarası
Statusid: Durumu olmasını istediğiniz id

