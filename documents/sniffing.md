# Sniffing

<h3> SNIFFER ARAÇLARINI KULLANMA </h3>

Sniffing kelimesinin Türkçe karşılığı koklama, dinlemedir. Sniffing bir ağ üzerindeki protokollerin dinlenmesi, koklanması ve ağda taşınan bilgilerin okunması anlamına gelir. Saldırganlar
bazı uygulamaları kullanıp, ağ üzerindeki protokolleri dinleyerek bu protokollerin içindeki bilgileri
ele geçirirler . Ağın güvenliğini sağlamak ve başkalarının ağa izinsiz şekilde girmesini
engellemek, bu açıdan kritik öneme sahiptir.

Ağı yöneten kişiler, ağ üzerinde haberleşmenin doğruluğunu kontrol etmek amacıyla birtakım
uygulamalardan faydalanırlar. Sniffing işlemlerinde yaygın olarak kullanılan uygulamalar şunlardır:
• Wireshark
• Tcpdump

<h3> Wireshark </h3>

Wireshark, yüklendiği bilgisayarın bağlı olduğu ağ üzerindeki protokolleri yakalayıp dinleyen,
ortaya çıkan bilgileri kaydedebilen, sonrasında bu kayıtları açıp okumaya izin veren bir uygulamadır.
Wireshark, açık kaynak bir yazılımdır ve grafik arayüzü sayesinde kullanımı kolaydır. 

<img src="https://github.com/FazzPy/security/blob/main/img/wireshark.PNG">

Arayüz ekranında görünen bölümler aşağıdaki gibi gruplanmıştır.
1. Menü seçeneklerinin yer aldığı menü alanıdır.
2. Uygulamada en sık kullanılan özelliklerin olduğu alandır.
3. Ağ üzerinde protokolleri filtrelemek için filtre değerinin yazıldığı alandır.
4. Ağ üzerinde izlenecek protokol isminin yazıldığı alandır.
5. Ağ üzerindeki tüm trafiği izlemek için kullanılan ağ kartları alanıdır.
6. Wireshark uygulaması hakkında geniş bilgi elde etmek için kullanılan alandır.

<h3> TCPDUMP </h3>

Tcpdump, Linux sistemlerinde kurulu olarak gelir ve ücretsiz bir araçtır. Paket analizi yapmak
için kullanılır. Tcpdump, Linux işletim sisteminde komut satırında çalışan bir araçtır. Ağ trafiğinin
fazla olduğu yerlerde ağı yöneten kişiler, istedikleri paketleri yakalayıp dinlemek için tcpdump
kullanırlar. Kali Linux işletim sisteminde tcpdump komutlarını kullanmak için root (yönetici) yetkisine sahip olmak gerekir. 

Tcpdump komutu çeşitli parametrelere sahiptir.

<img src="https://github.com/FazzPy/security/blob/main/img/tcpdump.PNG">

1. Adım: tcpdump parametresi yalın olarak kullanıldığında arayüz numarası en düşük ağı
dinlemeyi sağlar. eth0, eth1, eth2 şeklinde üç adet aktif ağ arayüzü olan bir bilgisayarda tcpdump
komutunu yalın olarak kullanınız. 

2. Adım: tcpdump -D parametresiyle ağ üzerinde dinlenebilecek bütün arayüzleri tcpdump -D komutu ile listeleyiniz.

3. Adım: tcpdump -i “arayüz adı” parametresi ismi yazılan arayüzü dinlemek için kullanılır.
eth0 arayüzünü dinlemek için **tcpdump -i eth0** yazınız. eth0 arayüzünde oluşan bütün
paketlerin listelendiğini görünüz.

4. Adım: tcpdump -n parametresi dinlemeye takılan paketlerin IP adresini ve port numarasını
yazdırır. tcpdump -n komutunu yazınız.

<h3>MAC SELİ (MAC FLOODING) SALDIRISI </h3>

MAC seli (MAC flooding), MAC adresi taşması anlamına gelir. Ağ üzerindeki Switch
(Yönlendirici) cihazlarında ağdaki haberleşmeyi yönetmek için MAC adres tablosu bulunmaktadır. Switch cihazında MAC adres tablosunun belli bir kapasitesi vardır. Saldırgan, bir
bilgisayardan sürekli yeni MAC adresi göndererek, Switch cihazının MAC tablosunu doldurup
görevini yapmasını engelleyebilir.

bu saldırı yöntemine MAC seli (MAC flooding)
saldırısı adı verilmektedir. 

<img src="https://github.com/FazzPy/security/blob/main/img/macflooding.PNG">

Switch cihazı bu saldırıya daha fazla dayanamayıp gelen paketleri belirli bir adrese değil de tüm
makinelere göndermeye başlar. HUB (çoklayıcı) gibi davranarak ağdaki trafiği ve işlemleri diğer
makineler dışında saldırgan makineye de gönderir. Bu durumda saldırgan makine, ağdaki tüm
trafiği okur ve ağda yavaşlamaya sebep olur. Ağa bağlı tüm makineler zamanla ağdan düşmeye
başlar. 

<h3>MAC Flooding Saldırısı Yapma</h3>

Kali Linux işletim sistemi üzerinden MAC flooding saldırısı yapmak için macof komutu kullanılır.
Macof -h komut dizini kullanılarak macof komutunun tüm parametreleri görülebilir.

<img src="https://github.com/FazzPy/security/blob/main/img/macflooding2.PNG">

macof [-i interface] [-s src] [-d dst] [-e tha] [-x sport] [-y dport] [-n times]

-i interface Arayüz
-s src Kaynak IP adresi
-d dst Hedef IP adresi
-e Specify Hedef MAC adresi
-x sport Kaynak port numarası
-y dport Hedef port numarası
-n times Gönderilecek paket sayısı

<h3>MAC Flooding Saldırı Tespit</h3>

MAC flooding trafiği Wireshark programı ile analiz edilebilir. Wireshark menü seçeneklerinden
Görsel’deki gibi Statistics >I/O Graph sekmesi tıklandığı zaman ağdaki paket sayısında belirli
bir sürede alttaki Görsel’deki gibi anormal bir artışın olması saldırının yapıldığını göstermektedir.

<img src="https://github.com/FazzPy/security/blob/main/img/macflooding3.PNG">

<img src="https://github.com/FazzPy/security/blob/main/img/macflooding4.PNG">

Wireshark menü çubuğundan Statistics > Conversations seçeneğine tıklanarak saldırı tespiti
yapılır. Tabloda IP adreslerinin sahteliği, paketlerin byte boyutu, byte boyutunun
belli bir oranda sabit olması ve paket transferleri arasındaki zaman farkının çok az olması bu ağa
bir MAC flooding saldırısı yapıldığını göstermektedir.

<img src="https://github.com/FazzPy/security/blob/main/img/macflooding5.PNG">

<h3>MAC Flooding Saldırısından Korunma Yolları</h3>

Ağda kullanılan IP-MAC adresi eşleşmeleri Switch cihazının port sayısı kadar yapılmalıdır.
Böylece Switch cihazının giriş portuna farklı bir IP-MAC eşleşmesine sahip ARP isteği engellenir.
Switch cihazının giriş portlarına belli bir sürede gelen ARP isteği sınırlandırılarak da saldırı
engellenebilir.

<h3>ARP ZEHİRLENMESİ (ARP POISONING)</h3>

ARP (Address Resolution Protocol), adres çözümleme protokolüdür. ARP, ağ üzerinde
haberleşen bilgisayarların IP adreslerini MAC adreslerine çevirir ve ARP tablosunda tutar. MACIP eşlemelerinin yer aldığı bu tablo zaman zaman güncellenir. ARP zehirlenmesi, saldırganın yerel
alan ağında sahte ARP mesajları gönderdiği bir saldırı türüdür. ARP tablosunun yanlış bilgilerle
doldurulmasıyla gerçekleşen bu saldırıda ağdaki tüm haberleşme saldırgan tarafından ele
geçirilir. Bir makinedeki ARP tablosunu görüntülemek için cmd ekranına arp -a kodu yazılır.

<img src="https://github.com/FazzPy/security/blob/main/img/arp.PNG">

ARP zehirlenmesi üç şekilde gerçekleştirilmektedir. Bunlar; hedef bilgisayarın ARP tablosunu
doldurma, ortadaki adam saldırı yöntemi (Man in the Middle), hedef bilgisayarın paketlerini
başkasına göndermedir.

<h3>Hedef Bilgisayarın ARP Tablosunu Doldurma</h3>

Saldırgan, hedef bilgisayardaki IP-MAC eşleşmelerinin yer aldığı ARP tablosunda değişikler
yapar. Böylece hedef bilgisayardaki paketlerin kendi belirttiği adrese gitmesini sağlayıp paket
içeriklerini okuyabilir. 

<h3>Ortadaki Adam Saldırı Yöntemi (Man In The Middle)</h3>

Saldırgan, ortadaki adam saldırısında aynı ağ üzerinde haberleşen iki cihazın arasına girerek
ağdaki tüm iletişimi dinleyebilir, iletişimi sonlandırabilir veya sahte bir iletişim oluşturabilir.

<img src="https://github.com/FazzPy/security/blob/main/img/mitm.PNG">

<h3>Hedef Bilgisayarın Paketlerini Başkasına Gönderme</h3>

Ağ içinde taşınan paketler, saldırganın belirlediği bilgisayara gönderilir. Hedef bilgisayarın
ulaşmak istediği HTTP paketindeki web sayfası yerine saldırganın belirlediği web sayfasının
açılması sağlanabilir.
