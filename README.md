git gitbub farkı

git: versiyon kontrol sistemi (yazdıgımız kodu commit edip push ladınız bu bizim 1.versiyonumuz ve bu devam ettikce 2-3. versiyonlar oluşur ve boyle devam eder 

github : kodları depoladıgı bulut tabanlı depo platformu (cogunlukla yazılımcıların kodlarını merkezi bir depoda tutmak amacı ile kullanılan ozelliktir ve en az bir gite ihtiyac duyar)

git init : yeni bir depo oluşturur ve yererel depoyu baslatır

git close : hali hazırda bir projeyi yeni dizi içinde farklı bir konumda kopyasını oluşturur 

git add : proje dizisindeki dosyaları aynı anda hepsini sahneye yerlestirir 

git commit : hali hazırda hazırlanmıs değişiklikleri anlık olarak goruntusunu alır 

git push : proje dosyamızı merkezi bir depoya yayınlamak / yuklemek için kullanılır "örnek : githuba proje atmak dosya yuklemek"

git pull : git pushun tam tersi uzaktaki bir depodan proje,dosya gibi dokuman yuklemek almak çekmek için kullanılır "örnek : githubdan dosya indirmek"

git branch mantıgı : farklı versiyonları aynı anda geliştirmek için kullanılır

git checkout -b : yeni bir branch oluşturup hemen ona geçiş yapar

git switch -c : yeni bir branch oluşturmadan geçiş yapar

 2. Semantic Commit Messages

feat : yeni bir şey eklendiğinde oluuşan mesaj

fix : hata giderildiğinde oluşan mesaj

docs : sadece dokümantasyon güncellemesi mesaj

style : kodun gorunumünü duzenle mesajı

refactor : kodun yapısını iyileştir mesajı 

test : testlerle ilgili değişiklik yap mesajı

chore : proje ayarları veya gorevleriyle ilgili düzenleme yap mesajı

revert : oneceki bir commiti geri alma mesajı 

perf : performans iyileştirmesi mesajı 

3. React Lifecycle Hooks

Functional Component:

useeffect : api çağrısı yapmak için kullanılır (sayfa yuklendiğinde verileri getirmek gibi)

usestatus : içinde bileşen tutar ve her seferinde renderler "örnek : butona basılınca artan sayac"

useref : status gibi  fakat renderlemez (içinde veri tutar)

Class Component:

componentditmount : bilesen ilk yuklendiğinde çalışır (veri çekme/branch baglama)

componentditupdate : bileşen her güncelleginde calısır (güncel veriye gore işlem yapmak)

componentunmount : bilesen kaldırıldıgında calısır (zamanlayıcı durdurma / event kaldırma)

functional / class component farkı

functional component : daha sade / modern ve hook destekli 

class comonent : daha eski fakat lifecycle yontemini net gosterir

merge ve rebase 

-merge : 2 dalı (branch) birlestirmek çin kullanılır (bu işlem mevcut commit gecmisini korur ve yeni bir birleştirme commiti oluşturur)

-rebase : bir daldaki değişiklikleri alıp bakşka bir dalın üzerine "yeniden oynatır" (bu işlem commit gecmişini daha temiz ve dogrusal hale getirir)

4. React Memoization:

react.memo() : bileşenin propsları degismedigi surece render edilmesini onler 

usememo() : hesap gerektiren degerleri onbelleğe alır 

usecallback() : fonksiyonları önbelleğe alır bileşenin gereksiz render edilmesini onler 

functional componet ne zaman kullanılır : 
                                          
                                          1)daha sade ve okunabilir kod isteğinde 
                                          
                                          2)reacts hooks (useeffect-usestate) kullanılacaksa 
                             
                             avantajları
                                          1)daha az kod
                                          2)daha modern
                                          3)daha iyi performans
                                          
class component ne zaman kullanılır : 
                                     
                                     1)eski projelerde 
                                      
                                      2)hooks öğrenmeden once yazılan bileşenlerde 
                          
                          avantajları 
                                      1)daha fazla kod
                                      2)this kullanımı karmasık
                                      3)artık pek tercih edilmiyor
                                      
use effect parametreleri : 
                           
                           1)-fn => çalışacak fonksiyon (bu fonksiyon component reade olduktan sonra calısır)
                           
                           2)-deps => bağımsız dizidir (hangi değiskenler değiştiginde fn fonksiyonu tekrar çalışsın onu belirler)
                           
                           KISACA
                           
1-parametre (ne yapılacak)

2-parametre (ne zaman yapılacak)

2.parametre nasıl davranır (deps)

-1 useeffect (() => {....}) hiç bagımlılık vermediyse (her renderda çalısır)

-2 useeffect (() => {....},[]) boş bapımlılık dizisi (sadece 1 kere calısır) örnek: componentditmount gibi (component ilk yuklendiğinde)

-3 useeffect (() => {....},[x,y]) x veya y değiştiğinde calısır ilk renderda da çalısır örnek: componentditupdate gibi (her güncellendiğinde)

abstract class component 

neden kullanılır : kod tekrarını azaltmak için 
                   geliştiriciye "şablon"sunmak için 
                   
ne işe yarar : ortak işlemler bir yerde toplanır kodun duzeni ve okunabilirliği artar

neden kullanılır : büyük projelerde / çok sayıda bileşenin ayrı yapıda çalıştığı durumlarda 

                                                  ÖZETLE 
                                                  
                                                 soyut sınıf : ortak mantıgı bir yere toplar 
                                                 alt sınıflar sadece farklı olan kısmı yazar react desteklemesede "class" ve "extends" ile bu yapı kullanılabilir


react context api :

ne işe yarar : uygulama genelinde "ortak veri" kullanmak istediğinde işimize yarar

1:tema
2:kullanıcı bilgileri 
3:dil seçimi 
4:sepet bilgisi

ozetle : 
         createcontext ==> yeni bir context tanımlar
         provider ==> veri sağlayan "sorma" bileşeni
         usecontext ==> veriyi alan tüketen hook


nerede kullanılır : 
                    1-tema yonetimi
                    2-kullanıcı login durumu 
                    3-dil seçimi
                    4-sepet bilgisi
                    5-uygulama ayarları

type - safing coding

anlamı : yazdıgın değişkenlerin / fonksiyonların / bileşenlerin ne tur veriyle calıştıgını acıkca belirtmek anlamına gelir

neden kullanılır : 
                   hataları erken bulmak 
                   kodların ne yaptıgını anlamak

1)type / interface =  ikiside veri şekillerini tanımlar 

-type : daha cok esnek,union gibi yapılar için daha iyi

-interfacwe : daha cok classlar veya buyuk projelerde kullanılır

2)enum = birbirine bağlı sabit değerleri temsil eden bir veri türüdür

                          ornek
                          günleri sayılarla ifade etmek yerine 
                          enum ile isimlendirerek daha anlaşılır hale getirebiliriz:

Ne işe yarar?

-1 Anlamlı isimlendirme sağlar:

-2 Hataları azaltır: Sadece belirli değerlerin atanmasını sağlar.

-3 Okunabilirliği artırır: Sayılar yerine anlamlı isimler kullanılır.

3)enum type = birden fazla tipten birini kabul eder 

                      unknown / qny / never  never farkları
                      
any ==> her şeyi kabul eder (hicbir kontrol yapmaz / tehlikeli)

unknown ==> ne oldugunu bilmediğin veri (kullanmadan once kontrol gerekir)

never ==> asla bir deger almaz genelde hata fırlatan fonksiyonlarda olur

                                kısaca 
                                any : ne verirsen gecer 
                                unknown : ne verdiğini bilmeden kullanamazsın
                                never : asla bir şey dönmez
                                
atomic design pattern : 

nedir : bileşen organizasyon modelidir  (bileşenleri "küçükten-büyüğe" katmanlı şekilde düzenlemeyi saglar)

neden kullanılır : kodun duzenli ve okunabiilir olması için

1)projede karmaşayı azaltmak ekip içi iş bbirliğini arttırmak gibi 

2)bileşenleri düzenli tekrar kullanılabilir ve anlamlı bir yapıda tutmak için 

                                              kısaca 
                                              buyuk projelerde "nerede ne var" / "bu bileşeni daha once yapmışmıydık" gibi soruları son verir 

atom ile maolekülün farkı : 

atom ==> en kucuk bileşen (button / input)

molekül ==> birden fazla atomun birleşmesiyle oluşur (label / input / errormessage) 

atom tek basına gorev yapar molekül bir işlevi yapar

molekül ile organizma farkı : 

molekül ==> daha küçük bir bileşen (input alanı)

organizma ==> birden fazla molekül ve atom içerir (login formu)

organizma daha karmaşık ve bağımsız şekilde çalışabilen yapıdır

template ne işe yarar : bir sayfanın yerleşim düzenini tanımlar fakat gerçek veri koymaz (header / sidebar gibi)

page ne işe yarar : templateyi alır ve içine gerçek veriyi yerleştirerek kullanıcıya gosterilen son sayfayı oluşturur (login page / profilepage)

                                                  ozetle 
                                                  atom : tuğla
                                                  molekül : tuğlalarla-duvar
                                                  organizma : duvarlarla-oda
                                                  template : oda planı 
                                                  page : gerçek ev












