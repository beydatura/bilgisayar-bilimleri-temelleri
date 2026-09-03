# VERİ YAPILARI VE ALGORİTMALAR

## BİG-O NOTASYONU (ZAMAN VE ALAN KARMAŞIKLIĞI)

* Bir algoritmanın girdi boyutu (n) büyüdükçe çalışma süresinin ve bellek kullanımının nasıl değiştiğini gösteren matematiksel gösterimdir.
* **O(1) - Sabit Zaman:** Girdi boyutu ne olursa olsun işlem süresi değişmez (Örn: Bir dizinin indeksindeki elemanı okumak).
* **O(log n) - Logaritmik Zaman:** Her adımda problem boyutu yarıya iner, son derece hızlıdır (Örn: Binary Search).
* **O(n) - Doğrusal Zaman:** Süre girdi boyutuyla doğru orantılı artar (Örn: Sıralanmamış bir dizide eleman aramak).
* **O(n log n) - Doğrusal-Logaritmik:** Verimli sıralama algoritmalarının ulaştığı ideal karmaşıklıktır (Örn: Merge Sort, Quick Sort).
* **O(n²) - Karesel Zaman:** İç içe döngülerde görülür; büyük veri setlerinde performansı ciddi oranda düşürür (Örn: Bubble Sort).

---

## DİZİ (ARRAY) VE BAĞLI LİSTE (LINKED LIST)

* **Dizi (Array):**
  * Bellekte ardışık (contiguous) alanlarda tutulan sabit boyutlu yapılardır.
  * İndeks ile doğrudan erişim çok hızlıdır ($O(1)$).
  * Boyutu esnek değildir; araya eleman ekleme veya silme kaydırma gerektirdiği için maliyetlidir ($O(n)$).
* **Bağlı Liste (Linked List):**
  * Veri (data) ve bir sonraki düğümün adresini (pointer) tutan bağımsız düğümlerden (node) oluşur.
  * Boyutu dinamiktir, bellekte dağınık bulunabilir.
  * Araya eleman eklemek veya çıkarmak pointer güncelleyerek çok hızlıdır ($O(1)$), ancak belirli bir indeksteki elemana ulaşmak baştan tarama gerektirir ($O(n)$).

---

## YIĞIN (STACK) VE KUYRUK (QUEUE)

* **Stack (Yığın):**
  * **LIFO (Last In, First Out):** Son giren ilk çıkar prensibiyle çalışır.
  * Temel operasyonlar: `push` (ekle), `pop` (en üsttekini çıkar), `peek` (en üsttekine bak).
  * Kullanım alanları: Tarayıcıdaki geri (back) tuşu, editörlerdeki "Geri Al (Undo)" işlemi, çağrı yığını (call stack).
* **Queue (Kuyruk):**
  * **FIFO (First In, First Out):** İlk gelen ilk çıkar prensibiyle çalışır.
  * Temel operasyonlar: `enqueue` (kuyruğun sonuna ekle), `dequeue` (kuyruğun başından çıkar).
  * Kullanım alanları: Yazıcı yazdırma sırası, mesaj kuyruk sistemleri (RabbitMQ, Kafka), CPU görev sıralaması.

---

## HASH MAP (HASH TABLOSU / SÖZLÜK)

* Verileri **Anahtar-Değer (Key-Value)** çiftleri halinde depolayan veri yapısıdır.
* Anahtarı bir sayısal indekse dönüştürmek için özel bir matematiksel fonksiyon (**Hash Fonksiyonu**) kullanır.
* Arama, ekleme ve silme işlemleri ortalama durumda $O(1)$ (sabit zaman) karmaşıklığında çalışarak olağanüstü hız sağlar.
* İki farklı anahtar aynı indeksi üretirse **Collision (Çakışma)** meydana gelir; bu durum Chaining (bağlı liste ile bağlama) gibi yöntemlerle çözülür.

---

## AĞAÇ YAPILARI (TREES)

* Hiyerarşik veri düzenlerini temsil eden, kök (root), dallar ve yapraklardan (leaf) oluşan döngüsüz yapılardır.
* **Binary Search Tree (BST - İkili Arama Ağacı):**
  * Her düğümün en fazla iki alt çocuğu bulunur.
  * Bir düğümün solundaki tüm değerler kendisinden küçük, sağındaki tüm değerler kendisinden büyüktür.
  * Denge korunduğunda arama ve ekleme süresi $O(\log n)$ karmaşıklığındadır.

---

## ARAMA VE SIRALAMA ALGORİTMALARI

* **Binary Search (İkili Arama):**
  * Sadece **sıralanmış** diziler üzerinde çalışır.
  * Diziyi sürekli ortadan ikiye bölerek aranan değeri bulur ($O(\log n)$).
* **Quick Sort:**
  * "Böl ve Yönet" (Divide and Conquer) prensibiyle bir pivot eleman seçip diziyi küçükler ve büyükler olarak ayrıştırarak sıralar (Ortalama $O(n \log n)$).
* **Merge Sort:**
  * Diziyi en küçük parçalara kadar bölüp ardından sıralı şekilde birleştiren kararlı (stable) bir algoritmadır (Her durumda $O(n \log n)$).