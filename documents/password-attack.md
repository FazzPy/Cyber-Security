# Parola Saldırıları

<h3>PAROLA, ŞİFRE VE HASH KAVRAMLARI</h3>

• Çevrimiçi (on-line) parola atakları
• Çevrimdışı (off-line) parola atakları
• Teknik olmayan parola atakları

<h3>Çevrimiçi Parola Saldırıları</h3>

Anlık çalışan sistem üzerinde çeşitli araçlarla parola denemeleri yaparak, kelime listelerini
(wordlist) parola alanlarına uygulayarak veya çalışan sistemi dinleyip, parolaları çözümleyerek
yapılan saldırılara çevrimiçi (on-line) parola atakları denir. Burada amaç, hâlihazırda çalışan
sistemin parolasını tespit etmektir.

Kali Linux işletim sisteminde parola atakları yapabilmek için birçok araç bulunmaktadır.
Çevrimiçi parola saldırıları yapabilecek araçlara Uygulamalar, Kali Linux, Password Attacks, Online
Attacks yolu kullanılarak ulaşılabilir.

Çevrimiçi atak yapacak menü incelendiğinde birçok araç bulunduğu görülür. Çevrimiçi ataklar
menüsünde acccheck, burpsuite, cewl, hydra, findmyhash, ncrack, medusa vb. araçlar açık
kaynak kodlu olarak bulunur. Kullanılacak atak türüne göre uygun araçlar seçilerek parola kırma
saldırısı düzenlenebilir.

<h3>Kaba Kuvvet Saldırıları</h3>

Parolayı elde etmek için deneme yanılma yöntemi kullanılarak yapılan atak türlerine kaba
kuvvet saldırıları denir. Bu yöntem, saldırganlar tarafından çok tercih edilir. Yöntemin uygulanış
kolaylığı, saldırganların bu tip saldırılara olan ilgisini artırır. Parolanın karmaşıklığı, çözüm süresini
uzatır. Bazen bir parolanın çözümü için saldırganlar günlerce bu yöntemi kullanarak atakta
bulunur.

Parolaları deneme yanılma yöntemi kullanarak çözmek bir hayli zordur. Bu nedenle saldırganlar
bazı araçları kullanarak işlerini kolaylaştırmaya çalışır. Kali Linux işletim sistemi on-line araçlar
menüsünde bulundan hydra aracı ile kaba kuvvet saldırıları düzenlenebilir.
Hydra aracı; FTP, SMTP, POP3, SSH, RDP, TELNET gibi birçok uzaktan erişim protokolünü
destekler. Hydra aracı, belirlenen servislere kaba kuvvet saldırısı gerçekleştirmeyi kolaylaştırır.
Çeşitli kelime listeleri kullanılarak aynı anda bir veya birden fazla hedefe parola kırma atakları
düzenlenebilir.

Kelime listesi; içinde rakamlar, büyük ve küçük harflerden oluşan kelimeler ve özel karakterler
barındıran, parola olma ihtimali bulunan kombinasyonların bir arada bulunduğu listelerdir. Bu
listeler, kullanıcılar tarafından hazırlanabildiği gibi internet üzerinde birçok yerden ücretsiz veya
ücretli olarak temin edilebilir. Kelime listeleri genellikle kaba kuvvet saldırılarında kullanılır.
Kaba kuvvet saldırılarına deneme kaynağı oluşturan kelime listelerinin içinde barındırdığı
kelimelerden biri sistemin şifresi olduğu takdirde atak başarıyla sonuçlanır. Kelime listesi parolayı
barındırmıyorsa atak sonuçsuz kalır ve kelime listesi kullanışsız olur. Saldırının başarıyla
sonuçlanması için kelime listeleri atak yapılan yere uygun ve listelerin içeriği geniş olmalıdır.
 Hydra aracı kelime listelerini kullanarak FTP, SMTP, POP3, SSH, RDP, TELNET gibi protokollere
ataklar düzenleme imkânı sağlar ve diğer araçlara göre daha hızlıdır. Hydra aracı, Kali
Linux işletim sistemi ile hazır bir şekilde gelmektedir. Farklı bir Linux sürümü
kullanılıyorsa Linux dağıtımının terminaline **sudo apt-get install hydra** komutu yazılarak
işletim sistemine bu araç yüklenmelidir.

Hydra aracına Uygulamalar, Kali Linux, Password Attacks, Online Attacks, hydra yolu kullanılarak
ulaşılabilir.

<img src="https://github.com/FazzPy/security/blob/main/img/hydra.PNG">

**Hydra Komut Yapısı**

hydra -l <kullanıcı adı> -P <parola> <ip adresi> <servis>

hydra -l user –P passlist.txt ftp://192.168.0.1
 
Yukarıdaki komut yazıldığı takdirde belirtilen IP adresinin FTP portuna kaba kuvvet saldırısı
gerçekleştirilir. Bu saldırıda kullanıcı adı “user” olarak denenirken parolalar için “passlist.txt”
kelime listesi oluşturulmuştur. Oluşturulan bu dosya içinde bulunan değerler saldırı için kullanılır


Hydra Parametreleri
-l: Kullanıcı adı biliniyorsa bu parametre ile birlikte kullanıcı adı yazılır.
-L: Belirtilen dosya içinden kullanıcı adını tarar.
-p: Parola biliniyorsa bu parametre ile birlikte parola yazılır.
 
 -P: Belirtilen dosya içinden parolayı tarar.
-V: Denenen kombinasyonları ekrana yazdırır. -f / -F: Kullanıcı adı ile şifre bulunduğunda
işlemi durdurur.
-s Port Numarası: Servis varsayılan portta değil de başka bir portta çalışıyor ise parametre ile
birlikte port tanımlanır.
-e nsr: Boş parola olduğunda veya kullanıcı adı ile parolanın aynı olduğu durumları tarar.
-h: Hydra ile kullanılacak parametrelerin hepsinin adını ve görevini yazar.
 
Yukarıda sıklıkla kullanılan parametrelerin görevleri verilmiştir. Tüm parametrelerin
görülebilmesi için “hydra –h” komutu uygulanır.
 
Kaba kuvvet saldırılarının gerçekleştirilebileceği araçlardan bir diğeri de medusa isimli açık
kaynak kodlu araçtır. Medusa aracı, hydra gibi birden fazla hedefe saldırı yapabilir ve bu saldırılar
için kelime listelerini kullanır. Medusa ile hedef cihazlarda AFP, CVS, FTP, HTTP, IMAP, MS-SQL,
MySQL, NNTP, PcAnywhere, POP3, REXEC, RLOGIN, RSH, SMBNT, SMTP-AUTH, SMTP-VRFY, SNMP,
SSHv2, TELNET portlarına ve servislerine parola atakları gerçekleştirmek mümkündür. Medusa
aracına Uygulamalar, Kali Linux, Password Attacks, Online Attacks, medusa yolu kullanılarak
ulaşılabilir.
 
**Medusa Komutları**
 
medusa -h 192.168.138.128 -u ”root" -P parolalistesi.txt -M http
 
medusa -h 192.168.138.128 -u ”root" -P parolalistesi.txt -M ftp
 
medusa -h 192.168.138.128 -u ”root" -P parolalistesi.txt -M telnet
 
 **Medusa Parametreleri**
 
-h: Sadece tek bir hedefe saldırı yapılacağında kullanılır.
 
-H: Birden fazla hedefe yapılacak saldırılarda kullanılır.
 
-u: Kullanıcı adı bilinen bir saldırı yapılacağında kullanılır.
 
-U: Birden fazla kullanıcı adı kelime listesinden deneneceğinde kullanılır.
 
-p: Şifresi bilinen bir saldırı yapılacağında kullanılır.
 
-P: Birden fazla şifre kelime listesinden deneneceğinde kullanılır.
 
-m: Bu parametre ile hedefteki servis bilgisi tanımlanır.
 
-b: Yapılan işlemlerin satır satır gözükmesi istenilmediğinde kullanılır.
 
-d: Medusa ile kullanılabilecek parametrelerin tamamını listeler.
 
-F: Parola ve kullanıcı adı bulunursa yapılan işlemin sonlanmasını sağlar. Aksi hâlde parola ve
kullanıcı adı bulunsa dahi denemeler devam eder.
 
 <h3>Kelime Listesi Oluşturma</h3>
 
 Parola ataklarında kaba kuvvet saldırıları için kullanılacak kelime listelerini daha verimli
saldırılar yapmak adına kullanıcının kendisi oluşturabilir. Çeşitli yöntemlerle oluşturulan kelime
listeleri ile hedef cihazların parola ve kullanıcı adlarını daha hızlı çözme şansı elde edilir.
Kelime listesi oluşturulmadan önce hedefle ilgili bilgi toplanmalıdır. İnternetten arama
yöntemleri ile hedef kişi veya kurum hakkında daha önceden internete sızmış bir parola listesinin
kontrolü yapılmalıdır. Benzerlik olan bir kelime listesi bulunursa hedefe yönelik düzenlemeler
yapılarak yeni listelerin oluşması sağlanabilir.
Kelime listesi oluştururken cewl, crunch, cupp gibi çeşitli yöntemler bulunmaktadır. Açık
kaynak kodlu araçlar kullanılarak çeşitli özelliklerde kelime listeleri hazırlanabilir.
Cewl aracı kullanılarak internet üzerindeki bir web sitesinin içinde geçen ifadelere göre bir
kelime listesi hazırlanması mümkündür.
 
Cewl Parametreleri
 
-v: Çıkan sonucu daha detaylı görmek için kullanılır.
 
-d: Bu parametre derinliği ifade etmektedir. Sayısal bir ifade ile birlikte kullanılır. 2. sayfada
aramak için –d 2 şeklinde kullanılmalıdır.
 
-w: İşlem sonucunu istenilen dosya adıyla tercih edilen yere kaydetmeye yarar.
 
-e: Sitede bulunan e-mail adreslerini çıkarır.
 
-m 6: En az 6 karakter uzunluğundaki kelimelerden oluşacak şekilde kelime listesi hazırlar.
 
 <h3>Cewl Aracıyla Kelime Listesi Oluşturma</h3>
 
 Aşağıdaki işlem adımlarına göre hedef web sitesinin içinde geçen ifadeleri kullanarak bir
kelime listesi oluşturunuz ve oluşturduğunuz kelime listesini “siberkitap.txt” ismiyle masaüstüne
kaydediniz.
 
 1. Adım: Cewl aracını Kali Linux işletim sisteminde Uygulamalar, Kali Linux, Password Attacks,
Online Attacks, cewl yolunu kullanarak açınız.
 
 2. Adım: Hedef web adresini belirledikten sonra cewl aracında 2. derinlikte araştırma
yaparak 10 karakterli kelime listesini wordlist1 ismiyle masaüstünde oluşturunuz:
  cewl –d 2 –m 10 https://hedefwebsitesi –w /root/Desktop/wordlist1
 
Oluşturulan kelime listesi masaüstünde konumlanacaktır. Yapılan işlemin sonucunu
görüntüleyiniz.
 
 Cewl kullanarak hedeflediğiniz bir web sitesinden 6 karakterli kelime listeleri oluşturunuz.
Arama verilerinde e-mail adreslerinin bulunmasını sağlayınız. Arama derinliğini sadece ilk sayfada
tutunuz ve dosyayı masaüstünde parola ismiyle kaydediniz.
 
 <h3>Çevrimdışı Parola Saldırıları</h3>
 
 Çevrimdışı saldırılar, anlık olarak hedef sistemin parola ve kullanıcı adına yönelik atak
yapmaktan farklı şekilde sistemde kullanıcı adı ve parolaların saklandığı yere ulaşmayı amaçlayan
saldırılardır. Sistemde kullanıcı adı ve parolalar çeşitli yöntemlerle saklanır. Şifrelenmiş (encyption)
veya hash edilmiş, bir başka deyişle özetlenmiş bilgiler şeklinde tutulan bu parolaların bulunduğu
dizinlere erişilerek özet bilgilerden parolalara ulaşılması amaçlanır.
Kaba kuvvet, sözlük saldırıları ve rainbow table olmak üzere üç farklı türde çevrimdışı parola
saldırısı gerçekleştirilir.
Kali Linux işletim sisteminde çevrimdışı parola atakları yapabilmek için birçok araç bulunur.
Çevrimdışı parola saldırıları yapılabilecek araçlara Uygulamalar, Kali Linux, Password Attacks,
Offline Attacks yolu kullanılarak ulaşılır.
 
 Linux tabanlı işletim sistemlerinde kullanıcı bilgileri /etc/passwd dosyasında saklanır.
Kullanıcıların isimleri ve parolaları ise /etc/shadow dosyasının içinde şifrelenmiş şekilde bulunur. 
 
  <img src="https://github.com/FazzPy/security/blob/main/img/etcshadow.PNG">
 
 Root yetkisine sahip kullanıcıya ait bilgiler, shadow dosyasının içeriğinde şifrelenmiş şekilde
verilir. Dosyadaki ifadeler incelendiğinde “:” ile ayrılmış alanların olduğu görülmektedir. Bu
alanların ilk kısmı, kullanıcı adını gösterir. Dosyaya bakıldığında kullanıcı adının “root” olduğu
görülür. İkinci ve en önemli kısım, parolanın olduğu şifrelenmiş kısımdır. Bu alanda “$6$” şeklinde
görüntülenen kısım, parola için hangi özet alma algoritmasının kullanıldığını belirtir.
 
Özet alma algoritmaları şunlardır:
 
$1$: md5 algoritması
 
$2y$: Blowfish algoritması
 
$5$: SHA 256 algoritması
 
$6$: SHA 512 algoritması
 
Shadow dosyası incelendiğinde root kullanıcı parolasının SHA 512 ile şifrelendiği görülür.
Ayrılan üçüncü kısım, parolanın 1 Ocak 1970 tarihi ile arasındaki gün sayısını; dördüncü kısım, Parola Atakları 213
parola değişikliği için gereken minimum gün sayısını; beşinci kısım, parola değişikliği yapılması
için azami gün sayısını; altıncı kısım, parola değişikliği yapılması için kalan gün sayısını; yedinci
kısım, parolanın geçersiz sayıldığı gün sayısını ve son kısım ise parolanın geçersiz olduğu gün ile
1 Ocak 1970 tarihi arasındaki gün sayısını verir. Özet bilgilerde parola süreleri ayarlanmışsa bu
bilgiler görülebilir fakat parolalar, şifrelenmiş algoritmalarla görülür ve bu algoritmaları çözmek
için çeşitli araçlara ihtiyaç duyulur.
 
 
 <h3>Çevrimdışı Kaba Kuvvet Saldırıları</h3>
 
 John the ripper, çevrimdışı bir parola atak aracıdır. Hash kırma aracı olarak kullanılan john
oldukça pratik bir araçtır. Çevrimdışı atak yapmak için öncelikle hedef makineye sızılması ve hash
dosyalarının ele geçirilmesi gerekir. Ele geçirilen hash dosyalarında yapılacak ataklarla şifreler
çözülerek parolaların elde edilmesi mümkündür.
Passwd ve shadow hash dosyaları görünür olarak gelmez. Gerek komut satırından “unshadow”
komutunu uygulayarak gerekse sistem üzerinden görünür yaparak bu dosyalar görüntülenebilir.
 
 John the ripper Aracının Parametreleri ve Kullanımı
--help: Bu araç ile kullanılacak parametrelerin listesini ve parametrelerin işlevlerinin bilgisini
verir.
--format: Şifreleme algoritmasının ne olduğuna göre özel çözüm yapmak için kullanılır.
 ÖRNEK: --format=sha512crypto
Show: Hash bilgisi çözülen şifrenin ne olduğunu ekranda görüntüler.
john [parametre] şifreli_dosya_yolu şeklinde kullanılır.
John the ripper, kullanıcıya birçok parola kırma yöntemini sağlar. Single Crack, sözlük listesi ve
kurallı sözlük listesi john aracı ile uygulanabilecek çevrimdışı saldırı yöntemlerindendir.
 
 • Single Crack Modu: Bu modda john aracı, yaygın kullanılan parolaları deneyerek şifreyi
 çözmeye çalışır. İnternetten elde edilmiş parolaları deneyen bu mod ile yaklaşık 5000
 adet yaygın parola, şifreyi kırmak için denenir.
ÖRNEK: john –single sifre.txt
• Kelime Listesi Kullanarak Şifre Kırma: Bu mod ile john aracı belirtilen kelime listelerini
 uygulayarak, şifreyi kırıp parolayı elde etme amacındadır.
John the ripper aracı ile kurallar belirtilerek şifre çözümünü filtreleme şansı yakalanır. Böylelikle şifreyi çözmek için zaman kazanılır. Bu araçta maksimum ve minimum parola uzunlukları,
özel karakter kullanılıp kullanılmayacağı, hangi özel karakterlerin kullanılacağı veya alfanumerik
değerlerin olup olmayacağı kullanıcı tarafından belirlenebilir.
 
 **John Aracıyla Parola Saldırısı**
 
 Aşağıdaki işlem adımlarına göre hash bilgileri ele geçirilmiş bir cihazın hash dosyasını john the
ripper aracıyla analiz ederek root kullanıcısının parolasını elde ediniz.

 
 1. Adım: John aracını Kali Linux işletim sisteminde Uygulamalar, Kali Linux, Password Attacks,
Offline Attacks, john yolunu kullanarak açınız.
 
 2. Adım: Elde ettiğiniz hash dosyasını masaüstüne “sifreroot” ismiyle kaydediniz ve aşağıdaki
komutları uygulayarak hash dosyasının içeriğini görüntüleyiniz.
 
root@Kali: cd Desktop
 
root@Kali:/Desktop cat sifreroot
 
Not: İçeriğe bakıldığında root kullanıcısının $6$, bir diğer ifadeyle SHA 512 kullanılarak şifrelendiği
anlaşılır.
 
3. Adım: Masaüstünde özet hash bilgileri bulunan “sifreroot” dosyasına john aracı ile aşağıdaki komutlarla atak gerçekleştirip parolayı elde ediniz.
 
root@Kali: cd Desktop
 
root@Kali:/Desktop john sifreroot --show
 
 **Hashcat** aracı ile özet bilgisi olan birçok şifrelenmiş bilginin parolası elde edilebilir. CPU tabanlı
işlem yapan hashcat aracı aynı zamanda GPU kullandığı için çok daha hızlı bir şekilde şifre çözme
işlemi gerçekleştirilebilir. Hashcat aracının birçok parametresi bulunur.
 
<h3>Hashcat Aracının Kullanımı</h3>
 
hashcat [parametre] dosyanin_yolu [mask/kelime listesi/sözlük listesi dizini]
 
hashcat -m 0 -a 0 hashdosyasi.txt pass.txt
 
 Yukarıda yazan komut incelendiğinde -m 0 parametresi ile md5 şifreleme kullanılarak
oluşturulmuş bir parolanın çözülmek istendiği görülür. -a 0 ise direkt saldırı parametresidir.
Hashcat oldukça hızlı bir şifre çözücüdür. Hashdosyasi.txt’in içeriğinde bulunan md5 şifrelerini
pass.txt içinde bulunan kelime listeleri ile deneyerek çözmeye çalışır, şifreler eşleştiği takdirde
hashcat parolaları çözer.
 
 <h3>Sözlük Saldırıları</h3>
 
 Sözlük saldırılarında elde bulunan hazır parola listelerinden yararlanılır. Hedef sisteme
atak yapılmak istendiğinde parola listelerinin olduğu hazır dosyalar kullanılır ve şifreler kısa
sürede çözülür. Dünya üzerinde belli başlı sistematik parolalar, doğum tarihleri, ad ve soyadı
kombinasyonları, cep telefonları, bölgesel ve şehirsel özellikler, hayvan adları, takım isimleri
gibi yaygın kullanıma sahip olan parola setlerinin oluşturulduğu sözlük listeleri bu saldırı
türünde kullanılır. İnternet ortamında ücretsiz veya parayla satılan sözlük listeleri bulunur. 
 
 **Crunch**, Kali Linux off-line password menüsünde hazır olarak gelen bir sözlük listesi oluşturma
aracıdır. Crunch, kullanıcının isteğine göre özelleştirilmiş kelime listeleri hazırlayarak kullanmasını
sağlayan kelime listesi oluşturma aracıdır. Kelime listelerinin yetersiz kaldığı anlarda crunch ile
oluşturulmuş sözlük listeleri çok önemli işlev görür. 
 
 <h3>Crunch Kullanımı</h3>
 
Terminal programına crunch yazarak bu araca ulaşmak mümkündür.
 
Crunch <min> <max> (özelleştirilmiş seçenekler) şeklinde bir kullanımı bulunur.
 
Min: Minimum karakter sayısı
 
Max: Maksimum karakter sayısı
 
Seçenek: -o, -p, -b, -f gibi kişinin isteğine bırakılan parametreler bulunur.
 
Terminale Man crunch yazılarak parametreler ve kullanımları hakkında detaylı bilgi alınabilir 
 
Crunch aracı ile birlikte gelen karakter kümeleri vardır. Bu kümeler kullanılarak özelleştirilmiş
sözlük listeleri oluşturulabilir. Bu kümelerden faydalanılarak kullanıcıya özgü yeni sözlük listeleri
oluşturulabilir. 
 
 Crunch, özelleştirilmiş sözlük listeleri oluşturulmasına yardımcı olurken charset.lst isimli
dosyayı kullanır. Bu dosyanın içeriğinde çeşitli karakter kümeleri bulunur ve bu kümeler
özelleştirilerek sözlük listeleri oluşturulur. Örneğin yalnızca rakamlar tercih edilecekse dosyada
bu gruba verilen numerics charseti kullanılmalıdır. charset.lst dosyasının içeriğini ve karakter
kümelerini görüntülemek için Görsel’de verilen komut girilmelidir.
 
<img src="https://github.com/FazzPy/security/blob/main/img/crunch.PNG">
 
Charset içinde bulunan kümelerden uygun olanlar seçilip, komut dizini oluşturularak sözlük
listesi hazır hâle getirilebilir.
Yalnızca rakamlardan oluşan minimum 1, maksimum 4 karakterli yeniliste.txt isimli bir sözlük
listesi oluşturulmak istendiğinde aşağıdaki komut satırı uygulanmalıdır.
 
**crunch 1 4 -f /usr/share/crunch/charset.lst numeric -o yeniliste.txt**
 
Yukarıdaki ifade -f parametresi ile charset küme değerini numeric olarak tanımlar. -o
parametresi ile de çıktı verilecek dosya oluşturulur. Yer belirtilmemişse root klasörünün içinde
yeniliste.txt isimli sözlük dosyası görüntülenebilir.
 
Dosyanın içeriği incelendiğinde minimum 1 karakterli, maksimum 4 karakterli numerik bir
sözlük listesinin oluştuğu görülür.
 
Crunch aracında -t parametresi ile kullanılabilen bazı karakterler ve görevleri şu şekildedir:
 
• @ işareti küçük harfli karakterleri yazdırmak için kullanılır.
• , işareti büyük harfli karakterleri yazdırmak için kullanılır.
• % işareti rakam yazdırmak için kullanılır.
• ^ işareti özel karakterler yazdırmak için kullanılır.
 
<h3>Crunch Aracıyla Sözlük Listesi Oluşturma</h3>
 
1. Adım: Kali Linux işletim sisteminin terminaline crunch yazarak araca geçiş yapınız.
2. Adım: Aşağıda belirtilen komutları girerek özelleştirilmiş sözlük listesini oluşturunuz:
  root@Kali: crunch
  root@Kali: crunch 10 10 –t 1881,,,,mk –o tutumluolun.txt
3. Adım: Oluşturulan tutumluolun.txt isimli sözlük listesini root klasörünü açarak kontrol ediniz.

Not:
 Sözlük listesinde geri kalan dört karakterin büyük harf olması istendiği için “,” işareti
kullanılmıştır.
 
<h3>Rainbow Tabloları</h3<
 
 Rainbow table parolaların düz ve şifrelenmiş hâlinin, bir başka deyişle hash hâlinin bulunduğu
tablolardır. Parola temelli kullanıcı doğrulama işlemleri için sistemler genellikle kullanıcı adı ve
parolayı veri tabanlarında saklar. Parolaları salt olarak saklamak doğru olmayacağı için parolalar
şifrelenip saklanır. Bu durumda saldırganın her parola için uygun hash algoritmasını tespit edip,
hash hâline erişerek elde ettiği şifrelenmiş parolanın doğruluğunu kontrol etmesi gerekir. Rainbow
tablolarının kolaylığı bu noktada devreye girer. Hazırlanmış veya hazır olan kelime listelerindeki
şifreleri tek tek denemek son derece yavaş bir işlemdir. Rainbow tablosu, içinde parolaların salt
hâlini ve hash hâlini birlikte içerir. Bu sayede sistem her parola için hash işlemini tekrar yapmak
ihtiyacı duymaz, doğrudan hashleri kontrol ederek parolaya erişebilir. Saldırgan, veri tabanına
erişip şifrelenmiş parolaları elde ettiğinde, rainbow tablosu ile olası parolaların şifrelenmiş hash
hâllerini karşılaştırarak herhangi bir kişinin parolasına ulaşabilir ve sisteme o kişinin bilgileriyle
giriş yaparak gerçek bir kullanıcı gibi davranabilir.
 
Sistem yöneticileri bu tür bir saldırıya karşın parolalara rastgele karakterler ekleyerek
parolaların hash hâllerini saklarlar. Key stretching, siber güvenlik uzmanlarının rainbow tablosu
saldırılarına karşı kullandığı bir diğer yöntemdir. Bu yöntemde salt şifre ve bazı ara karma
değerler, karma fonksiyonunda birçok defa işlenir ve her bir şifrenin karma değerini hesaplamak
için gerekli sürenin uzaması sağlanır. Klasik yöntemle rainbow tabloları karşılaştırıldığında zaman
ile bellek arasında bir tercih durumu vardır. Ne kadar çok bellek ayrılırsa (rainbow) o kadar kısa
zamanda hedefe ulaşılır.
 
 Salt: Veriler hash algoritmalarından geçirilirken rainbow tablosu saldırıları aracılığıyla kolayca
kırılamasın diye verinin sonuna, başına veya ortasında bir yere yerleştirilen karakter dizisidir.
• Siber -> hash -> 112312311231
• Siber -> salt(sona +++) -> Siber+++ -> 1823891239812
 
 Tablolar rtgen, ophcrack, SMB hash generator gibi araçlarla oluşturulabilir, çevrimiçi sitelerde
aranabilir veya internetten hazır tablolar indirilebilir. Bu yöntemin en büyük problemi, alınacak
önlemlere göre yapılan saldırının günlerce sürebilmesidir. 
 
 Rainbowcrack, Kali araçları içinde hem rainbow tabloları oluşturulmasını hem de bu tabloları
kullanarak saldırı yapılmasını sağlayan açık kaynak kodlu bir araçtır. Parola kırmanın yanı sıra rtgen
ile rainbow tabloları oluşturur, rtsort ile tabloları sıralar, rt2rtc ve rtc2rt ile rainbow tablolarının
uzantısını değiştirir.
 
 Rainbowcrack programına Uygulamalar, Kali Linux, Password Attacks, Offline Attacks,
rainbowcrack yolu kullanılarak ulaşılabilir. Aracı açtıktan sonra parametreleri ve kullanım
örnekleri ekranda görüntülenebilir.
 
 <img src="https://github.com/FazzPy/security/blob/main/img/rainbowcrack.PNG">
 
  Rainbowcrack Kullanımı ve Parametreleri
 
rtgen özet_algoritma karakter_seti minimum_karakter_sayısı maksimum_karakter_sayısı
tabloların_sıralanması zincir_uzunluğu zincir_sayısı tablo_başlangıç_sayısı şeklinde kullanımı
bulunur.
 
Özet_algoritma: LM, NT, md5, sha1
 
Karakter_seti: charset.lst dosyasında bulunan karakter kümeleri (alfanumeric, numeric vb.)
 
Minimum_karakter_sayısı: 1,2,3,...
 
Maksimum_karakter_sayısı: 1,2,3,...
 
Tabloların_sıralanması: 0,1,2,3,…
 
Zincir_uzunluğu: ..1000...10000...20000... Her bir zincirin uzunluğu belirtilir. Daha büyük
değer, başarı oranını artıracaktır ancak bu, parola kırma süresini de artırır. Uzunluk, parola kırma
süresinin karesiyle doğru orantılıdır.
 
Zincir_sayısı: Üretilecek zincirlerin sayısı belirtilir. Maksimum değer 134217728’dir. Bu değer
ile 2 GB’lık bir dosya üretilecektir.
 
Tablo_başlangıç_sayısı: 0, 1, 2,… Her zincir için başlangıç değerinin kaç olacağı belirtilir.
 
Aşağıda belirtilen komutlar yazılarak oluşturulacak tablo bir hayli kaplar ve rtgen ile özet
oluşturulması da ortalama yirmi dakika sürer.
 
<img src="https://github.com/FazzPy/security/blob/main/img/rtgen.PNG">
 
Rtsort ile zincirlerin bitiş değerleri daha kolay bir arama için sıralanabilir. Rtgen ile oluşturulan
tablolar rcrack ile kullanılmadan önce rtsort ile sıralanmalıdır. Rcrack eldeki özetlerin tablodaki
eşlerini bulacak olan esas araçtır. Örnek ifade şu şekilde olacaktır :
 
rcrack kullanılacak_tablo.rt -seçenek hash\hash_dosyası\pwdump_dosyası
 
Rcrack ile kullanılabilecek seçenekler aşağıda verilmiştir:

-f : ile pwdump dosyası
-l : ile içinde özetlerin bulunduğu bir dosya
-h : ile direkt olarak özetin kendisi
 
 
<h3>Teknik Olmayan Parola Atakları</h3>
 
Teknik olmayan saldırılar, içeriğinde teknik bilgi ve donanım gerektirmeden yapılan saldırılardır.
Parolasını elde etmek için bir kişinin takibini yapmak, klavye tuşlarının hareketlerini elde eden
keylogger programları kullanmak ve sosyal mühendislik yöntemleri kullanarak kişilerin yerine
parolalarını ele geçirmek teknik olmayan parola ataklarına girer.
Kişilerin kullanıcı girişi gerektiren herhangi bir siteye girme denemeleri yapması, pass the
hash tarzı açık kaynak kodlu araçları kullanması ve internet ortamında bulunan çeşitli keylogger
araçları kullanması bu atak türlerinin en yaygın örnekleridir.
 
 Özellikle sosyal mühendislik yoluyla şifre elde etmeye çalışan kişilere karşı dikkatli olunmalıdır. Cihazların güvenlik protokollerinin güncel olması, antivirüs programı kullanılması ve en
önemlisi kullanıcıların dijital okuryazarlığının bulunması bu tarz teknik olmayan saldırıları önler.
