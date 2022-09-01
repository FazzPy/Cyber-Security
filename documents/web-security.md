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


