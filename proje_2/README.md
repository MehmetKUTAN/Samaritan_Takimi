Madde-1: Veri setine göre uzun soluklu filmler hangi dilde oluşturulmuştur? Görselleştirme yapınız.
    
    
    Netflix_Original dosyası okundu ve 'veri' adındaki değişkene atandı. 90 dakika ve üstündeki filmler uzun soluklu film kabul edildi ve görselleştirme yapıldı. 
    Buna göre en fazla uzun soluklu filmin İngilizce dilinde çekildiği anlaşıldı.

Madde-2: 2019 Ocak ile 2020 Haziran tarihleri arasında 'Documentary' türünde çekilmiş filmlerin IMDB değerlerini bulup görselleştiriniz.
    
    
    Tarih(Premiere) sütunundaki veri tarih formatına çavirildi (Örneğin 2020-05-25 formatına). Sonra istenen aralıktaki veri alınıp görselleştirildi.

Madde-3: İngilizce çekilen filmler içerisinde hangi tür en yüksek IMDB puanına sahiptir?
    
    
    english_max_imdb=veri[veri['Language']=='English'] koduyla İngilizce diilindeki filmler ayrıştırıldı. 
    max_imdb = english_max_imdb.max() koduyla da en yüksek IMDB puanlı tür tespit edildi.

Madde-4: 'Hindi' Dilinde çekilmiş olan filmlerin ortalama 'runtime' suresi nedir?
    
    
    mean_runtime=veri[veri['Language']=='Hindi'] koduyla Hindi dilindeki filmler dataframe'den ayrıştırıldı.
    ortalama_süre = mean_runtime.mean(axis=0) koduyla ortalama Runtime süresi hesaplandı.

Madde-5: 'Genre' Sütunu kaç kategoriye sahiptir ve bu kategoriler nelerdir? Görselleştirerek ifade ediniz.
    
    
    türler=veri['Genre'].value_counts() koduyla Genre sütunundaki tür sayısı hesaplandı ve türler adındaki değişkene atandı.
    türler.plot.pie(subplots=True, figsize=(30, 30)) koduyla türler bir pasta grafiğine döküldü.

Madde-6: Veri setinde bulunan filmlerde en çok kullanılan 3 dili bulunuz.
    
    
    ilk_3_dil=veri['Language'].value_counts() koduyla datafram'deki diller kullanıldığı film sayısına göre listelendi.
    ilk_3_dil.head(3) koduyla ilk 3 sırada yer alan diller tespit edildi.

Madde-7: IMDB puanı en yüksek olan ilk 10 film hangileridir?
    
    
    veri.sort_values(by=['IMDB Score']) koduyla İMDB puanına göre filmler sıralandı.
    ilk_10_imdb=veri.tail(10) koduyla ilk 10'daki filmler alındı.

Madde-8: IMDB puanı ile 'Runtime' arasında nasıl bir korelasyon vardır? İnceleyip görselleştiriniz.
   
   
    import scipy.stats as stats ile scipy kütüphanesi koda dahil edildi.
    import numpy as np ile numpy kütüphanesi koda dahil edildi.
    import seaborn as sns ile seaborn kütüphanesi koda dahil edildi.
    Gerekli kodlar yazılıp görselleştirme yapılarak sonuçlar gösterildi.

Madde-9: IMDB Puanı en yüksek olan ilk 10 'Genre' hangileridir? Görselleştiriniz.
    
    
    sort_list=[] adında boş bir liste oluşturuldu
    imdb=veri['IMDB Score'] ve Genre=veri['Genre'] kodlarıyla Genre ve IMDB Score sütunlarına göre dataframe'den veri çekildi.
    for i in range(len(imdb)) koduyla imdb sütununun uzunluğu miktarında bir sayı dizisi oluşturularak üzerinde gezinildi ve bu sayılar İMDB Score ile Genre sütunundaki
    verilerin indeksleri olarak kullanılıp o indekslerdeki verileri alındı. Bu veriler oluşturulan listeye sözlük içerisinde çiftler olarak aktarıldı. Daha sonra bu listede ilk ondaki imdb puanları sıralandı. key=[] ve values=[] listeleri oluşturuldu.
    for i in range(len(top_10)): kodu ile 10 adet sayı barındıran bir sayı dizisi oluşturup üzerinde gezinildi ve i değişkenine atandı. key.append(top_10[i]['imdb']) ve
    values.append(top_10[i]['Genre']) kodlarıyla da i'inci indeksteki verileri alınıp daha önce oluşturulan listelere eklendi. Daha sonra gerekli veriler grafiğe döküldü.

Madde-10: 'Runtime' değeri en yüksek olan ilk 10 film hangileridir? Görselleştiriniz.
    
    
    Madde-9'daki işlemlere benzer işlemler gerçekleştildi ve görselleştirme yapıldı.

Madde-11: 11 Hangi yılda en fazla film yayımlanmıştır? Görselleştiriniz.
    
    
    count ile bir yıl içerisinde yayınlanan film adet sayısını buluyoruz Bulunan film  yapısının veri türü pandas.series olduğu için sort_values() ile sıralamasını yapıyoruz. Ardından plot ile film adet sayısı ve yillarin grafiğini çiziyoruz


Madde-12: Hangi dilde yayımlanan filmler en düşük ortalama IMBD puanına sahiptir? Görselleştiriniz.
    
    
    count ile bir yıl içerisinde yayımlanan filmlerin IMDB skoruna göre Diller ayrıştırımını yapıyoruz. pandas.series olduğu için sort_values() ile sıralamasını yapıyoruz.ascending=True yaparak sıralamayı küçükten büyüge doğru sıralıyoruz ve plot.pie ile pasta grafiği oluşturuyoruz

Madde-13: Hangi yılın toplam "runtime" süresi en fazladır?
    
    
    Sum() ile aynı yıllar içerisinde "Runtime" sürelerini topluyoruz. Toplanılan bu sürelerden sonra  pandas.series olduğu için sort_values() ile sıralamasını yapıyoruz.ascending=False yaparak sıralamayı Büyükten  küçüge doğru sıralıyoruz ve ekrana basıyoruz

Madde-14: Her bir dilin en fazla kullanıldığı "Genre" nedir?
    
    
    diller_kümesi=set() adında bir küme oluşturduk.
    İlk for döngüsünde her dilin bir kez bulunduğu ve her dili barındıran küme elemanı oluşturuldu.
    İkinci for döngüsünde dil kümesindeki her bir dil üzerinde gezinerek o dile ait en fazla tür tespit edildi.

Madde-15: Veri setinde outlier veri var mıdır? Açıklayınız.
    
    
            mean_runtime_hindi=veri[veri['Language']=='Hindi'] ve mean_runtime_hindi=veri[veri['Language']=='Dutch'] mean_runtime_english=veri[veri['Language']=='English'] ile Hindi, Dutch ve English dillerine ait veriler dataframe'den çekildi. 
            ortalama_süre_hindi = mean_runtime_hindi.mean(axis=0) ve ortalama_süre_dutch = mean_runtime_dutch.mean(axis=0) ile dillere ait filmlerin ortalama runtime süreleri hesaplandı. 
        data1=mean_runtime_hindi['Runtime']
        data2=mean_runtime_dutch['Runtime']
        data3=mean_runtime_english['Runtime'] , bu üç satur kodla y ekseninde yer alacak Runtime süreleri değişkenlere atandı.
        fig = plt.figure(figsize =(14, 12)) --->14x2 'lik grafik alanı oluşturuldu.    
        bp = ax.boxplot(data) ---> kutu grafiğ oluşturuldu,

        Kutu grafiğindeki verilere göre Hindi ve Enhlish dillerinde outlier veri tespit edildi.
