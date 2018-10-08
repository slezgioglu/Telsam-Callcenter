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


function myTelefonSendAPI(id, message) {
    var result = null;
	//var obj = document.getElementById(id);
    $.ajax({
        url      : address,
        type     : 'get',
        dataType : 'json',
        data     : JSON.stringify(message),
        beforeSend: function (xhr) {
            xhr.setRequestHeader ("Authorization", "Basic " + btoa('telsam:1234'));
        },
        success: function(data){
            //result = data.data.results;
			//obj.value=result;
			ajaxRequest(id, '_myTelefonSendAPI', ['send=OK', 'actions='+data.data.actions, 'results='+data.data.results]);
            console.log(data.data.results);
        }
    })
    .done(function() {
        //console.log('Send - OK');
    })
    .fail(function() {
		//obj.innerHTML="ERR";
        //console.log("Send - ERR");
		ajaxRequest(id, '_myTelefonSendAPI', ['send=ERR', '', '']);
    });
}




















function myTelefonSendTransfer(id,BlindTransfer) {
swal({
  title: 'Aktarılacak numarayı giriniz',
  input: 'text',
  showCancelButton: true,
  confirmButtonText: 'Aktar',
  cancelButtonText: 'İptal',
  showLoaderOnConfirm: true,
  preConfirm: function (number) {
    return new Promise(function (resolve, reject) {
		if (isNaN(number)) {
			reject('Sadece rakam girebilirsiniz!')
		} else {
			if (BlindTransfer){
			myTelefonSendAPI(id, {"data":{"actions": "blindtransfercall","parameters":[{"line": "1","to": number}]}});
			resolve();
			}else
			{
			//myTelefonSendAPI(id, {"data":{"actions": "holdretrievecall","parameters":[{"line": "1"}]}});	
			myTelefonSendAPI(id, {"data":{"actions": "callstart","parameters":[{"line": "2","number": number}]}});	
			myTelefonSendTransfer_OK(id);
			}
			
		}
    })
  },
  allowOutsideClick: false
}).then(function (number) {
	if (BlindTransfer){
	  swal({
		type: 'success',
		title: 'Aktarma İşlemi Başarılı',
		html: 'Aktarılan numara: ' + number
	  })
	}
})
}








function myTelefonSendTransfer_OK(id) {
swal({
  title: 'Şuanda Aktarmak İstiyormusunuz',
  //input: 'text',
  showCancelButton: true,
  confirmButtonText: 'Tamam',
  cancelButtonText: 'İptal',
  showLoaderOnConfirm: true,
  preConfirm: function () {
    return new Promise(function (resolve, reject) {
			myTelefonSendAPI(id, {"data":{"actions": "attendedtransfercall","parameters":[{"from": "1","to": "2"}]}});	
			resolve()
    })
  },
  allowOutsideClick: false
}).then(function () {
  swal({
    type: 'success',
    title: 'Aktarma İşlemi Başarılı'
  })
}, function (dismiss) {
  // dismiss can be 'cancel', 'overlay',
  // 'close', and 'timer'
  if (dismiss === 'cancel') {
    swal('Aktrama','İptal Edildi!','error');
	myTelefonSendAPI(id, {"data":{"actions": "hangupcall","parameters":[{"line": "2"}]}});	
	}
})
}


