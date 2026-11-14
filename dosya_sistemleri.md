# DOSYA SİSTEMLERİ

Dosya sistemi donanım üzerindeki verileri düzenleme ve takip etme yöntemidir.

Bir depolama alanını devasa bir apartman gibi düşünelim.

Diskin tamamı tek parça halinde kullanılmaz. Çünkü bilgisayarın:

- Verileri düzenli yerleştirmesi,

- Nerelerin boş olduğunu takip etmesi,

- Dosyaları bulabilmesi
gerekir.

Bu nedenle depolama alanı küçük parçalara bölünerek yönetilir. Bu parçalardan birine basitçe BLOK diyebiliriz.

### Blok:
Elimizde 1 GB'lık tek parça bir depolama alanı var ve hiçbir şekilde bölünmemiş şekilde düşünürsek.

Bir dosyanın nereye yazıldığını, hangi alanların boş olduğunu ve dosyanın nerede bittiğini yönetmek oldukça zor olurdu.

Bloklar sayesinde işletim sistemi, depolama alanını daha düzenli yönetebilir.

Bunu bir otopark gibi de düşünebiliriz:
Her park yeri bir blok gibi düşünülebilir.

Dosya sistemi hangi yerlerin:
- Dolu
- Boş

olduğunu takip eder.

- Bir dosya tek bloktan büyükse birden fazla blok kullanılır. Yani dosya fiziksel olarak birden fazla parçaya bölünebilir. 

- Bu blokların yan yana olması şart değildir.

# !DİKKAT!
Dosyanın içindeki gerçek veri ile dosya hakkındaki bilgiler aynı şey değildir.

Dosyanın adı, boyutu ve konumu gibi bilgiler de ayrıca tutulur. Bunlara genel olarak metadata (üst veri) denir.

#### Dosya sistemi
- Dosyaların isimlerini takip eder

- Klasör yapısını oluşturur

- Dosyaların konumunu takip eder

- Boş alanları takip eder

- Erişim ve bazı güvenlik bilgilerini yönetir

### NTFS, ext4 ve APFS:
Bunlar dosya sistemi türüdür.

Farklı işletim sistemleri farklı dosya sistemlerini tercih edebilir.

| Dosya Sistemi | En çok ilişkilendirildiği sistem |
| --- | --- |
| NTFS | Windows |
| ext4 | Linux |
| APFS | Apple ekosistemi/macOS |

Hepsinin temel amacı aynıdır:

- Dosyaları depolamak ve düzenlemek.

#### NTFS
Windows'un yaygın dosya sistemi

NTFS'in temel özelliklerinden bazıları:
- Büyük dosya ve diskleri destekler.
- Dosya ve klasör izinlerini yönetebilir.
- Journaling (günlükleme) özelliğine sahiptir.

##### Journaling:
 NTFS (Windows), ext4 (Linux) veya APFS (macOS) gibi dosya sistemlerinin, sabit sürücüye (HDD/SSD) yapılacak değişiklikleri asıl veri yazılmadan önce "journal" (günlük) adı verilen özel bir alana kaydetme mekanizmasıdır. 

 Elektrik kesintisi veya ani PC çökmesi (mavi ekran) gibi durumlarda, bilgisayar yeniden açıldığında dosya sisteminin taranıp onarılması saatler sürmez; sistem günlüğe bakarak yarım kalan işlemleri saniyeler içinde ya tamamlar ya da geri alır (veri tutarlılığı sağlar).


#### ext4 
Linux sistemlerinde yaygın kullanılan bir dosya sistemidir.

- Dosyaları ve klasörleri yönetir.
- Metadata tutar.
- Journaling kullanır.


#### APFS
Apple cihazları için geliştirilmiş modern bir dosya sistemidir.

- Modern depolama teknolojilerine uygun yapı
- Güçlü şifreleme desteği
- Snapshot gibi özellikler

##### Snapshot:
Bir dosya sisteminin belirli bir andaki durumunun kaydını oluşturma mantığıdır.

|  | NTFS | ext4 | APFS |
| --- | --- | --- | --- |
| En çok kullanıldığı yer | Windows | Linux | macOS |
| Journaling | Var | Var | Modern veri bütünlüğü mekanizmaları var |
| İzin yönetimi | Var | Var | Var |
| SSD odaklı modern tasarım | Kısmen | Genel amaçlı | Özellikle güçlü |

## HDD/SSD
HDD ve SSD'nin temel görevi bilgisayar kapansa bile veriyi saklamak.

### HDD 
Bilgisayarlarda ve diğer elektronik cihazlarda verilerin kalıcı olarak saklanmasını sağlayan mekanik bir depolama birimidir.

HDD'nin içinde fiziksel olarak dönen diskler bulunur.

Bir HDD'yi eski tip bir plak çalar gibi düşünürsek:
- Plaka: Verilerin yazıldığı dönen yüzey
- Okuma/yazma kafası: Veriyi okuyan veya yazan parça
- Motor: Plakaları döndürür

Bir dosya istediğinde bilgisayarın yaptığı işlem kabaca şöyledir:

"Bu dosyanın verisi diskin şu bölgesinde."

Sonra HDD:
1. Plakayı döndürür.
2. Okuma/yazma kafasını doğru konuma getirir.
3. Veriyi okur.

HDD'de fiziksel hareket olduğu için zaman kaybedilir.

HDD'lerde:
- Rastgele dosya erişimi daha yavaştır.
- Fiziksel darbeye karşı daha hassastır.
- Mekanik ses çıkarabilir.

### SSD 
Verileri fiziksel veya hareketli parçalar yerine NAND flash bellek çiplerinde depolayan yeni nesil bir veri depolama birimidir.

SSD özellikle şunlarda belirgin şekilde hızlıdır:
- Bilgisayarın açılması
- Programların açılması
- Çok sayıda küçük dosyanın okunması
- Dosya kopyalama işlemleri

###### NOT:
SSD'nin hızı; kullanılan teknolojiye, bağlantıya ve diskin yaptığı işe göre değişebilir.


HDD:

Fiziksel olarak doğru yere git  →  Veriyi oku

SSD:

Elektronik olarak ilgili bellek hücresine eriş  →  Veriyi oku


| HDD/SSD | Dosya Sistemi |
| --- | --- |
| Verinin saklandığı fiziksel donanım. | Bu donanım üzerindeki verileri düzenleme ve takip etme yöntemi. |
