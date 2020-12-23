---
title: Virgül 23 Aralık 
author: Emin Reşah
date:  2020-12-23 23:25:40+0300
expiryDate:
dp: 15137
featured_image: /images/header-77.jpg
---

Ted Chiang'ın bir hikayesini okudum. Kısa bir hikaye ama *özgür irade* konusunda söyledikleri ilginç. Chiang, Lem'den sonra en sevdiğim bilimkurgu yazarı olabilir. 

Hikayede bir araç var, bir düğmesi ve bir ışığı var. Bu ışık düğmeye basmadan tam bir saniye *önce* yanıyor. Sonra değil, önce. Zamanda bir saniye geriye sinyal gönderiyormuş. Böyle bir aracı kullanmaya başlayınca insanların önemli bir kısmının artık hiçbir şey yapmaz olduklarını söylüyor. Özgür iradeleri olmadığına inandıklarında hayattan çekiliyorlarmış. 

Özgür iradenin *determinizmle* bir sorunu var, bunu görebiliyoruz. Eğer ne yapacağımız beynimizdeki fiziksel değişimlere bağlıysa, bu fiziksel değişiklikler de deterministse, ne yapacağımızın *özgür iradeyle* ilgisi yoktur. Beynimiz bir durumda *şunu istiyor* ve biz onun *irademiz* olduğunu sanıyoruz ama aslında hepsi *sebep sonuç* içinde. 

Determinist sistemlere inanmayabilirsiniz, Heisenberg'in belirsizliği dersiniz veya bunun gibi süreçlerin beynin çalışmasını etkileyecek ufak ölçeklerde determinizmi ortadan kaldırdığını iddia edersiniz. Bu makul bir çıkış. Ben de beynin kuantum mertebesinde çalışan kısımlarının determinist olmadığına inanabilirim. 

Ancak bunun başka bir çözümü daha var: Beyinde tek bir merkez yok, birden fazla *zihin* var dersek, bunların kendileri determinist olsa dahi, meydana getirdikleri sistem kaotik olur. 

Diyelim beynimiz birkaç farklı unsurdan oluşuyor. Bu unsurların birbirlerini ne şekilde etkileyeceklerini önceden belirlemek hemen hemen imkansız. Hepsi kendi başına determinist, hatta çok basit olabilir, bununla beraber bunların birleşmesinden oluşan *makine* hiç de basit olmayacak ve hesaplanması *önceden* mümkün olmayan şekilde davranacaktır. *Özgür irade* dediğimiz konu da belki böyle ortaya çıkan, insanların zihninde tek bir ses yok, bu seslerin hepsi bir şekilde birbiriyle etkileşim halinde ve (birine *irade* adını verdiğimiz) bu seslerin sonucunda hangisinin galip geleceğine önceden karar vermek mümkün değil. 

Şöyle diyelim: Zihnimizde 5 ayrı *düşünce üreteci* olsun. Bunlar birbirlerinden etkilenip durum
değiştiriyorlar. Bilincimiz ve irademiz bunlardan sadece biri olsun. Diğer dördü kontrolümüzde
değilse, beşincisi bize rastgele görünecektir. 

{{< rawhtml >}}
<div>
$$A_i = (B_{i-1} + C_{i-1}) mod 10$$
$$B_i = (C_{i-1} + D_{i-1}) mod 20$$
$$C_i = (D_{i-1} + E_{i-1}) mod 30$$
$$D_i = (E_{i-1} + A_{i-1}) mod 40$$
$$E_i: (A_{i-1} + B_{i-1} + C_{i-1} + D_{i-1} + E_{i-1}) mod 50$$
</div>
{{< /rawhtml >}}

Başta bütün değerlerin 1 olduğunu kabul edelim. Kurallar tek tek determinist olmakla
beraber \(E\)nin hangi değerleri alacağını önceden tahmin edemeyiz. Böyle bir zihin
determinist ancak kaotiktir. Bu sebeple sadece bilinci bilerek *özgür irade* gibi bir kavramın
anlaşılması mümkün değil. 

Böyle bir sistemi simüle etmek için şu programı yazdım. 

```python

current = {"a": 1,
           "b": 1,
           "c": 1,
           "d": 1,
           "e": 1}

def sim_chaos(timesteps):
    global current
    e_values = []
    for n in range(timesteps):
        e_values.append(current["e"])
        next = {}
        next["a"] = (current["b"] + current["c"]) % 10
        next["b"] = (current["c"] + current["d"]) % 20
        next["c"] = (current["d"] + current["e"]) % 30
        next["d"] = (current["e"] + current["a"]) % 40
        next["e"] = (current["a"] + current["b"] + current["c"] + current["d"] + current["e"]) % 50
        current = next

    return e_values


print(sim_chaos(100))
```

Sonuçta ilk 100 \(E\) değeri şöyle çıktı:

```
[1, 5, 13, 35, 37, 16, 7, 14, 27, 28, 40, 11, 1, 12, 8, 12, 15, 16, 42, 20, 12, 13, 1, 41, 29, 21, 12, 33, 20, 11, 28, 14, 19, 19, 24, 30, 2, 31, 10, 28, 22, 34, 47, 29, 23, 31, 3, 26, 49, 26, 13, 16, 10, 43, 37, 30, 8, 12, 49, 8, 0, 16, 42, 45, 43, 49, 49, 47, 26, 3, 2, 31, 14, 26, 21, 33, 38, 38, 32, 19, 36, 46, 8, 34, 19, 45, 15, 3, 13, 18, 37, 28, 45, 8, 42, 37, 37, 20, 12, 24]
```

Beş adet hayli basit kuralın bir araya gelmesiyle bile kaotik görünen ve nasıl çalıştığını
anlamadığımız bir *zihin* elde ettik. 

Böyle çok primitif kuralların bile önceden kestirilmesi zorken, her biri tek tek determinist çalışsa dahi, beynimizi oluşturan unsurların bir araya geldiklerinde tahmin edilebilir şekilde davranacaklarını düşünmek temelsiz hale geliyor. 

Baktığımızda sayı dizisinin de bir *karakteri* olduğunu düşünebiliriz, arada tekrar eden sayılar
var, `19, 19` `49, 49` veya `37, 37` gibi bazı denk gelişler bize bu sayı dizisinin hiç de öyle
basit kurallardan oluşturulmuş olmadığını düşündürüyor. Biraz daha karmaşık 
kurallardan oluşmuş, biraz daha fazla unsur içeren bir *zihnin* özgür iradesi olduğunu düşünme
ihtimalimiz ise hayli kuvvetli. 

Okur burada tabii ki *ya benim hissettiğim bu özgür irade* diyecek. Aynı his bende de var,
istediğimi yapıyormuşum ve istemediğimi yapmıyormuşum gibi düşünüyorum. Bununla beraber bu hissin
büyük ölçüde kendi kendimize anlattığımız bir hikaye olma ihtimali de kuvvetli. Zihnimizin düşünen
birden fazla unsuru varsa, bunların arasındaki *konuşma* ve etkileşim bize *bilinç* hissi
verecektir. Normalde belki de hayli basit kurallarla çalışan bir zihnin hesaplama esnasında ürettiği
*özgürlük ve irade* hissi. 


