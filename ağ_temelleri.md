# Ağ Temelleri (Networking)

## Network:
Bilgisayarlar,telefonlar,yazıcılar vb birçok cihazın bir araya gelerek etkileşimde bulunabildiği bir ortamdır.

Neden ağ kurarız?
- Dosya paylaşmak.
- Yazıcı gibi ortak kaynakları kullanmak.
- İnternete erişmek.
- Sunuculardan hizmet almak.
- Cihazların birbiriyle veri alışverişi yapmasını sağlamak.


## Client(istemci):
Bir sunucudan hizmet veya veri talep eden cihaz ya da yazılımdır.

Örneğin:
- Bilgisayardan Google'a girildiğinde tarayıcı istemci rolündedir.

## Server(Sunucu):
İstemcilerden gelen istekleri karşılayan ve onlara hizmet sağlayan sistemdir.


## LAN ve WAN:
### LAN (Local Area Network)
Yerel alan ağıdır. Ev, okul, ofis veya laboratuvar gibi sınırlı bir coğrafi alandaki cihazları birbirine bağlar.

Örnek: Üniversitedeki bilgisayar laboratuvarındaki bilgisayarlar.

### WAN (Wide Area Network)
Geniş alan ağıdır. Birbirinden uzak konumlardaki ağları birbirine bağlar.

Örnek: İstanbul'daki ve Ankara'daki iki şirket şubesinin ağlarının birbirine bağlanması.


## Ağ cihazları
### Switch (Anahtar):
- LAN içeriisnde(Aynı yerel ağ içerisinde), cihazların birbiriyle doğrudan iletişim kurmasını sağlayan cihazdır.
- Genellikle MAC adreslerini kullanarak verinin hangi porta gönderileceğini belirler.

### Router (Yönlendirici):
- Farklı ağlar arasında veri iletimini sağlar.
- LAN'daki cihazlar, farklı ağlara veya internete erişim sağlamak istiyorsa router gereklidir.
- IP adreslerini kullanarak paketleri yönlendirir.

### Firewall (Güvenlik Duvarı):
- Ağ trafiğini belirlenmiş güvenlik kurallarına göre kontrol eder.
- Örneğin belirli bir IP adresinden gelen bağlantıyı engelleyebilir veya belirli portlara erişime izin verebilir.
- Firewall her zaman ayrı bir fiziksel cihaz olmak zorunda değildir. Bilgisayarda çalışan yazılım tabanlı bir firewall da olabilir.


## Ağ adresleme
### IP adresi (internet protocol address):
IP adresi, bir cihazın IP ağı üzerindeki mantıksal adresidir.

cihazların ağ üzerindeki benzersiz kimlik numarası.

#### IPv4:
Pv4, günümüzde hâlâ çok yaygın kullanılan IP adresleme sürümüdür.

Bir IPv4 adresi:
- 32 bitten oluşur.
- 4 bölümden oluşur.
- Bölümler nokta ile ayrılır.
- Her bölüm 0–255 arasında bir değer alır.
- Bilgisayarlar bu adresi aslında ikili sayı sistemiyle (binary) işler.
- Her bölüm 8 bitten oluşur. Toplamda 4 × 8 = 32 bit eder.

#### IPv6:
IPv4 adreslerinin sayısı sınırlıdır. İnternete bağlanan cihazların artmasıyla daha geniş bir adres alanına ihtiyaç duyulmuştur.

IPv6, 128 bitlik adresleme sistemidir.

### Ip adresi alma
Bir cihazın ağ üzerinde iletişim kurabilmesi için IP adresine ihtiyacı vardır.

Bu adres iki temel yöntemle verilebilir.

#### Statik IP (Static IP):
- IP adresinin elle, manuel olarak tanımlanmasıdır.
- Örneğin bir sunucuya sürekli aynı IP adresiyle ulaşılmasını istiyorsak statik IP kullanabiliriz.

#### Dinamik IP (Dynamic IP):
- IP adresinin otomatik olarak atanmasıdır. Bunun için genellikle DHCP kullanılır.

##### DHCP:
- DHCP (Dynamic Host Configuration Protocol), cihazlara otomatik olarak ağ yapılandırma bilgileri dağıtan protokoldür.
- DHCP yalnızca IP adresi vermez. Subnet Mask, varsayılan Gateway ve DNS gibi bilgileri de dağıtabilir.

#### Private IP:
- Yerel ağlarda kullanılan IP adresleridir.
-Bu adresler internet üzerinde doğrudan yönlendirilemez. Farklı evlerdeki cihazlar aynı özel IP adresini kullanabilir.

#### Public IP:
- İnternet üzerinde yönlendirme yapılabilen IP adresidir. Genellikle internet servis sağlayıcısı tarafından evdeki Router'a atanır.
- Her cihazın internet üzerinde kendine ait benzersiz bir IP adresi olması gerekmez. Aynı yerel ağdaki cihazlar özel IP kullanabilir ve birden fazla cihaz ortak Public IP üzerinden internete çıkabilir.

### NAT (network address translation)
Ağ adresi çevirisi anlamına gelir. Özel IP adreslerinin başka IP adreslerine çevrilmesini sağlar.

Evdeki Router, yerel ağdaki cihazların internetle iletişim kurmasını sağlarken özel IP adreslerini kendi genel IP adresi üzerinden çevirebilir.

- IPv4 adreslerinin daha verimli kullanılmasını sağlar.
- Birden fazla cihazın aynı Public IP üzerinden internete çıkmasına yardımcı olur.
- Özel ağların adreslerinin doğrudan dış ağlara taşınmasını engelleyen bir adresleme sınırı oluşturur.

### Subnet Mask (Alt ağ maskesi)
- Subnet Mask, bir IP adresinin hangi bölümünün ağı, hangi bölümünün cihazı (host) temsil ettiğini anlamayı sağlar.

Örneğin:
- IP adresi: 192.168.1.10
- Subnet Mask: 255.255.255.0
Burada Subnet Mask bize ilk üç bölümün ağ kısmını, son bölümün ise cihaz kısmını temsil ettiğini gösterir.

#### CIDR gösterimi
- Subnet Mask yerine /24, /16, /8 gibi gösterimler de vardır.

Örneğin:

192.168.1.10/24

Buradaki /24, IP adresinin ilk 24 bitinin ağ kısmı olduğunu belirtir.

| CIDR | Subnet Mask |
| --- | --- |
| /8 | 255.0.0.0 |
| /16 | 255.255.0.0 |
| /24 | 255.255.255.0 |


### Gateway (Varsayılan ağ geçidi)
- Gateway, bir cihazın kendi ağı dışındaki ağlara ulaşmak için kullandığı çıkış noktasıdır.
- Çoğu ev ve küçük ofis ağında bu görevi Router üstlenir.

İnternette bir siteye girmek istenildiğinde bilgisayar öncelikle hedef IP adresinin kendi yerel ağında olup olmadığını kontrol eder.
- Hedef aynı ağdaysa veriyi yerel ağ üzerinden göndermeye çalışır.
- Hedef farklı ağdaysa paketi varsayılan Gateway'e gönderir.


### MAC adresi (Media access control address)
- MAC adresi, bir ağ arayüzünü yerel ağ iletişiminde tanımlamak için kullanılan adreslerden biridir.

IP ve MAC adreslerini birbirine karıştırmamak önemli.
- IP adresi: Cihazın IP ağı üzerindeki mantıksal adresi.
- MAC adresi: Yerel ağdaki veri iletiminde kullanılan ağ arayüzü adresi.

| Adres türü | Örnek |
| --- | --- |
| IP | 192.168.1.10 |
| MAC | 3C:52:82:A1:B2:C3 |

MAC adresinin özellikleri
- Geleneksel MAC adresleri 48 bittir.
- Genellikle 6 çift hexadecimal karakterle gösterilir.
- Örneğin 3C:52:82:A1:B2:C3.
- İlk 3 byte çoğunlukla üreticiye ait OUI bilgisini içerir.
- Ethernet ve Wi-Fi gibi ağ teknolojilerinde yerel bağlantı için kullanılır.
- (getmac) komutuyla öğrenilebilir.


| IP | MAC |
| --- | --- |
| Mantıksal adres | Yerel bağlantıda kullanılan adres |
| Ağlar arasında yönlendirmede kullanılır | Yerel ağda çerçeve iletiminde kullanılır |
| IPv4 32 bit, IPv6 128 bit | Geleneksel Ethernet MAC 48 bit |
| Değişebilir | Yazılımsal olarak değiştirilebilir |
| Router IP adreslerine bakarak yönlendirme yapar | Switch MAC adreslerine bakarak iletim yapar |


#### ARP:
- IPv4 yerel ağlarında bir IP adresine karşılık gelen MAC adresini bulmak için kullanılır.


## DNS
DNS, alan adlarını IP adreslerine çözümleyen sistemdir.

## Port
Port, bir cihaz üzerindeki ağ iletişiminin hangi uygulama veya hizmete yönlendirileceğini belirlemek için kullanılan numaradır.

##### Port numaraları nasıl sınıflandırılır?
TCP ve UDP port numaraları 0–65535 arasındadır.
Üç temel aralık vardır:
| Port Aralığı | Sınıfı |
| --- | --- |
| 0-1023 | Well-known ports |
| 1024-49151 | Registered ports |
| 49152 | Dynamic / Private ports |


## TCP ve UDP
| TCP | UDP |
| --- | --- |
| Güvenilir iletişime odaklanır | Daha basit ve düşük ek yüklü iletişim sağlar |
| Bağlantı kurar | Bağlantı kurmadan veri gönderebilir |
| Eksik verilerle ilgilenebilir | Teslim garantisi vermez |
| Sıralı teslim sağlamaya çalışır | Sıra garantisi yoktur |
| Örnek: web, dosya aktarımı, SSH | Örnek: bazı canlı yayınlar, oyunlar, DNS |


- TCP'nin temel amacı, gönderilen verinin karşı tarafa düzenli ve güvenilir şekilde ulaşmasını sağlamaktır.


## Paket
Bilgisayar ağlarında da büyük veriler, ağ üzerinden taşınabilecek parçalara ayrılabilir.

Bu parçalara günlük kullanımda genellikle paket (packet) denilir.

Paketin, nereye gideceğini ve nasıl işleneceğini anlatan bilgiler de taşıması gerekir.

### Header (Başlık)
Paketin nasıl işleneceği ve nereye gönderileceğiyle ilgili bilgileri içerir.

### Payload (Yük)
Asıl taşınan veridir.

## Ping
Bir cihazın başka bir cihaza ağ üzerinden ulaşılabilir olup olmadığını ve yanıt süresini kontrol etmeye yardımcı olur.

## Traceroute / Tracert 
Bir web sitesine ulaşırken veri genellikle tek seferde doğrudan hedefe gitmez.

Yol üzerinde birden fazla Router bulunabilir.

Traceroute, verinin hedefe giderken geçtiği ağ noktalarını görmeye yardımcı olur.
 
| Windows | Linux/macOS |
| --- | --- |
| tracert | traceroute |


## Nslookup
DNS sorgularını incelemek için kullanılan bir araçtır.



| Araç | Temel amacı |
| --- | --- |
| Ping | Hedefe ulaşılabilirliği ve yanıt süresini kontrol etmeye yardımcı olur |
| Tracert / Traceroute | Hedefe giderken geçilen ağ adımlarını göstermeye yardımcı olur |
| Nslookup | Alan adıyla ilgili DNS sorgusu yapar |


## Telnet
- Ağ üzerinden uzaktaki cihazlara komut satırı aracılığıyla erişmek için kullanılan bir protokoldür.
- İletişimi şifrelemeden gerçekleştirir.
Yani kullanıcı adı, parola ve gönderilen diğer veriler ağ üzerinde okunabilir durumda olabilir.
- Varsayılan portu: 23
- Günümüzde güvenli uzaktan yönetim için tercih edilmez.

## SSH 
- Ağ üzerinden uzaktaki cihazlara güvenli şekilde erişmek ve onları yönetmek için kullanılan protokoldür. 
- Varsayılan portu: 22


| TELNET | SSH |
| --- | --- |
| Güvenli değildir. | Güvenlik gözetilerek tasarlanmıştır. |
| Tüm verileri düz metin olarak ağ üzerinden gönderir. | Her şeyi şifreler ve gizlilik bütünlük sağlar. |
| Basit kullanıcı adı ve parlola tabanlı kimlik doğrulamaya dayanır. | Çeşitli kimlik doğrulama yöntemlerini destekler. |
| 23 numaralı portu kullanır. | 22 numaralı portu kullanır. |