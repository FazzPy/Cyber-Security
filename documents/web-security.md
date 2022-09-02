# WEB GÜVENLİĞİ

Web uygulamalarında kullanılan sunucuların ve web uygulamasının kendi güvenlik
yapılandırmalarının hatalı olması, uygulamalar hazırlanırken güvenlik protokollerinin
uygulanmaması veya hatalı kod yapılarının oluşturulması kurum ve kişiler için büyük tehlike
arz eder. OWAPS, web uygulamalarındaki güvenlik açıklarının kapatılması ve bu uygulamaların
güvenli bir şekilde korunmasını sağlamak için çalışmalar yapan özgür bir topluluktur. OWAPS,
saldırganların yetkisiz erişim, yetki yükseltme ve bilgi sağlamak için genellikle sistemlerdeki
 Web Güvenliği 319
düzeltilmemiş açıklıklardan yararlandığını tespit etmiştir. Saldırganlar bu açıklıklardan sızarak
sistemin içine, korumasız dosyalara ve dizinlere erişmeye çalışırlar. OWASP topluluğuna göre
dünyada en çok bulunan zafiyetlerden biri, hatalı güvenlik yapılandırmalarıdır. OWASP Top 10’da
bu zafiyet altıncı sırada yer alır. Bu tür açıklıklar genellikle saldırganlara bazı sistem verilerine veya
işlevlerine yetkisiz erişim hakkı sağlar. Doğru yapılandırılmamış sistemler tamamen saldırganın
eline geçebilir ve bu durum büyük problemlere yol açabilir. Özellikle varsayılan yapılandırma
ayarlarında bırakılmış sistemler, kullanılan ama ihtiyaç duyulmayan servisler ve güncelliğini
yitirmiş servisler, yapılandırma temelli güvenlik açıklarına örnek teşkil eder.
Dizin listesinin sunucuda varsayılan olarak bırakılması, yapılandırma hatalarına örnek
verilebilir. Bir sitenin dizin listesine ulaşmak için herhangi bir şifreye ihtiyaç yoktur. Tarayıcıya
adres bilgilerini girmek, dizin listesine ulaşmak için yeterlidir. Wordpress sitelerde wp-content
veya wp-includes gibi klasörler herkese açıktır ve herhangi biri tarayıcıya ilgili adresi girdiğinde
tüm verileri görüntüleyebilir. Örneğin https://siteadi.com/wp-content/uploads/
linki tarayıcıya eklendiğinde dizin tarama daha önce kapatılmadıysa sitedeki dosyalar herkes
tarafından görüntülenir ve kolayca gezilebilir. Bu riski en aza indirmek ve siteyi korumak için dizin
listelemesi veya diğer adıyla dizin taraması kapatılmalıdır.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/directoryerror.PNG">

Gereksiz özellikler, artık kullanılmayan ve var olmayan uygulamalar ile iletişim kurmaya
çalışan bileşenler saldırganların bu programı taklit etmesiyle güvenlik zafiyeti oluşturabilir. Bir
uygulamada varsayılan olarak açık kalmış bağlantı noktaları uzaktan saldırı yapılmasına yol
açabilir. Güvenlik duvarlarının yanlış yapılandırılması, kurum içi anahtarlama ve yönlendirici
cihazlarının varsayılan ayarlarda kalması, bu cihazların yetkilendirme ayarlarının yapılmaması ve
port güvenliklerinin varsayılan ayarlarda kalması gibi durumlarda güvenlik problemleri ortaya
çıkar. Örneğin bir saldırgan; web sunucusunda açık unutulan ve ayarları varsayılan olarak bırakılan uzak masaüstü erişim bağlantı noktasını, açık bağlantı noktalarını taratarak tespit edebilir,
varsayılan kullanıcı adı ve şifrelerini deneyerek sistemi ele geçirebilir. OWASP standartlarında
yanlış güvenlik yapılandırmalarına karşı alınması istenen önlem, bir web uygulaması için gerekli
olmayan bütün iletişimlerin engellenmesidir. 

OWASP, web uygulamalarının güvenliği için şu çözümleri önermektedir:<br>
• Kütüphaneler ve web platformları güncel tutulmalıdır.<br>
• Varsayılan olarak daha güvenli bir yapılandırma oluşturulmalıdır.<br>
• Kullanılmayan servisler, uygulamalar, varsayılan kullanıcılar ve test kullanıcıları sistemden
 kaldırılmalıdır.<br>
• Sunucu ve veri tabanı arasındaki bağlantı şifrelenmelidir.<br>
• Üçüncü parti uygulamaların güvenli kaynaklardan geldiğine emin olunmalıdır.<br>
• Tüm uygulama kaynaklarının yine uygulama tarafından başlatıldığına emin olunmalıdır.<br>

<h3> WEB SERVİSİ </h3>

Web servisleri, HTTP protokolü kullanılarak masaüstü, mobil veya diğer sistemlere hizmet
veren yapılardır. Web servislerinde istemci ve sunucu olmak üzere iki taraf vardır. İstemci cihazlar
web servislerine isteklerde bulunur. Web servisler ise uygun formatta istemciye cevap döndürür
ve istemci, son kullanıcıya bu formatı işleyerek verir.
Web servisleri, uzak sistemler veya farklı platformlar arasında XML, JSON, CSV vb. ortak
bir biçim kullanarak veri alışverişini sağlar. Bu servisler; Java, C++, C#, PHP, Node.js, Python,
GO, Linux, Windows vb. HTTP protokolü üzerinden iletişim yapan ve kullanılacak ortak biçimi
(genellikle XML ve JSON) destekleyen yapılar arasında iletişimi sağlar. Web servislerindeki bazı
kavramlar aşağıda verilmiştir.

**SOAP (Simple Object Access Protocol)**: Uygulamaların HTTP protokolü üzerinden haberleşmesini sağlayan, XML tabanlı mesajlar içeren servis protokolüdür.

**REST (Representational State Transfer)**: HTTP protokolünü kullanarak web servislerinde
hizmet vermektedir. REST, istemci ve sunucu arasındaki bu hizmeti GET, POST, PUT gibi HTTP
metotlarını kullanarak gerçekleştirir. REST servisler de URL’ler ile doğrudan HTTP metotlarıyla
istek yapar, SOAP gibi bir WDSL’e gerek yoktur. Bir diğer önemli fark ise SOAP’ta sadece XML
üzerinden mesajlaşma yapılırken REST servisinde başta JSON olmak üzere XML, hatta Text
formatında bile veri iletilebilir.

**WSDL (Web Services Description Language)**: SOAP, web servisleri için gerekli tanımlamaları
yapan bir dildir ve SOAP’ın web servisler için kullanılması zorunludur. WSDL; fonksiyonlar,
veri tipleri, fonksiyon açıklamaları gibi tanımlamaları kullanıcıya sunar. Saldırgan, web servisi
oluşturmak için kullanılan teknolojiyi tespit eder. Güvenlik açıklarını bulmak için WSDL arayüzü
taraması yapar

**WADL (Web Application Description Language)**: WADL, REST servisin hangi fonksiyonları
desteklediğini, hangi metotlar ile kullanıldığını, servise giriş / çıkış olarak hangi parametrelerin
verildiğini veya alındığını, bu parametrelerin tiplerinin ne olduğunu gösteren XML tabanlı bir
dokümandır.

<h3>Web Servisinin Keşfi</h3>


Uygulamaların kullandığı web servislerini keşfetmek için çeşitli yöntem ve teknikler vardır. Bu yöntem ve tekniklerin bazıları şunlardır:<br>
• Proxy yazılımı kullanarak, web servislerine ulaşmadan önce araya girip trafiğin incelenmesi
 yoluyla keşif<br>
• Arama motorlarını kullanarak directory listing tarzı açıkların keşfedilmesi<br>
• Rastgele veri gönderme metodunu kullanan fuzzing testleri yöntemiyle keşif<br>
• Swf veya jar dosyalarının decompile araçları ile tersine işlem görerek web servislerinin keşfi<br>

Uygulamalardaki web servisleri keşfedildikten sonra web servislerinin zafiyetleri incelenir ve
web servislerinde bulunan zafiyetlere gerekli güvenlik önlemleri alınır.

Swf intruder veya burpsuite tarzı programlar sayesinde uygulamaların hangi web servislerini
kullandığı tespit edilebilir. Swf intruder ile hazırlanmış bir flash dosyasının içeriği incelenerek
kullandığı web servisini bulmak mümkündür

Proxy yazılımları ile web servislerinde araya girme işlemleri uygulanabilir, kullanılan web
servisleri öğrenilebilir. Kali Linux işletim sisteminde kullanılan çeşitli web Proxy yazılımları vardır. 

Bu yazılımlara Uygulamalar, Kali Linux, Web Applications, Web Application Proxies yolu
kullanılarak ulaşılır.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/webapp.PNG">

Bu araçlardan en popüler olarak kullanılanı **burpsuite** yazılımıdır. Kali Linux içinde burpsuite
yazılımının ücretsiz versiyonu gelir. Ücretsiz versiyonda özelliklerin tamamı kullanılamaz.
Özelliklerin tamamını kullanabilmek için pro versiyonu satın alınmalıdır. Burpsuite kullanılıp,
“.dll?wsdl”, “.ashx?wsdl”, “.exe?wsdl” veya “.php?wsdl” vb. ifadeler aratılarak web servisler
tespit edilebilir.

Arama motorları kullanılarak da web servislerin tespiti yapılabilir. Birçok web servis
uygulamasında WSDL dosyaları halka açık hâlde bulunur. Bir saldırgan aşağıdaki metotları
kullanarak bu dosyalara erişebilir.

filetype:wsdl

index of "/wsdl"

inurl:wsdl

inurl:asmx

filetype:asmx inurl:(_vti_bin | api | webservice | ws )

allinurl:dll?wsdl filetype:dll

Fuzzing test araçlarını kullanarak da web servislerinin keşfini yapmak mümkündür.

Wfuzz en sık kullanılan test aracıdır ve Kali Linux işletim sisteminde kullanıma hazır olarak gelir. 

wfuzz ile yapılan zafiyet taramasının bir çıktısı verilmiştir.

**wfuzz -p 127.0.0.1:8080 -c --hc 404,XXX -z list,ws-webservice-{taraması yapılan web servisler}-z **

komutu kullanılarak web servis keşfi yapılır.

<h3>WEB SERVİSLERİNE YÖNELİK ZAFİYET İŞLEMLERİ</h3>

Web servislerinin kullandığı metotlar yukarıda anlatılan yöntemlerle keşfedilerek ve bu
yöntemlere ait parametreler üzerinde değişiklikler yapılarak zafiyetler bulunabilir.
Web servis testleri için kullanılabilecek araçların bazıları aşağıda listelenmiştir.

• WebScarap<br>
• SoapUI<br>
• WCFStorm<br>
• SOAP Cleaner<br>
• WSDigger<br>
• wsScanner<br>
• Wfuzz<br>
• RESTClient<br>
• Burpsuite<br>
• WS-Attacker<br>
• ZAP<br>
• Metasploit<br>
• WSDL Analyzer<br>
OWASP’ın tespit ettiği zafiyetlerden bazıları aşağıda verilmiştir.<br>

Injection Zafiyetleri: Injection saldırılarının temel amacı, sisteme zararlı kodlar sızdırmak
veya sistemden veriler elde etmektir. En riskli açıklar, injection açıklarıdır. Bu açıklar, web uygulamalarının kodlanması esnasında yapılan dikkatsizliklerden ve hatalardan kaynaklanır. Injection
açıkları ile hedef sistemde veri okunabilir, silinebilir, veriye zarar verilebilir.
Injection çeşitleri aşağıda sıralanmıştır.

a) **Sql Injection**: Sql veri tabanlarına erişim ve yönetim için kullanılan standart bir yapıdır.
Veri tabanına Sql ile veriler işlenirken araya birtakım karakterlerin eklenmesiyle Sql injection
meydana gelir. Sql injection ile saldırı yapılan sitede veri tabanındaki veriler okunabilir, okunan
veriler ile panellere erişim sağlanabilir, uzaktan kod vb. çalıştırılabilir. Sql injectionun çeşitleri;
Classic Sql, Error-based Sql, Union-based Sql, Blind Sql, Boolean-based Sql, Time-based Sql, Outof-band Sql’dir.

b) **Command Injection**: Genellikle sunucu bazlı çalışan uygulamalarda gerekli filtrelemelerden
geçirilmeden doğrudan kod çalıştırılmasına dayanır. Çalıştırılan bu komutlar sunucuda hâkimiyet
sağlar. Bu zafiyetle beraber sistem yöneticisi olunabilir ve sistem uzaktan yönetilebilir.

c) **XPATH Injection**: XML, kullanıcıların verilerini kendi kendine yapılandırmasına olanak
sağlayan bir dildir. XPATH, XML verileri üzerinde herhangi bir değişiklik yapılmaksızın veri
almak veya okumak için kullanılan bir dildir. Bu zafiyet, Sql injectiona benzer bir yapıdadır. Sql
injectiondaki gibi kullanıcı girdilerinden XPATH sorguları yapan web sitelerine bazı karakterler
sıkıştırılarak oluşur.

ç) **LDAP Injection**: LDAP, dizin hizmetlerinin yönetiminde kullanılan bir protokoldür. LDAP ile
dizinlerde kayıt ekleme, silme, düzenleme, arama gibi işlemler yapılabilir. LDAP komutlarının
belirli bir denetlemeye tabi tutulmadığı uygulamalarda bu komutların değiştirilmesiyle saldırı
gerçekleşir. LDAP ile Sql injectionda olduğu gibi veriler okunabilir, değiştirilebilir, yetkisiz
kullanıcılara yetkiler verilebilir.

d) **PHP Object Injection**: PHP, kullanıcıdan alınan verinin “unserialize()” fonksiyonundan
geçirilmesi sonucu ile oluşur.

e) **SSI Injection**: SSI, web uygulamalarında statik yapılı sayfalara dinamik içerik eklemeyi
sağlar. Sunucuya gönderilen zararlı kodların çalışmasıyla beraber SSI injection oluşur.

**Hatalı Kimlik Doğrulama ve Oturum Yönetimi Zafiyeti**: Oturum saldırılarına yönelik
gerçekleştirilir. Phishing saldırıları bu zafiyete örnek olarak gösterilebilir. Bu yöntem, hedef kitleye
yönelik sahte sistemler hazırlanarak kişileri kandırmaya dayanır. Buradaki temel amaç, kullanıcı
hesapları veya kredi kartı gibi bilgileri elde etmektir.

**Cross-Site Scripting (XSS) Zafiyeti**: XSS zafiyeti HTML, CSS, JavaScript ile hazırlanmış zararlı
kodları kullanıcıların tarayıcısında izinsiz olarak çalıştıran bir açıktır. XSS ile hedef kullanıcının
oturum bilgileri, tuş girişleri, tarayıcı yönetimi gibi işlevler gerçekleştirilebilir. Dışarıdan girilen
değerlerin filtrelenmemesi sonucunda ortaya çıkar. XSS de kendi içinde Reflected XSS, Dom
Based XSS ve Stored XSS olmak üzere üç bölüme ayrılır.

**Güvensiz Doğrudan Nesne Referansları Zafiyeti**: Güvensiz bir şekilde doğrudan nesnelere
erişim sağlanabilir. Genellikle her nesnenin bir ID değeri veya buna karşılık gelen bir yapısı vardır.
Örneğin php_id=1 olduğu varsayılırsa normal kullanıcılar id değeri 1 olan nesneye erişim sağlarken
normal kullanıcıların id değeri 2 olan nesneye erişim sağlamaması gerektiği hâlde id değeri
2 olan nesneye erişim sağlamasından dolayı ortaya çıkan bir zafiyettir. Bu durum, sistemdeki
yetkilendirilmelerden kaynaklanır.

**Hatalı Güvenlik Yapılandırması Zafiyeti**: Sistemlerdeki güvenlik yapılandırmalarının hatalı
olmasından dolayı ortaya çıkar. Genellikle sunucu yapılandırılmalarında varsayılan ayarlar
kullanılır. Varsayılan ayarlar güvenli değildir. Bunu önlemek için güvenlik ayarlarının doğru bir
şekilde yapılandırılması ve yapılandırmada gereksiz servislere yer verilmemesi gerekir.

**Hassas Veri Zafiyeti**: Yedekler, kimlik bilgileri, kredi kartı gibi hassas verilere yönelik saldırılardır. Bu teknik genellikle Brute Force, loglama, tarayıcı zafiyetleri, ARP spoofing gibi saldırıları içerir.

**Eksik İşlev ve Erişim Kontrolü Zafiyeti**: Bu zafiyet, eksik işlev ve erişim kontrollerine dayanır.
Örneğin hedef site http://hedef-site.com ve admin panel yolu giriş varsayılırsa http://hedef-site.
com/giris şeklinde aynı zamanda sisteme giriş yaptığında kullanıcılar admin.php adlı yönetim
dosyasına yönlendirilsin. Kullanıcıların http://hedef-site.com/giris’te belirli kontrollerden
geçirilip, admin.php’ye yönlendirilmesi gerekirken yanlış bir yapılandırılma ile giriş kontrolleri
yapılmaksızın, saldırganın direkt olarak http://hedef-site.com/admin.php adlı dosyaya erişim
sağlamasından kaynaklanan zafiyet türüdür. Bu zafiyetin **LFI** ve **RFI** olmak üzere iki farklı türü
bulunur.

a) **LFI: Local File Inclusion olarak bilinir**. LFI, localdeki dosyaları kaynak kodlarıyla okumayı
sağlar. /etc/passwd dosyalarını okumak için kullanılır. Bununla birlikte LFI ile sisteme Shell de
yüklenebilir. LFI sadece hedef siteyi etkilemez, tüm sunucuyu etkiler.

b) **RFI: Remote File Inclusion olarak bilinir**. Bu açık ile hedef sisteme uzaktan dosya çağrılabilir.
Bu sayede hedef sisteme zararlı kodlar yüklenebilir. 

**Cross-Site Request Forgery (CSRF) Zafiyeti**: CSRF saldırıları, güven saldırıları olarak da bilinir.
Buradaki temel amaç, hedef sitede yetkili bir kullanıcıya işlem yaptırmaktır. Örneğin hedef sitenin
http://hedef-site.com ve hedef sitede yüzlerce kullanıcının aynı zamanda birkaç admin olduğu
varsayılırsa burada saldırganın temel hedefi, site üzerinden yetki almak ve admin olmaktır.

**Bilinen Güvenlik Açıklarına Sahip Bileşenleri Kullanma**: Bilinen zafiyetlerin sistemlerde yer
almasıdır. Çoğu açık kaynak kodlu yazılımda bulunan zafiyetler bildirilmez. Aynı zamanda bu
yazılımların tüm modülleri sistem yöneticileri tarafından bilinmez. Bu tür yazılımlardan dolayı
ortaya çıkan zafiyetlerdir.

**URL Yönlendirme Zafiyetleri**: Günümüzde hemen hemen herkesin denk geldiği sahte link
yönlendirmeleri ve fake siteler bu başlık altında incelenir. Özellikle sosyal medyada bu zafiyet çok
kullanılır.

**Burpsuite**, zafiyet taraması işlemlerinde en çok kullanılan Proxy programıdır. Web işlemleri
gerçekleştirilirken istemci-sunucu mimarisi kullanılır. Bir web sitesi incelenmeye başlandığında
gelen giden verilere, isteklere, isteklerin gidiş dönüş şekillerine göre işlemler gerçekleştirilir.
Zafiyet taraması işlemlerinin sağlıklı yürütülmesi için istemci ile sunucu arasında yapılan her
işlemin hem istemciden çıkıp sunucuya varmadan, kontrolü hem de sunucudan istemciye dönen
cevabın istemciye varmadan araya girilerek kontrol edilmesi çok önemlidir. Burpsuite burada
devreye girer ve istemci ile sunucu arasındaki tüm verileri kendi üzerinden geçirerek mevcut
özellikleri ile bu bilgilerin test edilmesini sağlar.

**Burpsuite**, bünyesinde birçok özellik ve eklenti bulundurur. Burpsuite kendi içinde Repeater,
Intruder, Decoder, Spider, Scanner, Comparer, Sequencer özelliklerini barındır. Bu özellikler,
kullanıcıya zafiyet testi işlemlerinde kolaylık sağlar ve hız kazandırır.

<h3>URL Yönlendirme Zafiyeti (Open Redirect)</h3>

Yönlendirme açıkları önemli ve sık kullanılan bir web uygulama güvenliği zafiyetidir. Uniform
Resource Locator (URL), internet üzerinde tutulan dosyaların veya çeşitli kaynakların adresi
olarak bilinmektedir. URL adresleri çeşitli alanlara ayrılmıştır ve bu adresler internet tarayıcılarına
yazıldığında kullanıcıyı belirtilen adrese yönlendirir.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/url.PNG">

Web siteleri hazırlanırken dış kaynaklı adresleri yönlendirme ihtiyacı doğar. Bu ihtiyaçlara çözüm bulmak için çeşitli web programlama dillerinde farklı fonksiyonlar kullanılır.

Örneğin PHP dilinde “header” ve “redirect” parametreleri yönlendirme amaçlı kullanılır. Yönlendirme
işleminde doğru filtreleme yapılmadığı takdirde kullanıcılar ilgili alana istedikleri veriyi girebilir.
Kullanıcılara izin verilen bu giriş işlemleri, yönlendirme zafiyetini (Open Redirect) oluşturur.
Bu zafiyete yönelik saldırıların mantığı, saldırıyı yapan kişinin hedefini başka bir sayfaya
yönlendirmesidir. Bunun sonucunda “RCE”, “XSS” gibi sosyal mühendislik saldırıları ve hedefe
zararlı dosya indirme saldırıları birleştiğinde çok tehlikeli olabilir.

Bir blog sitesi ve bu sitede iki arkadaşın blog sitelerine yönlendirme yaptığı linkler olsun.

<a href=”/redirect.php?go=aliningunlugu.com”>Ali’nin Günlüğü</a>

<a href=”/redirect.php?go=ayseninfotografdunyasi.com”>Ayşe’nin Fotoğraf Dünyası</a>

Bu iki link de sunucudaki `redirect.php` dosyasına parametre yollayarak yönlendirme yapsın.

<a href=”/redirect.php?go=aliningunlugu.com”>Ali’nin Günlüğü</a>

<a href=”/redirect.php?go=ayseninfotografdunyasi.com”>Ayşe’nin Fotoğraf Dünyası</a>

Bu iki link de sunucudaki `redirect.php` dosyasına parametre yollayarak yönlendirme yapsın.

Kodlarda da görüldüğü gibi herhangi bir kontrol yapılmadan `go` parametresi ile gelen siteye
doğruca yönlendirme yapılır. Bazen yönlendirme işlemi açık bir adresle değil, base64 gibi bir
algoritmayla kodlanarak yapılabilir. 


```
aliningunlugu.com => YWxpbmluZ3VubHVndS5jb20=
<a href=”/redirect.php?go=YWxpbmluZ3VubHVndS5jb20=”>Ali’nin Günlüğü</a>

<?php
header(“Location: “ . base64_decode($_GET[‘go’]));
?>
```

Bu örnekteki kod, saldırgan için zafiyetin kullanılmasına daha açıktır. Son kullanıcı gideceği
adresi açıkça göremediği için saldırgan, base64 sonucunu istediği adres ile değiştirip, hedef
kullanıcının tıklamasını sağlayarak kendi hazırladığı zararlı bir adrese kullanıcıyı yönlendirebilir.
Saldırgan, hedef kullanıcının bilgisayarına zararlı yazılımı otomatik indirebilir veya varsa sitedeki
XSS zafiyeti ile birleştirerek oturum bilgilerine erişebilir.

<h3> Yönlendirme Zafiyetini Kullanarak Saldırı Yapma </h3>

Aşağıdaki işlem adımlarına göre localhostta konumlandırılmış PHP ile hazırlanan bir web
uygulamasında yönlendirme zafiyetini kullanarak istenilen site (www.mesleklisesi.com) yerine
www.google.com sitesine yönlendirilmesini sağlayınız.

1. Adım: PHP komut yapısında header() işlevini ham bir HTTP başlığı göndermek için kullanınız.
Bir başka deyişle belirtilen HTTP adres yapısına tıklayıp bir yönlendirme işlemi gerçekleştiriniz.

```
<?php
header("Location:” . $_GET[‘url’]
exit;
?>
```

Yukarıdaki PHP kod blokunda header() fonksiyonu kullanılarak $_GET yöntemi ile yakalanan
URL parametresinin değerine bir yönlendirme yapıldığı görülmektedir.

Index.php sayfasından gönderilen URL parametresinin değerini yakalayarak (www.
mesleklisesi.com) adresine istenen şekilde sayfayı yönlendiriniz

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/urlrouting.PNG">

2. Adım: Burpsuite gibi bir araya girme programı ile istekleri yakalayınız. İstekleri yakalayıp
incelediğinizde görüleceği üzere PHP kod blokunda herhangi bir filtreleme işlemi yapılmadığı için
bu aşamadaki URL parametresi istenen herhangi bir adrese yönlendirilebilir.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/burpurl.PNG">

3. Adım: Burpsuite uygulamasını kullanarak, url= parametresinin değerini http://www.
google.com olarak değiştirip isteği sunucuya yollayınız ve zafiyeti test ederek sonucu izleyiniz.

4. Adım: Localhostta bulunan web sitesinin yönlendirme işlemini tekrar deneyiniz. www.
mesleklisesi.com olan yönlendirme işlemi www.google.com’a yönlendirilerek zafiyetin başarılı
bir şekilde kullanıldığı görülür.

Bu tarz saldırılara karşı önlem almak istendiğinde kodları yazan geliştirici, gelecek isteklerdeki
verileri doğru bir şekilde filtreleyerek işlemin uygulanmasını sağlamalıdır. Güvenli URL
adreslerinden oluşan listelerle çalışarak güvenliği artırmalıdır. Web uygulamalarında güvenilir
olmayan dış kaynaklara erişim sağlanmak istendiğinde kullanıcılar uyarılmalıdır. Kodlama
yapılırken yönlendirme fonksiyon komutları yerine özel linkler ile bağlantılar kurulmalıdır. 

<h3>XSS (Cross Site Scripting) Zafiyet</h3>

XSS, tarayıcı üzerinden gerçekleştirilen bir saldırı çeşididir. Genellikle tarayıcıdaki çerezlerin
çalınması veya kullanıcının izni ve bilgisi olmadan sayfanın zararlı bir adrese yönlendirilmesiyle
uygulanır. Bu saldırı çeşidinde sunucu sistem değil, sitenin yöneticisi veya kullanıcıları hedeftir.
Bu saldırının üç farklı çeşidi olmasına rağmen en zararlısı DOM XSS'dir. XSS zafiyeti kullanılarak
yapılabilecekler aşağıda verilmiştir.

• Cookie bilgileri çalınabilir.<br>
• Web sayfası başka bir sayfaya yönlendirilebilir.<br>
• Farklı bir sunucudan zararlı kodlar çalıştırılabilir.<br>
• Keylogger olarak kullanılabilir.<br>

**A) Stored XSS**

Bu yöntemde bir içerik kayıt formuna (Input) ihtiyaç vardır. Saldırgan, veri tabanına kaydedilip,
son kullanıcıya gösterilen herhangi bir kayıt formundan JavaScript kodları yazıp bu kodların veri
tabanına kaydedilmesini sağlar. Böylelikle veri tabanından o kayıt çağrıldığında istenen kodlar
çalışıyorsa sitede XSS açığı olduğu söylenebilir.

**B) Reflected XSS**

XSS’in hedef sitede etkin olup olmadığını öğrenmenin en hızlı yolu bu yöntemi denemektir.
Bunun için URL’den gelen JavaScript kodlarının gömülü olduğu parametrenin çalışıp çalışmadığı
kontrol edilir. Herhangi bir önlem alınmadan JavaScript kodları çalışıyorsa bu yöntemle farklı
amaçlara yönelik saldırılar planlanabilir.

Bu yöntemde URL’den girilen herhangi bir bilginin veri tabanına kaydedilmese dahi anında site
içinde çalışması gerekir. Böylelikle zararlı kod içeren bir link hazırlanıp, hedef kişiye gönderilerek
tarayıcı üzerinden istenen bilgiler çalınabilir.

Zafiyet Aranan Link:

 https://www.benim-sitem.com/arama.php?ara=cicek
 
Linkte görüldüğü üzere `ara` parametresi ile çiçek aramak istenmektedir. Bir sitede XSS açığı
olduğundan şüpheleniliyorsa site aşağıdaki gibi zararlı bir link ile kontrol edilebilir.

**Zafiyet Uygulanan Link**

https://www.benim-sitem.com/arama.php?ara=<script>alert(‘Bilgilerinizi ele geçirdim!’)</script>

Linke tıklandıktan sonra bir bildirim çıkıyorsa `alert()` fonksiyonu yerine JavaScript ile zararlı
kodlar yazılarak kötü niyetli işler yapılabilir.

DOM bir W3 standardıdır ve HTML ile XML gibi hiyerarşik yapıların modellerini tanımlar. DOM,
web tarayıcıları kullanılarak girilen internet sayfasını bir belge, sayfa içindeki elemanların hepsini
de bir nesne olarak kabul eder. Sayfada bulunan yazılar, resimler ve diğer elemanların hepsi birer
nesnedir. DOM, sayfa içindeki nesnelere müdahale ederek özelliklerinin değiştirilmesini sağlar.
Bütün bu işlemleri yapabilmek için JavaScript gibi script dilleri kullanılır.
Bu yöntemin çalışma şekli Stored XSS'e benzer ama zararlı JavaScript kodunun veri tabanına
yazılmasına gerek yoktur. DOM XSS, URL'den alınan bir bilginin doğrudan DOM nesnesine
eklenmesi sonucu ortaya çıkan bir zafiyettir. 

 Aşağıdaki gibi bir kodun web sitesinde yer aldığını varsayınız.
 
 ```
<script>
 document.write(“Şu an bu linki incelemektesiniz : “ + document.baseURI);
</script>
 ```

Script kodunda `document.baseURI` ile adres kısmındaki herhangi bir bilgi hiç kontrol
edilmeden `document` nesnesine yazılmıştır. Bu durumda kullanıcının yazabileceği herhangi
zararlı bir kod doğrudan çalışacaktır.

**Zararlı Link**

https://www.benim-sitem.com/index.html#<script>alert(‘Bilgilerinizi ele geçirdim !’)</script>

Bu zararlı link ile # simgesinden sonra gelen kısım HTML’e göre bir etiket olduğu için DOM
tarafından ekleme anında çalıştırılabilir şekilde linke eklenecektir. Önceki kısım ise sadece
metinden ibaret olduğu için görüntülenmesi dışında hiçbir zarar vermeyecektir.
XSS temelde kullanıcıyı hedef aldığı için ilk aşamada zarar verilemese de farklı saldırı
yöntemleriyle birleştirilerek sisteme ciddi zararlar verilebilir. Ayrıca JavaScript kodları encode
edilmiş şekilde de olabilir. Kodun okunaklı olup olmaması önemli değildir. Önemli olan husus,
hedef tarayıcıda JavaScript kodunun çalışmasıdır.
XSS zafiyet saldırılarından korunmak için Web Application Firewall (WAF) kullanılmalıdır. Bunun
yanında giriş işlemlerinde < , > , / , = gibi XSS zafiyetinde kullanılan karakterler engellenebilir veya
sadece gereken bilginin alınması sağlanabilir.

<h3>HTML Injection Zafiyeti</h3>

HTML injection olarak adlandırılan bu zafiyet, dışarıdan herhangi bir kişinin siteye HTML kodu
enjekte etmesine olanak tanıyan bir güvenlik açığıdır. HTML injection, kullanıcıların dışarıdan veri
girdisi yaptığı bütün form işlemlerinde oluşabilen bir zafiyettir. Web sitesi içindeki bir yazı kutusu,
bir liste kutusu, arama kutusu, yorum yapma gibi veri girdisinin yapılacağı alanlarda kullanılan bir
açıktır. XSS ile benzerlik gösteren özellikleri olsa da HTML injection sadece HTML etiketleri ile
kullanılır. HTML injection zafiyeti kullanılarak yapılabilecek işlemler şunlardır:

• Web sayfasının içerik bilgilerini değiştirme<br>
• Kullanıcı oturum verilerini elde etme<br>
• SRF karşıtı işlemlerin keşfi<br>
• Tarayıcıda kaydedilen parolaları elde etme<br>

**Web Sayfasının İçerik Bilgilerini Değiştirme**: En basit saldırı tekniklerinden biridir. Saldırganın
zafiyetli site üzerinde sitenin görünürlüğünü veya site içinde ekli olan dosyaları, görselleri, yazıları
değiştirmesi ile meydana gelen bir saldırı türüdür. Örneğin saldırgan, satmak istediği bir ürünün
görsel reklamı için depolanan bir HTML eklemesi kullanabilir.

**Hassas Oturum Verilerini Elde Etme**: Bu saldırı tekniğinde saldırgan, sitede hazır verilen form
elementlerini kullanarak veya kendi eklediği HTML form kodları ile bir form sayfası oluşturabilir
ve bu sayfaya girilen değerleri kendi local ağına yönlendirip kullanıcı verilerini çalmaya yönelik
bir saldırı gerçekleştirebilir.

CSRF Karşıtı İşlemlerin Keşfi: Saldırgan, siteler arası istek sahteciliği olarak da bilinen bu saldırı
türünü kullanabilmek için CSRF karşıtı belirteçleri sızdırmaya çalışabilir. Bu konuda saldırgan,
HTML kodlarından ve HTML injection zafiyetinden yararlanabilir.

**Tarayıcıda Depolanan Parolaları Elde Etme**: HTML eklemeleri saldırganlarca tarayıcı parola
yöneticileri tarafından otomatik olarak doldurulan formları yerleştirmek için de kullanılabilir.
Saldırgan uygun bir form eklemeyi başarırsa parola yöneticisi kullanıcı kimlik bilgilerini otomatik
olarak ekler.

Kodları yazan kişinin özensiz, plansız ve güvenlik risklerini hiçe sayarak web sitesini geliştirmesi
sonucu HTML injection zafiyeti ortaya çıkar. PHP dilinin eski ve güvensiz sürümlerinin kullanılması,
tarayıcı eklentileri ve eklentilerin sürümlerinin eski olması, HTML veri girişi alanlarının gerekli
kontrollerden geçmeden kodlanması bu zafiyeti saldırganların kullanmasına sebebiyet verir.

<h3> HTML Injection Zafiyetini Kullanarak Saldırı Yapma </h3>

Aşağıdaki işlem adımlarına göre hedefteki bir sosyal paylaşım web sitesinin HTML açıklarıyla
kullanıcı verilerini elde ediniz.

1. Adım: Hedef sitede veri girişi yapılan alanlara HTML kodları girerek, açık olup olmadığını
deneyiniz.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/access.PNG">

2. Adım: Hedef sitede veri girişi yapılan alanlara girilen kodların çalışıp çalışmadığını test
ediniz. Kodlar çalışıyorsa açık var demektir. İşleme devam ediniz.

3. Adım: Sosyal paylaşım web sitesinde HTML injection zafiyetini tespit ediniz. Bu açığı
kullanarak, siteye girecek kullanıcı bilgilerini ele geçirme amaçlı bir metin gönderip (VIP üyelik
hakkı kazandınız.) Kullanıcıların metindeki adrese giriş yapmasını sağlayınız.

Örnek HTML Kodu : 

 ```
<h1><mark>KAZANDINIZ!!!</mark>VIP Üyelik Hakkı Kazandınız. Üyeliğinizi ücretsiz VIP seçeneğine yükseltmek için TIKLAYINIZ</h1><a href=”https://fake-sitemiz.
com”>TIKLAYINIZ</a>
 ```
4. Adım: Siteye giriş yapan kişileri hazırladığınız sahte siteye yönlendirerek kişilerin bilgilerini girmesini isteyiniz ve verileri ele geçiriniz. Bu noktada saldırganın uygulayacağı sosyal
mühendislik yöntemleri inanırlığını artırarak verilerin ele geçirilmesini sağlar.

<h3> LFI (Local File Inclusion) ve RFI (Remote File Inclusion) Açıkları </h3>

LFI ve RFI, son kullanıcının izni olmayan dosyalara erişiminden doğan açıklardır. Bu iki açığın
kullanım şekli neredeyse aynıdır.

**LFI**'de amaç; sunucudaki bir dosyaya yazılımın doğal yollarla izin vermediği, herhangi bir
tıklama veya yönlendirme ile erişilmeyen, herhangi bir yerde açıkça erişilemeyen dosyaya
erişmektir.

**RFI**'de ise amaç, sunucuda var olmayan bir dosyayı yazılımın izin verdiği veya vermediği bir
form ekranından ya da adres satırından sunucuya yüklemek ve orada çalıştırmaktır.
Kullanım şekilleri aynı olsa da sonuç bakımından ikisi arasında belirgin farklar vardır. LFI ile
sunucuda bilinen bir dosyaya erişildiği veya dosya çalıştırıldığı için genellikle sunucudaki bir ayar
dosyası okunup sunucudan şifreler veya değerli bilgiler elde edilir. RFI ise kullanıcının istediği
dosyayı sunucuya yükleyip, hedef işletim sisteminde çalışacağını düşünerek hazırlanacak herhangi
bir zararlı dosyanın sunucuda çalıştırılabilmesidir. Böylelikle sunucuya yetkili erişim kazanmak da
dâhil olmak üzere istenen dosyayı okuma, herhangi bir dosyayı değiştirme, silme, sunucudaki
kurulu başka programları çalıştırabilme gibi birçok sonuç elde edilebilir. Sonuç olarak saldırgan,
sunucuyu kendi bilgisayarı gibi kullanabilir. Her iki durumda da verilebilecek zararın büyüklüğü
saldırganın hayal gücüne bağlıdır. Teknik bilgi ve kötü niyet ne kadar fazlaysa hem sunucuya hem
de sunucunun sahibi kişi veya kuruma verilebilecek zarar da o kadar fazla olur.
 
**Örnek**

LFI açığına örnek için bir galeri sitesi ve bu sitede iki tane link olsun.

Müşteri Projeleri Sayfası: https://www.ornek-sitem.com/?kaynak=musteri.php

Kendi Projelerimin Sayfası: https://www.ornek-sitem.com/?kaynak=benim.php

İki linkin de çok masum bir amacı olduğu düşünülebilir. Burada önemli olan ‘kaynak’ adlı
parametredir. Bu parametre ile “musteri.php” ve “benim.php” dosyaları çağrılabilir. Kaynak kod
aşağıda verilmiştir.

```
<?php
$dosya = $_GET[‘kaynak’];
if(isset(“sayfalar/” . $dosya)) {
 include(“sayfalar/” . $dosya);
} else {
 include(“hata.php”);
}
?>
```

LFI açığı tam burada devreye girer. Kodda da görüldüğü gibi `kaynak` değeri ne olursa olsun
sadece sunucuda var olup olmadığı kontrol edilip, hemen altındaki`include(“sayfalar/” . $dosya);`
satırında başka bir kontrol yapılmadan dosya doğruca çağrılmıştır. Kötü niyetle düşünülürse burada
var olmayan ama sunucuda var olan başka bir dosya çağrılabilir. Örneğin Linux sunucularda `/etc/
passwd` dosyası kullanıcı adlarını ve şifrelerini saklar. Bu dosyaya erişilirse sunucu şifresi elde
edilir. Bunun için link aşağıdaki gibi değiştirilip dosyaya erişim denenebilir.

https://www.ornek-sitem.com/?kaynak=../../../../../../../../../../../../etc/passwd

Burada önemli nokta, sunucuda var olduğu bilinen dosyanın konumu bilinerek veya tahmin
edilerek adres girilmesidir. Örneğin `passwd` dosyası her zaman `/etc/passwd` konumundadır ama
site `/var/www/projeler/okul_projeleri/web_dersi/ornek-sitem.com` adından yayın yapabilir. Bu
durumda `passwd` dosyasına erişebilmek için kök dizine kadar geri gidilmesi, ardından tekrar
gerçek yoldan ilerlenerek dosyaya erişilmesi gerekir. Aynı yöntemle projenin `config.php` dosyası
veya önemli başka bir dosya okunabilir.

**Örnek**

RFI açığına örnek için URL’den dosya çağrılabilen bir link olsun. Aşağıdaki kodda görüldüğü
üzere hiçbir kontrol yapılmadan $_GET ile gelen kaynak linki doğruca çalıştırılmak istenmiştir.

```
<?php
 include($_GET[“kaynak”]);
?>
```

Bu durumda masum bir dosya çağırmak yerine aşağıdaki gibi bir yöntemle sunucuda hazırlanan
zararlı dosya çalıştırılabilir.

Her ne kadar örnek kod ve anlatım PHP dilinde olsa da aynı durum diğer diller için de geçerlidir.
Bu saldırıdan korunmanın yolu, gönderilen tüm dosyaların hem yollarının hem de içeriklerinin
çok katı kurallarla kontrol edilmesidir. LFI açığında sadece izin verilen klasörlerdeki dosyaların ve
dosya uzantılarının çağrılması şart koşulabilir. RFI açığında ise kullanılan yazılım dilinin ayarlarında
uzaktan dosya çalıştırılması engellenebilir.

<h3>WEB UYGULAMALARINDA OTOMATİZE ARAÇLARLA ZAFİYET TESPİTİ</h3>

Web sitelerindeki zafiyetlerin tespiti gerek kişinin bilgisi dâhilînde kod yapısını inceleyerek
veya çeşitli keşif yöntemleri ile manuel olarak gerekse otomatik test araçları ile sağlanabilir.
Web sitelerine otomatize araçlarla yapılan test sonuçlarındaki zafiyetler tespit edilerek güvenlik
açıklarının kapatılması mümkündür. Sızma ve zafiyet testlerinde otomatize araçlardan faydalanılır.
Web site açıklarını tespit etmek için çok fazla araç vardır. Kali Linux işletim sisteminde de
birçok yönteme uygun araç hazır olarak gelir. Kali Linux işletim sisteminde Uygulamalar, Kali
Linux, Web Applications, Web Vulnerability Scanner yolu izlenerek otomatize web site zafiyet
araçlarına erişmek mümkündür. Kali Linux işletim sisteminde burpsuite, nikto, skipfish, w3af,
whatweb, wpscan gibi çeşitli amaçlara hizmet eden ve web açıklarını bulan otomatize araçlar yer
alır.

Web sitesinde bulunan açıkların tespitinde açığın keşfedilmesi en çok vakit alan şeylerden
biridir. Kullanıcılar bu açıkları keşfetmediği sürece diğer aşamaya geçemez. Gerek kötü amaçlı
kullanıcılar gerekse sızma testi yapan ve güvenlik önlemi almaya çalışan kullanıcılar öncelikle
zafiyetlerin keşfini yapmalıdırlar. Keşif için yukarıda da belirtildiği gibi birçok araç bulunur. Bu
araçlardan bazılarının kullanım amaçları ve bulduğu zafiyetler aşağıda verilmiştir.

**Wafw00f**: Bu araç bir web sayfasının önünde hangi güvenlik duvarı olduğunun keşfinde
kullanılır. Güvenlik duvarının hangi sistemlere sahip olduğu bilinirse ona göre daha özel saldırılar
gerçekleştirilebilir. Bu noktada kullanıcılar güvenlik duvarlarının ve yük dengeleyici cihazlarının
güncelliğinden ve güvenliğinden emin olmalıdır. Kötü amaçlı kullanıcılar, kullanılan cihazı bu
yöntemle belirler.

**Wpscan**: Bu aracı kullanarak wordpress kurulan sitelerin açıklarını keşfetmek mümkündür.
Saldırganlar, wpscan ve wpscan on-line aracını kullanarak wordpress açıklarını keşfeder ve bu
zafiyetleri kullanarak saldırılarda bulunur. Site özellikle wordpress sürümü ve onunla beraber
gelen açıklara karşı güvende tutulmalı ve açıklar kapatılmalıdır.

**Nessus**: Bu araç daha çok iç ağda kullanılır. Lisansları alındığı takdirde mobil cihaz zafiyetlerinden uygulama zafiyetlerine kadar birçok alanda tarama yapabilir. Sunucu ağı ve son kullanıcı
ağları tek seferde nessus ile taratılıp, zafiyetler öğrenilerek gerekli aksiyonları (güncelleme vb.)
alınabilir. Nessus Professional ücretli bir programdır. Nessus Home ise ücretsiz kullanılabilecek
sürümüdür. 

**Nikto**: Bu araç, web sunucularına karşı kapsamlı testler gerçekleştiren bir açık kaynak (GPL) web
sunucusu tarayıcısıdır. Ayrıca birden çok dizin dosyasının varlığı, HTTP sunucusu seçenekleri gibi
sunucu yapılandırma ögelerini kontrol eder ve kurulu web sunucuları ile yazılımları tanımlamaya
çalışır. Nikto aracı ile web sitesi zafiyetleri çok kolay tespit edilebilir.

**Nmap**: Ağ keşfi ve güvenlik denetimi için ücretsiz ve açık kaynak bir araçtır. Birçok sistem ve ağ
yöneticisi nmap aracını ağ envanteri ve hizmet güncelleme programlarını yönetme veya hizmet
çalışma süresini izleme gibi görevler için de yararlı bulur. Bu araç; ağda hangi bilgisayarların mevcut
olduğunu, bu bilgisayarların hangi hizmetleri sunduğunu, hangi işletim sistemlerini çalıştırdığını,
ne tür paket filtrelerinin veya güvenlik duvarlarının kullanıldığını ve düzinelerce başka özelliği
belirlemek için ham IP paketlerini kullanır. Nmap, büyük ağları hızla taramak için tasarlanmıştır.

**Skipfish**: Google tarafından desteklenen ve web uygulaması güvenlik testlerinde kullanılan
araçlardandır. Güvenlik zafiyetlerinin yanı sıra sözlük taraflı taramalar da gerçekleştirebilir.

**W3af**: Web uygulamaları için kullanılan saldırı ve denetim programıdır. Bu araçla web sitesi
analizi ve zafiyet taraması yapılabilir.

<h3>W3af Aracının Kullanımı </h3>

W3af aracı kullanılarak web sitelerinde zafiyet taramasının otomatik bir şekilde yapılması
sağlanabilir. Bu araçla birçok zafiyetin keşfedilmesi mümkündür. XSS açıkları, SQL injection
açıkları, SSI detection, LFI açıkları, RFI açıkları, Buffer Overflow açıkları gibi birçok açık w3af ile
tespit edilebilir.
W3af aracı, Kali Linux işletim sisteminde hazır olarak gelir. Uygulamalar, Kali Linux, Web
Applications, Web Vulnerability Scanner, w3af yolu izlenerek veya uçbirime w3af yazılarak açılır.
Uygulama açıldıktan sonra tarama yapılacak web sitesi yazılarak zafiyetlerin keşfine başlanabilir.

**W3af Aracıyla Web Site Zafiyetlerinin Keşfi**

Aşağıdaki işlem adımlarına göre meslek.eba.gov.tr adresinin zafiyet taramasını yapınız.

1. Adım: Kali Linux işletim sistemini kullanarak w3af aracını açınız ve zafiyet taramasını
otomatize yapmak için hızlı tarama alanını tıklayarak meslek.eba.gov.tr’yi hedef adres kısmına
giriniz.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/w3af.PNG">

2. Adım: Taramanın sonuçlanmasını bekleyiniz ve sonuçları Log, Vulnerabilities alanından
görüntüleyiniz. Taramanın sonucunda hiç açık olmadığını doğrulayınız.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/w3af1.PNG">

3. Adım: Tarama sonucunda bulunan açıkları görüntüleyiniz.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/w3af2.PNG">

<h3>WEB UYGULAMALARI GÜVENLİK DUVARI (WAF) VE UYGULAMA FİLTRELERİNİ ATLATMA </h3>

Web uygulamalarını geliştiriciden bağımsız olarak saldırılara karşı korumak için Web
Application Firewall (WAF), bir başka deyişle web uygulamaları güvenlik duvarı kullanılır. Bu
sayede özel bir koruma sağlanabilir. Normal güvenlik duvarları sadece gelen ve giden paketleri
kontrol eder, ona göre işlem yapar. WAF ise normal güvenlik duvarlarının yaptığı işin yanında
gelen ve giden paketlerde zararlı içerikler olup
olmadığının da kontrolünü sağlar. Uygulama
geliştiriciler kod yapılarını hazırlarken veri giriş
alanlarını filtreleyerek web uygulamalarını
güvenli hâle getirirler. Bunun yanında uygulama
katmanında bulunabilecek bir WAF ile de
güvenliklerini sağlamak isterler. WAF dışında
IPS sistemleri de kullanılır. IPS’ler saldırı tespiti,
analizi ve engellenmesi için kullanılır. Gelen ve
giden paketlere bakılarak, zararlı bir içerik olup
olmadığı kontrol edilir. Uyarının yanında çeşitli
aksiyonlar da alır. Zararlı içerik tespit edilmesi
durumunda trafik kesilebilir ve engelleme işlemi
yapılabilir.

Alınan tüm önlemlere rağmen yanlış yapılandırmalar, korumanın devre dışı bırakılması veya
geleneksel güvenlik duvarı gibi sadece kara listeye dayalı bir güvenlik önlemi yapılandırılmasının
olması bu sistemlerin atlatılmasına sebebiyet verebilir. Sistemi atlatmak için kullanılabilecek
yöntemlerden bazıları aşağıda verilmiştir.

<h3>SSL Kullanarak WAF Atlatma</h3>

WAF yapılandırmalarında sıklıkla SSL yapılandırmaları doğru yapılmaz veya SSL servisleri hiç
yapılandırılmaz. Bu bilgi dâhilînde çeşitli yöntemler kullanılarak WAF/IPS sistemlerinin atlatılması
mümkündür.

SSL, kullanıcılar ile web uygulamaları arasındaki trafiği şifreleyerek güvenli bir ortam sağlayan
sistemdir. SSL, güvenli veri iletimi sağlamak için kullanıcı ve sunucu arasındaki trafiği şifreler. Bu
kanaldan aktarılan saldırı aktivitelerinin görülebilmesi için SSL trafiğinin bu sistemler üzerinde
sonlandırılması veya trafiğin açıldıktan sonra sunuculara yollandığı bir bölgede (SSL offloader
veya reverse Proxy sistemleri ile sunucular arasında) konumlandırılması gerekir. Dolayısıyla bu
şekilde konumlandırılmayan saldırı tespit sistemleri, SSL trafiğini analiz edemez ve saldırıları
engelleyemez. Gerekli ayarların yapılıp yapılmadığını anlamak için kullanılabilecek en basit
yöntem, saldırı tespit sistemi tarafından engelleneceği bilinen bir isteğin sunucuya hem HTTP hem
de HTTPS veya SSL aktif edilmiş sistem üzerinden gönderilmesidir. Örneğin GET /../../../../../etc/
passwd HTTP/1.0 dizin atlatma tekniğini kullanan bir saldırı imzası ile bu işlem gerçekleştirilebilir.
İlgili istek her iki kanaldan gönderildiğinde de engellenebiliyorsa gerekli ayarlar yapılmış demektir.
Windows işletim sisteminde putty adlı uygulama kullanılarak SSH tünelleme yapılabilir. Bunun
yanı sıra sshuttle adlı araçla SSH tünelleme işlemi basit ve hızlı bir şekilde gerçekleştirilebilir.

<h3>Güçlü SSL İmzalarıyla Sistemleri Atlatma</h3>

Sunucu üzerinde desteği bulunan SSL Chip’lerin kullanımı durumunda güvenlik sistemini
atlatmak mümkündür. Bunun için Diffie-Hellman anahtar değişimi kullanılabilir. Bu, kriptografik
anahtarların değişiminde kullanılan özel bir yöntemdir ve kriptografi alanında uygulanan ilk
pratik anahtar değişimi örneklerinden biridir. Diffie-Hellman anahtar değişimi metodu, iki tarafın
güvensiz medya üzerinden karşılıklı ortak gizli anahtar elde etmelerine olanak sağlar. Bu anahtar
daha sonra bir simetrik anahtar şifre ile güvenli olmayan kanaldan iletişimi şifrelemek için
kullanılabilir.

<h3>Filtreleme İfadelerini Değiştirmek</h3>

WAF sistemleri genellikle önceden oluşturulmuş kara liste (İstek içinde SELECT ifadesi
geçiyorsa engelle.) ve beyaz liste (Parametre değeri yalnızca 0 ve 65535 arasında olabilir,
 Web Güvenliği 344
bu kurala uymayan bir istek geliyorsa engelle.) ile gelen istekleri karşılaştırarak, bir saldırı
olup olmadığını tespit eder. Özellikle kara liste kontrolleri belirli ifadeler oluşması durumunda
saldırıları tespit edeceği için sadece ' , ", >, <, / gibi ifadeleri gönderildiğinde bu tip istekleri
engelleyemeyebilir. Örneğin aşağıdaki gibi bir istek güvenlik kontrollerine takılırken parametrelerin
sonunda yapılacak ufak değişikliklerle WAF atlatmak mümkündür.

**WAF’a Yakalanan İstek**

http://www.ornek-site.com.tr/giris.php?id=123’+union+selec+1,2,3--

**WAF’a Yakalanmayan İstek**

http://www.ornek-site.com.tr/giris.php?id=123’

Böylelikle sisteme SQL injection işlemi yapılıp yapılamayacağı tespit edilebilir.

<h3>HTTP Parametre Değişikliğiyle Sistemi Atlatma</h3>

Saldırgan, HTML parametrelerini değiştirerek sistemi atlatabilir. Sistem genellikle bazı
parametreleri engellerken bazılarını içeriye alabilir. Bu sayede sistem atlatılabilir.

**WAF’a Yakalanan İstek**

http://www.ornek-site.com.tr/giris.php?id=123

**WAF’a Yakalanmayan İstek**

http://www.ornek-site.com.tr/giris.php?id=789

Sistemde kullanılan sunucu türlerine göre sistemlerin vereceği tepkiler değişir. Bu durumda
hangi sistemin kullanıldığının tespitinin ardından filtreleme işlemi o sunucuya göre değiştirilmelidir.

<h3> Basit Karmaşıklaştırma Teknikleriyle Atlatma </h3>

Özellikle uygulama geliştiriciler bazı problemleri engellemek için belirli anahtar kelimelere
göre filtreleme fonksiyonları hazırlayabilir. Örneğin Cross-Site Scripting saldırılarını engellemek
için script, alert, src; SQL Injection saldırılarını engellemek için ise select, union, from gibi ifadeler
geçen istekleri filtreleyen veya bunları içerikten silerek çözüm üretmeye çalışan fonksiyonlarla
sıkça karşılaşılır ancak filtreleme fonksiyonlarında gerekli kontrollerin düzgün yapılmaması nedeni
ile saldırı ifadeleri içinde büyük ve küçük harflerin karışık kullanımıyla gerçekleştirilen saldırılarda
başarı elde edilebilir.

Örneğin bu tarz filtrelerde <script>alert(123)<script> gibi bir istek engellenebilirken, gerekli
kontrollerin düzgün yapılmaması durumunda <ScriPt>aLerT(123)</sCRipt> gibi büyük ve küçük
harfler bir arada kullanılarak karmaşıklaştırılmış bir istek filtreden kaçabilir.
 
 <h3>Encoding Tekniklerini Kullanmak</h3>
 
 Kara listeye alma temelli kontrolleri atlatmak için kullanılabilecek bir diğer yöntem, saldırı
isteklerini kısmen veya tamamen sunucu tarafından desteklenen encoding teknikleri ile
değiştirerek yollamaktır. Örneğin çoğu uygulamada web uygulama problemlerinin ortaya
çıkmasına neden olan ‘, “, <, >, /, ; , |, \ gibi karakterlerin filtrelendiği veya bu karakterlerinin
kullanılması durumunda önlerine \ karakteri eklenerek (escaping) veya çıktılarda encode
edilerek işlendiği görülür ancak bu işlem sadece bu karakterlerin normal veya birkaç farklı
gösterimi için gerçekleştirilmesi durumunda değişik encoding yöntemleri ile kontroller atlatılabilir.
 
 ‘ karakterinin farklı gösterimleri aşağıda verilmiştir.
 
URL Encode -%27<br>
Double URL Encode -%2527<br>
UTF-8 (2 byte) -%c0%a7<br>
UTF-8 (JAVA) -\uc0a7<br>
HTML Entity -&apos;<br>
HTML Entity Number -&#27;<br>
Decimal -&#39<br>
Unicode URL Encoding -%u0027<br>
Base64 -Jw==<br>

 Güvenlik filtreleri tarafından yakalanan saldırı ifadeleri değişik encoding teknikleri ile birlikte
kullanılarak uygulamanın ve web sunucusunun da izin vermesi durumunda bu kontrollerin
atlatılması mümkün olabilir.
Bütün bu atlatma yöntemlerinin yanında aynı işlevi gören farklı mantıksal operatörler
kullanmak, aynı işlevleri gören farklı fonksiyonlar kullanmak, script tag işaretleri olmadan XSS
zafiyetini kullanacak saldırıları gerçekleştirmek mümkündür. 
 
 
 
 
 
