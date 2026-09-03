# BİLGİSAYAR AĞLARI VE WEB MİMARİSİ

## CLIENT - SERVER MİMARİSİ

* **Client (İstemci):** Hizmet, veri veya sayfa talep eden kullanıcı tarafıdır (web tarayıcısı, mobil uygulama vb.).
* **Server (Sunucu):** İstemciden gelen istekleri (request) işleyip uygun cevabı (response) döndüren merkezi sistemdir.
* Web üzerindeki iletişimin çok büyük kısmı bu istek-cevap döngüsüyle yürütülür.

---

## HTTP VE HTTPS PROTOKOLLERİ

* **HTTP (Hypertext Transfer Protocol):** Web üzerinde istemci ve sunucu arasındaki veri iletim kurallarını belirleyen protokoldür.
* Veriler şifrelenmeden, düz metin (plain text) olarak iletilir.
* **HTTPS (HTTP Secure):** HTTP protokolünün SSL/TLS şifreleme katmanı ile güvenli hale getirilmiş halidir.
* Ağ trafiği dinlense bile aradaki verilerin (şifreler, kredi kartı bilgileri vb.) okunmasını engeller.

---

## TCP VE UDP FARKLARI

* **TCP (Transmission Control Protocol):**
  * Bağlantı odaklıdır; veri aktarımı öncesinde bağlantı kurulur (3-Way Handshake).
  * Veri paketlerinin sırayla ve eksiksiz ulaştığını garanti eder; kayıp paket varsa tekrar gönderilir.
  * Web siteleri, dosya indirme ve e-posta gibi doğruluğun kritik olduğu alanlarda kullanılır.
* **UDP (User Datagram Protocol):**
  * Bağlantısızdır; paketlerin hedefe ulaşıp ulaşmadığını veya sırasını kontrol etmez.
  * Hata denetimi minimumda olduğu için çok hızlıdır ve gecikmesi düşüktür.
  * Canlı yayınlar, sesli görüşmeler ve online oyunlar gibi hızın kayıptan önemli olduğu yerlerde tercih edilir.

---

## IP VE DNS KAVRAMLARI

* **IP Adresi:** Ağa bağlı her cihazın diğer cihazlar tarafından tanınmasını sağlayan benzersiz kimlik numarasıdır (Örn: IPv4: `192.168.1.1`, IPv6).
* **DNS (Domain Name System):** İnsanların hatırlayabileceği alan adlarını (örn: `google.com`) bilgisayarların anlayabileceği IP adreslerine çeviren internetin telefon rehberidir.

---

## REST VE RESTFUL API

* **API (Application Programming Interface):** İki farklı yazılımın birbiriyle konuşmasını ve veri alışverişi yapmasını sağlayan arayüzdür.
* **REST (Representational State Transfer):** HTTP metodlarını temel alan, hafif ve esnek bir mimari tasarım standardıdır.
* Temel HTTP Metodları:
  * **GET:** Sunucudan veri okumak/listelemek için kullanılır.
  * **POST:** Sunucuda yeni bir kayıt oluşturmak için veri göndermektir.
  * **PUT / PATCH:** Sunucudaki mevcut bir veriyi güncellemek için kullanılır (PUT tamamını, PATCH kısmi parçayı).
  * **DELETE:** Sunucudaki bir kaynağı silmek için kullanılır.

---

## HTTP STATUS (DURUM) KODLARI

* **2xx (Başarılı):** `200 OK` (İstek başarılı), `201 Created` (Yeni kayıt oluşturuldu).
* **3xx (Yönlendirme):** `301 Moved Permanently` (Sayfa kalıcı olarak taşındı).
* **4xx (İstemci Hatası):** 
  * `400 Bad Request` (Hatalı istek formatı).
  * `401 Unauthorized` (Kimlik doğrulanmamış / giriş yapılmamış).
  * `403 Forbidden` (Giriş yapılmış ama bu veriyi görmeye yetki yok).
  * `404 Not Found` (Aranan kaynak bulunamadı).
* **5xx (Sunucu Hatası):** `500 Internal Server Error` (Sunucu tarafında kod patladı/hata verdi).

---

## WEBSOCKET PROTOKOLÜ

* İstemci ile sunucu arasında tek bir bağlantı üzerinden çift yönlü (full-duplex) ve gerçek zamanlı veri akışı sağlar.
* Sürekli yeni HTTP isteği gönderme maliyetini ortadan kaldırır.
* Canlı sohbet (chat) uygulamaları, borsa grafikleri, canlı telemetri/sensör panelleri ve çok oyunculu oyunlarda kullanılır.

---

## WEB GÜVENLİĞİ VE OTURUM TEMELLERİ

* **CORS (Cross-Origin Resource Sharing):** Bir web sitesinin, tarayıcı üzerinden başka bir alan adındaki (domain/port) sunucuya istek atmasını kısıtlayan güvenlik mekanizmasıdır.
* **Cookie vs LocalStorage:**
  * **Cookie:** Küçük boyutlu, süresi belirlenebilen ve her HTTP isteğinde sunucuya otomatik gönderilen veri deposudur.
  * **LocalStorage:** Tarayıcıda kalıcı olarak saklanan, sunucuya otomatik iletilmeyen daha geniş kapasiteli depolama alanıdır.
* **JWT (JSON Web Token):** Kullanıcı oturum açtıktan sonra istemciye verilen, yetkilendirmeyi (authentication) taşınabilir ve şifreli şekilde doğrulayan belirteçtir.