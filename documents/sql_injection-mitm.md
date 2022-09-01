# SQL INJECTION ATAĞI

Bilgisayara bilgiler bir şekilde kaydedilmeli ve gerektiğinde o verilere ulaşılabilmelidir. Bu
nedenle de veri tabanı denilen kavram ortaya çıkmıştır. Veri tabanı, bilgileri belirli bir formda
kaydeder ve kullanıcılar gerektiğinde veri tabanından verilere ulaşır. Bu noktada veri tabanına
bilgileri kaydedip geri çağırmak için genellikle SQL dili kullanılır.
SQL Injection, bir saldırgan tarafından uygulamanın veri tabanı sunucusuna yapılan sorgulara
müdahale edilip, SQL dilinin özelliklerinden faydalanılarak söz dizimi hatalarının veya özel
karakterlerdeki anormal davranışların kullanıldığı zafiyet türüdür. Bu zafiyet kullanılarak normalde
yetkisiz kişilerin ulaşamayacağı verilere saldırgan kolaylıkla erişebilir. Verilere erişmekle kalmaz,
saldırgan bu verileri manipüle edebilir, değiştirebilir, silebilir veya kaydedebilir. SQL Injection en
tehlikeli atak türlerinden biridir. Bu atak bazı durumlarda saldırganın bir arka kapı (backdoor)
oluşturmak veya DoS atağı gerçekleştirmek için ilk kullandığı atak türü olabilir. Başarılı bir saldırı
sonucunda parolalar, kredi kartı bilgileri, kullanıcı bilgileri gibi hassas verilere yetkisiz kişilerin
erişmesi kurbana büyük kayıp verdirecektir. Ayrıca saldırgan bu atakla içeride kalıcı bir arka kapı
oluşturabilir ve uzun süre fark edilmeyerek iç ağda olan biteni izleyebilir. 

<h3>SQL Injection Atak Türleri</h3>

SQL Injection atak türleri In-Band, Blind ve Out Of Band ana başlıklarında gruplandırılabilir.
Band, bir iletişim kanalının kapasitesidir. Teknik olarak bir istemci, bir sunucuya HTTP paketi
gönderdiğinde istemci ile sunucu arasında açılan soketin (band) kapasitesini ifade eder. 

1. In-Band SQL Injection (Classic)
Klasik Injection tekniği olarak isimlendirilen In-Band (bant içi) SQL Injection, HTTP Post ve Get
isteklerinin aynı iletişim yolu üzerinden gönderilip alındığı atak türüdür. Saldırgan SQL Injection
atağını başlatmak, devam ettirmek ve durdurmak için aynı kanal üzerinden iletişim kurar. Bu
atağın Erorr Based ve Union Based olmak üzere iki yaygın çeşidi vardır.

a) Error Based SQL Injection

Veri tabanına yazılan çeşitli sorgular ile veri tabanının kasıtlı olarak hata vermesini sağlayan ve
 SQL Injection ve Man In The Middle (MITM) 255
bu hataları kullanarak daha derinlemesine sorgular yazma imkânı veren In-Band atak türüdür.
Bu sayede saldırgan, veri tabanının versiyon bilgisi ve tablo adı gibi önemli bilgilere erişebilir.
Bir sonraki yazacağı sorgularda bu bilgileri kullanabilir. Ayrıca versiyon bilgisini öğrenmesi
durumunda güncel olmayan bir versiyon ise versiyon ile ilgili açıkları, zafiyetleri tespit edebilir.

b) Union Based SQL Injection
Veri tabanına uygulama tarafından gönderilmek istenen sorguya ek yeni sorgular yapmak ve
sorgu derinliğini geliştirmek için iki veya daha fazla sorguyu birleştiren, “UNION” anahtar kelimesi
ile yapılan SQL Injection atak türüdür. Bu atak türünde en çok dikkat edilmesi gereken nokta, ana
sorgudan dönen sütun sayısı ile UNION sorgusu sonucu dönen sütun sayısının eşit olmasıdır.

Ana sorguda kaç sütun döndüğünü tespit etmek için aşağıdaki yöntemler kullanılabilir.

1. Yöntem: ‘ ORDER BY 1--

 ‘ ORDER BY 2--
 
 ‘ ORDER BY 3--
 
 …
 
2. Yöntem: ‘ UNION SELECT NULL --

 ‘ UNION SELECT NULL NULL --
 
 ‘ UNION SELECT NULL NULL NULL --
 
 …
 
 2. Blind SQL Injection (Inferential)
 3. 
Saldırgan ile hedef uygulama arasında gerçek herhangi bir veri alışverişinin yapılmadığı
bir atak çeşididir. Saldırgan, sunucuya verileri gönderir ve veri tabanının yapısı hakkında daha
fazla bilgiye ulaşmak için sunucunun yanıtını ve davranışlarını gözlemler. Saldırgan, sorguların
sonucunu göremez veya rastgele bir sorgu göndererek deneme yanılma yoluyla gelen cevaba
göre yeni bir strateji oluşturur. Bu nedenle bu atak türü Çıkarımsal (Inferential) veya Kör (Blind)
SQL Injection olarak da isimlendirilir. 

a) Boolean (True/False) Based SQL Injection

Bu atak türünün adından da anlaşılacağı üzere saldırgan, veri tabanına bir sorgu gönderir ve
cevap olarak True (Doğru) veya False (Yanlış) bilgisi geri gelir. Çoğu SQL sorgusu bir koşul içerir. Bu
koşul sağlanıyorsa sonuç döner ve kayıtlar görüntülenir fakat bu teknikte saldırgan, uygulamanın
hangi koşulu belirttiğini bilmediği için normalde False dönen cevabı True yaparak gerekli veri
tabanı kayıtlarına ulaşabilir. 

b) Time Based SQL Injection

SQL sorguları genellikle uygulama tarafından eş zamanlı olarak çalışır. İsteğe hemen cevap
verilir fakat saldırgan, isteğin belirli bir süre sonra çalışmasını çeşitli komutlarla öteleyebilir.
Bu sayede gönderdiği sorgunun çalışıp çalışmadığını test edebilir, veri tabanını bu süre içinde
bekleterek cevap vermesini geciktirebilir. 

3. Out Of Bant (OOB) SQL Injection

SQL sorguları genelde sunucu ve istemci arasında olur. Bu teknikte saldırgan, sunucuya
gönderdiği sorgular ile DNS, HTTP gibi protokol isteklerini sorguya enjekte ederek sunucunun
iletişim dışına çıkmasını (Out Of Band) ve başka bilgileri istemesini (DNS isteği gibi) tetikler. Bu
tekniğin diğer tekniklerden farkı, saldırganın veri tabanından almak istediği bilgileri aramak için
(Error-Based, Union Based), True/False (Boolean Based) sorgusu yazmak yerine sistemdeki verileri
HTTP, DNS veya SMB protokolleri üzerinden iletmesidir. Kısaca saldırgan, bilgileri toplamak ve
sonuçları görmek için aynı iletişim kanalını kullanmaz. Çok yaygın bir teknik değildir ve veri tabanı
sunucusunda aktif çalışan hizmetlere bağlı olarak gerçekleştirilebilir. 

SQL Injection atağı için gerekli kurulumlar önceden yapılmalıdır. SQL Injection atağı yapabilmek
için zafiyete sahip bir veri tabanına ihtiyaç duyulur. Bu tür atakların yapılmasına olanak veren
çeşitli sanal sistemler vardır. Bu öğrenme biriminde sanal sistemlerden hazır zafiyetlerin yüklü
olduğu DVWA (Damn Vulnerable Web Application), kullanıcıların yetenek ve becerilerini eğitim
amaçlı olarak kolaydan zora geliştirebilme imkânı veren yazılım kullanılacaktır.

<h3>DVWA Konfigürasyonu</h3>

1. Adım: DVWA kurduktan sonra 127.0.0.1 localhost adresini tarayıcıya yazınız.

2. Adım: Açılan pencerede kullanıcı adı ve şifre girildikten sonra bir ekranla
karşılaşılır. Bu ekranın en altında yer alan “Create/Reset Database” seçeneğini seçerek bir veri
tabanı kurulum işlemi gerçekleştiriniz. 

3. Adım: Veri tabanı kurulumunu gerçekleştirdikten sonra tekrar giriş yapınız. Yeni kurulan
veri tabanının varsayılan kullanıcı adı “admin”, şifresi ise “password”dür.

4. Adım: Veri tabanı oluşturmadan önceki ekranda çok fazla seçenek yokken
kurulum yapıldıktan sonraki ekranda daha fazla seçenek olduğu görülür. Görsel
8.4’te kırmızı kutu ile belirtilen SQL Injection seçeneğini seçiniz.

<h3>Error Based SQL Injection Atağı</h3>

1. Adım: Error Based SQL Injection atağı için veri tabanının hata vermesini sağlayan kodları
enjekte ediniz. Bunun için User ID kutusuna  tek tırnak (‘) işareti koyunuz.

kullanılan veri tabanı tipinde bu ifadenin tanınmadığını belirten
bir uyarı mesajı geri döner. Dönen hata mesajından hangi veri tabanı yazılımının kullanıldığı
bilgisini öğreniniz.

<h3>Union Based SQL Injection Atağı </h3>

1. Adım: Union Based SQL Injection atağı gerçekleştirmek için kaç tane sütun olduğu bilgisi
öğrenilmelidir. Bunu öğrenmek için order by komutları ile 1’den başlayarak, veri tabanında hata
alıncaya kadar işleme devam ediniz.

**' order by 3#** ...

2. Adım: Yazılan order by komutları sonucunda ‘ order by 3# sorgusunda görüldüğü gibi hata alınır. 
Bu durum, tabloda iki sütun olduğu anlamına gelir. Union sorgunuzu bu değer üzerine kurunuz.

3. Adım: kutu içine **‘ union select database(), version()#**
sorgusunu yazarak ilgili veri tabanı adına ve versiyon bilgisine ulaşınız.

geri dönen sonuçta veri tabanı adının dvwa olduğu ve MariaDB
veri tabanının 10.1.26 versiyonunu kullandığı bilgisine ulaşılır.

4. Adım: Veri tabanı kullanıcı adı ve şifre bilgilerine ulaşmak için:
  **' union select user, password from users#** komutunu verin.
  
Ulaşılan şifreler Surname kısmında bulunur ve md5 formatında sistem tarafından kriptolanmıştır. 
Bu kriptoları çözmek için Kali Linux üzerindeki john, hashcat gibi araçlar kullanılır. 

<h3>Boolean Based SQL Injection Atağı</h3>

1. Adım: User ID bölümüne yazılan bir sorgu sonucu cevap döner. Bir başka deyişle sorgu
sonucu True ise kayıtlar ile karşılaşılır. Burada yazdığınız **1’ or ‘1’=’1** sorgusu ile cevabın her zaman
True olarak dönmesini ve sorgunun her koşulda çalışmasını amaçlayınız. 

2. Adım: yazılan sorgu sonucu hep True değerleri elde edilir. Tüm kayıtlara ulaşınız.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/dvwa.PNG">

<h3>Time Based SQL Injection Atağı</h3>

1. Adım: **1’ sleep(5)#** SQL sorgusunu yazınız. Veri tabanı bu sorgu ile parantez
içinde belirtilen sayı kadar beklemeye geçer ve cevabı hemen göndermez.

2. Adım: Belirli bir zaman geçtikten sonra görüldüğü gibi sorgu sonucu geri
döner. Sistemin hemen vermesi gereken sorgu cevabını belirli zaman sonra verdiğini görü- nüz.
Bu durum, veri tabanı yazılımına müdahale edebildiğinizi gösterir

<h3>Sqlmap Komutunun Kullanımı</h3>

Sqlmap komutu Kali Linux üzerinde yüklü olarak gelir. Web uygulamalarındaki SQL Injection
açıklarını bulmaya ve bulunan açıkları kullanarak hedef bilgisayar üzerinde bu sorguların
çalışmasına olanak sağlayan bir komuttur. Bu komut ile veri tabanı türü, adı,
kullanıcıları, veri tabanı tabloları vb. tüm bilgilere ulaşabilmek mümkündür. Komut satırında -h
parametresi ile yardım sayfası açılarak bu komutun kullanımları daha detaylı incelenebilir.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/sqlmap.PNG">

**sqlmap -u "http://localhost/vulnerabilities/sqli/** Komutunu deneyiniz.

<h3>Uygulama</h3>

1. Adım: sqlmap komutu ile hedefteki SQL Injection açıklarını tespit ediniz.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/sqlmap2.PNG">

• -u parametresi ile sqlmap fonksiyonuna bir URL belirtileceği bildirilir.

• --dbs parametresi ile veri tabanı listesi ekrana getirilir.

2. Adım: Veri tabanı tablolarını ve tablo isimlerini ekrana yazdırınız.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/sqlmap3.PNG">

• -D parametresi ile veri tabanı adı belirtilir.

• --tables parametresi ile tespit edilen tablo isimleri ekrana yazdırılır.

3. Adım: Veri tabanı kolonlarını ekrana getiriniz.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/sqlmap4.PNG">

• -T parametresi ile tablo adı belirtilir.

• --columns parametresi ile kolon bilgileri ekrana yazdırılır.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/sqlmap5.PNG">

görüldüğü gibi tüm kullanıcı isimleri ve şifreleri hashlenmiş bir şekilde
ekrana yazdırılmıştır. Şifreler, hash değerlerinin yanında parantez içlerinde çözülmüş olarak
görülmektedir.

4. Adım: Kolonlardaki değerleri ekrana yazdırınız

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/sqlmap6.PNG">

• -C parametresi ile kolon adı belirtilir.

• --dump parametresi ile belirtilen kolonlardaki bilgiler ekrana yazdırılır.

Sqlmap komutu kapsamlı, geniş ve çok kullanılan bir komuttur. Veri tabanı ile ilgili tüm işlemler
bu komut üzerinden gerçekleştirilir. Bu komut; bir istek dosyası yüklemek, post isteği yapmak,
formlara parametre girmek, HTTP Authentication (Yetkilendirme), Proxy ve Tor kullanarak sorgu
çalıştırma gibi çok kapsamlı yeteneklere sahiptir. 

<h2>MAN IN THE MIDDLE (MITM) ATAĞI</h2>

İletişim hâlindeki iki bilgisayarın (istemci-istemci, istemci-sunucu vb.) arasına girerek orada
olup biteni dinleyen, iletişimi üstüne çekerek trafiğin kendi üstünden akmasını sağlayan veya
kurulan iletişimde paketleri değiştirerek veri manipülasyonuna sebep olan atak türüdür. Saldırgan,
iki cihazın arasına girdiği için ortadaki adam (MITM) olarak adlandırılır. MITM, diğerlerine göre
en tehlikeli atak türüdür çünkü saldırgan direkt olarak kişisel bilgileri (şifreler, hesaplar, kredi
kartı bilgileri vb.) çok kolay bir şekilde ele geçirebilir. Bu atak, yerel ağdan yapılabildiği gibi uzak
ağdan da gerçekleştirilebilir.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/mitm.PNG">

<h3>MITM Saldırı Türleri</h3>

Bu öğrenme biriminde MITM saldırısının sahte erişim noktası, ARP sahtekârlığı, DNS
sahtekârlığı türleri anlatılacaktır. 

<h3>Sahte Erişim Noktası (Fake Access Point)</h3>

Sahte erişim noktası atak türünde saldırgan, var olan erişim noktasını (Wi-Fi) de-authentication
yöntemiyle devre dışı bırakır. Devre dışı bıraktığı Wi-Fi adını (SSID) v1, v2 gibi sahte ek isimlerle
kullanır. Kullanıcının ilk bakışta fark edemeyeceği bir isimle kendi Wi-Fi ağını yayınlar. Örneğin
SSID’si “Okul” olan bir Wi-Fi ağını “Okulv2”, “Okul-Kat1” gibi adlar vererek isimlendirir. Bu
durum, ağa bağlanan kişilerin değişikliği fark etmemesini sağlar. Bağlantısı kopan tüm cihazlar,
bağlanması gereken Wi-Fi’ye değil de saldırganın yayınladığı ağa bağlanır. Saldırgan artık tüm ağ
trafiğini üzerine çekmiştir ve bu trafiği yönetebilir, yönlendirebilir, manipüle edebilir. 

<h3>ARP Sahtekârlığı (ARP Spoofing)</h3>

ARP, adres çözümleme protokolüdür. IP adreslerini MAC adreslerine çözümlemek için
kullanılır. Başka bir ana bilgisayar gibi görünmeye çalışan saldırgan, yanıt vermemesi gereken
isteklere kendi MAC adresini kullanarak yanıt verir. Böylelikle istemci, yanıt veren bilgisayarı bir
ağ geçidi olarak algılar ve trafiği ona yönlendirir. Saldırgan daha sonra üstünden akan trafik ile
tarayıcıda depolanan PII (Personal Identifiable Information) kişisel tanımlama bilgilerini analiz
edebilir, hedefe zarar vermek için kullanabilir.

<h3>DNS Sahtekârlığı (DNS Spoofing)</h3>

DNS, alan adlarını IP adresine çözümleyen protokoldür. DNS önbellek zehirlenmesi de denilen
bu atak, yasal çevrimiçi trafiğinde kullanıcının güvendiği bir web sitesinin sahtesinin yapıldığı
veya kullanıcıyı sahte bir web sitesine yönlendirmek için hazırlanan DNS kayıtlarının hedefe
ulaştırıldığı bir saldırı türüdür. 

<h3>MITM Saldırı Teknikleri</h3>

MITM ataklarında saldırgan, hedefi ağına düşürmek için değişik teknikler kullanır. Bu öğrenme
biriminde paket koklama, paket enjeksiyonu, oturum çalma, SSL açma anlatılacaktır. 

<h3>Paket Koklama (Sniffing)</h3>

Paket koklama, saldırganın ağ üzerinde dolaşan paketleri toplayarak, o paketlerde geçen
bilgileri açıp okuması sonucu oluşan tekniktir. Bu sayede saldırgan, hedefin neler yapmak istediği
hakkında bilgi toplar, ağın kendi üzerinden akmasını sağlar veya ağ trafiğini manipüle eder.
Sniffing sık kullanılan bir tekniktir. 

<h3>Paket Enjeksiyonu</h3>

Hedef ve internet arasındaki iletişimi dinleyen (sniffing) saldırgan, bu aşamada hedefe zararlı
paketler gönderir ve hedefin indireceği paketlere müdahale edebilir. Bunu yapabilmek için saldırgan, 
ağ cihazlarını dinleme moduna (Promiscuous mode) alır. Bu sayede örneğin a.exe isimli
programı indirmeye çalışan bir hedefin anlamaması için aynı isimli (a.exe) ama sahte (fake) yazılım indirmesi sağlanır ve hedefe zararlı yazılım enjekte edilir.

<h3>Oturum Çalma</h3>

Web sitelerinde oturum açıldığında arka planda session (web oturumu) denilen olay
gerçekleşir ve oturum bilgilerini kaydeder. Bu sayede web sitesinde her yeni linke tıklandığında
veya form açıldığında oturum kapatılmadığı için tekrar tekrar şifre girmek gerekmez. Bu noktada
saldırgan, trafiği koklayarak bu oturum açma belirteçlerine erişebilir ve oturumu ele geçirebilir.
Bu snifing araçlarını kullanan saldırgan, meşru isteklerde bulunarak hedefin bilgileri ile oturum
belirteçlerini tanımlayabilir ve kullanabilir. 

<h3>SSL Çalma (SSL Strip)</h3>

HTTP ve HTTPS, internette en sık kullanılan protokollerdendir (Son yıllarda daha güvenli
olan HSTS kullanılmaktadır.). HTTP güvensiz, HTTPS ise SSL kullandığı için güvenli kabul edilir.
HTTP paketlerini çözmek ve işlemek, HTTPS’ye göre daha kolaydır. Bu nedenle HTTPS olan web
sitelerinin HTTP sitelerine indirgenmesini sağlayan araçlar mevcuttur. Saldırganlar bu paketleri
engellemek, HTTPS tabanlı web sitesinden gelen istekleri değiştirerek HTTP tabanlı siteye
dönüştürmek ve yönlendirmek için SSL çalma tekniğini kullanırlar. 

Örnek Olay;

Ücretsiz bir Wi-Fi ağı bulduğuna sevinen genç Giray, heyecanlı bir şekilde hemen bilgisayarından
Wi-Fi ağına bağlanır ve maillerini okumak ister. Süreç Giray için şöyle işleyecektir:
Giray’dan gelen mailine giriş bilgisi HTTP üzerinden olduğu için saldırganın bilgisayarında
çalışan SSL Strip bu bilgileri alacak ve kaydedecektir. Bu bilgileri kullanarak saldırgan, mail
servisinde HTTPS bağlantısı ile oturumu açacaktır. Mail servisinden dönen HTTPS cevapları HTTP
ile değiştirecek ve Giray’a geri gönderecektir. Böylece kullanıcı fark etmeden, HTTPS kullandığını
düşünerek HTTP üzerinden işlemlerini gerçekleştirecektir. 

<h3>MITM Araçları</h3>

MITM ataklarında saldırganların kullandığı birden fazla araç mevcuttur. Bu ataklarda en çok
kullanılan araçlar; bettercap, hetty, proxy.py, burp, mitmproxy, ettercaptir. 

<h3>Bettercap Aracı</h3>

Bettercap; bir ağa karşı MITM atakları gerçekleştiren, gerçek zamanlı olarak HTTP, HTTPS veya
TCP trafiğini monitör eden (izleyen), yöneten, yönlendiren, sniffing (koklama) yapan güçlü, esnek
ve taşınabilir bir araçtır. Go dilinde yazılmıştır. Açık kaynak ve kapalı kaynak işletim sistemlerinde
çalışabilir. Bu araç, Wi-Fi ve Ethernet ağlarında, Bluetooth cihazlarında aktif ve pasif IP ve port
taraması yapabilir.
Bettercap aracı hâlihazırda Kali Linux içinde gelmez. Sonradan kurulması gerekir. 

**sudo apt-get install bettercap** komutu ile indirebiliriz.

<h3>Bettercap Aracının Kullanımı ve Çalıştırılması</h3>

1. Adım: Daha önceden kurulan bettercap aracını **sudo bettercap iface eth0** komutu ile çalıştırılır.

Bettercap aracı parametresiz olarak çalıştırabilir ve dinlemesi gereken arayüz (interface)
yazılabileceği gibi bu şekilde iface parametresi ile direkt bir arayüz belirtilerek de çalıştırılabilir.
eth0, ethernet arayüzünün Kali Linux işletim sistemindeki karşılığıdır. 

2. Adım: Çalışan servisleri görmek veya hangi komutun hangi parametre ile çalışacağını öğrenmek için **help** komutunu yazınız.

3. Adım: **net.probe on** komutuyla etraftaki cihazların bulunmasını ve MAC
adres bilgileri ile IP bilgilerinin alınmasını sağlayınız. 

4. Adım: **net.show** komutu ile net.probe servisinin çalışıp çalışmadığını bir tablo ile de
görüntüleyiniz.

net.show komutu ile IP ve MAC adreslerine, ağ isimlerine
(Name), üretici firma (Vendor) gibi bilgilere erişilebilir. 

5. Adım: help komutu ile arp.spoof işleminin nasıl çalıştırılacağını, çalıştırılırken hangi parametreleri alabileceğini görünüz.

**help arp.spoof**

arp.spoof on: ARP spoof atağını başlatır.

arp.ban on: Bu atak başlatıldığında karşı tarafa de-authentication saldırısı yapılmış gibi olur
ve hedefin ağ ile ilişiği kesilir.

arp.spoof off: ARP spoof atağı sonlandırılır.

arp.ban off: ARP ban atağı sonlandırılır.

Parameters kısmından arp.spoof atağının daha efektif çalışması sağlanabilir.

Varsayılan (default) olarak, kapalı (false) gelen bu parametreler açılarak atağın daha kullanışlı ve doğru
çalışması ayarlanabilir.

arp.spoof.fulldublex: Bu parametre doğru olursa hem hedefe hem de modeme atak
gerçekleştirilir. Bu durum, yapılan atağın daha iyi çalışmasını sağlar.

arp.spoof.internal: True seçeneği ayarlanırsa yerel bilgisayarlar arasında bir spoofing işlemi
yapılacaktır. Aksi takdirde external (haricî) ağlardaki gelen ve giden bağlantılar spoof edilir.

arp.spoof.targets: Normalde tek bir hedefe atak yapılırken bu parametre sayesinde birden
fazla hedefe atak yapılabilir. Parametreden sonra IP adresleri virgül ile ayrılarak yazılabilir. 

6. Adım: Görsel’deki parametreleri yazarak arp.spoof konfigürasyonunu tamamlayınız.
Arp.spoof ile ilgili log mesajları da sistem üzerinden görülür. 

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/arpspoofingconfig.PNG">

parametrelerden görüldüğü üzere 192.168.1.21 numaralı makineye bir arp.
spoof saldırısı gerçekleşecektir. Bu saldırı öncesi hedef bilgisayarın MAC adres tablosu Görsel'deki gibidir.

<img src='https://github.com/FazzPy/Cyber-Security/blob/main/img/mactable.PNG'>

arp.spoof on komutu yazıldıktan sonra atak başlar ve MAC adres tablosunda mac adresleri aynı olmuştur.

MAC adresi ile atak yapılan bilgisayarın MAC adresi aynı
olmuştur. Bu sayede modeme giden tüm paketler saldırganın bilgisayarına da gelir.

7. Adım: Bu adıma kadar arp.spoof atağının tüm ayarlamalarını ve yapılandırmalarını yaptınız.
Şimdi ise hedefin yaptığı tüm işlemleri izlemek ve sniffing yapabilmek için net.sniff komutu ile
işlemi başlatınız.

**help net.sniff**

**net.sniff on** komutuyla sniffing işlemi başlatılır. Böylelikle hedefin modemden
istediği tüm bilgiler aynı anda hem modeme hem de saldırganın bilgisayarına gelir. Görsel’de
gelen ve giden web sayfaları, GET istekleri, 200 OK bilgileri gibi çok detaylı logları ve protokolleri
(DNS, HTTP vb.) listelenmektedir.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/netsniff.PNG">

Bu aşamadan sonra saldırgan istediği bilgiye ulaşabilir, istediği bilgiyi değiştirebilir ve hedefe
diğer saldırı yöntem ve tekniklerinin vereceği zararın çok daha fazlasını saniyeler içinde verebilir.
MITM saldırıları, diğer atak türlerinden (dış ağdan gelen saldırılar) en tehlikeli olanıdır çünkü
saldırgan yan odanızda veya karşınızdadır. Saldırganın yapabileceklerinin bir sınırı yoktur.
