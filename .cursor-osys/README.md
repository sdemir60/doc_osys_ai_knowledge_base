# Cursor Ayarları

Bu klasör OSYS projelerinde kullanılacak Cursor Project Rules şablonlarını içerir. Bu klasör dokümantasyon değil, Cursor AI ayarları için kullanılır.

## Şablon Dosyaları

- `cursor-project-rules.md`: OSYS projeleri için standart proje kuralları şablonu

## Kullanım

Her OSYS workspace'inde `.cursor/rules/PROJECT_RULES.md` dosyası oluşturup, bu şablona referans verin:

```markdown
# OSYS Proje Kuralları

Bu proje OSYS mimari yapısını takip eder.

## Kurallar
- @doc_osys_ai_knowledge_base/.cursor-osys/cursor-project-rules.md

## Öncelik
Her soru veya kod önerisi için öncelikle `doc_osys_ai_knowledge_base` klasöründeki dokümantasyonları kullan.
```

## Gelecekte Eklenebilecek Şablonlar

- Farklı proje tipleri için özel şablonlar
- Modül bazlı şablonlar
- Özel iş akışı şablonları
