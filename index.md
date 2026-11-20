---
layout: default
title: Gizlilik Politikası
lang: tr
---

# Denge Gizlilik Politikası

Son güncelleme: 20 Kasım 2026

Bu metnin güncel hâli: https://beratchi.github.io/denge-gizlilik/

Denge, kişisel yaşamını takip etmen için yapılmış bir uygulamadır. Bu metin Denge'nin hangi bilgiyi nerede tuttuğunu, telefondan ne zaman ve nereye bilgi çıktığını ve bunları nasıl silebileceğini anlatır. Android ve iPhone sürümleri için aynıdır.

## Kısaca

- Hesap açman gerekmez. Reklam, kullanım analizi, çökme raporu ve izleme (tracking) yoktur; reklam kimliği okunmaz.
- Kayıtların telefonunda saklanır. Denge'nin kendi sunucusunda yalnızca, açarsan, arkadaşınla paylaştığın ortak alışveriş listesi ve ortak borç defteri durur.
- Telefondan bilgi yalnızca aşağıda sayılan özellikleri kullandığında çıkar. Sağlık verilerin hiçbir sunucuya gönderilmez.
- Her şeyi uygulamanın içinden silebilirsin: Ayarlar > Uygulama > Veriler > **Tüm verileri sil**.

## Telefonunda kalan bilgiler

Şunlar yalnızca telefonundaki Denge veritabanında ve uygulama klasöründe durur:

- Profil bilgilerin (ad, doğum yılı, cinsiyet, boy, kilo, hedefler).
- Uyku, beslenme, su, hareket, sağlık, ruh hâli, öz bakım, alışkanlık, görev, plan, odak, okuma, dil, para, ilişki ve ev kayıtların.
- Fotoğraflar, sesli notlar, uyku ses kesitleri, rota kayıtları ve fişler.
- **Kara kutu** notların ve fotoğrafların: yalnızca senin bildiğin kodla şifrelenir; kod hiçbir yerde saklanmaz.
- Otomatik yedekler (son 7 tanesi).

Bu bilgileri Denge'nin geliştiricisi de dahil kimse göremez.

## Telefondan çıkan bilgiler

### Ortak alan (isteğe bağlı)

Ayarlar > Ortak alan'dan bir arkadaşınla ortak alan kurarsan, ikinizin telefonu Denge'nin sunucusu üzerinden eşitlenir. Sunucu Supabase'tedir ve Avrupa Birliği'nde (İrlanda) bulunur.

- **Gönderilenler:** ortak listedeki ürünler (ad, miktar, kategori, alındı işareti); ortak defterdeki borçlar ve ödemeler (tutar, para birimi, tarih, vade, not, taksit bilgisi); Profil'deki adın (arkadaşın seni bu adla görür).
- **Gönderilmeyenler:** başka hiçbir kayıt, liste ya da kişi.
- **Kim görür:** yalnızca alandaki iki kişi. Sunucu her telefona yalnızca kendi alanının kayıtlarını gösterir.
- **Kimlik:** e-posta, telefon numarası ya da şifre istenmez. Her telefon sunucuda içinde kişisel bilgi olmayan anonim bir oturumla tanınır.
- **Silme:** "Ortak alandan çık" eşitlemeyi durdurur. Arkadaşın alanda kalırsa ortak kayıtlar onun için sunucuda kalır; ikiniz de çıkınca alan ve bütün kayıtları sunucudan silinir.

### Fotoğraftan yemek tanıma (isteğe bağlı)

Beslenme'de fotoğraftan öğün eklemek için kendi Anthropic (Claude) API anahtarını girmen ve fotoğraflarının Anthropic'e gönderilmesine açıkça izin vermen gerekir.

- **Gönderilenler:** yalnızca "Çek" ya da "Galeri" ile seçtiğin fotoğraf ve istersen yazdığın kısa not. Fotoğraftaki konum ve çekim bilgileri gönderilmeden önce silinir.
- **Nereye:** Anthropic'e, senin anahtarınla, yani senin Anthropic hesabına. Anthropic bu isteği kendi API koşullarına ve gizlilik politikasına göre işler.
- **Saklama:** Denge fotoğrafı saklamaz; geçici kopya ekrandan çıkınca silinir. Anahtar telefonun güvenli anahtar deposuyla şifreli durur ve Denge'nin yedeklerine girmez.
- **İzni geri alma:** Fotoğraftan tanıma ayarlarında anahtarı sil.

### Arama ve bağlantı özellikleri

Bazı özellikler, aradığın şeyi ücretsiz ve herkese açık bir servise sorar. Bu isteklerle Denge seni tanıtan bir bilgi göndermez. Her internet isteğinde olduğu gibi, servis telefonunun IP adresini görür.

- **Kitap arama ve kapaklar:** yazdığın kitap adı, yazar ya da ISBN Open Library ve Google Books'a sorulur; kapak görselleri oradan indirilir.
- **Kaydettiğin bağlantılar:** başlığı ve önizlemesi için sayfanın kendisi açılır. YouTube, TikTok ve Vimeo bağlantılarında önizleme o sitelerden alınır. "Çevrimdışı kopya" açıksa (varsayılan açık) sayfanın okunur metni de indirilir.
- **Beslemeler (RSS):** eklediğin beslemeler, en sık üç saatte bir, kendi adreslerinden yenilenir.
- **Tarif içe aktarma:** yapıştırdığın tarif sayfası açılır.
- **Sözlük (varsayılan kapalı):** aradığın kelime MyMemory'ye ve İngilizce için Free Dictionary API'ye gönderilir.
- **Barkod:** okuttuğun barkod numarası Open Food Facts'e sorulur.
- **Döviz ve altın kuru:** kurlar Türkiye Cumhuriyet Merkez Bankası'ndan alınır; geçmiş bir kur istersen yalnızca o tarih gider.

### Telefonunun kendi servisleri

Bunları Denge değil, telefonun ve senin seçtiğin hesaplar yönetir:

- **Sağlık verileri (Android'de Health Connect, iPhone'da Apple Sağlık):** Denge yalnızca izin verdiğin türleri okur ve yazar. Bu veriler telefonda kalır.
- **Sesle yazma:** telefonun konuşma tanıma servisi kullanılır; bu servis internete bağlanabilir.
- **Takvim:** zaman bloklarını ve odak oturumlarını yazmayı seçersen, seçtiğin takvime yazılır. O takvim bir hesapla eşitleniyorsa bilgi o hesaba gider.
- **Telefon yedeği:** telefonunun kendi yedeği (Google ya da iCloud) açıksa Denge'nin verileri de o yedeğe girer. Ortak alan oturumu bu yedeğe girmez.
- **Kendi yedeklerin ve dışa aktarmalar:** yedeği ya da dışa aktarma dosyasını yalnızca sen seçtiğin klasöre kaydeder ya da paylaşırsın. Bu dosyalar şifresizdir (kara kutu içeriği dışında); dikkatli sakla.

## Sağlık verileri

Denge sağlık, uyku, beslenme, ruh hâli ve ilaç kayıtlarını hiçbir sunucuya göndermez (fotoğraftan yemek tanımayı kullanırsan yalnızca seçtiğin fotoğraf ve not Anthropic'e gider, kayıtların gitmez). Bunları reklam, pazarlama ya da veri madenciliği için kullanmaz ve kimseyle paylaşmaz. Apple Sağlık ya da Health Connect'ten okunan veriler yalnızca telefonunda gösterilir.

Denge kişisel bir takip defteridir. Tıbbi tanı koymaz, tedavi önermez. Hesaplanan değerler (vücut kitle indeksi, kalori hedefi, uyku puanı gibi) tahmindir. Sağlığınla ilgili kararlar için bir sağlık uzmanına danış.

## İzinler

Denge bir izni yalnızca o özelliği ilk kullandığında ister. İzni vermezsen o özellik dışında her şey çalışır.

- **Kamera:** barkod ve kod okuma ve fotoğraf eklediğin yerler (yemek, kara kutu, ev, notlar).
- **Mikrofon:** sesli notlar, telaffuz çalışması ve gece uyku sesi ölçümü.
- **Konum:** yürüyüş ve koşu rotası kaydı ve bir yere varınca hatırlatan görevler.
- **Kişiler:** yalnızca "Rehberden içe aktar" dersen ad, telefon ve özel günler alınır.
- **Takvim:** etkinliklerini planlayıcıda göstermek ve seçersen zaman bloklarını yazmak için.
- **Bildirimler:** hatırlatmalar, alarmlar ve süren sayaçlar.
- **Sağlık ve hareket:** adım sayısı, kilo ve izin verdiğin diğer türler.
- **Yüz ya da parmak izi:** uygulama kilidi ve kara kutu.
- **Ekran süresi ve uygulama kullanımı (Android):** Dijital Denge'nin süre ölçümü ve odak modu. Yalnızca telefonda işlenir.
- **Banka bildirimleri (Android, isteğe bağlı):** yalnızca seçtiğin uygulamaların bildirimlerinden harcama önerisi çıkarılır; internete gönderilmez.

## Saklama ve silme

- **Telefondaki kayıtlar:** sen silene kadar durur. **Tüm verileri sil** bütün kayıtları, medyayı, hatırlatmaları ve istersen otomatik yedekleri siler, ortak alandan çıkar ve fotoğraf tanıma anahtarını siler. Uygulamayı kaldırmak da telefondaki verileri siler.
- **Silinmeyenler:** Health Connect ya da Apple Sağlık'a yazılmış kayıtlar (oranın ayarlarından silinir), seçtiğin klasördeki yedekler ve telefonunun kendi yedekleri.
- **Ortak alan:** yukarıda anlatıldığı gibi, ikiniz de çıkınca sunucudan silinir.
- **Dışa aktarma:** kayıtlarını istediğin zaman JSON, ZIP ya da CSV olarak alabilirsin (Ayarlar > Uygulama > Veriler).

## Çocuklar

Denge çocuklara yönelik değildir ve bilerek çocuklardan bilgi toplamaz.

## Haklar ve iletişim

Kişisel verilerinle ilgili haklarını (bilgi alma, düzeltme, silme, itiraz; 6698 sayılı KVKK ve GDPR) uygulamanın içinden kullanabilirsin: kayıtlarını görebilir, düzeltebilir, dışa aktarabilir ve silebilirsin. Ortak alan sunucusundaki kayıtlarla ilgili bir istek ya da soru için Denge'nin geliştiricisine yaz: https://github.com/beratchi/denge-gizlilik/issues (destek sayfası: https://beratchi.github.io/denge-gizlilik/destek).

## Değişiklikler

Denge'nin topladığı ya da gönderdiği bilgiler değişirse bu metin aynı sürümde güncellenir ve üstteki tarih değişir.
