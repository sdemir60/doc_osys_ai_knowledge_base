# Cursor Ayarları

Bu klasör OSYS projelerinde kullanılacak Cursor Project Rules şablonlarını içerir. Bu klasör dokümantasyon değil, Cursor AI ayarları için kullanılır.

## Şablon Dosyaları

- `osys-project-rules.mdc`: OSYS projeleri için standart proje kuralları şablonu

## Kullanım

Her OSYS workspace'inde `.cursor/rules/project-rules.mdc` dosyası oluşturup, bu şablona referans verin:

```markdown
# OSYS Proje Kuralları

Bu proje OSYS mimari yapısını takip eder.

## Kurallar
- @doc_osys_ai_knowledge_base/.cursor-osys/osys-project-rules.mdc

## Öncelik
Her soru veya kod önerisi için öncelikle `doc_osys_ai_knowledge_base` klasöründeki dokümantasyonları kullan.
```

**Not:** Bu dosyayı direkt OSYS projelerinin `.cursor/rules/` klasörüne kopyalayıp kullanabilirsiniz.

## Gelecekte Eklenebilecek Şablonlar

- Farklı proje tipleri için özel şablonlar
- Modül bazlı şablonlar
- Özel iş akışı şablonları
