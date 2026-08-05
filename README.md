# Gizlilik Politikalari

NCosy tarafindan yayinlanan mobil uygulamalarin gizlilik politikalari.
GitHub Pages ile yayinlanir; Google Play Console'un "Gizlilik Politikasi URL'si"
alaninda bu adresler kullanilir.

**Yayin adresi:** https://ncosy.github.io/privacy/

> Bu depo **herkese acik** olmalidir. Google Play'in istedigi gizlilik politikasi
> URL'si herkesin erisebilecegi bir adres olmak zorundadir; ayrica ucretsiz
> GitHub hesaplarinda Pages yalnizca herkese acik depolarda calisir.
> Depoda kaynak kod veya gizli bilgi bulunmaz, yalnizca statik HTML sayfalari.

## Yapi

```
/
├── index.html                    # Uygulama listesi
└── <uygulama-slug>/
    └── index.html                # O uygulamanin politikasi (TR + EN)
```

## Yayindaki politikalar

| Uygulama | Paket adi | URL |
|---|---|---|
| Dogum Gunu Takibi | `com.ncosy.birthdaylist` | https://ncosy.github.io/privacy/birthday-tracker/ |
| Kac Gun Kaldi - Gun Sayaci | `com.ncosy.mysayac` | https://ncosy.github.io/privacy/days-left-countdown/ |
| Kac Gun Oldu | `com.ncosy.kacgun` | https://ncosy.github.io/privacy/days-since-counter/ |
| Evet Hayir | `com.evethayirduz` | https://ncosy.github.io/privacy/yes-no-decider/ |
| Karar Carki | `com.evethayircark` | https://ncosy.github.io/privacy/decision-wheel/ |
| Mizika | `com.charmonicam` | https://ncosy.github.io/privacy/harmonica/ |
| Notlarim | `com.mynotesapp` | https://ncosy.github.io/privacy/my-notes/ |
| Harcama Takibi | `ncosy.harcamalistesi` | https://ncosy.github.io/privacy/expense-tracker/ |

## Yeni uygulama eklemek

1. `<uygulama-slug>/index.html` olustur (mevcut bir politikayi sablon olarak kullan).
2. Uygulamaya ozgu bolumleri guncelle: uygulama adi, paket adi, saklanan veriler,
   izinler, kullanilan ucuncu taraf SDK'lar.
3. Kok `index.html` icindeki listeye ekle.
4. Yukaridaki tabloya ekle.
5. Commit + push. GitHub Pages 1-2 dakika icinde yayina alir.

### Dikkat

Politika metni uygulamanin **gercek** davranisini yansitmalidir. Play, beyan ile
uygulamanin davranisi arasindaki uyusmazlik nedeniyle uygulamayi kaldirabilir.
Ozellikle su noktalar her uygulama icin ayri kontrol edilmelidir:

- Veriler cihazda mi tutuluyor, yoksa bir sunucuya mi gonderiliyor?
- Manifest'te hangi izinler var?
- Hangi ucuncu taraf SDK'lar veri topluyor? (AdMob, Firebase, analitik vb.)

AdMob kullanan uygulamalar icin toplanan veriler Google'in resmi listesindedir:
https://developers.google.com/admob/android/privacy/play-data-disclosure

## Play Console'da kullanimi

- **Gizlilik Politikasi URL'si:** Politika > Uygulama icerigi > Gizlilik Politikasi
- **Veri Guvenligi formu:** Politika > Uygulama icerigi > Veri guvenligi
  (form ile bu sayfadaki beyanlar tutarli olmalidir)
