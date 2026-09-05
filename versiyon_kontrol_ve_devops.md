# VERSİYON KONTROL VE DEVOPS TEMELLERİ

## GİT KAVRAMLARI VE ÇALIŞMA ALANLARI

* **Repository (Repo):** Projenin tüm kodlarını, geçmiş sürümlerini ve dosya değişikliklerini barındıran depodur.
* **Working Directory:** Proje dosyalarınızın bilgisayarınızda aktif olarak düzenlendiği yerel çalışma alanıdır.
* **Staging Area (Index):** Yapılan değişikliklerin bir sonraki sürüme dahil edilmek üzere işaretlendiği geçici bekleme bölgesidir (`git add`).
* **Commit:** Projedeki değişikliklerin anlık bir ekran görüntüsü gibi kalıcı olarak Git geçmişine kaydedilmesidir (`git commit`).
* **Push & Pull:**
  * **Push:** Yerel bilgisayardaki commit'leri GitHub/GitLab gibi uzak sunucuya (remote) aktarma işlemidir.
  * **Pull:** Uzak sunucudaki en güncel değişiklikleri yerel çalışma alanına indirip birleştirme işlemidir.

---

## DAL VE BİRLEŞTİRME (BRANCHING & MERGING)

* **Branch (Dal):** Ana kod akışını (genellikle `main`) bozmadan yeni özellikler geliştirmek veya hata ayıklamak için açılan bağımsız paralel çalışma hattıdır.
* **Merge:** Farklı bir branch'te yapılan geliştirmelerin ana branch ile birleştirilmesi işlemidir.
* **Merge Conflict (Çakışma):** İki farklı geliştiricinin aynı dosyanın aynı satırlarında farklı değişiklikler yapması sonucu Git'in hangi satırı kabul edeceğini bilemeyip kararı geliştiriciye bıraktığı durumdur.
* **Pull Request (PR) / Merge Request:** Geliştiricinin tamamladığı branch'i ana koda dahil etmeden önce ekip arkadaşlarının incelemesi (Code Review) için açtığı talep ekranıdır.

---

## CI/CD (SÜREKLİ ENTEGRASYON VE DAĞITIM)

* **CI (Continuous Integration - Sürekli Entegrasyon):**
  * Geliştiricilerin kodlarını sık sık ana depoya göndermesi ve her push işleminde otomatik testler ile derleme adımlarının çalıştırılmasıdır.
  * Hataların çok erken aşamada tespit edilmesini sağlar.
* **CD (Continuous Delivery / Deployment - Sürekli Dağıtım):**
  * Kodların testlerden başarıyla geçtikten sonra otomatik olarak test veya üretim (production) sunucularına paketlenip yayına alınması sürecidir.
  * Canlıya çıkış sürelerini hızlandırır ve manuel dağıtım risklerini sıfıra indirir.

---

## KONTEYNERLEŞTİRME VE DOCKER

* **"Benim bilgisayarımda çalışıyordu ama sunucuda çalışmıyor"** sorununu çözmek için uygulamanın tüm bağımlılıklarıyla (kod, kütüphaneler, ayarlar) birlikte izole bir ortamda paketlenmesidir.
* **Image (İmaj):** Bir uygulamanın çalışması için gereken tüm dosyaların dondurulmuş şablonudur (tarif gibidir).
* **Container (Konteyner):** Bu imajın bağımsız, hafif ve izole bir şekilde ayağa kalkmış, çalışan canlı örneğidir.
* **Sanal Makine (VM) vs Docker:** Sanal makineler ayrı bir işletim sistemi (Guest OS) çekirdeği çalıştırarak ağırlaşırken; Docker konteynerleri ana işletim sisteminin çekirdeğini paylaşarak çok daha hızlı başlar ve minimum RAM tüketir.