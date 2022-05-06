
Power-BI-GEO
Power BI GEO Maps çalışmalarının takibi için kullanılmaktadır.
POWER BI MAPS 

Genel Bilgiler :

Halihazırda 4 adet Map (Filled Map-Map-Shape Map ve ArcGIS ) Power BI da yüklü bulunmaktadır. İlave olarak Power BI Marketplace içinde ilave harita uygulamalarıda mevcuttur. Power BI Microsft ürünü olduğu için Haritalar BING haritaları kullanmatadır. Eğitimde kullanışlı olan Map ve Shape Map uygulaması yapılmaktadır.
Kullanılacak verisetti data.police.uk/downloads/London City Police bölgesi 2019-2022 csv verileri olacak raporlama ve görselleştirme bu csv veriler üzerinden yapılmatadır. Data query de  ETL işlemleri ile gereksiz kolonlardan kurtulacak ilave ihtiyaç kolon eklenecek ve farklı aylara ait ayrı csv dosyaları merge işlemine tabi tutulmuştur.
Coğrafya çalışmalarında enlem ve boylam bilgilerinin BI uygun olarak +-90 ve +- 180 arasında olması ile ülke , şehir, ilçe isimleri veri katogorilerinin biçimde verilmesi gereklidir. Aksi halde tanıyamıyabiliyor yada farklı ülkedeki şehir aynı şehir ismli yerleri verebilmektedir.
Raporlama ve Görselleştirme için Tarih[Month] Zaman analizi için, Longitude ve Latitude enlem ve boylam haritada koordinat bulunması için [ilave sutun açılarak bu değerler 1000000 bölünmüş ve değerler uygun hale getirilmiştir.],
Location ve LSOE generik yer belirlemek için yani alt konumlama için ve Crime Type ise analiz edilecek suç çeşitliliği için kullanılmıştır. Total rakamları tespit etmek için Crime Number sutunu oluşturulmuş ve her bir olay iin 1 olarak verilmiştir. Bu entityler geliştirilerek RİSK DEĞERLENDİRME GÖRSELLEŞTİRMESİ yapılabiir.

Grafik 1 Çizgi Grafik :
Axis_Eksen: Month Ay değerleri zaman analizi için, Valu_Değer: Count Crime ile aylık zamanda suç miktarları trend çizgisi ile görselleştirildi.
2 adet grafiğin 1 tanesi sabit gene karşılaştırma için diğeri inteactions ile etkileşime açık yapıldı.

Grafik 2 Ağaç Grafik :
Group: Crime Type ile değerler Valu_Değer: Count Crime ile suç miktarları görselleştirildi.

Grafik 3 Map Harita Uygulaması : Burada [İ] harfi ile üst sağda problemler yazıyor kontrol et. Unutma veri sayısı Map grafikte max 3500 oluyor.
Konum/Location   : LSOA ve Location koyarak haritada Drill up ve down yapabiliriz.. 1041 adet LSOE adsız olduğu için Avrupada çıkıyor suçlar dril downda . Filrelemede bu 1041 seçilmeyebilir.
Açıklama/Legend  :
Enlem/ Latitude    : Average yaparak Latitude 
Boylam/Longt      :  Average yaparak Longtitude koy.
Boyut/Size            : Crime Size ile boyutu belirle
İpuçları/Tooltips   :.
Bu grafik user friendly ve tercih edilir. Suçları bölge ve LSOE göre birbirleriyle kıyaslayabilir, trendi değerlendirebilir, diğer suç ve lalanlar ile kıyaslayabilir, dril up ve down etkin kullanarak RİSK DEĞERLENDİRME ANALİZLERİ yapabiliriz.

Grafik 4 Shape Map Şekil Harita Uygulaması : Staik Harita. ABD iNGİLTERE vb ülkeler var . Ben json TURKİYE yukledim. Çok Kulanışlı değil. Statik olduğu için Dril up ve down DESTEKLEMİYOR.Uygulama olarak Şekil haritasının tooltipsi Map ile yapılıyor ve detaylandırılıyor.

Konum/Location   : Ülke _ type json harita bilgisi
Açıklama/Legend  :
Boyut/Size            : Crime Size ile boyutu belirle
İpuçları/Tooltips   :.Tooltips olarak Map harita yapılıyor.
Burada mapshaper isimli program csv dosyaların json dosyalarının detaylandırmasını düzenlemek için kullanılabilyor. Kesin ve detaylı olan veriler düzenlenip Simplfy ile basitleştirilebilmektedir. 
