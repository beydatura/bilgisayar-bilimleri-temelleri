# YAZILIM MİMARİSİ VE TASARIM PRENSİPLERİ

## NESNE YÖNELİMLİ PROGRAMLAMA (OOP) TEMELLERİ

* **Encapsulation (Kapsülleme):** Verilerin (field/state) doğrudan dışarıdan erişilmesini engelleyerek metotlar (getter/setter) aracılığıyla kontrollü erişim sağlanmasıdır.
* **Inheritance (Kalıtım):** Bir sınıfın ortak özellikleri ve işlevleri başka bir üst sınıftan devralmasıdır; kod tekrarını önler.
* **Polymorphism (Çok Biçimlilik):** Aynı arayüzü veya ata sınıfı paylaşan nesnelerin aynı metoda kendi ihtiyaçlarına göre farklı tepkiler vermesidir (Method Overriding / Overloading).
* **Abstraction (Soyutlama):** Karmaşık arka plan işlemlerini gizleyip kullanıcıya/geliştiriciye yalnızca gerekli olan işlevsel arayüzü (Interface / Abstract Class) sunmaktır.

---

## SOLID PRENSİPLERİ

Yazılımın esnek, genişletilebilir ve kolay bakım yapılabilir olmasını sağlayan beş temel kuraldır:

* **S - Single Responsibility Principle (SRP):** Bir sınıfın veya fonksiyonun değişmek için yalnızca tek bir nedeni, yani tek bir görevi olmalıdır.
* **O - Open/Closed Principle (OCP):** Yazılım varlıkları geliştirmeye ve genişletilmeye açık (open), ancak mevcut kaynak kodun değiştirilmesine kapalı (closed) olmalıdır.
* **L - Liskov Substitution Principle (LSP):** Alt sınıflar, türedikleri üst sınıfların yerine hiçbir hata veya mantıksal bozulma oluşturmadan geçebilmelidir.
* **I - Interface Segregation Principle (ISP):** Kullanıcılar/sınıflar kullanmadıkları metotları barındıran şişkin arayüzleri uygulamaya zorlanmamalıdır; arayüzler olabildiğince küçük ve özelleşmiş tutulmalıdır.
* **D - Dependency Inversion Principle (DIP):** Üst seviye modüller alt seviye modüllere doğrudan bağımlı olmamalıdır; her iki seviye de soyutlamalara (interface/abstract) bağımlı olmalıdır.

---

## TASARIM KALIPLARI (DESIGN PATTERNS)

Sıkça karşılaşılan yazılım problemlerine getirilen standart ve kanıtlanmış mimari çözüm şablonlarıdır:

* **Singleton:** Bir sınıftan uygulama yaşam döngüsü boyunca yalnızca tek bir nesne örneğinin (instance) üretilmesini ve buna global erişim sağlanmasını garanti eder (Örn: Veritabanı bağlantı yöneticisi).
* **Factory Method:** Nesne oluşturma mantığını istemciden gizleyerek bir arayüz veya ata sınıf üzerinden dinamik nesne üretilmesini sağlar.
* **Observer:** Bir nesnede (Subject) değişiklik olduğunda, o nesneyi dinleyen tüm bağlı bileşenlere (Observers) otomatik bildirim gönderilmesini sağlar (Örn: Event sistemleri, state yönetimi).

---

## YAZILIM MİMARİSİ YAKLAŞIMLARI

* **Monolitik Mimari (Monolithic):**
  * Kullanıcı arayüzü, iş mantığı ve veritabanı işlemlerinin tek bir kod tabanında birleşik olarak çalıştığı sistemdir.
  * Başlangıçta geliştirmesi, test etmesi ve yayına alınması son derece kolaydır.
  * Proje büyüdükçe bağımlılıklar artar, ölçeklemesi ve bakım yapılması zorlaşır.
* **Mikroservis Mimarisi (Microservices):**
  * Sistemin bağımsız, küçük ve kendi veritabanına sahip olabilen servis parçacıklarına bölünmesidir.
  * Servisler birbirleriyle HTTP/REST veya mesaj kuyrukları (gRPC, RabbitMQ) üzerinden haberleşir.
  * Her servis bağımsız ölçeklenebilir ve farklı teknolojilerle yazılabilir; ancak ağ trafiği yönetimi ve dağıtık sistem karmaşıklığı getirir.