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
    ├── index.html                # O uygulamanin politikasi (TR + EN)
    └── hesap-silme/
        └── index.html            # Hesap silme sayfasi (yalnizca hesap
                                  # olusturmaya izin veren uygulamalarda)
```

### Hesap silme sayfasi ne zaman gerekli

Google Play, kullanicilarin hesap olusturabildigi uygulamalarda **web
uzerinden erisilebilir bir hesap silme sayfasi** sart kosuyor. URL, Play
Console > Uygulama icerigi > Veri guvenligi bolumunde isteniyor ve magaza
girisinde gosteriliyor.

Sayfa su ucunu birden karsilamali:

- Magaza girisindeki uygulama veya gelistirici adina atifta bulunmali
- Silme adimlarini belirgin sekilde gostermeli
- Silinen ve saklanan veri turlerini, ek saklama surelerini yazmali

Ornek: `paradar/hesap-silme/`

## Yayindaki politikalar

Adlar magaza girislerindeki adlarla birebir ayni tutulur. Her uygulamanin
**iki paket adi** vardir: Play'deki Android paketi ile App Store'daki iOS
bundle kimligi farklidir (Paradar haric). Ayni gizlilik sayfasi iki platform
icin de kullanilir.

| Uygulama | Android | iOS | URL |
|---|---|---|---|
| Dogum Gunu Takibi & Burc | `com.ncosy.birthdaylist` | `com.letworktech.birthdaylist` | https://ncosy.github.io/privacy/birthday-tracker/ |
| Kac Gun Kaldi - Gun Sayaci | `com.ncosy.mysayac` | `com.letworktech.kacgunkaldi` | https://ncosy.github.io/privacy/days-left-countdown/ |
| Kac Gun Oldu - Gun Sayaci | `com.ncosy.kacgun` | `com.letworktech.kacgunoldu` | https://ncosy.github.io/privacy/days-since-counter/ |
| Evet mi Hayir mi? - Karar | `com.evethayirduz` | `com.letworktech.evethayir` | https://ncosy.github.io/privacy/yes-no-decider/ |
| Karar Carki - Cevir Karar Ver | `com.evethayircark` | `com.letworktech.kararcarki` | https://ncosy.github.io/privacy/decision-wheel/ |
| Mizika - Harmonika Cal | `com.charmonicam` | `com.letworktech.mizika` | https://ncosy.github.io/privacy/harmonica/ |
| Notlarim - Not Defteri | `com.mynotesapp` | `com.letworktech.notlarim` | https://ncosy.github.io/privacy/my-notes/ |
| Harcama Takibi - Butce | `ncosy.harcamalistesi` | `com.letworktech.harcamatakibi` | https://ncosy.github.io/privacy/expense-tracker/ |
| Paradar: Gelir Gider Takibi | `com.letworktech.paradar` | `com.letworktech.paradar` | https://ncosy.github.io/privacy/paradar/ |

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
