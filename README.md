# Antrenman Takip

Telefonda çalışan kişisel antrenman takip uygulaması. Kurulum gerektirmez, hesap açılmaz,
sunucu yoktur — tüm veriler telefonun tarayıcı deposunda (`localStorage`) tutulur.

**Adres:** https://hbtokgoz.github.io

## iPhone'a kurulum

1. Safari ile https://hbtokgoz.github.io adresini aç
2. Alt çubuktaki **Paylaş** simgesine dokun
3. **Ana Ekrana Ekle** → **Ekle**

Ana ekrandan açtığında tarayıcı çubuğu olmadan, normal bir uygulama gibi tam ekran çalışır
ve internet olmadan da açılır.

## Neler var

| Ekran | İçerik |
|---|---|
| **Bugün** | Haftalık/toplam istatistik, antrenman günü seçimi, son antrenmanlar |
| **Antrenman** | Set set ağırlık + tekrar girişi, geçen seferki değerler, otomatik dinlenme timer'ı |
| **Takvim** | Aylık takvimde antrenman günleri, seri takibi, seans detayları |
| **İlerleme** | Hareket bazlı ağırlık grafiği, hacim grafiği, haftalık hacim, kişisel rekorlar |
| **Program** | Gün ve hareket ekleme/düzenleme/silme/sıralama |

Detaylar:

- **Akıllı ön dolgu** — her set kutusunda geçen antrenmandaki değer soluk olarak yazılıdır.
  Aynı ağırlıkla devam edeceksen bir şey yazmadan ✓ işaretlemen yeterli.
- **Dinlenme timer'ı** — bir seti işaretleyince otomatik başlar. Süre bitince bip sesi ve
  titreşim verir; `+15` ile uzatabilir, `Atla` ile kapatabilirsin. Varsayılan süre Ayarlar'dan
  değiştirilir.
- **Ekran kapanmaz** — antrenman sürerken ekran uyanık tutulur (destekleyen tarayıcılarda).
- **Yarıda kalan antrenman** — uygulamayı kapatsan bile devam eden antrenman kaydedilir,
  açtığında kaldığın yerden devam edersin.
- **Hacim** = ağırlık × tekrar toplamı.
- **Seri** = art arda en az bir antrenman yapılan hafta sayısı.

## Yedekleme

Veriler yalnızca bu cihazda durur. Safari'nin site verilerini temizlemek ya da telefon
değiştirmek kayıtları siler. Ayarlar ekranından:

- **Yedek Al** → JSON dosyası indirir
- **Yedekten Geri Yükle** → o dosyayı geri okur

Ara sıra yedek almanı öneririm.

## Program

Başlangıç programı `Workout_Programme_Phase1_Revised.xlsx` dosyasındaki Phase 1
(Adaptasyon) planından alınmıştır: Push, Pull, Legs, Upper. Program ekranından
istediğin gibi değiştirilebilir; geçmiş kayıtlar bundan etkilenmez.

## Teknik

Tek bir `index.html` — bağımlılık, derleme adımı ve build aracı yok. Grafikler elle
üretilen SVG'dir. `sw.js` çevrimdışı çalışması için kabuğu önbelleğe alır.
`main` dalına yapılan her push GitHub Pages'e otomatik deploy edilir.

```
index.html               uygulama (HTML + CSS + JS)
sw.js                    service worker (çevrimdışı önbellek)
manifest.webmanifest     PWA tanımı
icon-*.png               ana ekran simgeleri
```
