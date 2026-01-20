# 🏢 Apartmanı Yönetim Sistemi

Modern, hızlı ve WhatsApp entegrasyonlu web tabanlı apartman yönetim paneli. Bu sistem, apartman yöneticilerinin mali kayıtları tutmasını, sakinlerle iletişimi otomatize etmesini ve detaylı raporlar almasını sağlar.

---

## 🚀 Öne Çıkan Özellikler

### 1. 📱 WhatsApp Otomasyonu (Node.js Entegrasyonu)
Sistem, sakinlerle olan iletişimi tamamen dijitalleştirir:
*   **Giriş Bilgileri:** Yeni kayıt olan sakine kullanıcı adı ve şifresini tek tıkla WhatsApp üzerinden gönderir.
*   **Bireysel Borç Hatırlatma:** Sakine özel güncel borç durumunu şık bir formatla gönderir.
*   **Toplu Borç Mesajı:** Borcu olan tüm sakinlere tek seferde WhatsApp üzerinden hatırlatma yapar.
*   **Duyuru Sistemi:** Yayınlanan genel duyuruları tüm sakinlerin telefonuna anlık olarak iletir.

### 2. 💰 Gelişmiş Finansal Yönetim
*   **Kasa Takibi:** Net nakit durumu, bekleyen alacaklar ve ödenecek faturaların anlık özeti.
*   **Toplu Aidat Tahakkuku:** Tüm dairelere (veya dükkanlar hariç) tek tıkla aylık aidat borcu yansıtır.
*   **Gecikme Zammı:** Kat Mülkiyeti Kanunu'na uygun olarak, vadesi geçen borçlara otomatik **%5 gecikme tazminatı** uygular.
*   **Gider Yönetimi:** Fatura ve harcamaları kategorize eder, makbuz/fiş görsellerini sisteme yükleyerek dijital arşiv oluşturur.

### 3. 📄 Profesyonel Raporlama ve Belgelendirme
*   **Tahsilat Makbuzu:** Yapılan her ödeme için yazdırılabilir, profesyonel görünümlü dijital makbuz oluşturur.
*   **Cari Hesap Ekstresi:** Her sakinin detaylı borç/alacak geçmişini (ekstre) PDF olarak kaydetme veya yazdırma imkanı.
*   **Finansal Analiz:** Tarih aralığına göre gelir-gider dağılımı ve aidat tahsilat performans grafikleri.

### 4. 👥 Sakin ve Daire Yönetimi
*   **Ev Sahibi / Kiracı Ayrımı:** Mülk sahibi ve yaşayan kişi bilgilerini ayrı ayrı takip eder.
*   **Daire/Dükkan Tipleri:** Bağımsız bölümleri tipine göre ayırarak farklı borçlandırma kuralları uygulayabilir.
*   **Hızlı Arama:** Gelişmiş filtreleme ile daire veya isim üzerinden saniyeler içinde sorgulama.

### 🌍 5. Çoklu Dil Desteği (TR / EN)
* **Arayüz:** Kullanıcılar tek tıkla paneli **Türkçe** veya **İngilizce** kullanabilir.
* **Akıllı Bildirimler:** Yabancı uyruklu sakinlere giden WhatsApp ve E-Posta bildirimleri, sistemde kayıtlı uyruklarına göre **otomatik olarak kendi dillerinde** gönderilir.

### 📱 6. Tam Responsive & Mobil Uygulama Deneyimi
* **Mobil Menü:** Telefondan girildiğinde özel "Hamburger Menü" ve kayar sidebar (çekmece menü) devreye girer.
* **Kullanıcı Dostu:** Sakinler için basitleştirilmiş, sadece ihtiyaçları olan butonları (Ödeme, Ekstre) içeren temiz mobil arayüz.
* **WebView Hazır:** Android WebView entegrasyonuna %100 uyumlu altyapı.

### 💳 7. QR Kodlu Ödeme Kolaylığı
* **Dinamik IBAN:** Yönetici panelinden IBAN güncellendiğinde tüm sistemde anında değişir.
* **QR Kod:** Sakinler, ödeme ekranında IBAN'ı elle yazmak yerine ekranda çıkan **Karekod (QR)**'u banka uygulamalarına okutarak saniyeler içinde ödeme yapabilir.
---

## 🛠 Teknik Alt Yapı

*   **Backend:** PHP 8+ (PDO ile Güvenli Veritabanı Yönetimi)
*   **Frontend:** Bootstrap 5, FontAwesome 6, Google Fonts
*   **Performans:** Toplu WhatsApp gönderimlerinde sunucu yükünü dengeleyen `Wait & Retry` mekanizması ve `Time Limit` yönetimi.
*   **Database:** MySQL
*   **Entegrasyon:** Node.js tabanlı WhatsApp API (Bağlantı Test Aracı Dahil)
*   **Güvenlik:** 
    *   CSRF Token koruması.
    *   `password_hash` ile şifreleme.
    *   SQL Injection koruması (Prepared Statements).
    *   XSS Filtrelemesi.

---

🌟 Yeni Nesil Özellikler
* **Çoklu Dil ve Uyruk Desteği: Kullanıcı arayüzü tek tıkla Türkçe veya İngilizce olarak değiştirilebilir.

* **Akıllı Bildirim Sistemi: Yabancı uyruklu sakinlere giden tüm WhatsApp ve E-Posta bilgilendirmeleri, sistemdeki uyruk kayıtlarına göre otomatik olarak İngilizce formatında gönderilir.

* **Karekod (QR) ile Kolay Ödeme: Sakinler, ödeme ekranında IBAN kopyalamak yerine banka uygulamalarıyla anında okutabilecekleri dinamik QR kodlarını kullanabilirler.

* **Yönetilebilir Dinamik IBAN: Site IBAN adresi yönetim panelinden tek tıkla güncellenebilir; bu değişiklik tüm kullanıcı ekranlarına ve QR kodlara anlık yansır.

---

### 🛡️ Güvenlik Önlemleri
Bu proje, apartman verilerinin güvenliği için endüstri standartlarını kullanır:
* **Strict CSRF Protection:** Tüm form ve silme işlemlerinde Cross-Site Request Forgery koruması aktiftir. GET istekleri ile veri değişimi engellenmiştir.
* **RBAC (Role-Based Access Control):** Yönetici (Tam Yetki) ve Denetçi (Sadece Okuma) yetkileri backend seviyesinde ayrıştırılmıştır.
* **SQL Injection Koruması:** Tüm veritabanı sorguları `PDO Prepared Statements` ile filtrelenir.
* **XSS Filtrelemesi:** Kullanıcı girdileri ekrana basılırken temizlenir.
* **Güvenli Parola Saklama:** Şifreler `password_hash (Bcrypt)` ile veritabanında şifreli tutulur.

---

## ⚙️ Kurulum

1.  **Veritabanı:** `includes/db.php` dosyasındaki bağlantı bilgilerini kendi sunucunuza göre düzenleyin.
2.  **WhatsApp API:** Node.js sunucunuzun `localhost:3000` (veya belirlediğiniz port) üzerinde çalıştığından emin olun.
3.  **Uploads:** `uploads/` klasörüne yazma izni (chmod 777) verin.
4.  **Test:** `admin/test_wa.php` dosyasını çalıştırarak WhatsApp sunucusuyla olan bağlantıyı doğrulayın.

---

## 📝 Notlar
Bu proje, apartman yönetim süreçlerini şeffaflaştırmak ve kağıt israfını önlemek amacıyla geliştirilmiştir. Özellikle **%5 Gecikme Zammı** ve **WhatsApp hatırlatıcıları** ile tahsilat oranlarını %40'a kadar artırmayı hedefler.

---

### 👨‍💻 Geliştirici
*   **Proje Adı:** Apartmanı Yönetim Paneli
*   **Kullanım Amacı:** Özel Site/Apartman Yönetimi

---

- ✅ **Nakit Kasa Takibi**
- ✅ **Toplu Borçlandırma**
- ✅ **WhatsApp Mesajlaşma**
- ✅ **PDF Makbuz Üretimi**
- ✅ **Gecikme Zammı Hesaplama**
- ✅ **Belge/Fiş Arşivleme**

