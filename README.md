# OSYS AI Knowledge Base

Bu proje OSYS projesi için AI destekli dokümantasyon ve bilgi tabanıdır. Cursor AI ile OSYS projelerinde çalışırken bu dokümantasyonlar kullanılır.

## Klasör Yapısı

- `mimari_yapi.md`: OSYS mimari yapısı ve katmanlar
- `standartlar/`: Proje yapısı, kodlama, tasarım, veritabanı standartları
- `moduller/`: Modüller hakkında bilgiler
- `ekranlar/`: Ekranlar ve ekran özelinde kodlar (menü yolu ile isimlendirilmiş)
- `veritabani/`: Veritabanı objeleri (tablolar, prosedürler, görünümler, fonksiyonlar, ilişkiler)
- `gozlemler_ve_notlar.md`: Sorunlu görülen alanlar ve notlar
- `surecler/`: Süreçler hakkında detaylı bilgiler
- `.osys/`: Cursor AI ayarları ve şablonları (dokümantasyon değil, Cursor ayarları için)

## Kullanım

### 1. Workspace'e Ekleme
Bu dokümantasyon klasörünü OSYS workspace'lerine ekleyin.

### 2. Project Rules Ekleme
Her OSYS workspace'inde `.cursor/rules/PROJECT_RULES.md` dosyası oluşturup `.osys/cursor-project-rules.md`'ye referans verin. Detaylar için `.osys/README.md` dosyasına bakın.

### 3. User Rules (Cursor Settings)
Cursor Settings → Rules and Commands → User Rules'a genel kuralları ekleyin (Türkçe cevap, kod yazma yaklaşımı vb.)
