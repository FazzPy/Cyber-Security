# DOS / DDOS ATAKLARI

DoS atağı, bir sistemi kullanılamaz hâle getirmek, çevrimdışı yapmak veya o siteye girip
kullanmak isteyen normal kullanıcıları sisteme erişemez duruma getirmek için tasarlanmış bir
atak türüdür. Bu tarz ataklar genelde çok fazla sayıda kullanıcısı olan sistemlere yapılır.
Atağın amacı, hedefi ulaşılamaz yaparak zarara uğratmaktır. Aynı zamanda başka bir atağın fark
edilmemesini sağlayarak dikkatleri farklı yöne çekmek ve hedef şaşırtmak için kullanılır. Örneğin
ön tarafta DoS saldırısı yaparak sistemi meşgul eden saldırgan, arka tarafta fidye (ransomware)
saldırısı yapabilir. DoS saldırıları güvenlik açıklarından, arabellek taşmalarından, yazılım kaynaklı
açıklardan yararlandığı gibi daha çok bir sistemdeki dar boğazlardan faydalanır. Bir sistemin
işleyebileceği en yüksek miktarda trafik, veri bağlantısı, bant genişliği gibi bir eşik değeri olan ve
bir bileşen (RAM, önbellek vb.) tarafından sınırlandırılan bölümleri kullanır. Çoğu DoS atağı bu en
yüksek kapasiteyi aşacak şekilde tasarlanmıştır. Böylelikle o siteye gerçekten erişmek isteyenlere
sistem cevap vermez. Hedef, maddi ve manevi zarara veya itibar kaybına maruz kalır

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/dos.PNG">

DoS atakları farklı türlerde gerçekleştirilir. Bant genişliğine yönelik ataklar, belirli bilgisayarı
(host) ve servisleri düşürmek için yapılan ataklar ile SYN tekniği kullanılarak yapılan ataklar en
yaygın DoS atağı türleridir. Bu atakları gerçekleştirmek için farklı araçlar (tools) kullanılır. Bu
öğrenme biriminde Kali Linux 2021.2 işletim sistemi üzerinden araçlar anlatılacaktır.

<h3>Bant Genişliğini ve Belirli Bir Hostu Düşürmek İçin Kullanılan
 Atak Araçları</h3>
 
 Yapılan bir DoS atağı, çoğu zaman hedefin bant genişliğini tüketir ve normal kullanıcıları
hizmetlere ulaşamaz hâle getirir. Bu atak aynı zamanda bir bilgisayarı ağ trafiğinden düşürmek
için de kullanılır.
Bir ağda bilginin karşıya sorunsuz bir şekilde ulaştığını gösteren unsurlar vardır. Bu unsurlar;
Gizlilik (Confidentiality), Bütünlük (Integrity), Erişilebilirlik (Availability) olarak sıralanabilir. Dos
ve DDoS atakları bu unsurlardan erişilebilirlik kısmını devre dışı bırakarak bilginin bir uçtan diğer
uca ulaşmasını engellemek için kullanılır.

<h3>LOIC (Low Orbit Ion Cannon) Aracı</h3>

LOIC aracı, C# dilinde yazılmıştır. Açık kaynak olarak kullanıma sunulan bu araç Windows ve
Linux platformlarında kolaylıkla kullanılabilir. LOIC en yaygın kullanılan DoS ve DDoS aracı olarak
tespit edilmiştir.

LOIC aracını kullanabilmek için Kali Linux üzerinde mono isimli bir yardımcı araç yüklenmelidir.
Mono, programların çapraz platformu desteklemesi için kullanılan bir araçtır. Mono programı
daha net bir ifade ile .Net Framework’ün Linux tabanlı sistemlerde çalışmasını sağlar. 

Görsel’de görüldüğü üzere mono aracı üç aşamada kurulur ve en sondaki komut ile LOIC
aracı çalıştırılır. LOIC aracı çalıştığında altında ki Görsel’deki ekran ile karşılaşılır.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/mono.PNG">

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/loic.PNG">

**Not : Star Wars temalı olsaydı güzel olurdu...**

Bu araç ayrıca DDoS saldırısı gerçekleştirmek için diğer bilgisayarlarla haberleşebilir. Aynı
zamanda zombi (zararlı yazılım enjekte edilmiş cihazlar) makineleri de yöneterek daha büyük
zararlar verebilecek DDoS atakları gerçekleştirir. Bu araç, sızma testi (penetration test) için
sistemlerin DoS saldırılarına karşı dayanıklılığını ve stres testine vereceği tepkiyi ölçmede kullanılır.

<h3>OWASP SwitchBlade</h3>

Hizmet reddi atağı gerçekleştiren bir başka araç yeni adıyla OWASP SwitchBlade, eski adıyla
DoS HTTP POST olarak bilinen araçtır. Bu araç, sitelerdeki DoS ataklarına karşı test için yazılsa
da saldırganlar bunu kötü amaçlı kullanabilir.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/switchblade.PNG">

1 No.lu Alan: Atak tipinin seçildiği alandır. Slow headers, Slow POST ve SSL Renegotiation
olmak üzere üç farklı atak tipi vardır.

a) Slow Headers: Bu atak tipi seçildiğinde araç çok yavaş bir hızda HTTP başlıkları gönderir
ancak hiçbir zaman verinin tamamını göndermez. İletişimi sonlandırmamak için ara ara başlık
bilgilerini gönderir. Bu nedenle sunucunun tüm kaynakları meşgul olur.

b) Slow POST: Saldırgan, bu atak tipinde web sitesinin form alanlarına POST işlemi
yapacaktır. Form verilerini çok yavaş bir hızla iletip, daha fazla veri geleceğini zannederek
sunucunun kaynaklarının tükenmesine neden olacaktır.

c) SSL Renegotiation: SSL yeniden anlaşma olarak isimlendirilen bu atak tipinde saldırgan,
devamlı yeni SSL anlaşmaları göndererek sunucunun tüm CPU’sunu kullanmayı amaçlar.

2 No.lu Alan: Burada aracın daha karmaşık çalışmasını sağlamak için çeşitli parametreler
bulunur. Bu parametreler; bağlantılar (connectons), bağlantı hızı (connection rate), zaman aşımı
(timeout) değeridir.

3 No.lu Alan: Bu kısımda ise aracı çalıştırmak ve araçtan çıkmak için butonlar bulunur. Gerekli
atak tipleri ve parametreler girildikten sonra “Run attack” butonuna basılarak atak başlatılır.
“Quit” butonuyla da araçtan çıkılır.

<h3> HULK Aracı </h3>

HULK (HTTP Unbearable Load King) aracı belirli bir hostu hedef alabildiği gibi bir web sitesine
de hizmet reddi atağı başlatabilir. Buradaki amaç, sitenin veya hedefin stres testini ölçmektir. Bu
araç, Python dilinde yazılmıştır ve tüm işletim sistemlerinde çalışabilir. HULK aracı; yönlendirici
(router), anahtar (switch), güvenlik duvarı (firewall) gibi ağ cihazlarını test etmek için kullanılabildiği
gibi sunucuların IP havuzlarına direkt atak yapabilir. Bu nedenle çok tehlikeli bir araçtır. Bu araç
Github depoları klonlanarak indirilir.

**git clone https://github.com/grafov/hulk.git**

Kurulum işlemi bittikten sonra HULK aracını kullanmak için aracın indirildiği “Home” dizine
gidilmelidir.

<h3>HULK Aracının Kullanımı</h3>

1. Adım: Home dizinine indirilen hulk aracına erişiniz.

2. Adım: 2 numaralı kutucukta görüldüğü gibi boş alanda farenin sağ tuşuna
basılarak açılan pencerede Open in Terminal seçeneğini seçiniz.

3. Adım: 3 numaralı alanda hulk aracını çalıştırmak için hulk.py programını
kullanınız ve parametre olarak hedef IP adresini yazınız.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/hulk.PNG">

HULK aracı çalıştırıldıktan sonra işlemci, RAM ve Wi-Fi ağındaki işlem yükü artışı
görülür.

HULK aracı kapatıldıktan sonra işlemci, RAM ve Wi-Fi kaynaklarının hızla
düştüğü gözlemlenir.

HULK aracının performansını artırmak veya azaltmak için HULKMAXPROCS ve GOMAXPROCS
parametreleri kullanılır.

HULKMAXPROCS: Bu parametre ile bağlantı havuzu ayarlanabilir. Varsayılan değeri 1024’tür.
GOMAXPROCS: Bu parametre ile atak yapması istenen işlemci sayısı artırılıp azaltılabilir.

Örnek :

**HULKMAXPROCS=8192**

**GOMAXPROCS=4**

<h3>SYN Atak Yöntemi Kullanan Araçlar</h3>

SYN atak yönteminde kullanan araçlar aşağıda başlıklar hâlinde verilmiştir.

**SYN Taşması (SYN Flood)**

Bilgisayarlar arasında iletişimin sağlanması için ağ cihazları TCP ve UDP olmak üzere iki farklı
protokol kullanır. TCP protokolü Üç Yollu El Sıkışma (Three-Way Handshake) tekniğini kullanarak
karşıdaki bilgisayarla bir bağlantı kurar. Birbirlerine SYN, SYN/ACK ve ACK mesajları göndererek
TCP bağlantısının başlaması için aralarında bir güven oluşturur.

Siyah renkli istemci, normal bilgisayar gibi görünen bir saldırgandır. Bu saldırgan normal
bir şekilde iletişimi başlatmak için SYN iletişim başlatma paketini gönderir, sunucu da normal
bir şekilde SYN/ACK paketini cevap olarak gönderir. Saldırgan bu aşamadan sonra siyah renkli
istemcinin göndermesi gereken ACK paketini göndermez ve onun yerine SYN paketlerini
göndermeye devam eder. Bu durumda sunucunun ilgili portu, gelecek ACK
paketlerini beklemeye başlar. İletişim başlayacağı için sunucu ilgili portunu açık (varsayılan olarak
120 sn.) tutar. Bu nedenle açık olan port sayısı artar ve sunucunun kaynakları tükenir. Saldırgan
olmayan bir kişi iletişim başlatmak için SYN paketi gönderdiğinde ona ayıracağı portu kalmaz ve
sunucu cevap veremez duruma gelir.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/synflood.PNG">

SYN atağında kullanılan farklı araçlar mevcuttur. Bu öğrenme biriminde en etkili araç olan
“hping” komutu incelenecektir. 

<h3>Hping3 Komutu </h3>

Hping, komut satırında kullanılabilen ve ping komutunun gelişmiş versiyonu olan TCP/IP paket
oluşturma ve çözme aracıdır. Bu aracın ping komutundan farkı sadece ICMP yankı isteklerini
(ICMP Echo Request) göndermemesi, aynı zamanda TCP, UDP, ICMP ve RAW-IP gibi protokolleri
de desteklemesidir. Dosya gönderme, traceroute gibi birçok yeteneğe sahiptir. Hping komutunun
en yeni sürümü hping3’tür.

Sistemde hping3 komutunun yüklü olup olmadığını kontrol etmek için 1 numaralı alandaki
komut yazılarak versiyon bilgisi öğrenilebilir. Versiyon bilgisi sonucu Görsel’deki gibi değilse
2 numaralı alandaki komut ile kurulum yapılır.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/hping3.PNG">

**hping3 -h 3 ile ilgili hangi parametrenin hangi görevi yerine getirdiği görülür. **

<h3>Hping3 Komutunun Kullanımı</h3>

1. Adım: Görsel’deki hping3 komutu ile SYN atağını başlatınız. Bu komutun açılımı ile ilgili
parametreler aşağıda verilmiştir.

• -sudo: Komutu çalıştırabilmek için geçici root olmayı sağlar.
• -hping3: Ana komuttur, atağı yönetir.
• -S: Atağın SYN paketi ile olacağını belirtir.
• --flood: Cevaplar beklenmeden paketlerin art arda hızlı bir şekilde gönderilmesini sağlar.
• -p: Port numarasını belirtir. 

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/hping3atak.PNG">

Saldırı başlatıldığında işlemci performans göstergesi 100’lere kadar çıkacaktır. Bu durum,
hedefin normalde yapabilmesi gereken işlemleri gerçekleştiremeyeceği ve sistem kaynaklarının
boşa kullanılacağı anlamına gelir. Hedef bilgisayarda neler olup bittiği Wireshark ile izlenebilir.
Wireshark programı, paket yakalamak ve analiz etmek için kullanılan ücretsiz bir yazılımdır. Atak
başlatılmadan önce Wireshark programı açılır ve bu programın Wi-Fi ağını dinlemesi sağlanır .

<h3>DDoS ATAĞI (DAĞITILMIŞ HİZMET REDDİ ATAĞI)</h3>

DDoS atağı, DoS atağının gelişmiş bir versiyonudur. DDoS atağı çok daha yıkıcı ve tehlikelidir.
Bu atak iki farklı şekilde organize edilir. İlk yöntem, illegal sitelerde buluşan çok sayıda saldırganın
seçilen hedefe belirli bir gün ve saatte atak araçlarını kullanarak saldırmasıdır. Bu yöntem pek
tercih edilmez. İkinci yöntem ise saldırganların önce ağ içindeki savunmasız sistemleri bularak o
sistemlere zararlı yazılım (malware) enjekte etmesidir. Böylelikle saldırganlar, zombi olarak tabir
edilen bilgisayarlar edinir. Saldırganlar, zombileri kullanarak istediği bir zaman diliminde herhangi
bir sisteme atak yapabilir. En çok tercih edilen bu yöntemdir. Bu sayede saldırgan,
kendini de gizler ve olan biteni arka planda izler. Bu atak yöntemi, Mass-Intrusion (Kitlesel Saldırı)
faz tekniği olarak da adlandırılır. Mass-Intrusion fazı, DDoS ataklarının ilk aşamasını oluşturur. 

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/ddos.PNG">

Zombi Bilgisayar: Bir saldırgan tarafından virüs, Truva atı gibi zararlı bir yazılım yüklenmiş
bilgisayarlardır. Saldırgan bu sayede istediği zaman bu bilgisayarı kullanarak çeşitli ataklar
gerçekleştirebilir. Böylelikle saldırgan, kullanıcı farkında olmadan kullanıcının bilgisayarını
uzaktan istediği gibi yönetir. Çoğu zararlı yazılım bu amaç için yazılmıştır.

Botnet: Robot ve Network kelimelerinin birleşimidir. Zombi bilgisayarlardan kurulan orduya
denir.

<h3>DDoS Atak Araçları</h3>

Çeşitli DDoS atak araçları vardır. Bu öğrenme biriminde slowloris aracı açıklanacaktır.

<h3>Slowloris Aracı</h3>

Slowloris aracı adını lorigiller olarak isimlendirilen, çok yavaş hareket eden bir hayvandan
almıştır. Bu araç, Python dilinde yazılmıştır ve açık kaynak olarak “github”da bulunur. HTTP
istek (request) ve HTTP yanıt (response) paketlerinin iletiminden kaynaklanan açığı kullanarak
çalışır. Normalde sunucuya bir HTTP isteği gönderildiğinde sunucudan yanıtı gelir.
Slowloris aracı, sunucuya isteği tek seferde değil de parçalar hâlinde gönderir. Bu durumda
sunucu, isteklerin tamamlanacağını düşünerek bağlantıyı sürdürür. Slowloris, kısmi HTTP
paketlerini göndermeye devam eder (Görsel 7.19). Sonunda sunucuya ayrılan tüm bağlantı portlar
tüketilir ve normal bir kullanıcı sunucuya ulaşmak istediğinde sunucunun kaynakları tükendiği
için erişemez. Slowloris en tehlikeli teknik olan düşük ve yavaş atak aracı sınıfına girmektedir.
Eksik paketler gönderdiği için saldırı tespit sistemleri (IDS) bu tür DDoS atağını tespit edemez.
Ayrıca günlük (log) oluşturmayı engelleyebilir. Bu durum, siber güvenlik analistlerinin olayı tespit
etmesini güçleştirir. 

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/slowloris.PNG">

**git clone https://github.com/gkbrk/slowloris.git** komutu kullanılarak slowloris aracı işletim sistemine indirilir. İndirilen araç bir
klasör içinde gelir. Herhangi bir kurulum işlemi gerektirmez fakat daha farklı kullanımlar için bir
konfigürasyon dosyası içerir.

slowloris “github”dan indirildiğinde bir klasör
olarak gelir. Klasörün içine girildiğinde Bu ekranda farenin sağ tuşuna tıklanarak Open in Terminal seçeneği seçilir. 

Uygulamaya başlamadan önce bir web sunucu servisinin çalışıp çalışmadığından emin
olunmalıdır.

<h3>Slowloris Aracının Kullanımı</h3>

Aşağıdaki işlem adımlarına göre slowloris aracının kullanımını gerçekleştiriniz.

1. Adım: Apache web sunucusunu aktifleştiriniz ve sunucunun çalışmasını kontrol ediniz.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/apache.PNG">

2. Adım: Slowloris aracının olduğu dizine gidiniz.

3. Adım: Farenin sağ tuşuna tıklayarak Open in Terminal seçeneğini seçiniz. 

4. Adım: **python3 slowloris.py 192.168.1.22 -s 500** komutunu kullanarak bir iç IP’ye atak gerçekleştiriniz. 

lowloris komutu parametresiz kullanıldığında 150 soket bağlantısı gerçekleştirir. -s
parametresi, soket bağlantı sayısını varsayılan değerinde farklı bir değere ayarlamak için kullanılır. -s 500 parametresi ile soket sayısı 500’e ayarlanır.

5. Adım: Apache2 sunucu loglarını inceleyip sayfalarca kayıt oluşturulduğunu görünüz.

<h3>Formları Kullanarak DDoS Atağı</h3>

Formları kullanarak DDoS atağı yapmak için kullanılan araçlar başlıklar hâlinde verilmiştir.

<h3>RUDY (RU-Dead-Yet) Aracı</h3>

RUDY aracı, diğer araçlar gibi hızlı istekler ile sunucuyu meşgul etmek yerine uzun form alanları
göndererek web sunucusunu hizmet veremez duruma getirmek için kullanılır. İstemci normal bir
iletişimde form alanlarına ait bilgileri HTTP Post ile gönderir. Sunucu da form bilgilerini alır ve
HTTP yanıt bilgisini gönderir.

Atak aracı öncelikle hedef web sayfasındaki form alanlarını tarar. Bir form sayfası bulduğunda
normal bir bilgisayar gibi HTTP Post isteği oluşturur. Çok uzun bir post isteği olacağını belirten bir
başlık bilgisi gönderir. Sonrasında form verilerini çok küçük paketlere (1 Byte-10 KB arası) böler
ve 10 saniyelik rastgele aralıklarla sunucuya gönderir. RUDY aracı paketleri sürekli
gönderir. Sunucu yavaş bağlantı hızına sahip bir kullanıcıdan bilgi aldığını zannederek bağlantıyı
açık tutar. Böylelikle işlemesi gereken trafik maksimum boyuta çıkar ve normal kullanıcıların
istekleri reddedilir. 

Çok çeşitli dillerde yazılmış RUDY aracı kodları vardır. Bu kodlar kullanılarak veya çeşitli
özellikler eklenerek araç geliştirilebilir.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/rudy.PNG">

<h3>RUDY Aracının Kullanımı</h3>

1. Adım: Bir yerel web sunucusunu aktifleştiriniz. Bu uygulama, Apache2 web
sunucusu üzerinde yapılmıştır.

2. Adım: Yerel web sunucusuna form sayfaları içeren bir web sitesi ekleyiniz.

3. Adım: Rudy'i indirdiğiniz klasöre gidin.

4. Adım: **rudy -t "http://192.168.1.22/index.html" -d 5 -n 500** Komutunu çalıştırın.

-rudy: RUDY aracını çalıştırmak için gerekli ana komut

-t: Hedef (Target) IP adresi veya web sitesi (Gerekli bir komuttur.)

-d: Gecikme (Delay), gönderilen her bayt arasındaki bekleme süresi

-n: En fazla bağlantı sayısı (numberOfConnections)

Değişik dillerde yazılan RUDY araçlarının parametreleri için yardım kılavuzu incelenir. komutta kullanılan -d ve -n parametreleri isteğe bağlı olarak yazılır. Sadece -t parametresi
zorunludur. Diğer parametreler (-d, -n) kullanılmazsa varsayılan değerler ile atak başlatılır. 
