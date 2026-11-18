# Linux
Linux, bir işletim sisteminin temelini oluşturan çekirdektir (Kernel).

Linux özellikle şu alanlarda çok kullanılır:
- Sunucular ve web altyapıları
- Siber güvenlik
- Ağ cihazları
- Bulut sistemleri
- Yazılım geliştirme
- Sistem yönetimi

#### Kernel (Çekirdek): Donanım ve yazılım arasındaki temel yönetimi gerçekleştirir.
#### Distribution (Dağıtım): Linux çekirdeğinin etrafına araçlar, programlar ve arayüzler eklenerek oluşturulan işletim sistemi paketidir.
- Ubuntu
- Kali Linux
- Debian
- Arch Linux

# Linux komutları
| Komut | Görevi |
| --- | --- |
| pwd | Bulunduğun dizini gösterir. |
| ls | Dosya ve klasörleri listeler. |
| cd | 	Dizin değiştirir. |
| clear | 	Terminal ekranını temizler. |
| mkdir | Klasör oluşturur. |
| touch | Dosya oluşturur. |
| cp | Dosya veya klasör kopyalar. |
| mv | Taşıma ve yeniden adlandırma işlemini yapar. |
| rm | Dosya silme işlemini yapar. |
| rmdir | Klasör silme işlemini yapar. |
| cat | Dosya içeriğini görüntüler. |
| head | Dosyanın başını görüntüler. |
| tail | Dosyanın sonunu görüntüler. |
| grep | Dosya içerisinde arama yapar. |
| find | Dosya ve klasör arama yapar. |


### Linuxtaki Bazı Önemli Klasörler
| Klasör | Görevi |
| --- | --- |
| / | Dosya sisteminin başlangıcı |
| /home | Normal kullanıcıların kişisel dosyaları |
| /root | Root kullanıcısının ana dizini |
| /etc | Sistem yapılandırma dosyaları |
| /bin | Temel komut programları |
| /var | Değişken veriler, loglar vb. |
| /tmp | Geçici dosyalar |
| /usr | Birçok program ve kullanıcı araçları |



# Linux'ta Kullanıcılar
Linux, çok kullanıcılı (multi-user) bir işletim sistemidir.

Yani aynı bilgisayarı birden fazla kişi kullanabilir ve her kullanıcının kendisine ait hesabı, dosyaları ve yetkileri olabilir.

Her kullanıcının kendine ait bir kullanıcı kimliği bulunur. Buna UID (User ID) denir.
- Root kullanıcısının UID değeri 0'dır.
- Normal kullanıcıların UID değerleri genellikle 1000 ve üzerindedir (dağıtıma göre değişebilir).

## Root Kullanıcı:
Root, Linux'taki en yüksek yetkiye sahip özel kullanıcıdır. 

Root kullanıcısı:
- Sistem dosyalarını değiştirebilir.
- Kullanıcı oluşturabilir ve silebilir.
- Program yükleyebilir ve kaldırabilir.
- Sistem ayarlarını değiştirebilir.
- Diğer kullanıcıların dosyalarına erişebilir.
- Sistem servislerini yönetebilir.

## sudo:
"sudo", normal kullanıcının belirli bir komutu geçici olarak daha yüksek yetkiyle çalıştırmasını sağlar.

Açılımı genellikle superuser do olarak açıklanır.

## su:
"su", başka bir kullanıcı hesabına geçiş yapmak için kullanılır.


# Linux'ta Gruplar
Linux'ta gruplar, kullanıcıları belirli yetkiler altında bir araya getirmek için kullanılır.

## Grup Komutları:
| Komut | Görevi |
| --- | --- |
| groups | Kullanıcının dahil olduğu grupları gösterir. |
| id | Kullanıcının UID, GID ve grup bilgilerini gösterir. |
| whoami | Şu anda hangi kullanıcı olduğumuzu gösterir. |
| useradd | Yeni kullanıcı oluşturur. |
| usermod | Kullanıcı hesabını değiştirir. |
| userdel | Kullanıcı hesabını siler. |
| groupadd | Yeni grup oluşturur. |

## Linux'ta kullanıcı bilgilerinin depolanması:
| Dosya | İçeriği |
| --- | --- |
| /etc/passwd | Kullanıcı hesaplarına ait temel bilgiler |
| /etc/shadow | Parola hashleri ve parola bilgileri |
| /etc/group | Grup bilgileri |


# Linux'ta Dosya-Klasör İzinleri

| İzin | Dosyada | Klasörde |
| --- | --- | --- |
| r (read) | İçeriği okuma | İçindeki isimleri listeleme |
| w (write) | İçeriği değiştirme | İçine dosya/klasör oluşturma, silme veya yeniden adlandırma |
| x (execute) | Çalıştırma | Klasöre erişme ve içinden geçebilme |


- Linux, dosya izinlerini üç kategori üzerinden değerlendirir.

| Sembol | Açılımı | Anlamı |
| --- | --- | --- |
| u | User | Dosyanın sahibi |
| g | Group | Dosyanın ait olduğu grup |
| o | Others | Diğer tüm kullanıcılar |

- "ls -l" ile dosya izinleri görüntülenir

Örnek çıktı: -rwxr-xr-- 1 xxxx xxxx xxxx date xxxx

Çıktının ilk kısmı önemlidir. Parçalara ayırırsak:

|  |  |  | 
| --- | --- | --- |
| - | dosya türü | Normal dosya. |
| rwx | owner | Dosya sahibi okuyabilir, yazabilir ve çalıştırabilir. |
| r-x | group | Grup üyeleri okuyabilir ve çalıştırabilir ama yazamaz. |
| r-- | others | Diğer kullanıcılar yalnızca okuyabilir. |

# NOT
İlk karakter farklı da olabilir:
- -: Normal dosya
- d: Klasör
- l: Sembolik bağlantı (symbolic link) 

## chmod – Dosya izinlerini değiştirme
chmod (change mode), dosya veya klasörlerin izinlerini değiştirmek için kullanılır.

İki temel yöntem var:
1. Sembolik yöntem
2. Sayısal yöntem 

### Sembolik yöntem
Örneğin dosyanın sahibine çalıştırma izni vermek istiyoruz:

chmod u+x script.sh

Burada:
- chmod: İzin değiştir.
- u: Dosya sahibi.
- +: İzin ekle.
- x: Çalıştırma izni.
- script.sh: Dosya.

| Operatör | Anlamı |
| --- | --- |
| + | İzin ekle |
| - | İzin kaldır |
| = | İzinleri tam olarak belirle |

### Sayısal yöntem
Her iznin sayısal bir karşılığı vardır:

| İzin | Değer |
| --- | --- |
| r | 4 |
| w | 2 |
| x | 1 |
| - | 0 |

Bu değerler toplanarak her kullanıcı kategorisinin izin değeri bulunur.

#### Örnek

|  |  |  |
| --- | --- | --- |
| rwx | 4+2+1=7 | Okuma+Yazma+Çalıştırma |
| r-x | 4+1=5 | Okuma + Çalıştırma |
| rw- | 4+2=6 | Okuma + Yazma |
| r-- | 4 | Sadece okuma |

## chown – Dosya sahipliğini değiştirme
Dosyanın sahibini değiştirmek için chown (change owner) kullanılır.
#### Örnek
sudo chown ahmet dosya.txt


# Umask
Linux'ta yeni oluşturulan dosya ve klasörlerin varsayılan izinlerini etkileyen bir değer vardır: umask.

Yaygın değerlerden biri 022'dir.

Linux'ta yeni dosyalar için temel varsayılan izin 666, klasörler için ise 777 kabul edilir. Umask, bu izinlerden belirli izinleri kaldırır.

#### Örneğin 022 umask ile:

| Tür | Temel izin | Sonuç |
| --- | --- | --- |
| Dosya | 666 | 644 |
| Klasör | 777 | 755 |

- Burada önemli bir ayrıntı: Dosyalara varsayılan olarak çalıştırma izni verilmez. Bu nedenle normal bir yeni dosya 777 üzerinden değil, 666 üzerinden değerlendirilir.


# Linux süreçleri (Processes) ve sistem kaynakları
## Process (Süreç)
Process (Süreç), çalışmakta olan bir programın işletim sistemi tarafından yönetilen örneğidir.

Örneğin:
- Chrome'u açtığında Chrome için süreçler oluşur.
- Terminal açtığında terminal uygulaması için süreç oluşur.
- Bir Python dosyasını çalıştırdığında Python programı bir süreç olarak çalışır.

- Program: Diskte bulunan, henüz çalıştırılmamış yazılım dosyası.
- Process: Programın çalıştırılmasıyla oluşan süreç.

## Process ID (PID)
- Linux'ta çalışan her sürece bir kimlik numarası verilir. Buna PID (Process ID) denir.
- PID sayesinde işletim sistemi hangi sürecin hangisi olduğunu ayırt edebilir.
- Bir de PPID (Parent Process ID) kavramı var.
- Bir süreç başka bir süreç tarafından başlatıldığında, başlatan süreç onun parent process'i olur.
- PPID, sürecin ebeveyninin PID değeridir.

## Process durumları
Bir süreç her zaman aktif olarak işlemci üzerinde çalışmaz.

İşletim sistemi süreçleri farklı durumlarda tutar.

Temel süreç durumları:

| Durum | Açıklama |
| --- | --- |
| New | Süreç oluşturuluyor. |
| Ready | CPU kullanmayı bekliyor. |
| Running | CPU üzerinde çalışıyor. |
| Waiting / Blocked | Bir olayın gerçekleşmesini bekliyor. |
| Terminated | Süreç sonlandırılmış. |

## ps – Çalışan süreçleri görüntüleme
ps (Process Status), sistemdeki süreçler hakkında bilgi verir.

## top – Sistem kaynaklarını canlı izleme
top, çalışan süreçleri ve sistem kaynaklarının kullanımını gerçek zamanlıya yakın şekilde gösterir.

top ekranında şunları görebilirsin:
- CPU kullanım oranı
- RAM kullanımı
- Çalışan süreçler
- Süreçlerin PID değerleri
- Süreçlerin CPU ve RAM tüketimleri

top ekranından çıkmak için q tuşuna basılır.

### htop 
htop, top komutuna alternatif olan daha görsel ve kullanıcı dostu bir süreç izleme aracıdır.

Genellikle renkli göstergeler ve daha kolay gezinme imkanı sunar.

Ancak her Linux dağıtımında varsayılan olarak kurulu olmayabilir.

## kill – Süreç sonlandırma
Bazen bir program yanıt vermeyi bırakabilir veya gereksiz yere kaynak tüketebilir.

Bu durumda süreci sonlandırmak isteyebiliriz.

Bunun için kill komutu kullanılır.

## Arka plan ve ön plan süreçleri
Linux'ta terminal üzerinden çalıştırdığın programlar genellikle ön planda başlar.

| Komut / Tuş | Görevi |
| --- | --- |
| & | Komutu arka planda başlatır. |
| Ctrl + Z | Ön plandaki işi duraklatır. |
| bg | Duraklatılmış işi arka planda sürdürür. |
| fg | İşi tekrar ön plana getirir. |
| jobs | Mevcut kabuk oturumundaki işleri listeler. |
