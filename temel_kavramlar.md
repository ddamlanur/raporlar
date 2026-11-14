# Bilgisayar Bilimleri Temelleri

## CPU (Merkezi İşlem Birimi)
CPU, bilgisayarın komutları işleyen ve bilgisayarın çalışmasını yöneten temel bileşenidir.
### Komutları işler: 
Programların bilgisayara verdiği talimatları gerçekleştirir.
### Matematiksel işlemler yapar: 
Toplama, çıkarma ve karşılaştırma gibi işlemleri gerçekleştirir.
### Mantıksal kararlar verir:  
Örneğin, x > 10 koşulunun doğru mu yanlış mı olduğunu değerlendirir.
### İşlemleri koordine eder: 
Diğer bilgisayar bileşenlerinin nasıl çalışacağını yönlendirmeye yardımcı olur. 
#### CPU'nun çalışma mantığını üç temel adımı:
    1.Fetch (konutu getir)
    2.Decode (komutu çözümle)
    3.Execute (komutu uygula)

### CPU'nun Temel Parçaları:

#### 1. Kontrol Birimi (Control Unit — CU) 
CPU'nun işlemlerini yönetir ve koordine eder. 

Komutları çözümler, ilgili bileşenlerin ne yapması gerektiğini belirler.

Örnek: Bir toplama komutunun yürütülmesi için gerekli birimleri yönlendirir.

#### 2. Aritmetik ve Mantık Birimi (ALU) 
Matematiksel ve mantıksal işlemleri gerçekleştirir.
- Toplama, çıkarma gibi işlemler
- Büyüktür (>), küçüktür (<), eşittir (==) karşılaştırmaları
- AND, OR gibi mantıksal işlemler

#### 3. Yazmaçlar (Registers) 
CPU'nun içindeki çok küçük ve çok hızlı veri saklama alanlarıdır. İşlem sırasında gereken verileri, komutları veya adresleri tutarlar.
Örnek: İşlem sonucu veya sıradaki komutun adresi bir yazmaçta tutulabilir. 

#### 4. Çekirdekler (Cores) 
Komutları yürütmek için gereken işlemci kaynaklarını içeren bir işlem birimidir.

Çok çekirdekli işlemciler, uygun iş yüklerinde birden fazla işi paralel yürütebilir.

#### 5. Önbellek (Cache)
Cache, CPU'nun ihtiyaç duyduğu verilere RAM'e kıyasla daha hızlı ulaşabilmesi için kullanılan küçük ve hızlı bellektir.
##### Cache Katmanları:
###### L1 Cache
- Genellikle en hızlı ve en küçük cache katmanıdır.
###### L2 Cache
- L1'den genellikle daha büyüktür, erişim gecikmesi de daha yüksektir.
###### L3 Cache
- Genellikle L1 ve L2'den daha büyüktür.
- Genellikle L1 ve L2'den daha yavaştır ama RAM'den daha hızlıdır.

## RAM (Geçici Bellek)
Bilgisayarın o anda çalıştırdığı programların ve kullandığı verilerin geçici olarak tutulduğu bellektir. 
### RAM nasıl çalışır?
 1. Bir programı açarsın.
 2. İşletim sistemi, programın çalışması için gerekli kod ve verileri RAM'e yükler veya bellekte erişilebilir hâle getirir.
 3. CPU, ihtiyaç duyduğu komut ve verileri cache ve RAM üzerinden alır.
 4. İşlemler sırasında ortaya çıkan geçici sonuçlar RAM'de veya CPU register'larında tutulabilir.
 5. Program kapandığında belleği artık kullanılabilir hâle gelir; işletim sistemi belleği başka işler için yeniden kullanabilir.

## Disk (Depolama)
Disk, bilgisayardaki dosyaları, programları ve işletim sistemini kalıcı olarak saklamak için kullanılan depolama birimidir.

HDD ve SSD olmak üzere iki ana türü vardır (SSD'ler daha hızlı çalışır).




| Bileşen | Temel Görevi | Kalıcı mı? |
| --- | --- | --- |
| Register | CPU içindeki anlık değerler | Hayır |
| Cache | CPU'nun sık ihtiyaç duyduğu veriler | Hayır |
| RAM | Çalışan programların verileri | Hayır | 
| SSD/HDD | Dosya ve programları saklamak | Evet |
 
#### NOT:
CPU: İşlemi yapan.
RAM: Çalışırken gereken verileri tutan.
SSD: Dosyaları kalıcı olarak saklayan.
