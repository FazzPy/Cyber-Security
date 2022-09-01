# SIZMA TEKNİKLERİ

<h3>Beyaz Kutu (White Box) Test</h3>

Herhangi bir sistemin veri akışını doğrulamak, kullanılabilirliğini ve güvenliğini geliştirmek için
güvenlik uzmanlarının yazılımın yapısını, tasarımını ve kodlamasını kontrol ettiği test tekniğidir. 
Sızılacak sistem hakkında her türlü bilgi ve erişim izni mevcuttur. 

Güvenlik uzmanına kurum tarafından sistemin kodları verilir ve bu kodlar görülerek test yapılır.
Beyaz kutu test tekniği hem kod geliştiriciler hem de güvenlik uzmanları tarafından kullanılır. Diğer
sızma testi çeşitlerine göre maliyeti en ucuz testtir. Bu test çeşidinde kontrol edilen durumlar
aşağıda verilmiştir.

• Kodlama yapılırken yanlış veya fazla yazılan bölümler
• Kod aracılığıyla belirli girdilerin akışı ve çalışması
• Veri girişleri sonrasında almak istenilen çıktılar
• Programda kullanılan döngülerin çalışması
• Çalışan her kod blokunun ve görevinin test edilmesi

<h3>Beyaz Kutu Test Araçları</h3>

Yaygın olarak kullanılan açık kaynak kodlu beyaz kutu test araçları (programları) şunlardır:

JUnit: Java programlama dilini kullanan yazılım test uzmanları için bir birim test aracıdır.
HtmlUnit: Yazılım test uzmanlarının kullandığı tarayıcı işlevselliğini programlı olarak simüle
eden, HTTP çağrıları yapmasına izin veren Java tabanlı bir test aracıdır. Çoğunlukla web tabanlı
uygulamalarda JUnit gibi diğer birim test araçlarının üzerinde uyum testleri yapmak için kullanılır.
PyUnit: Python programlama dilini kullanan yazılım test uzmanları için bir birim test aracıdır.
Selenium: Çeşitli platformlarda ve tarayıcılarda web uygulamalarını otomatik olarak doğrulamak için kullanılan test araçları paketidir. Python, C# ve JavaScript dâhil olmak üzere çok çeşitli
programlama dillerini destekler.

<h3>Gri Kutu (Gray Box) Test</h3>

Bu test tekniği, siyah kutu testi ile beyaz kutu testinin bir kombinasyonudur.
Çalışma yapılacak sistem hakkında temel bilgiler ve erişim izni mevcuttur. Hedef IP listesi,
sunucular vb. bilgiler güvenlik uzmanına verilir. Siyah kutu test yöntemine göre daha kısa zaman
alır. Bu test tekniğinin temel amacı, uygulamanın kodlama hatası veya yanlış kullanımı nedeniyle
oluşan sorunları bulmaktır.

<h3>Gri Kutu Test Araçları</h3>

Gri kutu testleri yapmak için aşağıda listelenmiş araçlar kullanılır.
Selenium: Çeşitli platformlarda ve tarayıcılarda web uygulamalarını otomatik olarak doğrulamak için kullanılan test araçları paketidir. Python, C# ve JavaScript dâhil olmak üzere çok çeşitli
programlama dillerini destekler.
Appium: Mobil uygulamalar için test otomasyonu olan Appium 2013 yılında çıkmıştır. IOS,
Android ve Windows uygulamalarının test edilmesini sağlar.
NUnit: Açık kaynak kodlu .Net platformundaki bütün dilleri destekleyen, yazılımlara birim
testi yapmak için kullanılan bir Framework’tür. 

Aşağıdaki işlem adımlarına göre gri kutu testini yapınız.
1. Adım: Maillere bakmak için öncelikle oturum açma sayfasında adresi ve şifreyi doğru
şekilde yazınız. Giriş başarılı ise kullanıcıya ne gibi haklar verildiğini inceleyiniz.
2. Adım: Maillere bakmak için oturum açma sayfasında adres veya şifreden herhangi biri
yanlış yazıldığında kullanıcıya nasıl bir mesaj verildiğini inceleyiniz.
İki adımdan oluşan bu çalışma bir gri kutu test örneğidir. Test kullanıcısı, oturum açma
sayfasında şifresini ve mail adresini yazarak bu bilgilerin işlevselliğini test etmeye çalışır. Bir başka
deyişle test kullanıcısı gerekli bilgileri girer ve veri tabanındaki bilgilerle bunların doğruluğunu
karşılaştırır. Kullanıcı bu şekilde sistem davranışını kontrol eder.

<h3> Siyah Kutu (Black Box) Test </h3>

Hedef sistem hakkında hiçbir bilgi mevcut değildir. Bilgi toplamak çok zaman alır. Güvenlik
uzmanı olan kişi, hacker gibi düşünerek sistem hakkında bir açık bulabilmek için çok sayıda araç
(program) ve yöntem denemek zorundadır.

<h3>Siyah Kutu Test Yöntemleri</h3>


Programlardaki bir dizi işlevi sistematik olarak test etmek için test senaryoları tasarlanmalıdır.
Test uzmanları aşağıdaki siyah kutu testi yöntemlerini kullanarak test senaryoları oluşturabilir.
Eşit Bölümlere Ayırma: Bu yöntemle sisteme veya uygulamaya giriş değerleri sonuçtaki
benzerliğine göre farklı sınıflara veya gruplara ayrılır.
Sınır Değer Analizi: Bu yöntem tüm test seviyelerinde uygulanabilir. Bu yöntemin uygulaması
kolay, hata bulma becerisi yüksektir.
Karar Tablosu: Karmaşık iş kurallarına sahip sistemlerin test edilmesinde kullanılan yöntemdir.
Karar tablosu yönteminin en büyük avantajı, test sırasında gözden kaçabilecek olasılıkların net bir
şekilde listelenerek gözden kaçırma riskinin en düşük seviyelere indirilmesidir.
Durum Geçişi: Belli iş kurallarına bağlı şartların oluşması ve bir durumdan diğerine geçilerek
bir noktada sonlanması durumunu test etmektir.
Hata Tahmini: Kodda geçerli olabilecek hatayı tahmin etmeye yönelik bir çalışmadır. Hata
tahmin tekniği herhangi bir özel kurala uymaz.
Grafik Tabanlı: Tüm nesneler belirlenir ve grafik hazırlanır. Bu nesne grafiğinden her nesne
ilişkisi belirlenir ve hataları keşfetmek için test senaryoları yazılır.
Karşılaştırma: Bu yöntemde test etmek için aynı yazılımın farklı bağımsız sürümleri birbirleriyle karşılaştırılır.

<h3>SIZMA TESTİ UYGULAMA ALANLARI </h3>

• Ağ güvenliği sızma testleri
• Web uygulamalarına yönelik sızma testleri
• Mobil uygulamalar için sızma testleri
• Kritik altyapılı sistemler için sızma testleri
• Yük (DDoS) testleri
• Bulut sistemi için sızma testleri
• Kablosuz ağlar için sızma testleri
• Sosyal mühendislik testleri
• Veri tabanı sızma testleri


<h3>Ağ Sızma Testleri</h3>

Bu testler, iç ağ sızma testleri ve dış ağ sızma testleri olmak üzere ikiye ayrılır.

İç Ağ (Internal) Sızma Testleri: Bir devlet kurumunun veya özel bir kurumun kendi içindeki
ağ sistemine veya bilgilere erişilebileceğini araştırır . Güvenlik uzmanı ağda bulunan
cihaz, yazılım, şifreler gibi bütün ayrıntıları kontrol etmek zorundadır.


İç ağ sızma testi için yapılması gereken işlemler şunlardır :

• İç ağda mevcut bulunan ağ numaralandırmasını (IP listesi) kontrol etmek
• Bir veya daha fazla program (araç) kullanarak ağ genelinde güvenlik açığı taraması gerçek-
 leştirmek
• Nmap gibi bir program ile tüm ağı tarayarak hangi bağlantı noktalarının ve hizmetlerin çalışıp
 çalışmadığını belirlemek
• Wireshark gibi açık kaynak kodlu bir programla kablosuz ağ trafiği de dâhil olmak üzere ağ
 trafiğini taramak ve veri paketlerini incelemek
• Ağda kullanılan işletim sistemleri ve yazılımlar için güvenlik açıkları olup olmadığını kontrol
 etmek
 • İşletim sistemlerinin ve kullanılan yazılımların güncel olup olmadığını kontrol etmek
• Standart bir metasploit taraması yaparak bulunan güvenlik açıklarından yararlanmak için
 uygun exploitler seçmek ve kullanmak
• Ağdaki bilgisayarların paylaşımlarına bağlanmayı denemek
• Ana bilgisayarlarda şifreleri kırmaya çalışmak
• Sunucularda, yazıcılarda, anahtarlarda, yönlendiricilerde ve kablosuz erişimde varsayılan
 parolaları denemek
• Ağın herhangi bir yerinde yetkisiz cihazların veya yazılımların olup olmadığını kontrol etmek
• Artık kuruluşta bulunmayan çalışanlar için hâlâ aktif hesapların olup olmadığını kontrol
etmek
• Kullanılan parolaların ne sıklıkla değiştirildiğini kontrol etmek
• Rapor oluşturmak

Dış Ağ (External) Sızma Testleri: Bir devlet kurumunun veya özel bir kurumun dışarıya açık
olan sistemleri üzerinden hangi bilgilere ve sistemlere erişilebileceğini araştırır .
Güvenlik uzmanı dış ağla ilgili olan cihaz, yazılım, şifreler gibi bütün ayrıntıları kontrol etmek
zorundadır.

Dış ağ sızma testi için yapılması gereken işlemler şunlardır:
• Ağda IP adreslerinin kontrolü için tarama işlemi yapmak
• Varsa web sunucusunun IP adresini kontrol etmek
• Yönlendiricinin ayarlarını kontrol etmek
• OWASP gibi programlar kullanarak web sitesinin güvenlik açıklarını kontrol etmek
• Web sitesi için manuel olarak tespit edilen güvenlik açıklarına saldırı yapmak
• Web sitesinde bulunan güvenlik açıklarına uygun exploitler seçerek saldırı yapmak
• Kablosuz ağı kontrol etmek ve yetkisiz kullanıcı varsa çıkarmak
• Herkesin kullanımında olan bir cihaz için parola deneme işlemi yapmak
• Rapor oluşturmak

<h3> Web Uygulama Sızma Testi</h3>

Bu test, herhangi bir web adresini hedef alarak bu adres üzerinden bir sisteme veya çeşitli
verilere erişilebileceğini araştırır . İlgili kurumun internete açık olan (DNS, FTP, mail,
web vb.) servislerini kontrol etmek için kullanılır.

Güvenlik uzmanı, web sızma testi için OWAPS Metodolojisi kılavuzunda belirtilen aşağıdaki
işlem basamaklarını sırasıyla yapabilir.

• Giriş ve Hedefler
• Bilgi Toplama
• Yapılandırma ve Dağıtım Yönetimi Sınaması
• Kimlik Yönetimi Testi
• Kimlik Doğrulama Testi
• Yetkilendirme Testi
• Oturum Yönetimi Testi
• Giriş Doğrulama Testi
• Hata İşleme
• Şifreleme
• İş Mantığı Testi
• İstemci Tarafı Test

OWASP; kuruluşların güvenilir uygulamaları tasarlamalarını, geliştirmelerini, edinmelerini,
işletmelerini ve sürdürmelerini sağlamaya adanmış açık bir topluluktur. Tüm OWASP araçları,
belgeleri, forumları ve bölümleri ücretsizdir ve uygulama güvenliğini artırmak isteyen herkese
açıktır. OWASP Web Uygulaması Güvenlik Sınama Yöntemi, siyah kutu test yaklaşımını temel alır.

<h3>Mobil Uygulama Sızma Test</h3>

Günümüzde mobil cihazlar ve bunlarla beraber kullanılan mobil uygulamalar hızla artmaktadır.
Dünya nüfusunun büyük bir bölümü akıllı cep telefonu kullanmaktadır. Mobil uygulamalarda
kredi kartı verilerinden tıbbi verilere kadar birçok hassas bilgi işlenir ve saklanır. Kullanıcı sayısının
artışı ile beraber uygulama ve uygulama içindeki modüller saldırganların hedefi hâline gelebilir.
Mobil uygulama sızma testiyle mobil cihazlar ve uygulamalar güvenli hâle getirilir.

<h3>Kritik Altyapı Sistemleri Sızma Testleri </h3>

Gelişen bilgi ve iletişim teknolojisiyle birlikte birçok ülkede kurulan kritik altyapı, devletler için
hayati öneme sahip ağların yönetildiği sistemlerin bütünüdür. Kritik altyapılar sakladığı verinin
özelliği ve ulaşılabilirliği bozulduğunda can ve mal kaybına, büyük ekonomik zararlara, kişisel ve
ulusal güvenlik zafiyetine, kamu düzeninin bozulmasına sebep olabilecek alt sistemleri içeren
kompleks sistemlerdir. Avrupa Birliği tarafından 2004 yılında bu tanımlama temel alınarak kritik
altyapıya dâhil olabilecek sektörler dokuz başlık altında gruplandırılmıştır.
Bu sektörler şunlardır:

• Enerji kurumları ve ağları
• Bilgi ve iletişim teknolojileri ile bağlantılı yapılar
• Finansman hizmetleri
• Sağlık hizmetleri ve ilişkili yapılar
• Gıdanın kendisi, yapıları ve ağları
• Suyla ilgili altyapılar
• Ulaşım araçları ve ağları
• Nükleer, kimyasal, biyolojik maddeler gibi tehlike arz eden maddelerin üretimi, saklanması
 ve nakliyesi
• Hükümete ait değerli varlıklar ve işlevler 


<h3>Hizmet Engelleme ve Yük Testi </h3>

DDoS (Denial of Service), bir diğer adıyla servis dışı bırakma saldırıları, kuruma ait olan tüm
internet sistemini detaylı analiz ederek sistemi servis dışı bırakır (Görsel 3.9). Kurumların çevrimiçi
hizmetlerinin uzun süre ulaşılmaz hâle gelmesine sebep olur. DDoS günümüzde yaygın biçimde
kullanılan saldırı türlerinden biridir. DoS ve DDoS saldırılarında amaç, sistemin verdiği hizmetleri
aksatmaktır. Gerçekleştirilecek DoS/DDoS testleri, saldırılara karşı sistemlerin veya uygulamaların
dayanıklılığını ölçmeye ve sistemde veya uygulamalarda tespit edilen problemlerin giderilmesine
katkı sağlar.

<h3>Bulut (Cloud) Sızma Testi </h3>

Bulut (Cloud), bilgisayarın sabit diski yerine veri ve programların internet üzerinden
depolanması ve bunlara erişilmesi anlamına gelir. Bulut sisteminde veriler internet ortamında
saklandığı için güvenlik sorunlarını gündeme getirir.

<h3>Kablosuz Ağ (Wireless) Sızma Test</h3>

Kablosuz ağ sızma testi, kurumların kendi iç ağlarında kullandığı kablosuz ağ altyapısının
incelenerek sisteme dışarıdan gerçekleştirilebilecek sızmalara veya kötü niyetli kişilerin
saldırılarına karşı sızma testlerinin yapılmasını ve raporlama hizmetini içerir.

<h3>Sosyal Mühendislik Testleri</h3>

Sosyal mühendislik testleri, kurum çalışanlarından kaynaklanan zafiyetleri bulmaya yönelik bir
denetim çalışmasıdır.

Çok iyi cihazlar ve yazılımlarla kurulan güvenlik sistemleri bile kullanıcı hataları karşısında
yetersiz kalabilir. Sosyal mühendislik testleri, kurum çalışanlarının insani zafiyetlerini ortaya
çıkaracak şekilde güvenlik bilinç seviyesinin ölçüldüğü testlerdir.

<h3>Veri Tabanı Sistemlerine Yönelik Güvenlik Testleri</h3>

Veri tabanı sistemlerine yönelik güvenlik testleri; kurum bünyesinde kullanılan ORACLE,
MSSQL, MySQL gibi veri tabanı sistemlerinin yetkili kullanıcı gözüyle kontrol edilmesi ve güvenlik
açısından sorun çıkarabilecek unsurların belirlenmesi ile ilgili testlerdir.

<h3>SIZMA TESTLERİNDE İZLENECEK YOLLAR </h3>

Herhangi bir kurum için gerçekleştirilecek sızma testinde en yüksek verimi elde etmek için iyi
bir planlama şarttır. Sızma testlerinde izlenecek yollar aşağıda verilmiştir.
• Sızma testinin kapsamı belirlenir.
• Sızma testinin tüm ağ için mi, ağın belirlenen bir kısmı için mi yapılacağı netleştirilir.
• Sızma testini yapacak kişi (güvenlik uzmanı) veya şirket belirlenir.
• Sızma testi sonucunda hazırlanan rapordaki eksiklikler giderilir.





