Kurulum ve Çökülüm [1]_
=======================

:date: 2014-11-23 03:41:51 +0200

Malum-u kârî bilgisayar işleriyle meşgulüm. Sevdiğim tarafı *şiir gibi*
program yazmak olmasına rağmen, kader beni operasyon yöneticisi yaptı.
Nasıl oldu da oldu ben de anlamış değilim.

Halbuki bilgisayarın en sevmediğim tarafı bir şeyleri kurmak, ayar
yapmak, orasına burasını *zıvırtlamaktır.* Bilgisayarları klavyesinin
tuşları dökülünceye kadar kullanmamın sebebi budur. Allah’ın işi, ekmek
paramı tam da bu saçmalıktan, büyük çapta kullanılan programların
kurulumu, ayarı, bakımı falan gibi işlerden kazanıyorum son zamanlarda.

Geçen hafta sonu da bir güncellememiz vardı. Adını verirsem reklama
girer bir programın, Amerikanın benim bile bildiğim bazı büyük
şirketlerinin web üzerinden kullandığı bir envanter takip yazılımının
güncellemesini yapmakla sorumluyduk. Bu üçüncü denememizdi. Önceki iki
denemede altı saat olarak ayarladığımız *downtime*, bu sefer kırksekiz
saat olarak ayarlanmıştı. Bir web programının kırksekiz saat *biz yokuz*
demesi müstakilen bir utanç vesilesidir ama üst yönetim bunu anlamadı,
ben de *bu programlar olmasa buraları ne güzel idare ederim* modundayım
zaten, canları sağolsun.

Amerikada gece yarısı, bizde Cumartesi sabahın körü bu işe başladık.
Önceki iki denemeyi yapan adamı işten atmıştım. Planlarımızın arasında
bu kadar yakın bir deneme daha yoktu, yerine koyduğum adamlara *temrin
temrin temrin edin* diyecek zaman da olmadı. Her kurulumda olduğu
programın kendisi hakkında bir fikrim olmamasına rağmen başlarındaydım.
Bazı kararları benim vermem gerekiyor, yöneticinin tek vazifesi öncelik
belirlemek ve kararlar hakkında sorumluluk almak sanırım.

Başladık. Başlarda iyiydi. Programın türlü çeşit sunucuları ve modülleri
var. Bazı modüller bazı sunucularda çalışıyor, bazı sunucular sadece
test kurulumları için, bazısı müşteriye açık, bazısı değil… Durum
karışık yani. Internetten bir şey indirip de kurmak gibi değil,
sayfalarca dokümantasyon okumak, onlarca ayar yapmak gerekiyor. Tabi
okunacak doküman olduğunu, bunların doğru olduğunu, ayarları tam
anlattığını falan da kabul etmek gerekiyor.

Son bir modül çalışmadı. *Çalışmazsa canı sağolsun* diyebileceğimiz bir
modül de değil, web arayüzünün kendisi. Önceki denemelerde de
çalışmamıştı. Bu sefer kendimi konudan daha sorumlu hissettiğim için bir
yandan ben de uğraşıyorum. Saatlerce hata kaydı, program ayarı, Java
güncellemesi, *şu mu ki*, *bu mu ki* denemeleri yaptık. *Son altı saate
kadar uğraşacağız, eğer çalışmazsa geri alacağız* dedim, geri almak da
bir dert, benzer ayarları yapmak, veritabanını yeniden yüklemek
gerekiyor ve saire. Altı saat ayırmak normal yani.

Kırksekiz saat içinde yirmibeş saat çalışmışım, grupdaşlardan biri otuz
saate yakın, diğerleri de yirmi saatin üstünde çalıştı.

Biz çalıştık ama program çalışmadı.

Durum Moskova’nın banliyölerinden geri çekilen Alman ordusunun durumu
gibi, şehri alabileceğimizi gerçekten düşünmüştük ama direndi. Eh, ne
yapalım, bozguna bırakmadan geri çekilmek lazım.

48 saatin bitmesine beş saat kala, yenilgiyi kabul edip, tüm ayarları
eski haline getirmeye başladık. En önemli ayağı, kurulum sürecinde bazı
değişiklikler yapılan veritabanını yeniden yüklemek. Bunun için de
kuruluma başlayınca aldığımız yedekleri kullanıyoruz.

Adına C. diyeceğim Amerikalı, Yahoo’da falan çalışmış bir takımdaş
sorumlu bundan. Yedekleri başta almak ve güvenli bir yere koymak onun
görevi, başka bir görevi de yok zaten. Yedek dosyalarını yerel ağ
üzerinden kopyalamak bile kırk elli dakika aldığı için biraz yavaş bir
süreç bu.

Adam ilk denemesinde *dosyalar eksik* şeklinde bir uyarı almış. Bize de
anlattı. Teknik bir hata olabileceğinden yeniden denemesini istedik.
Deniyor ama uzun sürüyor, bizim beş saat bitiverdi, kendi de yoruldu.
Biz de zaten yorgunuz.

Süreyi uzattık, bir dört saat daha yeter dedi. Hadi bakalım, ne
deneyecekse…

Dört saat de bitti. Amerikanın gece yarısında bitmesi gereken işi,
sabahın sekizine kadar uzattık.

Sekiz de geçti.

Takımdaşların bazısı iptal. Ben adamın *başında* duruyorum kaçmasın
diye.

Hindistan ve Filipinlerden iki kişiyi yardıma çağırdım, SMS atarak.
*Allah rızası için bi el atın.* Hintli *ben bu işten pek anlamam
aslında* mealinde bir şeyler söyledi, Filipinli geldi, önce C.\`nin
yaptıklarını yapmaya tekrar çalıştı. C. bu arada laf üretiyor ve
arasında dedi ki, \*bu işi yapmak için *do\_backup incr* komutunu
kullandım.\*

Şimşek çaktı bende.

Oradaki *incr*, *incremental* kelimesinin kısaltması ve *bir önceki
yedekten beri değişmişleri yedekle* demek. Eğer günlük *incremental*
yedek alıyorsanız, sadece dünden beri değişen dosyaları bir yere
yedekliyorsunuz demektir. Çalışması için en başta bir *full* yedek
lazım. Bizim *çok tecrübeli* arkadaş da, 48 saat az gelmiş olacak ki,
*daha çabuk olsun* diye ezbere bir *incremental* yedek almış. Yalnız bir
sorun var, bu yedeğin *full* yedeği yok. Yani dünden beri değişen
dosyalar elimizde ama dosyaların gerisi mevcut değil. (Dosyayı örnek
olsun diye veriyorum, gerçekte veritabanıyla çalışıyoruz.)

Tabii ki yedeklere geri dönmeye çalışırken, *yedekler eksik* diye mesaj
alacağız.

Filipinli kız Allahtan biraz daha tecrübeli de, veritabanının değişiklik
kayıtlarından (yani tamamen farklı bir metodla) bizi son veritabanlarına
kavuşturabildi. Ama bu da birkaç saatimize daha maloldu. Dahası elde
ettiğimiz veritabanı, üzerinde güncelleme değişikliği yapılmış ve
kullandığımız programla uyumsuz veritabanı…

Değişikliklerin bazısının *geri al* seçeneği mevcut. Veritabanına bir
bilgi, bir sütun eklediyse onu siliyor falan. Olanların hepsini geri
aldırdım ve toplamda onaltı saat kadar bir gecikmeyle programı yeniden
açabildik.

Açamayabilirdik. Her şey kaybolmuş olabilirdi. *Allah’a şükredin
gavurlar* demek geldi içimden.

Yapmamız gereken testleri bile müşterilerle beraber yaptık. Destek
birimi o kadar baskı uyguluyor üstümüzde.

Uyumadan ilk yaptığım iş C.\`yi işten kovmak oldu. Veritabanı çalışmaya
başladığında uyumaya göndermiştim adamı, *kendi işimi kaybederim,
yaptığım son iş bari bu olsun* diye hemen kontratını iptal ettim.

Ancak maceramız *tabii ki* burada bitmedi.

Ertesi gün dört beş müşterinin programa giremediklerine dair raporlar
geldi. Veritabanında bir bozukluk varmış. Filipinlerde saat sabaha karşı
üç olduğu için Hintli ve bir Mısırlıyla başladık araştırmaya. Destek
ekipleri benden sorunun ne zaman çözüleceğine dair bilgi bekliyor.
Mesele o kadar tuhaf ve elimizde o kadar az bilgi mevcut ki *beş
dakikadan beş güne herhangi bir zaman* denebilir. Sonunda *3 ila 12
saatte çözeriz* gibi bir şeyler geveledim. 12 saate kadar Filipinli
uyanır, mesajımı görür, yardıma koşar gibilerinden.

Birkaç plan yaptık. Mısırlının bu veritabanıyla tanışıklığı eskiden.
*Falanca dosya bozulmuş, bu beş müşterinin bilgileri hep orada* gibi bir
şeyler söyledi. Ben de *bu beş müşterinin bilgilerini almak için önceki
yedeklerden birini yeni bir sunucuya kuralım, oradan da kopyala yapıştır
yaparız* gibi bir fikir verdim. Hintli bu işe başladı, Mısırlı *ben
başka bir şey deneyeceğim* dedi falan…

Yedekler yine çalışmadı tabii. Bu arada saatler ilerliyor, beş saati
geçtik.. Mısırlıya *şu sitede bulduğun komutları dene, belki çalışır*
dedim, kendim de çalışmayan yedekler, kendini *veritabancı* olarak
pazarlayan insanlar, beni yönetici yapan *felek* gibi derin konuların
arasında, nasıl olur da Destek ekibine *biz bu işi daha üç gün
çözemeyiz* diyebileceğimi düşünmeye koyuldum.

Destek ekibiyle konuşuyoruz, hoşbeş faslını uzatmayı ve usturuplu bir
İngilizce cümleyle meseleyi özetlemeyi düşünüyorum. Hatta yazdım
cümleyi, *üç gün* dedim, *Enter* tuşuna basacağım, gidecek.

Mısırlı konuşmaya başladı, *yaptım, yaptım, yaptım, oldu, çözdüm*,
sanırım bir yandan da klavye başında hopluyor herif, ilk düşüncem
balataları sıyırmış olabileceği oldu, çünkü uzun saatler bilgisayar
başında kalan insanlarda saçmalama ve hepten üşütme durumları
olabiliyor.

Baktım herif ciddi, eh, dedim, *are you sure? did you try to login?*
falan, denemiş, çalışıyormuş, ancak müşterilerin şifreleri bizde
olmadığı için bir de onların denemesi gerekti.

Bu arada destek ekibine nasıl da Hollywood filmi tarzı bir durum
olduğunu anlattım. Film seyretmeye ihtiyaç duymadığımı, çünkü hayatımın
yeterince macera, korku ve aksiyon içerdiğini.

Müşteriler de teyit etti.

Ben de altmış saatlik çalışmayla dolmuş dört günü kulağımda ertesi gün
doktora gitmeme sebep olacak bir iltihap, derin bir yorgunluk ve boşluk
duygusuyla kapattım.

Yazı bile yazamadım. Düşünün. Yazı bile yoktu.

.. [1]
   2011-08-21 02:39:56
