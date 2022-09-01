# Penetrasyon Testleri - 1


<h3> Metasploit </h3>

Metasploit, güvenlik testleri için geliştirilmiş açık kaynak kodlu bir test aracıdır. Metasploit,
Ruby programlama diliyle yazılmıştır ve Kali Linux içinde exploitleri kullanmaya yarayan bir araçtır.

Metasploit; sistemlerde bulunan açıkların tespit edilmesi, sistemlere sızılması, sistemlerin
sömürülmesi için gerekli programları içinde barındıran bir araçtır. Metasploit programında
1000’den fazla exploit aracı bulunmaktadır. Bu exploitlerin kullanımı için parametreler ve
modüller de vardır. Bu program, https://www.metasploit.com/ adresinden indirilebilir. 

Metasploit kullanılarak şu işlemler yapılabilir:
• Bir exploit seçme ve yapılandırma
• Veriyi seçme ve yapılandırma
• Hedef sistemin seçilen istismara duyarlı olup olmadığını test etme
• Saldırı önleme sisteminin (IPS) veriyi görmezden gelmesi için kodlama tekniği

Kali Linux işletim sisteminde terminal ekranına “msfconsole” yazarak Metasploit programı
çalıştırılır. Metasploit ile ilgili kullanabilecek parametrelerden bazıları şunlardır:

help: Hangi komutların kullanılabileceğini görüntüler.
search: Exploit araması yapar.
show: İstenen ifadeleri gösterir.
use: İstenen exploitin kullanılmasını sağlar.
set: Bir değişkene değer atamak için kullanılır.
set RHOST: Hedef IP adresidir.
set LHOST: Kullanıcı IP adresidir

Payload, hedef sistem üzerinde yıkıcı bir eylem gerçekleştiren, ayrıcalıklı erişim ve izinler
sağlayan kötü niyetli kodu ifade eder (Bir kullanıcı oluşturma, bir işlemi başlatma veya taşıma ve
hatta bir aşamada dosyaları silme vb.).

Msfvenom, Metasploit programı altında bulunan bir payload üretme aracıdır. 

<h3> SIZMA TESTİ AŞAMALARI </h3>

Sızma testi; bilgi toplama, ağ haritalama, zafiyet tarama, exploit seçimi, erişim elde etme,
araştırma, erişimlerin korunması, izlerin silinmesi, raporlama aşamalarından oluşur.

<h3>Bilgi Toplama </h3>

Sızma testi için belirlenen hedef hakkında bu aşamada
detaylı bilgi toplanır . Bu hedef bir web sayfası
olabilir. Bu hedef hakkında kimdir, nedir, ne iş yapar, hangi
sistem üzerine kuruludur vb. sorulara cevap aranır. 

Bilgi toplama, aktif bilgi toplama ve pasif bilgi toplama olmak üzere ikiye ayrılır

Pasif Bilgi Toplama

Pasif bilgi toplama, internet üzerinden herhangi bir araç veya program kullanılmadan yapılan
bilgi toplamadır. Arama motorlarından veya sosyal paylaşım platformlarından pasif bilgiler toplanabilir.

Aktif Bilgi Toplama

Aktif bilgi toplama, çok sayıda araç (program) kullanılarak yapılan bilgi toplama yöntemidir.
Aktif bilgi toplama işleminde ilk olarak port taraması yapılır. Sistemler hakkında hiçbir bilgi yoksa
sistemlerin belirlenmesinde hızlı bir “ping” taraması kullanılabilir. Bazı test uzmanları sadece açık
TCP ve UDP portlarına bakar

Aktif bilgi toplama işlemi Nmap programı ile yapılır.
Nmap Programı: Nmap, ağ taraması ve zafiyet tespiti için kullanılan açık kaynak kodlu bir
araçtır. Gordon Lyon tarafından geliştirilmiştir. Kali Linux denilen ücretsiz işletim sisteminde
bulunmaktadır. Bu program Windows işletim sistemine de yüklenebilir. Ağ yöneticilerine ağ
ortamlarını taramada büyük kolaylık sağlar. Bu program, https://nmap.org/download.html
adresinden indirilerek bilgisayara kurulabilir. Program çalıştırıldıktan sonra komut satırına ilgili
komutlar yazılarak işlem yapılabilir. 

<h3>Ağ Haritalama</h3>

Ağ haritalama, hedef sistemin ağ yapısının belirlenmesi için yapılan çalışmadır. Bu çalışma
yapılırken nmap gibi gelişmiş araçlar kullanılır. Bu program çalıştırıldığında sistemdeki açık portlar,
servisler, servislerin hangi yazılımın hangi sürümü olduğu bilgileri, ağ girişlerinde bulunan VPN,
firewall, IPS cihazları ve sunucuda çalışan işletim sistemi belirlendikten sonra hedef sisteme ait
ağ haritası çıkarılır.

<h3>Zafiyet Tarama</h3>

Bu sürecin amacı, belirlenen hedef sistemlerdeki açıklıkların ortaya çıkarılmasıdır. Bu işlem
için otomatize (nessus, nmap) araçlar kullanılır. Bu araçlarla yapılan zafiyet arama işlemlerinde
amaç, sistemin o anki güvenlik görüntüsünü almaktır. Kullanılan araç, bu işlem sonucunda
güvenlik açıklarını ve detaylarını gösteren bir rapor da oluşturur.
Zafiyet örnekleri şunlardır:
• Basit şifre ve parola kullanımı
• Web uygulamalarındaki önemli dosyalara erişilebilir olması
• Sistem içinde kritik öneme sahip dosyaların paylaşımda olması
• SSL şifrelemedeki eksiklikler
• SSL şifreleme desteği olmayan web siteleri
• İşletim sistemi ve uygulamalarındaki güncelleme eksiklikleri
• İletişim altyapısındaki eksiklikler 

<h3>Uygun Program ve Exploitlerin Seçimi </h3>

Hedef sistemde bulunan zafiyetler belirlendikten sonra uygun programlar ve exploitler
belirlenir. Zafiyetin çeşidine göre hedef sistemle bağlantı kurmak için gerekli exploitler ücretli
veya ücretsiz olarak internetten bulunabileceği gibi güvenlik uzmanı tarafından da yazılabilir.

<h3>Exploit (Açıklardan Yararlanma veya Sömürme İşlemleri) </h3>

Exploitler hedef sistemin açıklarını sömürmek, kullanmak, ele geçirmek ve bilgi çekmek
amacıyla oluşturulan yazılım ve araçlardır. Exploitler; C, Perl, Ruby, Python ve Php gibi programlama dillerinde küçük programlar hâlinde hazırlanır. İnternette ücretli veya ücretsiz kullanılabilecek exploitler mevcuttur. Exploitler kullanım alanlarına göre üç gruba ayrılmıştır. Bunlar; uzaktan
(remote) exploit, yerel (local) exploit, sıfır gün (zero day) exploit olarak sıralanabilir.

Uzaktan (Remote) Exploit: Uzaktaki bir bilgisayara ulaşmak ve sistemin açıklarını kullanarak
çeşitli bilgiler elde etmek için kullanılır.

Yerel (Local) Exploit: Sisteme içeriden erişimde bulunarak çeşitli bilgileri almak için kullanılır.
Hedef sistemde direkt olarak çalışan exploitlerdir. Hedef sisteme giriş yapıldığında hak yükseltme
işlemlerinde kullanılır. 

Sıfır Gün (Zero Day) Exploit: Bir sistemde daha önce görülmemiş bir zafiyet bulan ve bu
zafiyeti sömürmek için yazılan exploitlere denir. En tehlikeli exploit çeşidi budur. Bu exploitin çok
tehlikeli olmasının nedeni, bu açıklığın henüz sistem yöneticileri tarafından bilinmemesidir.

<h3>Erişim Elde Etme ve Yetki Yükseltme</h3>


Sızma testi sürecinde amaç, sisteme bir şekilde giriş hakkı elde etmektir. Bu süreçten sonra
sistemdeki kullanıcının haklarının artırılması hedeflenmelidir. Erişim elde edilen sistemlerde
yetki yükseltme işlemleri ile sistemdeki kısıtlamalar atlatılmaya çalışılır. Linux sistemler için root,
Windows sistemler için NT AUTHORITY\SYSTEM yetkileri kazanılır.
Erişim elde edilen sistemler üzerinden doğrudan erişilmeyen diğer ağlara yayılma işlemleri
yapılarak tüm sistemin ele geçirilmesi denenir. Erişim sağlanan sistemlerde çalışan uygulamalara
ait giriş bilgileri elde edilir. Önceki adımda kazanılan yüksek yetkiler ile sistemler üzerinde
şifrelenmiş veya açık bir şekilde bulunan parolalar elde edilir. Sistemler içinde bulunan önemli
dosyaların, dokümanların bir kopyası alınır ve rapora eklenir. 

<h3>Detaylı Araştırma</h3>

Sızma sürecinde erişim yapılan sistemlerden admin haklarını ele geçirmek için işletim
sistemindeki ve yazılım uygulamalarındaki tasarım hatalarından (desing flaws), programlama
hatalarından, yazılım hatalarından (bugs) ve yapılandırma hatalarından yararlanılır. Bu haklar;
saldırganın gizli verileri görmesini, dosyaları silmesini, virüsler ve Truva atları gibi kötücül
programları sisteme yüklemesini sağlar.

<h3>Erişimlerin Korunması</h3>

Sisteme girildiğinin anlaşılmaması için bazı önlemlerin alınmasında fayda vardır. Bunlar; giriş
kayıtlarının (logların) silinmesi, dışarıya erişim açılacaksa gizli kanalların kullanılması (covert
channel), arka kapı (backdoor), rootkit yerleştirilmesi olarak sıralanabilir. Erişim kontrolü için
overt ve covert olmak üzere iki türlü iletişim kanalı vardır.

Overt Channel: Yasal iletişim hattıdır. Sistem yöneticileri tarafından veri taşıma amacıyla
oluşturulmuştur.

Covert Channel: Trojanlar ile veri hırsızlığı gibi kurum politikalarına aykırı amaçlar için
kullanılan yetkisiz ve gizli kanaldır.

Arka Kapılar (Backdoor): Yazılım ve sistemlerde istemli veya istemsiz olarak bırakılan, veri
girişi veya çıkışı (veri sızdırması vb.) amacıyla kullanılan açık noktalardır.

Rootkit: Saldırgan istediğinde bağlantı kurması için kullanılan, dosya gizlemeye yarayan,
yasal yazılımları zararlı yazılımlarla değiştiren, amacına göre klavye girdilerini dinleyebilen arka
kapılardır. 

<h3>İzlerin Silinmesi </h3>

Hedef sistemde oluşturulmuş arka kapılar, test amaçlı scriptler, sızma testleri için eklenmiş
tüm veriler not alınmalı ve test bitiminde silinmelidir. Çalıştırılan exploitler sistemde herhangi bir
değişiklik yaptıysa yazılımlar orijinaline döndürülür ve oluşturulan dosyalar silinir.

<h3>Raporlama</h3>

Rapor, bir testin en önemli kısmıdır. Raporlar ne kadar açık ve detaylı hazırlanırsa kurumun risk
değerlendirmesi ve güvenlik açıklarını gidermesi de o kadar kolay olur. Testler esnasında ortaya
çıkan güvenlik açıklarının belgelenip, sözlü olarak anında bildirilmesi test yapan ekibin görevleri
arasındadır.

Rapor bulgularının farklı kategorilerde değerlendirebilecek şekilde hazırlanması gerekir.
Raporda sızma testinin hangi programlarla yapıldığının bildirilmesi, ilgili kurumun sistem
yöneticilerinin farkındalıklarını artırmak açısından önemlidir. Sızma testi raporu, ilgili kurumun
genel güvenlik değerlendirmesini ve iyileştirme önerilerini içermelidir.

<h3>Zamanlama</h3>

Hedef sistemlerin kritiklik durumlarına göre sızma testlerinin zamanlaması ayarlanmalı,
üretimi veya verilen hizmeti aksatmayacak şekilde uygun bir zaman belirlenmelidir. DDoS
testlerinin genellikle hafta sonu ve gece yarısı gerçekleştirilmesi önerilir.

<h3>SIZMA TEST KALİTESİNİN ÖLÇÜMÜ</h3>

Bu konuda ilgili kurumun yaklaşımı çok önemlidir. Kurumlar genellikle sızma testi yerine zafiyet
tarama işleminin yapılmasını ister ancak zafiyet tarama işlemleri sistemin tüm zayıf yönlerini
bulmaya ve gerekli önlemleri almaya yetmeyebilir. Bu nedenle sızma testi çeşitlerinin hepsi
uygulanarak sistemin bütün zafiyetleri ortaya çıkartılmalı ve alınacak önlemler tespit edilmelidir.
Bu şekilde tam bir güvenlik oluşturulabilir.
Sızma testleri uygulanıp, gerekli görülen iyileştirme çalışmaları tamamlandıktan sonra
doğrulama testi yapılarak güvenlik durumunun ne kadar iyileştirildiği belirlenmelidir.

<h3>BULGULARIN SAKLANMASI</h3>

Sızma testlerini yapan ekiplerin elde ettiği sonuçlar fiziksel ortamda koruma altına alınmalıdır.
Aksi hâlde hedef sistemlere ait çok hassas bilgiler başkalarının eline geçebilir. Test sonuçlarını
saklamak için Truecrypt gibi disk şifreleme yazılımları kullanılabilir.

