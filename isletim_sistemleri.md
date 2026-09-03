# İŞLETİM SİSTEMLERİ TEMELLERİ

## İŞLETİM SİSTEMİ (OPERATING SYSTEM - OS)

* Bilgisayar donanımı ile kullanıcı ve uygulama yazılımları arasında köprü görevi gören ana sistem yazılımıdır.
* Donanım kaynaklarının (CPU, RAM, Disk vb.) adil, güvenli ve verimli kullanılmasını sağlar.
* Dosya yönetimi, aygıt denetimi, güvenlik ve bellek yönetimi süreçlerini yürütür.

---

## PROCESS (SÜREÇ)

* Belleğe yüklenmiş ve CPU tarafından aktif olarak yürütülen bağımsız bir program örneğidir.
* Her bir process kendi adres alanına (bellek bölgesine) ve kaynaklarına sahiptir.
* Process'lerin durumları bulunur: New (Yeni), Ready (Hazır), Running (Çalışıyor), Waiting (Beklemede), Terminated (Sonlandı).

---

## THREAD (İŞ PARÇACIĞI)

* Bir process içindeki en küçük yürütme birimidir; process'in hafifletilmiş bir alt parçasıdır.
* Aynı process içindeki thread'ler ortak bellek alanını ve dosya kaynaklarını paylaşır.
* Thread değişimi (Context Switching), bağımsız process'lerin değişimine göre çok daha hızlıdır.

---

## CONTEXT SWITCHING (BAĞLAM DEĞİŞTİRME)

* CPU'nun mevcut çalışan görevi durdurup başka bir göreve geçiş yapması işlemidir.
* İşlem bölünürken mevcut durum (CPU register'ları, program sayacı) kaydedilir, yeni görevin durumu yüklenir.
* Çoklu görev (multitasking) hissini sağlayan temel mekanizmadır ancak belirli bir performans maliyeti üretir.

---

## CPU SCHEDULING (İŞLEMCİ ZAMANLAMA)

* CPU'nun boş kaldığı anda çalışmaya hazır process'ler arasından hangisini seçeceğini belirleyen algoritmalar bütünüdür.
* Temel algoritmalar:
  * **FIFO / FCFS:** İlk gelen ilk işlenir.
  * **SJF (Shortest Job First):** En kısa işlem süresi olan process'e öncelik verilir.
  * **Round Robin (RR):** Her process'e belirli bir zaman dilimi (time slice / quantum) verilir ve sırayla döner.
  * **Priority Scheduling:** Process'lerin öncelik değerlerine göre yürütülür.

---

## DEADLOCK (ÖLÜMCÜL KİLİTLENME)

* İki veya daha fazla process'in, birbirlerinin elinde tuttuğu kaynakları beklemesi sonucu sistemin kilitlenip ilerleyememesi durumudur.
* Deadlock oluşması için dört şartın aynı anda sağlanması gerekir:
  * Karşılıklı Dışlama (Mutual Exclusion)
  * Tut ve Bekle (Hold and Wait)
  * Kaynak Kesilmeme (No Preemption)
  * Dairesel Bekleme (Circular Wait)

---

## BELLEK YÖNETİMİ (MEMORY MANAGEMENT)

* **Sanal Bellek (Virtual Memory):** Fiziksel RAM yetersiz kaldığında, disk alanının bir kısmının RAM gibi kullanılmasını sağlayan tekniktir.
* **Paging (Sayfalama):** Belleğin sabit boyutlu bloklara ("page" ve "frame") bölünerek parçalanmanın (fragmentation) engellenmesidir.
* **Segmentation (Bölümleme):** Belleğin mantıksal birimlere (kod, veri, yığın) bölünmesidir.
* **Stack vs. Heap:**
  * **Stack:** Hızlı, yerel değişkenlerin ve fonksiyon çağrılarının tutulduğu otomatik bellek alanı.
  * **Heap:** Dinamik olarak oluşturulan verilerin tutulduğu, boyutu esnek ancak yönetimi daha yavaş olan alan.

---

## DOSYA SİSTEMLERİ (FILE SYSTEMS)

* Verilerin depolama aygıtlarında düzenli bir şekilde saklanmasını, adlandırılmasını ve erişilmesini sağlayan yapıdır.
* Dosya izinleri, dizin yapıları ve meta verilerin (oluşturulma tarihi, boyut vb.) kaydını tutar.
* Yaygın kullanılan dosya sistemleri: NTFS (Windows), EXT4 (Linux), APFS (macOS).