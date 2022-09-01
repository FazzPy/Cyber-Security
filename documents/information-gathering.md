# Fazz | İnformation Gathering

PASİF BİLGİ TOPLAMA YÖNTEMLERİ UYGULAMALARI

Pasif bilgi toplama yöntemlerinde bilgi alınmak istenen hedef ağ veya sistem ile doğrudan
iletişime geçilmez. Bu nedenle hedef sistemde log kaydı oluşmaz, iz bırakılmaz. Bu yöntemde
ağ veya sistem hakkında bilgi edinebilmek için internet kaynaklarından yararlanılır. Pasif bilgi
toplama yöntemleri ile yüzeysel bilgiler edinilir. Pasif bilgi toplama yöntemleri şunlardır:

• IP adresleri üzerinden bilgi toplama
• Domainler üzerinden bilgi toplama
• Web sayfalarından bilgi toplama

<h3>IP Adresleri Üzerinden Bilgi Toplama</h3>

Kâr amacı gütmeyen ICANN (Internet Corporation for Assigned Names and Numbers), IP
adreslerinin dağıtımında yetkili olan tek merkezdir. İnternet Tahsisli Sayılar ve İsimler Kurumu; IP
adres alanı tahsisi, protokol ataması, ülke kodu ve internet alan adı yönetimi, internet ana servis
sağlayıcı idaresinin koordinasyonu görevlerinden sorumludur.

<h3>Whois</h3>

Whois, sorgu yapılan IP adresi veya alan adı ile bazı bilgilere ulaşmayı sağlar. Whois sorgusu;
alan adı sahibi kişiye veya kuruma ait telefon numarası, adres, e-posta vb. iletişim bilgilerini ve
alan adı ile ilgili domain sunucu, IP aralığı vb. teknik bilgileri yasal çerçevede listeler. Alan adının
veya IP adresinin sahibi, kendine ait bilgilerin whois sorgusu sırasında listelenmesini istemeyebilir.
Bunun için whois gizleme servisinin aktif edilmesi gerekir. Böylece ICANN, bilgileri gizler ve whois
sorgusu yapanların bilgileri görmesini engeller.

<img src="https://github.com/FazzPy/security/blob/main/img/whois.PNG">

<h3>SHODAN CLI</h3>

SHODAN CLI komutları açık kaynak istihbarat gerçekleştirmek için kullanılabilir. Bu komutlar ile
hedef kolay ve pasif bir şekilde analiz edilir. Shodan arama motoru ile hedef sistemin altyapılarına
erişebilmek ve sistem hakkında daha ayrıntılı bilgi toplayabilmek için terminal üzerinden shodan
komutları uygulanır.

<img src="https://github.com/FazzPy/security/blob/main/img/shodan.PNG">

<h3>RIPE NCC</h3>

RIPE NCC; Avrupa, Ortadoğu ve Orta Asya’nın bazı bölgelerine IP adresi tahsisinden sorumlu,
kâr amacı gütmeyen bir kuruluştur. Belirtilen bölgelerde yer alan IP adreslerine ilişkin pasif
bilgi sorgulaması yapmak için https://www.ripe.net internet adresinden yararlanılır. İlgili web
sayfasında bilgi alınmak istenen IP adresi yazılarak sorgulama yapılır.

<img src="https://github.com/FazzPy/security/blob/main/img/ripe1.png">

Sorgu sonucunda görselde görülen bilgiler ile karşılaşılır:

<img src="https://github.com/FazzPy/security/blob/main/img/ripe2.PNG">

<h3>Bing Arama Motoru (IP Operatörü)</h3>

IP adresi verilen sunucuda yer alan web siteleri hakkında bilgi toplamak için kullanılır. Bing
arama çubuğunda ip: ip_adresi şeklinde sorgulama yapılır.

<h3>IP Location</h3>

IP Location, hedef IP adresini beş farklı servis üzerinde sorgulayarak coğrafi konum tespiti
sağlar. Coğrafi konum tespiti yapılmak istenen IP adresi arama çubuğuna yazılarak sorgulanır.

IP Location ile coğrafi konum sorgulama sonuçları servis sağlayıcılar arasında değişiklik
gösterebilir.

<h3>Domainler Üzerinden Bilgi Toplama</h3>

Her web sitesinin bir IP adresi bulunur. Web sitelerine erişmek için IP adreslerinin bilinmesi
gerekir. IP adreslerinin akılda tutulması ve hatırlanması zor olduğu için web sitelerine erişimde
genellikle domain (alan adı) kullanılır. Alan adı, IP adresinin kelimelerle ifade edilen hâlidir. 

Web tarayıcının adres çubuğuna eba.gov.tr alan adı yazıldığında DNS ile bu alan adının IP
adresi çözümlenir. Daha sonra bu IP adresindeki sunucuya erişilir.

Alan adının kullanımda olup olmadığına ilişkin bilgiyi toplamak için domain sorgulayan
internet siteleri kullanılır.

<h3>NS.TOOLS</h3>

NS.TOOLS, alan adının aktif mi yoksa pasif mi olduğunu öğrenmek için ping işlemi uygular.
Bu araç kullanılarak alan adı ile ilgili DNS, IP, e-mail ve web bilgileri de toplanır. Bilgi toplanmak
istenen web sitesi, arama çubuğuna yazılarak sorgulama yapılır.

<h3>TheHarvester</h3>

TheHarvester; internet üzerinden kişilerin ve kurumların ayak izini anlamak, hedef alan
adının e-posta adreslerini ve alt alan adlarını tespit etmek için kullanılan bir keşif aracıdır. Bu bilgi
toplama aracı, Kali Linux üzerinde yüklü olarak gelir. Komut satırında -h parametresi ile yardım
sayfası açılarak aracın kullanımı daha detaylı incelenebilir.

<img src="https://github.com/FazzPy/security/blob/main/img/harvester.PNG">

<img src="https://github.com/FazzPy/security/blob/main/img/harvester2.PNG">

•  d parametresi ile hedef alan adı belirtilir.
• -l parametresi ile arama yapılacak sonuç sayısı belirtilir.
• -b parametresi ile arama yapılacak arama motoru listesi belirtilir.

<img src="https://github.com/FazzPy/security/blob/main/img/harvester3.PNG">

 Hedef domain hakkında bilgi toplamak için kullanılan popüler arama motorları şunlardır:
  • google 
  • linkedin 
  • urlscan
  • bing 
  • linkedin_links 
  • yahoo
  • baidu 
  • netcraft
  • duckduckgo 
  • twitter

Hedef domain, yazılım sektörü ile ilgili ise popüler arama motorları listesine github da
eklenebilir.

<h3>TheHarvester Komutu</h3>

Aşağıdaki işlem adımlarına göre theHarvester komutunu kullanınız.
1. Adım: Bilgi toplamak istediğiniz hedef alan adını belirleyiniz.
2. Adım: Hedef e-posta adreslerini ve alt alan adlarını theHarvester komutu ile tespit ediniz 

<img src="https://github.com/FazzPy/security/blob/main/img/harvester4.PNG">

• d parametresi ile hedef alan adı belirtilir.
• -b parametresi ile arama yapılacak kaynak arama motorları belirtilir. Tüm arama motorlarını belirtmek için all kelimesi kullanılabilir.
• -l parametresi ile arama yapılacak sonuç sayısı belirtilir. Varsayılanda 500 değerine sahiptir.
• -S parametresi ile aramanın başlayacağı değer belirtilir. Varsayılanda 0 değerine sahiptir.
• -f parametresi ile arama sonuçlarının JSON ve XML formatında kaydedileceği dosya adı belirtilir.

Tespit edilen e-posta adreslerini, alt alan adlarını ve IP adreslerini inceleyiniz.

<img src="https://github.com/FazzPy/security/blob/main/img/harvester5.PNG">

Tespit edilen bilgilerin kaydedildiği XML ve JSON dosyalarını inceleyiniz.

theHarvester aracının kullanılan diğer önemli parametreleri ve parametrelerin işlevleri
şunlardır :
• -s parametresi ile shodan üzerinden bilgi toplanır.
• -g parametresi ile Google Dork kullanılarak bilgi elde edilir.
• -p parametresi ile hedef alan adı üzerinde port taraması yapılır.

<h3>Sublist3r</h3>

Sublist3r, hedef alan adının alt alan adlarını arama motorlarını kullanarak araştıran ve
araştırma sonuçlarını listeleyen bir araçtır. Python diliyle yazılmış bu aracın kullanımı kolaydır.
Sublist3r aracı hâlihazırda Kali Linux içinde gelmez. Sonradan kurulması gerekir.

**sudo apt-get install sublist3r**

Komut satırında -h parametresi ile yardım sayfası açılarak aracın kullanımı daha detaylı
incelenebilir.

**sublist3r -h***

**sublist3r -d www.google.com**

• -d parametresi ile alt alan adları tespit edilmek istenen hedef domain belirtilir

<h3>DNSENUM</h3>

Dnsenum; hedef alan adına ait IP adresleri, Mail sunucuları, DNS sunucuları, alt alan adları
gibi önemli bilgileri toplayan bir araçtır. Perl diliyle yazılan bu araç, Kali Linux üzerinde yüklü
olarak gelir.

Dnsenum aracı **dnsenum <alan adı>** şeklinde kullanılır.

Dnsenum komutu çalıştırıldığında hedef domainin IP adresleri, DNS sunucuları, Mail sunucuları
tespit edilir. Tespit edilen DNS sunucuları üzerinde hedef alan adına ait tüm kayıtların elde
edilmesi için bölge transferi (zone transfer) gerçekleştirilmeye çalışılır. Alt alan adlarının tespiti
için “/usr/share/dnsenum/” yolundaki “dns.txt” dosyası kullanılarak Brute Force gerçekleşir.
Tespit edilen IP adresleri için C blok IP aralıkları listelenir

<h3>LBD</h3>

LBD, hedef alan adının DNS ve/veya HTTP yük dengeleme kullanıp kullanmadığını kontrol
eden bir araçtır.

LBD aracı **lbd <alan adı>** şeklinde kullanılır.

<img src="https://github.com/FazzPy/security/blob/main/img/lbd.PNG">

<h3>DNSRECON</h3>

Dnsrecon, hedef alan adına ait alt alan adlarını ve IP adreslerini arama motorları üzerinden
tespit edebilen bir araçtır. Python diliyle yazılan bu araç, Kali Linux üzerinde yüklü olarak gelir.

<img src="https://github.com/FazzPy/security/blob/main/img/dnsrecon.PNG">

• -t parametresi ile hangi arama çeşidinin kullanılacağı belirtilir. Yandex arama motoru ile
arama yapmak için yand argümanı kullanılır.
• -d parametresi ile hedef alan adı belirtilir.

Dnsrecon aracının parametrelerini daha ayrıntılı incelemek için yardım sayfası kullanılabilir.
Dnsrecon aracı ile ilgili yardım sayfasına ulaşmak için komut satırında dnsrecon -h yazılır.

Dnsrecon komutu çalıştırıldığında hedef domainin Görsel'de görülen alt alan adları ve IP
adresleri ile karşılaşılır.

<img src="https://github.com/FazzPy/security/blob/main/img/dnsrecon2.PNG">

**Dnsrecon Komutu**

Aşağıdaki işlem adımlarına göre dnsrecron komutunu kullanınız.

1. Adım: Bilgi toplamak istediğiniz hedef alan adını belirleyiniz.
2. Adım: Hedef alt alan adlarını ve IP adreslerini dnsrecon komutu ile tespit ediniz.

<img src="https://github.com/FazzPy/security/blob/main/img/dnsrecon3.PNG">

• -t parametresi ile arama çeşidi belirtilir. Bing arama motorunu belirtmek için bing argümanı
kullanılır.
• -d parametresi ile hedef alan adı belirtilir.
• --json parametresi ile arama sonuçlarının JSON formatında kaydedileceği dosya adı belirtilir.

<h3>Maltego</h3>

Maltego, hedef kurum ve kişi hakkında detaylı bilgi toplamak için kullanılır. Ücretli ve ücretsiz
sürümleri bulunan maltego, Kali Linux üzerinde kurulu şekilde gelir. Bu araç, açık kaynaklardan
elde edilen bilgileri görselleştirerek bağlantı analizi ve veri madenciliği için uygun hâle getirmeye
odaklanır.

<img src="https://github.com/FazzPy/security/blob/main/img/maltego.PNG">

Sol tarafta bulunan Entity Palette penceresinin Infrastructure bölümündeki Domain nesnesi
sayfaya sürüklenir.

<img src="https://github.com/FazzPy/security/blob/main/img/maltego2.PNG">

Domain nesnesi üzerindeki alan adına çift tıklanır. Bilgi toplanmak istenen hedef domain
yazılır.

Domain nesnesi üzerinde sağ tuş yapılır. All Transforms seçeneğinin yanındaki ok tuşuna
tıklanarak bilgi toplama çalıştırılır.

<img src="https://github.com/FazzPy/security/blob/main/img/maltego3.PNG">

<img src="https://github.com/FazzPy/security/blob/main/img/maltego4.PNG">

Sayfanın içinde Domain nesnesinden uzaklaşıldığında toplanan bilgilerin türleri de
renklendirilmiş biçimde sunulur.

<h3>Web Sayfalarından Bilgi Toplama</h3>

Hedef sistemler, IP adresleri, alan adları, kullanıcı ve kurumlar hakkında web sayfalarından
detaylı bilgiler toplanabilir. Bu yöntemde bilgi toplamak için genellikle DNS sorgulama yapan özel
web sayfaları, arama motorları, arşiv siteleri, sosyal paylaşım ağları, bloglar, forumlar, kariyer
siteleri kullanılır.

<h3> Viewdns.info </h3>

Viewdns.info; IP adresinin coğrafi konumunu, MAC adres ile ağ cihazının üreticisini, bir sunucuda barınan web sitelerini, alt alan adlarını, DNS kayıtlarını, portların açık olma durumunu
bulmak için kullanılır. Bu web sayfası ile ping, traceroute ve çok daha fazla araç
kullanıma sunulur.

<img src="https://github.com/FazzPy/security/blob/main/img/viewdnsinfo.PNG">

<h3>Viewdns.info (Get HTTP Headers) Kullanımı</h3>

Aşağıdaki işlem adımlarına göre Get HTTP Headers aracını kullanınız.

1. Adım: HTTP başlığı bilgisini elde etmek istediğiniz hedef alan adını belirleyiniz.
2. Adım: Get HTTP Headers aracı ile hedef alan adını sorgulayınız.

<img src="https://github.com/FazzPy/security/blob/main/img/viewinfoheaders.PNG">

<h3>Archive.org</h3>
Archive.org, 1996 yılından itibaren tüm web sitelerinin indekslerinin belli dönemlerde
arşivlendiği bir web sayfasıdır. Bu web sayfası ile yayından kaldırılan veya yayında olan web
sitelerinin eski görüntülerine erişilebilir. Web sitelerinin yıllara, aylara ve günlere göre anlık
görüntülerine ulaşılabilir.
İlgili web sayfasındaki arama çubuğuna bilgi toplanmak istenen web sitesinin adresi yazılır.
Enter tuşuna basılır.

Sorgulama sonucundaki takvimde bilgi toplanmak istenen web sitesinin indekslenmiş
tarihlerdeki anlık görüntülerine ulaşılabilir.

<h3>Shodan.io</h3>

SHODAN (Sentient Hyper-Optimised Data Access Network), önsezileri güçlü en uygun veri
erişim ağı anlamını taşır. Saldırganlar, pasif keşif aşamasında hedef sistemlerin altyapılarına
erişebilmek ve daha ayrıntılı bilgi toplayabilmek için shodan.io web sitesini kullanabilirler. Bu
nedenle shodan, hackerların arama motoru olarak bilinir . Bu arama motoru,
dünya üzerinde internete bağlı olan farklı türlerdeki bilgi işlem sistemini tespit eder. Bilgi işlem
sistemlerinde yer alan cihazlar hakkında bilgi toplar. 

Kullanıcılar, shodan arama motorunu kullanarak ülke ve şehir bazlı filtreleme yapabilir.
Filtreleme sonucunda tespit edilen sistem üzerindeki port ve servis bilgilerine, IP adreslerine
ulaşılabilir.
Kullanıcılar bu arama motorunda IoT cihazları, IP kameraları, sunucuları, SCADA sistemleri,
nükleer santralleri, açık trafik ışığı sistemlerini aratabilir. Hatta bu arama motoru ile deniz uydu
alıcıları aratılarak gemilerin isimleri, konumları, iletişim numaraları dâhil birçok bilgi tespit
edilebilir. 

<h3>Google Dorking ve Google Hack Database</h3>

Kişi ve kurumların internet ortamında bıraktığı dijital ayak izleri, arama motorları tarafından
indekslenir. İndekslenen dijital ayak izleri, uzun bir süre arama motorlarında erişilebilir hâlde
bulunur. Hedef sistem, kurum veya kişi hakkında daha fazla bilgiye ulaşmak için arama motorları
kullanılır. En yaygın kullanılan arama motoru Google’dır.
Google arama motorunun sağladığı anahtar kelimeler (dorklar) ile detaylı bilgi toplama
yapılabilir. Arama motorunun indeksleme becerisi, zararlı olabilecek birçok kritik bilginin de
indekslenmesine yol açar. Bu indekslenme işlemi sonucunda arama motorlarının arama özellikleri
kötü amaçlar için kullanılabilir ve zafiyetli noktalar tespit edilebilir.
Google arama motorunun sağladığı anahtar kelimeler (dorklar) ile detaylı bilgi toplama
yapılabilir. Arama motorunun indeksleme becerisi, zararlı olabilecek birçok kritik bilginin de
indekslenmesine yol açar. Bu indekslenme işlemi sonucunda arama motorlarının arama özellikleri
kötü amaçlar için kullanılabilir ve zafiyetli noktalar tespit edilebilir.
Google arama motorundan bilgi toplamada kullanılabilecek bazı dorklar şunlardır:

• site: Belirtilen web site ile ilgili sonuçları listeler.
• filetype: Belirtilen uzantıya sahip dosyaları listeler.
• inurl: Belirtilen parametreyi içeren URL adreslerini listeler.
• intitle: Belirtilen parametreyi içeren başlığa sahip olan sonuçları listeler.
• intext: Belirtilen parametreyi içeren web sayfalarını listeler.
• mail: Belirtilen domaine ait mail adreslerini listeler.

Google Hack Database, Google sorgularının listesini içeren bir indeksleme veri tabanıdır. Bu
veri tabanına https://www.exploit-db.com/google-hacking-database bağlantısından erişilebilir.

Google Hack Database kullanılarak kullanıcı adı, parolalar, kritik bilgiler içeren hata mesajları
ve güvenlik zafiyetleri bulunabilir. İlgili veri tabanında yer alan güncel dorklar kullanılarak önemli
bilgiler toplanabilir.

<h3>OSINT FRAMEWORK</h3>

OSINT Framework, kullanıcıları yüzlerce pasif bilgi toplama aracına yönlendiren bir web
sitesidir. Bu web sitesindeki kategorilerden bilgi toplanmak istenen hedefe uygun olanı seçilir.
Seçilen kategorideki araçlar ile pasif bilgi toplama gerçekleştirilir.

<img src="https://github.com/FazzPy/security/blob/main/img/osint.PNG">

<h3>AKTİF BİLGİ TOPLAMA YÖNTEMLERİ UYGULAMALARI</h3>

Aktif bilgi toplama yöntemlerinde bilgi alınmak istenen hedef ağ veya sistem ile doğrudan
iletişime geçilir. Bu nedenle hedef sistemde log kaydı oluşur ve iz bırakılır. Aktif bilgi toplama,
saldırgan açısından en riskli bilgi toplama yöntemidir. Tespit edilme olasılığı bulunduğu için
saldırganın dikkatli olması gerekir. Bir siber güvenlik uzmanı da savunma amaçlı olarak aktif bilgi
toplama yöntemlerini iyi derecede bilmelidir.


Aktif bilgi toplama yöntemleri, sızma testlerinde sistemlerin açıklarını tespit etmeye imkân
sağlar. Aktif bilgi toplama yönteminde sağlanmaya çalışılan hedeflerden bazıları şunlardır:
• Erişilebilen tüm sunucuların tespit edilmesi
• Sunucuların üzerinde çalışan servis ve versiyonların tespit edilmesi
• Servis ve versiyonların potansiyel zafiyet analizinin yapılması
• Saldırı tekniklerinin geliştirilmesi
• Erişilebilen tüm web uygulamalarının tespit edilmesi
• Ağ hazırlanırken gerekli ayarların test edilmesi

<h3>Network Mapping (Ağ Haritalama)</h3>

Nmap (Network Mapper) yazılımı, ağ haritasının ve topolojisinin çıkarılmasında kullanılır.
Açık kaynak kodlu olan nmap, kullanılan en etkin ağ tarama yazılımıdır. Bu yazılım, bilgisayar
ağları uzmanı Gordon Lyon (Fyodor) tarafından geliştirilmiştir.
Nmap; ağ üzerindeki cihazların açık olan portlarını, işletim sistemlerini, çalışan servislerini ve
versiyonlarını bulmak, TCP/IP sistemlerini keşfetmek, zafiyetlerini tespit etmek amacıyla yaygın
biçimde kullanılır. 

NSE (Nmap Scripting Engine) araçları kullanılarak bazı zafiyetler tespit edilebilir.

Nmap komutu kullanılırken tarama türüne ve opsiyonlarına karar verilebilir, istenen
özelliklerde tarama işlemi gerçekleştirilebilir. Nmap, bir cihazı veya birden fazla cihazın bulunduğu
ağı tarayabilir. Tarama işlemi, çeşitli ağ protokolleri aracılığıyla bilgi toplamayı sağlar. Ağdaki cihaz
veya cihazlara ham paketler gönderilir. Bu paketlere verilen yanıtlar incelenerek keşif işlemleri
yapılır. Örneğin verilen yanıtlardan portların bir güvenlik duvarı tarafından açık, kapalı veya filtreli
olup olmadığı hakkında bilgi edinilebilir.
Nmap aracı, Kali Linux içinde kurulu olarak gelir. Nmap aracını kullanmak için hedef sisteme ait
bir IP adresi veya web site adresi gerekir. Bir IP adresinin bulunduğu ağın haritasının çıkarılması
için nmap komutunun en basit kullanımı **nmap <ip adresi>** şeklindedir.
 
 ekranda nmap komutu varsayılan olarak en çok kullanılan 1000 porta
SYN taraması yapar. Hedefe ilişkin SYN taraması yapmak, TCP protokolünün SYN bayrağını
kullanarak açık hizmetlerin bulunmasını sağlar
 
 IP adresinin nmap tarama sonucunda açık port ve servisleri
listelenmiştir. Ayrıca nmap komutunun sadece varsayılan 1000 portu 20.27 saniyede taradığı, 16
adet portun açık ve 984 adet portun da filtreli olduğu bilgileri görülür.

 
 <h3>Nmap Parametreleriyle Açık Sistemlerin Tespit</h3>
 
 Ağ güvenliği testlerine başlamadan önce yapılması gereken ilk işlem, ağ üzerindeki açık
sistemlerin tespitidir. Bunun için nmap parametreleri kullanılır. Komut satırında nmap -h komutu
uygulanarak açılan yardım sayfasında görülen nmap parametrelerinin kullanımı daha detaylı
incelenebilir.
 
 <h3>Nmap Parametreleri</h3>
 
 Nmap ağ haritalama uygulamasının parametreleri şunlardır:
-iL <dosya adı>: IP adreslerinin belirtildiği dosyadan bilgileri alarak tarama yapar.
-iR <host sayısı>: Host sayısı kadar hedefi tarar. Rastgele hedef seçer.
--exclude <host1[,host2][,host3],...>: Taranması istenmeyen IP adresleri belirtilir.
--excludefile <dosya adı>: Taranması istenmeyen IP adresleri bir dosya içinden alınır.
-sn: Port taramasını devre dışı bırakarak aktif hostların tespiti için sadece ping atar.
-Pn: Ping göndermeden tarar. Her IP adresini aktif kabul eder.
-PS: TCP SYN ping atarak keşif yapar.
-PA: TCP ACK ping atarak keşif yapar.
-PU: UDP ping atarak keşif yapar.
-PE: ICMP Echo Request ping atarak keşif yapar.
-PP: ICMP Timestamp ping atarak keşif yapar.
-n: Asla DNS çözümlemesi yapılmaz.
-R: Her zaman DNS çözümlemesi yapılır.
--traceroute: Traceroute özelliğini aktif hâle getirir.
-sS: TCP SYN taraması yapar. Gizli tarama olarak bilinir.
-sT: TCP bağlantılı tarama yapar.
-sA: TCP ACK taraması yapar.
-sU: UDP taraması yapar.
-sN: TCP NULL taraması yapar.
-sF: TCP FIN taraması yapar.
-sO: IP protokolü taraması yapar.
-p: Belirtilen portları tarar.
-F: Daha hızlı tarama yapar. En çok kullanılan 100 port taranır.
--top-ports <sayı>: Belirtilen sayı kadar sık kullanılan portları tarar.
-sV: Açık portta çalışan servisin versiyonunu tespit eder. -sC ile birlikte kullanılır.
-sC: -sV ile versiyon tespiti yapılırken nmap scriptlerini kullanır.
-O: İşletim sistemi bilgisini tespit eder.
-v, -vv: Ekranda gösterilecek detayları artırır.
--reason: Port durumunun nedenini gösterir.
--open: Sadece açık portları gösterir.
-p-: Bir IP üzerinde bulunması muhtemel 0-65535 arasındaki tüm portları tarar.
-A: Agresif tarama yapar.
-T: Zamanlama şablonu belirtir.
 
**nmap 192.168.1.56-100 IP Aralığı verir**

 <h3>PORT TARAMASI </h3>
 
**nmap -sn 192.168.56.0/24** -sn parametresi ile portlar taranmaz. Sadece ping atılarak aktif
hostlar belirlenir. 
 
 Hedef IP adresinin 80 numaralı portuna nmap taraması yapınız:
 **nmap -p 80 -n 192.168.56.102** -p parametresi ile 192.168.56.102 IP adresine sahip hostun 80 numaralı portu taranır. -n
parametresi ile DNS çözümlemesi yapılmaz. 
 
 Hedef IP adresinin sadece açık olan portlarına nmap taraması yapınız:
 **nmap -n -open  192.168.56.102** --open parametresi ile 192.168.56.102 IP adresine sahip hostun sadece açık portları taranır. 
 
 Hedef IP adresinin 22 ve 23 numaralı portlarına nmap taraması yapınız:
 **nmap -n -p 22,23 192.168.56.102** -p parametresi ile 192.168.56.102 IP adresine sahip hostun SSH ve TELNET portları taranır.
Belirtilen portlar virgülle ayrılır.
 
 Hedef IP adresinin tüm portlarına nmap taraması yapınız :
 nmap -n -p '*' 192.168.56.102 | -p '*' parametresi ile 192.168.56.102 IP adresine sahip hostun tüm portları taranır. 
 
 Hedef IP adresinin tüm TCP portlarına nmap taraması yapınız:
 **nmap -n -sT 192.168.56.102** -sT parametresi ile 192.168.56.102 IP adresine sahip hostun tüm TCP portları taranır. 
 
 Hedef IP adresinin 443 numaralı TCP portuna nmap taraması yapınız:
 **nmap -n -p T:443 192.168.56.102** -p T:443 parametresi ile 192.168.56.102 IP adresine sahip hostun HTTPS portu taranır.
 
 <h3>Portlarda Servis Tarama Teknikleri</h3>
 
 Hedef sistemlerin portlarındaki servislerin taranmasında kullanılan tekniklerdir.
--script parametresi ile zafiyet tespiti yapmak için 21 numaralı port üzerinden FTP servisi
kontrol edilir:
 
<img src="https://github.com/FazzPy/security/blob/main/img/nmapscript.PNG">
 
 --script parametresi ile zafiyet tespiti yapmak için 445 numaralı port üzerinden microsoft-ds
servisi kontrol edilir.
 
<img src="https://github.com/FazzPy/security/blob/main/img/nmapscript2.PNG">
 
 <h3>On-line Port Tarama Teknikleri</h3> 
 
 Port tarama işlemleri, web siteleri üzerinden de yapılabilir. On-line port taramak için https://
viewdns.info/portscan web sitesi kullanılabilir.
 
<img src="https://github.com/FazzPy/security/blob/main/img/onlineport.PNG">
