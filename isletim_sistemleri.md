# İŞLETİM SİSTEMLERİ

## Kernel
İşletim sisteminin çekirdeğidir. CPU, bellek ve aygıtlar gibi kaynakların yönetiminde rol oynar.

| Görev |   |
| --- | --- |
| Süreç Yönetimi | Çalışan programların yürütülmesini ve kaynak kullanımını yönetir. |
| Bellek yönetimi | Programlara bellek ayırır ve bellek erişimini düzenler. | 
| CPU zamanlaması | Hangi işin ne zaman CPU üzerinde çalışacağını belirlemeye yardımcı olur. |  
| Donanım erişimi | DProgramların dosya, ağ ve aygıt gibi sistem kaynaklarından yararlanmasını sağlar. | 


#### İşletim sistemi: 
Bilgisayarın çalışmasını sağlayan daha geniş yazılım bütünü.

#### Kernel: 
Bu bütünün kaynak yönetimi ve donanıma erişim gibi temel görevleri üstlenen çekirdeği.


## Süreç(Process):
#### Process: 
Bir programın çalıştırılmasıyla oluşan, işletim sisteminin takip ettiği çalışan örnek.
- Process'in hangi kaynakları kullandığını işletim sistemi yönetir. 
- Her process için ayrıca süreç kimliği gibi bilgiler de tutulur. Bu kimliğe PID (Process ID) denir.

##### Process'in durumları:
1. Running (Çalışıyor)
Process şu anda CPU üzerinde komut yürütüyor.
2. Ready (Hazır)
Process çalışmaya hazır ama CPU'nun kendisine ayrılmasını bekliyor.
3. Waiting / Blocked (Bekliyor)
Process, örneğin diskten veri gelmesi veya bir ağ isteğinin tamamlanması gibi bir olayın gerçekleşmesini bekliyor.


#### Program: 
Çalıştırılabilen talimatlar ve bunları içeren dosyalar.

Not:
Program = çalıştırılacak şey; process = çalışan örnek.

## Thread(iş parçacığı):
Bir process'in içinde bir veya daha fazla thread bulunabilir.
Thread, bir process içinde komutları yürüten akışlardan biridir.

| Process | Thread |
| --- | --- | 
| Çalışan program örneğidir. | Process içindeki yürütme akışıdır. |
| Kendine ait bir bellek alanına sahiptir. | Aynı process'teki thread'lerle çoğu belleği paylaşır. | 
| Kaynakları ve çalışma durumunu kapsar. |Komutları yürütmek için kendi yürütme durumuna ve stack'ine sahiptir. |  

## Sayfalama (Paging):
Bir process'in belleğini tek parça halinde düşünmek zorunda değiliz.
İşletim sistemleri, sanal belleği genellikle page (sayfa) adı verilen sabit boyutlu parçalara ayırır. Fiziksel RAM de frame (çerçeve) adı verilen parçalara bölünür.