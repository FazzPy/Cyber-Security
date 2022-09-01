# Kriptografi

<h3> ŞİFRELEME ALGORİTMALARI </h3>

Ağ yapılarında kullanıcının başka kullanıcıya gönderdiği bilgi üçüncü kişiler tarafından
dinlenebilme tehlikesi altındadır. Bilgilerin alıcı dışındaki kullanıcılar tarafından okunmaması için
koruma altına alınması gerekir. Yapılan bu koruma işlemine şifreleme (encrypt) adı verilir. Veriyi
şifrelemek (ciphertext) ve şifrelenen verinin şifresini çözmek için matematiksel algoritmalar
kullanılmalıdır. Şifreli verinin geri döndürülme işlemine şifre çözme (decrypt) adı verilir. Sistematik
anahtarlama sisteminde şifre ve deşifrede aynı anahtarlama kullanılır. Açık anahtarlama sisteminde ise şifrelemek için açık anahtarlama, deşifre yapmak için gizli anahtarlama kullanılır. Dijital
imzalar açık anahtar sistemi ile üretilir. Dijital imza sahibi, gönderilen veriyi imzalamak için gizli
anahtar kullanırken alıcı ise göndericinin açık anahtarını kullanarak veriyi kontrol eder.
Şifreleme algoritmaları anahtar kullanma yöntemlerine göre gizli anahtarlı (simetrik) şifreleme
algoritmaları ve açık anahtarlı (asimetrik) şifreleme algoritmaları olmak üzere iki kategoriye ayrılır.

<h3>Simetrik Şifreleme Yöntemleri</h3>

Simetrik şifreleme, bilgileri şifrelemek ve deşifre etmek için yalnızca bir gizli anahtar içeren
en basit şifreleme türüdür. Gizli anahtar şifreleme algoritmaları şifrelemek ve çözmek için aynı
anahtarı kullanır. Bu durum, veri şifrelemek açısından daha sorunsuz bir yaklaşımdır. Gizli anahtar
şifreleme yaygın kullanılan bir yöntemdir. Bu tip algoritmalarda şifrelenen veriyi alıcıya gönderirken ayrıca gizli anahtarı da alıcıya güvenli bir yöntemle göndermek gerekir. Gizli anahtar şifreleme
sistemi çok hızlı şifreleme ve şifre çözümleme işlemlerini gerçekleştirebilir. Görsel'de bir
simetrik şifreleme yöntemine ait blok diyagram verilmiştir.

<img src="https://github.com/FazzPy/security/blob/main/img/kritpgrafi.PNG">

Simetrik şifrelemenin avantajları şunlardır:
• Şifreleme ve şifreyi çözme işlemleri hızlıdır.
• Alıcı ve verici arasındaki iletişimin gizliliği sağlanır.
• Şifreli metin çözülemedikçe orijinal metin değiştirilemeyecektir.

Bunun yanında simetrik şifreleme sürecinin birtakım zorlukları da mevcuttur. Simetrik
şifrelemenin sahip olduğu başlıca zorluklar şu şekilde sıralanabilir:

• Anahtar saklamak zordur.
• n kullanıcılı bir sistem için [n * (n-1) / 2 ] anahtar saklanmalıdır.
• Güvenilir anahtar dağıtımı zordur.
• Kimlik doğrulama (authenticity) sağlamaz. Aynı anahtara sahip olan herhangi biri tarafından
 veri şifrelenmiş olabilir.
• Bütünlük sağlamaz. Araya giren kişi tarafından veri değiştirilmiş olabilir.
• Kimlik doğrulama ve bütünlük sağlamadığı için inkâr edilememezlik sağlamaz.

<h3>DES (Data Encryption Standart) Veri Şifreleme</h3>

DES dünyada en yaygın kullanılan şifreleme algoritmalarından biridir. DES, şifrelenecek açık
metni parçalara bölüp (blok) her parçayı birbirinden bağımsız olarak şifreler ve şifrelenmiş
metni açmak için de aynı işlemi bloklar üzerinde yapar. Bu blokların uzunluğu 64 bittir. Anahtar
uzunluğunun kısa olması nedeniyle DES şifreleri kırılabilir. Bunun üzerine Triple-DES, bir başka
deyişle 3DES geliştirilmiştir. 3DES, DES’in üst üste üç kere kullanılması yöntemiyle elde edilmiştir.
Bu sebeple normal DES’e göre üç kat daha yavaş çalışır. AES’in çıkması üzerine DES popülerliğini
kaybetmiştir.
DES, bit tabanında (1 ve 0) çalışan bir şifreleme algoritmasıdır. Bu şifreleme algoritmasında şifrelenecek mesaj 64 bitlik parçalara bölünür. Her 64 bitlik blok ise 8 karaktere karşılık
gelir (1 bayt 8 bittir.). 64 bitlik mesaj daha sonra sağ ve sol olmak üzere iki kısma ayrılır. 32
bitlik sağ kısım çaprazlanarak çıkışın sol bölümüne doğrudan aktarılmaktadır. Ayrıca bu 32
bitlik sağ kısım önce anahtar üreticisi tarafından üretilen 48 bitlik anahtar ile F fonksiyonuna
tabi tutulup sol kısımdan gelen 32 bitlik mesaj ile XOR işlemi yapılır. Elde edilen sonuç, çıkışın
sağ bölümüne aktarılır. Bu işlem 16 defa tekrar edileceği için ilk işlemde doğrudan aktarılan
32 bitlik sağ kısım, bir sonraki tekrarda sol kısma geçeceğinden F fonksiyonuna ve XOR (özel
veya değil) işlemine tabi tutulacaktır. Böylelikle şifreleme işlemi uygulanmamış hiçbir bit kalmayacaktır.

DES şifreleme algoritmasının çalışma mantığı:

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/des.PNG">

Blowfish: Günümüzün en hızlı blok şifreleyici algoritmalarından biridir. Bu şifreleme yönteminde karmaşık anahtar çizelgesi kullanıldığı için bu yöntemle elde edilen şifrelerin kırılması
oldukça zordur. Blowfish, 23'ten 448 bite kadar anahtar uzunluğuna sahiptir.

AES ( Advanced Encryption Standart ): DES’in zayıf yönlerinin kuvvetlendirilmiş hâlidir ve
blok şifreleme algoritmasını kullanır. AES uzunluğu 128 bitte sabit olan blok ile uzunluğu 128,
192 veya 256 bit olan anahtar kullanır. Kullanılan tekniklerden bazıları baytların yer değiştirmesi,
4x4 matrisler üzerine yayılmış metin parçalarının satırlarına uygulanan kaydırma işlemleridir.
Günümüzde kullanılan en popüler algoritmalardan biridir ve Brute Force saldırılarına karşı
dayanıklı olduğu düşünülür.

RC4 ( Rivest Encryption 4 ): Bu algoritma, şifrelenecek veriyi akan bir bit dizisi olarak algılar.
RC4, belirlenen anahtar ile veriyi şifreleyen bir algoritmadır. 128 bitlik bir RC4 şifrelemesi sağlam
bir şifreleme olarak kabul edilir. Bankacılık şifrelemelerinde yaygın olarak RC4 şifrelemesi kullanılır.

RC5 (Rivest Encryption 5): Modern şifreleme algoritmaları sınıfında yer alır. 16, 32 ve 64
bitli kelime uzunlukları ile çalışabilir. Anahtar boyutu ve döngü sayısı değişken olarak alınabilir.
Böylece yüksek anahtar boyutu ve fazla döngü sayısı ile uzun çalışma zamanı alır fakat kırılması
neredeyse imkânsız şifreler üretebilir.

<h3>Tek Yönlü Anahtarsız Şifreleme (Hash Fonksiyonları)</h3>

Değişken uzunluktaki bir veriyi girdi olarak alıp sabit uzunluktaki çıktıya dönüştüren fonksiyonlara hash (özetleme) fonksiyonları denir. Hash fonksiyonları verinin bütünlüğünü sağlamak
amacıyla kullanılan algoritmalardır. Bu algoritma ile alıcının orijinal metnin değiştirilmediğini
tespit etmesi hedeflenmektedir. İyi bir hash algoritması iki farklı girdiden aynı hash değerini
üretmeyecek kadar karmaşık olmalıdır. İki farklı değer için aynı hash kodu üretilirse bu durum
hash çarpışması olarak bilinir. Hash algoritmasına şifrelenmesi istenilen metin girilir ve hash
fonksiyonuyla metin hashing işlemi yapılır. Elde edilen metin, hash değeridir. Hash
algoritmaları şifreleme algoritması içermez.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/hash.PNG">

Hashing fonksiyonları temel olarak iki amaçla kullanılır.
• Gönderilen verinin bütünlüğü kontrol edilir. Bu şekilde verinin değişmediğinden emin olunur.
• Hedefe gönderilecek verinin boyutu, büyük boyutlardan daha küçük boyuta düşürülür.

SİBER kelimesi için hash fonksiyonu aşağıdaki gibi hesaplanabilir.
SİBER kelimesindeki bütün harfler, alfabedeki sıra numarasına göre kodlanır. S=22, İ=11, B=2,
E=6, R=21 olarak hesaplanır. Daha sonra tüm bu sayısal değerler toplanır. SİBER kelimesinin
özetleme algoritması sonucu 22+11+2+6+21=62 olarak bulunur. 

Not;
“SİBER” kelimesinin özetleme algoritması 62’dir ancak 62 sonucunu verecek başka girdilerin
olabileceği göz önünde bulundurulmalıdır. Örneğin “ÖMER” gibi bir parolanın özet fonksiyonu
da 62 sonucunu vermektedir. Bu durumda parolayı elde etmek isteyen biri, başka bir özet
fonksiyonundan farklı bir parolayı bulabilir. Özellikle parola saldırıları veya sözlük saldırılarına
karşı savunmasız kalabilir.
Hash fonksiyonları farklı alanlarda da kullanılmaktadır. Bunların arasında en sık kullanılan alan
parolaların saklanmasıdır. Parolalar kullanıcının yazdığı şekilde saklanmaz, özetleme fonksiyonu
 Şifreleme Teknikleri 177
kullanılarak kodlanır. Bu sayede parola özeti kaydedilse bile parolanın kendisi elde edilemez.
Windows işletim sistemlerinde LM ve NTLM özetleri, Linux işletim sistemlerinde ise md5 gibi
özetleme fonksiyonları kullanılır. Parola doğrulama özellikle kriptografik hash için önemli bir
uygulamadır. Kullanıcıların şifrelerini düz metin belgesinde saklamak bir felakete yol açar.
Belgeye erişmeyi başaran herhangi bir bilgisayar korsanı, korumasız şifrelerden oluşan bir
hazine keşfedecektir. Bu yüzden şifrelerin karma değerlerini saklamak daha güvenlidir. Bir
kullanıcı herhangi bir parola girdiğinde hash değeri hesaplanır ve ardından tabloyla karşılaştırılır.
Hesaplanan hash değeri kaydedilen değerlerden biriyle eşleşirse bu geçerli bir paroladır ve
kullanıcının erişimine izin verilebilir.


<h3>md5 Hash Fonksiyonu</h3>

tma, girdinin büyüklüğünden bağımsız olarak 128 bitlik bir çıktı üretir ve
girdideki en ufak bir bit değişikliği bile çıktının tamamen değişmesine sebep olur. md5 genellikle
veri bütünlüğünü doğrulamak için bir sağlama toplamı olarak kullanılır. Bir verinin (dosyanın)
doğru transfer edilip edilmediğinin veya değiştirilip değiştirilmediğinin kontrol edilmesi, md5’in
en fazla kullanıldığı yerlerden bazılarıdır.
Bir md5 hash işlemi, herhangi uzunlukta bir dizi alınıp, 128 bitlik bir algoritmaya kodlanarak
oluşturulur. Aynı girdiye ait md5 algoritması her zaman aynı çıktıyı üretir. Bu algoritma genellikle
veri tabanı parolalarını şifrelemek için kullanılır.

<h3> SHA-1 Hash Fonksiyonu </h3>

SHA-1 (Secure Hash Algoritması), güvenli hashing algoritması anlamına gelir. Algoritmanın
temel görevi, rastgele bilgilerin sabit bir uzunluğa sahip değerlere dönüştürülmesidir. SHA-1,
uzunluğu en fazla 264 bit olan mesajları girdi olarak kullanır ve 160 bitlik mesaj özeti üretir. Bu
işlem sırasında ilk önce mesajı 512 bitlik bloklara ayırır ve gerekirse son blokun uzunluğunu
512 bite tamamlar. SHA-1 algoritması ile sadece şifreleme işlemi yapılır, şifre çözümleme
işlemi yapılamaz. SHA-1 algoritması; e-posta şifreleme uygulamaları, güvenli uzaktan erişim
uygulamaları, özel bilgisayar ağları ve daha birçok alanda kullanılabilir. Günümüzde güvenliği
artırmak amacıyla veriler SHA-1 ve md5 algoritmaları birbiri ardına kullanılarak şifrelenir.
Basit bir ifadeyle SHA-256, 256 bitlik özet uzunluğuna sahip kriptografik hash fonksiyonlarından
biridir. Bu anahtarsız hash işlevi, bir MDC (Manipulation Detection Code) anlamına gelmektedir.
SHA-256, SHA ailesinin altı çeşidinden biridir (SHA-224, SHA-256, SHA-384, SHA-512, SHA512/224, SHA-512/256). Bu versiyonlar; çıktılarının boyutu, iç durum boyutu, blok boyutu,
mesaj boyutu ve turları açısından farklılık gösterir. Günümüzde SSL sertifika düzenleyicileri, daha
güvenilir olan SHA-256 kullanmaktadır.
Aşağıda belirtilen özellikler SHA-256’yı oldukça güvenli kılar.
• Hash değerinden ilk veriyi yeniden oluşturmak neredeyse imkânsızdır. Bir kaba kuvvet
 saldırısının ilk veriyi elde edebilmesi için 2256 girişimde bulunması gerekir.
• Aynı hash değerinde iki mesaja sahip olmak çarpışma olarak adlandırılır ve olası değildir.
 2256 olası hash değeriyle üretilen iki SHA-256 kodunun aynı olma olasılığı son derece küçük-
 tür.
 • Orijinal veri üzerinde yapılacak küçük bir değişiklik, hesaplanan SHA-256
 değerini fazlaca değiştirir ve yeni değerin benzer verilerden türetildiği anlaşılamaz.
 Buna çığ etkisi denir. Örneğin “Merhaba” kelimesinin SHA-256 hash kodu “7fdc9f47
 17c5fe66df286c700fab969b4d6209d03aa84624c5f8f58c17c9c058” iken “merhaba”
 kelimesinin SHA-256 hash kodu “4c6bcdd55f3153e1939669ab1ec039e4059174dc
 25abdfcb2f58868849b4d61b” olarak hesaplanmaktadır. 

Hash fonksiyonları ile Encrypt edilmesi istenen kelimeler benzersiz bir şekilde seçilirse
(örneğin “3pE4&.gh-!upDN” gibi) elde edilen SHA-256 kodunun geri döndürülmesi normal
şartlarda mümkün değildir.

<h3>ASİMETRİK ŞİFRELEME</h3>

Açık anahtarlı (asimetrik) şifreleme algoritması, gizli anahtar şifreleme algoritmasından
farklıdır. Açık anahtarlı şifreleme algoritmaları açık (public) ve özel (private) olmak üzere iki farklı
anahtar yöntemi ile çalışır. Dolayısıyla şifreleme ve çözme için kullanılan anahtar algoritmaları
birbirinden farklı ve yalnızca o kullanıcıya özeldir . Bu sistemin diğer bir özelliği ise
şifre anahtarının herkese açık olmasıdır. Bir yabancı, veriyi şifrelemek için şifreleme anahtarını
kullanabilir fakat sadece çözüm anahtar algoritmasına sahip kişi tarafından şifre çözülebilir.
Birkaç asimetrik şifreleme algoritması olsa da (Diffie-Hellman, DSA, Eliptik vb.) en yaygın olarak
kullanılanı RSA algoritmasıdır. Asimetrik algoritmalar, simetrik algoritmalara göre çok daha yavaş
çalışır.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/asimetrik.PNG">

<h3>RSA (Rivest-Shamir-Adleman) Şifreleme Tekniği</h3>

Üç bilim adamının baş harflerinden oluşan RSA, dijital imzalama için de kullanılmaktadır.
Bu algoritmanın güvenilirliği çok büyük asal sayıların işlem yapma zorluğuna dayanır. Bu
büyük sayılar nedeniyle oldukça güvenilirdir ama işlemler genellikle yavaştır. Günümüzde RSA,
bankacılık sistemlerinde ve ticari sistemlerde öncelikli tercih edilen şifreleme tekniğidir. RSA
algoritması kavramsal olarak güvenlidir ancak bir saldırgan tarafından istismar edilebilecek bazı
zafiyetlere sahiptir. Buna rağmen web sitelerindeki güvenli web sayfaları olarak ifade edilen
HTTPS bağlantılarında, SSH gibi alanlarda yaygın olarak kullanılmaktadır.

<h3>RSA Şifreleme Yönteminin Çalışması</h3>

RSA şifreleme yönteminde anahtar oluşturma, şifreleme ve şifre çözümleme olmak üzere üç
kısım bulunmaktadır.

1. Adım: İki asal sayı seçiniz. p=11, q=13 olarak belirleyiniz.
2. Adım: n değerini hesaplayınız. n=11*13, n=143 olarak bulunuz.
3. Adım: Φ(n) değerini hesaplayınız. Φ(n) = (p-1)(q-1) formülünü kullanıp, Φ(n)=(11-1)(13-1),
Φ(n)=120 olarak bulunuz.
4. Adım: 1 < e < Φ(n) koşulunu sağlayacak bir e tam sayısı seçiniz. e=7 olarak seçilebilir çünkü
120 ile 7 aralarında asal sayılardır.
5. Adım: d sayısı (1<d< Φ(n)) aralığında hesaplanır. Bu işlem için Uzatılmış Öklid Algoritması
(Extended Euclid Algorithm) kullanılabilir. Bu algoritmaya göre d.e ≡ 1 mod Φ (n) olacak şekilde d
sayısını hesaplayınız. Hesaplama yapmak için (1+ kmod Φ (n))/e formülü ile tam sayı bulununcaya
kadar k değerini artırınız.
1- k=0 için 1 + 0 * 120 / 7 => 1/7 (Tam sayı değil, alınamaz.)
2- k=1 için 1 + 1 * 120 / 7 => 121/7 (Tam sayı değil, alınamaz.)
3- k=2 için 1 + 2 * 120 / 7 => 241/7 (Tam sayı değil, alınamaz.)
4- k=3 için 1 + 3 * 120 / 7 => 361/7 (Tam sayı değil, alınamaz.)
5- k=4 için 1 + 4 * 120 / 7 => 481/7 (Tam sayı değil, alınamaz.)
6- k=5 için 1 + 5 * 120 / 7 => 601/7 (Tam sayı değil, alınamaz.)
7- k=6 için 1 + 6 * 120 / 7 => 721/7 => d= 103 olarak alınabilir.
Buna göre n değeri 143, özel anahtar d=103, ortak anahtar ise e=7’dir.
6. Adım: mesaj^e mod (n) hesaplamasını yapıp, 1027
 mod (143) =119 olarak bulunuz.
7. Adım: Şifrelenmiş_text^d mod (n) formülünü kullanıp, 119^103 mod (143) =102 olarak
şifreyi çözümleyiniz.

<h3>Diffie-Hellman Anahtar Değişimi</h3>

Açık anahtarlama sistemlerinden biri olan Diffie-Hellman yönteminde haberleşecek iki
tarafın ortak anahtarları kullanarak gizli bir anahtar üretmesi sağlanır. Üretilen gizli anahtar iki
taraf arasındaki haberleşmeyi şifrelemek için kullanılır.
Gizli anahtar üretme işlemi aslında bir matematiksel işlem sürecidir. Bu süreçte kullanılan
matematiksel işlem gab= gba mantığına dayanmaktadır.

**Diffie-Hellman Anahtar Değişimi - Uygulama**

1. Adım: Ali ve Bülent için ortak anahtarları belirleyiniz. Ortak anahtarları Ali için p=7 ve
Bülent için g=5 olarak seçiniz. Ortak anahtarlar gizli olmadığı için haberleşmeyi dinleyen herkes
bu değerlere ulaşabilir.
2. Adım: Ali için gizli bir sayı (özel anahtar) seçiniz (a=3) ve Ali için seçtiğiniz özel anahtarı
matematiksel bir işlemden geçirerek sonucu Bülent’e gönderiniz.
• ga mod p => 53 mod 7 işleminden elde edilen sonucu A=6 olarak hesaplayınız.
3. Adım: Bülent için gizli bir sayı (özel anahtar) seçiniz (b=10) ve Bülent için seçtiğiniz özel
anahtarı matematiksel bir işlemden geçirerek sonucu Ali’ye gönderiniz.
• gb mod p => 510 mod 7 işleminden elde edilen sonucu B=2 olarak hesaplayınız.
Elde edilen sonuçları (6 ve 2 değerleri) herkes görmektedir ancak bunlar gönderilmek istenen
değerler değil, onların şifrelenmiş hâlleridir.
4. Adım: Ali için (Ba mod p) denklemini hesaplayınız.
• (23 mod 7) = 1
5. Adım: Bülent için (Ab mod p) denklemini hesaplayınız.
• (610 mod 7) = 1
İkili arasında iletilen veri, 6 ve 2 değerleridir. İki taraf arasında aynı değer olan 1 değeri
üretilir ancak bu değer, iletişim kanalından iletilmediği için başka kimselerce elde edilemez. Ali,1
anahtarını kullanarak mesajı şifreler. Bülent ise kendisine gelen şifreli mesajı bu 1 anahtarını
kullanarak açar. 

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/diffie-helman.PNG">

<h3>STEGANOGRAFİ ŞİFRELEME YÖNTEMİ</h3>

Steganografi, “gizli veya gizlenmiş yazı” anlamına gelir. Siber güvenlikte ise steganografi
“veri gizleme” amacıyla kullanılır. Steganografi, gönderilen mesajın içine şifrelenmiş mesajın
saklanmasıyla üçüncü kişilerin asıl iletilmek istenen mesajdan haberdar olmamasını sağlamak
için geliştirilmiş bir tekniktir. Bir steganografi örneği aşağıda verilmiştir.
“Sabah aldığım kitabı işe giderken afacan arı sebebiyle merdivenlerde ablama kaptırdım.”
Yukarıdaki metne bakıldığında birinin aldığı kitapları bir arı yüzünden ablasına kaptırdığı ile ilgili
olduğu görülür ancak metindeki her kelimenin ikinci harfleri yan yana yazıldığında “AliŞifreEBA”
ortaya çıkar. Burada gizli bir şifre Ali kişisine aktarılır.
Başka bir örnekte ise gönderilen metindeki sırayla kelimelerin 1, 2, 3. ve sonra yeniden 1, 2,
3. harfleri alınarak şifrelenmiş bir metin elde edilebilir.
“Aslında olmasını istediğim konuyu sana aktarmayacağım.”
Yukarıdaki örnekten şifrelenmiş metin “AltKat” olarak bulunur.

Steganografi yöntemi ile ses, sayısal resim, video görüntüleri üzerine veri saklanabilir. Bu
veriler metin dosyası olabileceği gibi seçilen bir resim içine başka bir görüntüyü gizlemek de
olabilir.

<h3>Resim İçine Metin Gizleme Tekniği</h3>

Resimler ve diğer tüm dijital materyaller 1 ve 0 mantığı ile oluşturulur. Bu nedenle resimleri
oluşturan kod yapısında birtakım oynamalar ile resimlerin görünmeyen arka planlarına gizli
yazılar yazılabilir. Linux veya Windows tabanlı işletim sistemlerinde bunlar için hazır araçlar
kullanılır. Linux tabanlı işletim sisteminde **steghide** aracı kullanılarak resim içine metin gizleme
işlemi yapılır. Steghide, ses ve resim dosyalarının içine metin gizleyebilen bir steganografi aracıdır.

<h3>Steganografi İşlemi</h3>

1. Adım: Linux işletim sistemine steghide aracı kurulumu için terminal üzerinde **sudo apt-get install steghide** Yazınız.
2. Adım: Kurulumu yapılan klasöre gidiniz
3. Adım: İçine metin gizlenecek resmi, kurulumu yapılan “steghide” klasörünün içine kopyalayınız.
4. Adım: Gizlenecek metni bir txt uzantılı dosya içine yazınız. Bu uygulamada “Küçüklere sevgi,büyüklere saygı gösteriniz.” yazısı resim içine gizlenecektir.
5. Adım: Metin gizleme için *cd steghide* **steghide embed -cf resim1.jpg -ef sifre.txt**

steghide -embed -cf resim1.jpg ef sifre.txt komutu ile sifre.txt dosyasının içindeki yazılar
resim1.jpg içine gizlenecektir. Koddaki parametreler aşağıda verilmiştir.
-embed: Gizleme işleminin yapılmasını sağlar.
-ef: Gizlenecek dosyanın yolu için kullanılır.
-cf: Taşıyıcı resim dosyası yolu için kullanılır.

6. Adım: İşlemin tamamlanması için steghide aracına bir şifre giriniz. Şifreyi girdikten sonra sifre.txt içindeki yazılar resim1.jpg resim dosyasına gizlenecektir.
7. Adım: resim1.jpg dosyası içinden gizlenen metni tekrar elde etmek isterseniz aşağıdaki kod
blokunu yazıp çalıştırınız.

**steghide extract -sf resim1.jpg**


<h3>Resim İçine Resim Gizleme Tekniği</h3>

Bir resmin başka bir resmin içine nasıl gizlenebileceğini anlamak için dijital resmin ne
olduğunu bilmek gerekir. Bir dijital resim, piksel adı verilen dijital noktalardan oluşur. Pikseller ise
belirli bir rengin parlaklık değerlerini tutar. Dolayısıyla bir görüntü, sabit sayıda satır ve sütundaki
piksellerden oluşan bir matris olarak düşünülebilir. Pikseller tipik olarak kırmızı, yeşil ve mavi
renklerin (RGB) belirli yoğunluklarda gösterilmesi ile renkli resimleri meydana getirir.
RGB renk modeli elektronik sistemlerde görüntülerin algılanması, temsil edilmesi ve
gösterilmesi için geliştirilmiştir. Her bir piksel 8 bitlik değerler alan üç bölümden oluşur. Her
bir bölüm 8 bitle gösterildiği için 0-255 arasında farklı değer alabilir. Görsel’de 10x10 pixel
matrisinde her bir pikselin aldığı renkler gösterilmiştir. Her renk, RGB kodu ile ifade edilir.

<img src="https://github.com/FazzPy/Cyber-Security/blob/main/img/rgb.PNG">

8 bitlik yazımda en soldaki en anlamlı bittir. Bu bit değiştirilirse renkte önemli bir değişiklik
meydana gelir. Örneğin değeri 0010 1000 olan bir pikselin değeri 40’tır. En soldaki 0 değeri 1
olarak değiştirilirse yeni değer 1010 1000 olacaktır. Bu da 168’e eşittir. Bu pikselin alacağı renk
miktarı 40’tan 168’e çıkacaktır ve bu durum resmi oldukça etkiler. 

En sağdaki bit ise daha az anlamlı bittir. En sondaki bit değiştirilirse pikselin önceki değerinde
fazla bir değişim olmayacaktır. Sadece en sondaki bitin değerinde 1 sayılık değişim olacaktır. Bu
nedenle en sağdaki bitlerin değişimi ile resim görüntüsü üzerinde çok az bir etki olacaktır. İnsan
gözü bu etkiyi ayıramaz. Bu yöntem ise resim içine resim gizlemek için kullanılan steganorafinin
temelini oluşturur.
Resim içine resim gizlemek için birçok farklı yöntem bulunur. Linux ve Windows işletim
sistemleri için geliştirilmiş özel araçlar ile bu işlemler sağlanabileceği gibi web üzerinde on-line
araçlarla da bu işlemler kolaylıkla yapılabilir.

<h3>Steganografi Yöntemiyle Resim İçine Resim Gizleme</h3>

1. Adım: Web görüntüleyici üzerinden steganografi on-line web araçlarını aratınız ve ilgili web
sitesini açınız.
2. Adım: “Hide image” butonuna basınız. Bu özellik, resim gizlemek için kullanılır.
3. Adım: “Cover image” başlığı altındaki “Dosya Seç” butonuna basınız ve ana resmi seçiniz. Seçilen resmin içine başka bir resim gizlenecektir.
4. Adım: “Secret image” butonu altındaki “Dosya Seç” butonuna basınız. Gizlemek istediğiniz resmi seçiniz.
5. Adım: Sağ taraftaki Hidden bits kısmı 1-7 arasında bir değer alır. En az anlamlı bitler
üzerinden işlem yapmak için 1, daha anlamlı bitler üzerinden işlem yapmak için 7 seçilebilir
ancak 1-7 arasındaki seçim 5 ve yukarısında ise resim gizlemesi mümkün olmayabilir. Bu nedenle
Hidden bits:1 olarak seçiniz.
6. Adım: Gizleme işlemi tamamlanmıştır. Hazırlanan resim dosyasını “Download Full-size
Image” butonuna basarak indiriniz.
7. Adım: İndirilen dosya içine gizlenen resmi bulabilmek için aynı on-line web sitesi
kullanılabilir. “Unhide image” butonuna tıklayınız. İstenirse arama motorunda
diğer web araçları aratılarak farklı on-line araçlar da kullanılabilir.

ma olup olmadığı yine bazı on-line araçlarla tespit edilebilir. Bunun için en etkili
web araçları arama motorunda aranarak bulunabilir. Aramada image histogram anahtar kelimesi
kullanılarak bulunan web aracı ile oynama yapılmış (içine metin veya resim gizlenmiş) resimler
analiz edilebilir. Resim seçilmiş ve GENERATE butonuna basılarak resim analizi
sonuçları gösterilmiştir.
 
