[GLOBAL AI HUB](https://globalaihub.com/)  tarafından Python Bootcamp Projeleri kapsamında verilen projede öğrenci not sistemi oluşturuluştur. 

 1. Öğrenci not sisteminde Kullanıcı tarafından öncelikle öğrenciye ait ders ismi girilmektedir.
 2. Kullanıcı tarafından girilen ders isminden sonra kullanıcıya o derse ait kaçtane öğrenci bilgisinin girileceği istenmektedir.
 3. Girilen öğrenci sayısından sonra "primary key" olarak tanımlanan öğrenci numarası kullanıcıdan istenmektedir."ogrenci_kontrol" fonksiyonu tarafından denetlenen okul numarası eğer kullanıcı tarafından daha önce aynı okul numarası girildiyse False döndürerek öğrenci kaydı yapılmamaktadır. Eğer aynı kullanıcı Data içinde yoksa kullanıcıdan Adı,soyadı,vize notu,final notu gibi bilgiler alınmaktadır.
 4. Alınan bu bilgiler doğrultusunda kullanıcının Vize ve final notu ortalaması:

            Ortalama=(vize_notu*0.4)+(Final*0.6)
    
    "ortalama_hesapla" fonksiyonunda yukardaki formülüne göre hesaplanmaktadır.

 5.  Ortalaması hesaplanan öğrencinin  "ders_durumu" fonksiyonunda Not Harf aralığı hesaplanıp dersin durumu (Geçti,Kaldı) hesaplanmaktadır.
 6. Geri döndürülen bu değerler doğrultusunda kullanıcıya ait tüm veriler bir 'List' içinde tutularak DataFrame yazılması için hazır hale gelmektedir.
 7.  "write_excel"  fonksiyonunda 'list' içindeki veriler yazdırılarak DataFrame kayıt edilmektedir.
 8. 'write_excel' fonksiyonunda daha önceden böyle bir dosyanın olup olmadığı kontrol edilmektedir. Eğer böyle bir dosya var ise dosyanın uzunluğu hesaplanıp yeni kullanıcı eklenmektedir. Yani Güncelleme işlemi yapmaktadır.
 9.  'write_excel' fonksiyonunda daha önceden böyle bir dosya oluşturulmamış ise yeni dosya oluşturulup ana bilgiler girildikten sonra kullanıcıya ait bilgiler tek tek kayıt edilmektedir.

