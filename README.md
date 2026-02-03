# OSYS AI Knowledge Base

Bu proje OSYS projesi için AI destekli dokümantasyon ve bilgi tabanıdır. Cursor AI ile OSYS projelerinde çalışırken bu dokümantasyonlar kullanılır.

## Klasör Yapısı

- `mimari_yapi.md`: OSYS mimari yapısı ve katmanlar
- `gozlemler_ve_notlar.md`: Gözlemler, notlar ve farklı fikirler
- `standards/`: Proje yapısı, kodlama, tasarım, veritabanı standartları
- `modules/`: Modüller hakkında bilgiler
- `screens/`: Ekranlar ve ekran özelinde kodlar (menü yolu ile isimlendirilmiş)
- `database/`: Veritabanı objeleri (tables, procedures, views, functions, relations)
- `processes/`: Süreçler hakkında detaylı bilgiler
- `.cursor-osys/`: Cursor AI ayarları ve şablonları (dokümantasyon değil, Cursor ayarları için)

## Kullanım

### 1. Workspace'e Ekleme
Bu dokümantasyon klasörünü OSYS workspace'lerine ekleyin.

### 2. Project Rules Ekleme
Her OSYS workspace'inde `.cursor/rules/project-rules.mdc` dosyası oluşturup `.cursor-osys/osys-project-rules.mdc`'ye referans verin. Detaylar için `.cursor-osys/README.md` dosyasına bakın.

### 3. User Rules (Cursor Settings)
Cursor Settings → Rules and Commands → User Rules'a genel kuralları ekleyin (Türkçe cevap, kod yazma yaklaşımı vb.)
