# VERİTABANI SİSTEMLERİ VE YÖNETİMİ

## SQL VE NOSQL FARKLARI

* **SQL (İlişkisel - Relational):**
  * Verileri satırlar ve sütunlar halinde tablolarda (tables) saklar.
  * Katı ve önceden tanımlanmış bir şema (schema) yapısına sahiptir.
  * Tablolar arası ilişkiler (Primary Key, Foreign Key) üzerinden veri bütünlüğü sağlar.
  * Dikey olarak ölçeklenir (Vertical Scaling - daha güçlü donanım/RAM/CPU ekleme).
  * Örnekler: PostgreSQL, MySQL, MS SQL Server, Oracle, SQLite.
* **NoSQL (İlişkisel Olmayan - Non-Relational):**
  * Verileri JSON benzeri dokümanlar (Document), anahtar-değer (Key-Value), grafik (Graph) veya geniş sütunlu (Column) yapılarda tutar.
  * Esnek ve dinamik şemaya sahiptir; her kayıt farklı alanlar içerebilir.
  * Yatay olarak kolayca ölçeklenir (Horizontal Scaling - sisteme daha fazla sunucu ekleme).
  * Büyük veri (Big Data) ve gerçek zamanlı yoğun okuma/yazma gerektiren sistemlerde tercih edilir.
  * Örnekler: MongoDB, Redis, Cassandra, Neo4j.

---

## ACID PRENSİPLERİ (VERİTABANI GÜVENİLİRLİĞİ)

Bir işlemin (Transaction) güvenli ve tutarlı tamamlanabilmesi için sağlaması gereken dört temel kuraldır:

* **Atomicity (Bölünemezlik):** Bir işlem ya tamamen başarılı olur ya da hiç gerçekleşmez. Hata durumunda her şey işlem öncesine döner (Rollback).
* **Consistency (Tutarlılık):** İşlem tamamlandığında veritabanı kuralları, kısıtlamaları (constraints) ve bütünlüğü korunmuş olmalıdır.
* **Isolation (Yalıtım):** Aynı anda yürütülen işlemler birbirinin ara durumlarını görmez; işlemler sanki sırayla yapılıyormuş gibi izole çalışır.
* **Durability (Kalıcılık):** Başarıyla tamamlanan (Commit) bir işlemin sonuçları, elektrik kesintisi veya sistem çökmesi olsa dahi kalıcı olarak saklanır.

---

## NORMALİZASYON KAVRAMI

* İlişkisel veritabanlarında veri tekrarını (redundancy) en aza indirmek ve veri tutarsızlıklarını önlemek için tabloları mantıksal parçalara bölme sürecidir.
* **1NF (Birinci Normal Form):** Tablodaki her sütun atomik (bölünemez) tek bir değer içermeli, tekrarlayan sütun grupları bulunmamalıdır.
* **2NF (İkinci Normal Form):** Tablo 1NF'ye uymalı ve birincil anahtara kısmi bağımlılık (partial dependency) bulunmamalıdır; anahtar olmayan her alan birincil anahtarın tamamına bağlı olmalıdır.
* **3NF (Üçüncü Normal Form):** Tablo 2NF'ye uymalı ve geçişli bağımlılık (transitive dependency) bulunmamalıdır; birincil anahtar olmayan bir sütun başka birincil anahtar olmayan sütuna bağımlı olamaz.

---

## İNDEKSLER (INDEXING)

* Veritabanı sorgularının (`SELECT`) arama hızını büyük oranda artıran özel arama yapısıdır (genellikle B-Tree mimarisi kullanılır).
* Kitapların sonundaki indeks sayfalarına benzer; tüm tabloyu baştan sona taramak (Full Table Scan) yerine doğrudan hedeflenen satıra gidilmesini sağlar.
* **Maliyeti:** Veri arama hızını artırırken; yazma, güncelleme ve silme (`INSERT`, `UPDATE`, `DELETE`) işlemlerini yavaşlatır ve ek disk alanı tüketir.

---

## ORM (OBJECT-RELATIONAL MAPPING)

* Nesne yönelimli programlama dillerindeki sınıflar (class/object) ile ilişkisel veritabanı tabloları arasında köprü kuran kütüphanelerdir.
* Geliştiricilerin düz SQL sorguları yazmak yerine kendi programlama dillerinin sözdizimiyle veritabanı işlemleri yapmasını sağlar.
* Kodun okunabilirliğini artırır, SQL Injection gibi güvenlik açıklarına karşı koruma sağlar.
* Popüler ORM örnekleri: Hibernate (Java), Entity Framework (C#), Prisma / TypeORM (TypeScript/Node.js), SQLAlchemy (Python).