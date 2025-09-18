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

functional componet ne zaman kullanılır : 1)daha sade ve okunabilir kod isteğinde 
                                          2)reacts hooks (useeffect-usestate) kullanılacaksa 
                             
                             avantajları
                                          1)daha az kod
                                          2)daha modern
                                          3)daha iyi performans
                                          
class component ne zaman kullanılır : 1)eski projelerde 
                                      2)hooks öğrenmeden once yazılan bileşenlerde 
                          
                          avantajları 
                                      1)daha fazla kod
                                      2)this kullanımı karmasık
                                      3)artık pek tercih edilmiyor
                                      
use effect parametreleri : 1)-fn => çalışacak fonksiyon (bu fonksiyon component reade olduktan sonra calısır)
                           2)-deps => bağımsız dizidir (hangi değiskenler değiştiginde fn fonksiyonu tekrar çalışsın onu belirler)
                           
                           KISACA
                           
1-parametre (ne yapılacak)
2-parametre (ne zaman yapılacak)

2.parametre nasıl davranır (deps)

-1 useeffect (() => {....}) hiç bagımlılık vermediyse (her renderda çalısır)

-2 useeffect (() => {....},[]) boş bapımlılık dizisi (sadece 1 kere calısır) örnek: componentditmount gibi (component ilk yuklendiğinde)

-3 useeffect (() => {....},[x,y]) x veya y değiştiğinde calısır ilk renderda da çalısır örnek: componentditupdate gibi (her güncellendiğinde)
