# OSYS AI Knowledge Base Proje Kuralları

Bu proje OSYS projesi için AI destekli dokümantasyon ve bilgi tabanıdır.

## Proje Amacı
- OSYS projesi hakkında dokümantasyon tutmak
- Cursor AI ile OSYS projelerinde çalışırken bu dokümantasyonları kullanmak
- Yeni bilgiler öğrenildikçe dokümantasyonu güncellemek

## Dokümantasyon Yapısı
- `mimari_yapi.md`: OSYS mimari yapısı ve katmanlar
- `standartlar/`: Proje yapısı, kodlama, tasarım, veritabanı standartları
- `moduller/`: Modüller hakkında bilgiler
- `ekranlar/`: Ekranlar ve ekran özelinde kodlar (menü yolu ile isimlendirilmiş)
- `veritabani/`: Veritabanı objeleri (tablolar, prosedürler, görünümler, fonksiyonlar, ilişkiler)
- `gozlemler_ve_notlar.md`: Sorunlu görülen alanlar ve notlar
- `surecler/`: Süreçler hakkında detaylı bilgiler
- `.osys/`: Cursor AI ayarları ve şablonları

## Çalışma Prensibi
1. Bu projede çalışırken dokümantasyon yazma ve güncelleme odaklı ol
2. Yeni bilgi eklendiğinde ilgili klasör/dosyaya ekle
3. Dokümantasyon formatını koru (Markdown, Türkçe)
4. Her dokümantasyon dosyası açık, anlaşılır ve organize olsun
5. Yeni klasör/dosya oluştururken mevcut yapıya uygun isimlendirme kullan

## Dokümantasyon Ekleme/Güncelleme Kuralları
- Ekran dokümantasyonu → `ekranlar/ModulAdi_AltMenu_EkranAdi.md` formatında
- Veritabanı objesi → `veritabani/` altındaki ilgili klasöre (tablolar, prosedürler, görünümler, fonksiyonlar, ilişkiler)
- Modül bilgisi → `moduller/` klasörüne
- Standart → `standartlar/` altındaki ilgili dosyaya
- Süreç → `surecler/` altındaki ilgili dosyaya
- Gözlem/Not → `gozlemler_ve_notlar.md` dosyasına

## Önemli Notlar
- Bu proje dokümantasyon projesidir, kod yazma projesi değil
- Dokümantasyonlar zamanla doldurulacak, şablonlar hazır
- Yeni bilgi eklendiğinde ilgili dosyayı güncelle, yeni dosya oluşturma gerekiyorsa uygun klasöre ekle
