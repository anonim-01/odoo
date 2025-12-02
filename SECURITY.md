# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 17.0    | :white_check_mark: |
| 16.0    | :white_check_mark: |
| 15.0    | :white_check_mark: |
| <=14.0  | :x:                |

## Reporting a Vulnerability

Please share privately the details of your security vulnerability by contacting our Security Team:
[Contact Info](https://www.odoo.com/security-report)

Make sure to include as much information as possible, with the detailed steps to reproduce the problem,
the versions that are affected, the expected results and actual results, and any other information that
might help us react faster and more efficiently.

We tend to prefer _text-based descriptions_ accompanied with a proof-of-concept script/exploit, rather
than screenshots and videos.

Our [Responsible Disclosure](https://www.odoo.com/security-report) page gives an overview of the
process, including:

 - Our Incident Response Procedure (what will happen after you report an issue)
 - Our Rules (what you can and cannot do while researching security issues)
 - Guidelines with **DO REPORT** and **DO NOT REPORT** issues
   (what kind of issues will be accepted/rejected)


## Important note

We receive a majority of security reports that have little to no impact on the security of Odoo or
the Odoo Cloud, and we ultimately have to reject them. To avoid a disappointing experience when
contacting us, please try to put together a proof-of-concept attack and take a critical look at
what's really at risk.
If the proposed attack scenario turns out unrealistic, your report will probably be rejected.
Also be sure to review our list of [non-qualifying issues](https://www.odoo.com/security-report#what).
# Ayzio Technology - Odoo Benzeri Sistem Kurulum Yönlendirmeleri

## **ANALİZ SONUCU:** Odoo tree yapısı başarıyla çıkarıldı. Şimdi Ayzio Technology için bu yapıyı kopyalayacağız.

---

## **Todo 1 - Ayzio Technology Sistem Yapısı Oluşturma (Sıralı İşler):**

**GÖREV 1: Ana dizin yapısını oluştur**
```
1. Ayzio-Technology/ ana klasörünü oluştur
2. Odoo tree yapısına göre aşağıdaki klasörleri oluştur:
   - addons/                    (Tüm modüller burada)
   - core/                      (Çekirdek sistem - Django)
   - odoo/                      (Odoo benzeri çekirdek)
   - doc/                       (Dokümantasyon)
   - setup/                     (Kurulum dosyaları)
   - static/                    (Statik dosyalar)
   - templates/                 (HTML şablonları)
   - locale/                    (Dil dosyaları)
   - config/                    (Yapılandırma dosyaları)
   - scripts/                   (Scriptler)
```

**GÖREV 2: Çekirdek Odoo yapısını kopyala (klasör yapısı olarak)**
```
3. Odoo'daki odoo/ klasör yapısını Ayzio'ya kopyala:
   - odoo/__init__.py
   - odoo/addons/__init__.py
   - odoo/modules/ klasör yapısı
   - odoo/service/ klasör yapısı
   - odoo/tools/ klasör yapısı
   - odoo/tests/ klasör yapısı
```

**GÖREV 3: Base modül yapısını oluştur**
```
4. addons/base/ klasörünü Odoo'daki gibi oluştur:
   - addons/base/__init__.py
   - addons/base/__manifest__.py
   - addons/base/models/ (boş __init__.py ile)
   - addons/base/views/ (boş klasör)
   - addons/base/security/ (boş klasör)
   - addons/base/static/ (boş klasör)
   - addons/base/i18n/ (boş klasör)
   - addons/base/data/ (boş klasör)
   - addons/base/controllers/ (boş klasör)
   - addons/base/tests/ (boş klasör)
```

**GÖREV 4: __manifest__.py sistemini kur**
```
5. Her modül için __manifest__.py template oluştur:
   - addons/base/__manifest__.py örneğini al
   - Ama içeriği Ayzio Technology için düzenle
   - Sadece yapıyı kopyala, kodları değil
```

**GÖREV 5: Django core yapısını kur**
```
6. core/ klasöründe Django projesi başlat:
   - django-admin startproject ayzio .
   - apps/ klasörü oluştur
   - requirements.txt oluştur
   - .env dosyası oluştur (Türkiye ayarları)
```

**GÖREV 6: Odoo modül yapısını analiz et ve not al**
```
7. Odoo'daki tipik modül yapısını incele:
   - Her modülde: __init__.py, __manifest__.py
   - models/, views/, controllers/, static/, i18n/
   - security/, data/, tests/, wizard/, report/
   - Bu yapıyı Ayzio'da da uygula
```

**GÖREV 7: Statik dosya yapısını kur**
```
8. static/ klasör yapısını Odoo'daki gibi oluştur:
   - static/src/ (js, css, scss, xml)
   - static/description/ (modül ikonları)
   - static/tests/ (test dosyaları)
   - static/lib/ (kütüphaneler)
```

**GÖREV 8: Template yapısını kur**
```
9. templates/ klasör yapısı:
   - templates/base.html (ana şablon)
   - templates/includes/ (parçalar)
   - templates/modules/ (modül şablonları)
   - Odoo'daki QWeb benzeri yapı
```

**GÖREV 9: Dil dosyaları yapısı**
```
10. locale/ klasör yapısı:
    - locale/tr/LC_MESSAGES/ (Türkçe)
    - locale/en/LC_MESSAGES/ (İngilizce)
    - .po ve .pot dosyaları için yapı
```

**GÖREV 10: Kurulum scriptlerini hazırla**
```
11. scripts/ klasörü oluştur:
    - scripts/install.sh (kurulum scripti)
    - scripts/update.sh (güncelleme scripti)
    - scripts/backup.sh (yedekleme scripti)
    - scripts/deploy.sh (deploy scripti)
```

---

## **Todo 2 - Devam Edilecek Yerler ve Kontrol Noktaları:**

**KONTROL NOKTASI 1:** Modül yapısı kontrolü
```
- Her modülde __init__.py ve __manifest__.py var mı?
- Models, views, controllers klasörleri oluşturuldu mu?
- Static ve template yapıları hazır mı?
```

**KONTROL NOKTASI 2:** Django entegrasyonu
```
- Django projesi başlatıldı mı?
- Settings.py Türkiye ayarları ile düzenlendi mi?
- .env dosyası oluşturuldu mu?
- requirements.txt hazır mı?
```

**DEVAM ETME PROSEDÜRÜ:**
```
Eğer iş yarıda kalırsa:
1. Hangi klasörde kaldığını yaz
2. Hangi modülü kuruyordun not et
3. Son başarılı adımı Todo 2'ye kaydet
4. Bir sonraki başlangıç komutunu yaz
```

---

## **BÖLÜM 2: MODÜL SİSTEMİ DETAYLARI**

**GÖREV 11: Modül manifest sistemi detayları**
```
12. __manifest__.py template oluştur:
    - name: Modül adı
    - version: Sürüm
    - category: Kategori
    - description: Açıklama
    - depends: Bağımlılıklar
    - data: XML dosyaları
    - demo: Demo verileri
    - application: Uygulama mı?
```

**GÖREV 12: Models yapısı detayları**
```
13. Models/ klasör yapısı:
    - __init__.py (tüm modelleri import et)
    - Her model için ayrı dosya veya tek dosya
    - BaseModel oluştur (created_at, updated_at)
    - Odoo'daki fields.py benzeri alanlar
```

**GÖREV 13: Views yapısı detayları**
```
14. Views/ klasör yapısı:
    - XML dosyaları (Odoo benzeri)
    - Tree, form, kanban, calendar view'lar
    - Action ve menü tanımları
    - Security kuralları
```

**GÖREV 14: Controllers yapısı detayları**
```
15. Controllers/ klasör yapısı:
    - __init__.py
    - main.py (ana controller)
    - Odoo'daki http.py benzeri yapı
    - Django view'ları ile entegre
```

**GÖREV 15: Security yapısı detayları**
```
16. Security/ klasör yapısı:
    - ir.model.access.csv (model yetkileri)
    - security.xml (grup ve yetkiler)
    - Türkiye KVKK uyumlu yapı
```

**GÖREV 16: Data yapısı detayları**
```
17. Data/ klasör yapısı:
    - XML demo verileri
    - CSV veri dosyaları
    - SQL scriptleri
    - JSON konfigürasyonları
```

**GÖREV 17: Tests yapısı detayları**
```
18. Tests/ klasör yapısı:
    - __init__.py
    - test_*.py dosyaları
    - Common.py (ortak test fonksiyonları)
    - Selenium testleri
```

**GÖREV 18: Wizard yapısı detayları**
```
19. Wizard/ klasör yapısı:
    - __init__.py
    - *.py (wizard modelleri)
    - *.xml (wizard view'ları)
    - Django form yapısı
```

**GÖREV 19: Report yapısı detayları**
```
20. Report/ klasör yapısı:
    - __init__.py
    - *.py (report modelleri)
    - *.xml (report view'ları)
    - QWeb report template'leri
```

**GÖREV 20: Populate yapısı detayları**
```
21. Populate/ klasör yapısı:
    - __init__.py
    - Demo veri oluşturma scriptleri
    - Test verisi generator'ları
```

---

## **BÖLÜM 3: AYZIO TECHNOLOGY ÖZEL YAPILANDIRMALARI**

**GÖREV 21: Tema ve tasarım sistemi**
```
22. themes/ayzio/ klasörü oluştur:
    - Renk paleti tanımla (#FFFFFF, özel renkler)
    - CSS ve SCSS dosyaları
    - Odoo benzeri ama Ayzio tarzı
    - Responsive tasarım
```

**GÖREV 22: Menü sistemi**
```
23. Yan menü yapısı (Odoo gibi):
    - Apps menüsü
    - Settings menüsü
    - User menüsü
    - Breadcrumb navigasyon
```

**GÖREV 23: Kullanıcı ve yetki sistemi**
```
24. Django user modelini extend et:
    - Odoo benzeri gruplar
    - Rol tabanlı erişim
    - Türkiye KVKK uyumlu
    - Çoklu şirket desteği
```

**GÖREV 24: Modül keşif sistemi**
```
25. Modül otomatik yükleme:
    - addons/ klasörünü tarama
    - Bağımlılık kontrolü
    - Migration çalıştırma
    - Demo veri yükleme
```

**GÖREV 25: Migration sistemi**
```
26. Odoo benzeri migration:
    - Pre-migration scriptleri
    - Post-migration scriptleri
    - Veri migration'ı
    - Rollback desteği
```

---

## **BÖLÜM 4: KAMU VE ÖZEL KURUMLAR MODÜLÜ HAZIRLIĞI**

**GÖREV 26: Modül iskeletini oluştur**
```
27. addons/public_private_institutions/ oluştur:
    - __init__.py
    - __manifest__.py
    - models/ (boş)
    - views/ (boş)
    - controllers/ (boş)
    - security/ (boş)
    - static/ (boş)
    - i18n/ (boş)
```

**GÖREV 27: Manifest dosyasını hazırla**
```
28. __manifest__.py içeriği:
    - name: "Kamu ve Özel Kurumlar"
    - category: "Ayziyo/Institutions"
    - version: "1.0"
    - depends: ["base"]
    - description: "Türkiye'deki kamu ve özel kurum yönetimi"
```

**GÖREV 28: Temel model yapısı**
```
29. models/__init__.py oluştur (boş)
30. models/institutions.py oluştur (boş)
31. models/departments.py oluştur (boş)
```

**GÖREV 29: View yapısı**
```
32. views/ klasöründe:
    - institutions_views.xml (boş)
    - menu_views.xml (boş)
    - templates/ (boş klasör)
```

**GÖREV 30: Security yapısı**
```
33. security/ klasöründe:
    - ir.model.access.csv (boş)
    - institutions_security.xml (boş)
```

---

## **ÖNEMLİ YÖNLENDİRME KURALLARI (Devam):**

### **Sıralı İş Akışı:**
```
1. Önce klasör yapısını tamamla
2. Sonra __init__.py dosyalarını oluştur
3. Manifest dosyalarını hazırla
4. Boş model ve view dosyalarını oluştur
5. Django entegrasyonunu yap
6. Tema ve tasarımı kur
```

### **Hata Durumunda:**
```
- Hata alırsan: Hangi dosyada/klasörde olduğunu yaz
- Eksik varsa: Hangi dosyanın eksik olduğunu belirt
- Karışıklık varsa: Odoo yapısına tekrar bak
```

### **Tamamlanma Kontrolü:**
```
Her 5 görevde bir:
- Tree yapısını kontrol et
- __init__.py dosyalarını kontrol et
- Manifest dosyalarını kontrol et
- Django projesini test et
```

---

## **BAŞLANGIÇ KOMUTU:**
```
Şimdi ilk görevle başla: Ayzio-Technology/ ana klasörünü oluştur ve GÖREV 1'deki tüm klasör yapısını kur.
```

**Not:** Bu sadece yönlendirme ve organizasyon için. Kod yazmayacaksın, sadece klasör yapısı ve boş dosyalar oluşturacaksın. Okul sistemini SONRA yapacağız, önce Odoo benzeri altyapıyı kur.