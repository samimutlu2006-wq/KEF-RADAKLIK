# Kefkir Hayvancılık ve Adaklık – web sitesi

Tek sayfalık tanıtım sitesi. Bütün kod (HTML, CSS, JS) `index.html` içinde, fotoğraf ve videolar `assets` klasöründe.

```
index.html          sitenin kendisi
assets/img/         fotoğraflar, ikonlar, paylaşım görseli
assets/video/       ahır videosu (hero), hikâye videosu ve tesis tanıtım videosu
.nojekyll           GitHub Pages'in dosyalara dokunmaması için
```

## GitHub Pages'te yayınlama

1. GitHub'da yeni bir repo açın (örnek: `kefkir`). **Public** olsun.
2. Repo sayfasında **Add file → Upload files** deyin. Zip'i açıp içindeki `index.html`, `assets` klasörü ve `README.md` dosyasını sürükleyip bırakın, **Commit changes** ile kaydedin.
3. **Settings → Pages** bölümüne girin. *Source* olarak **Deploy from a branch**, branch olarak **main** ve **/(root)** seçip kaydedin.
4. Bir iki dakika sonra site `https://KULLANICIADI.github.io/kefkir/` adresinde açılır.

Kendi alan adınızı bağlamak isterseniz **Settings → Pages → Custom domain** kısmına yazmanız yeterli.

## Değiştirmeniz gereken yerler

`index.html` içinde `DÜZENLE` diye aratırsanız hepsini bulursunuz.

| Ne | Nerede |
| --- | --- |
| WhatsApp numarası | Dosyanın sonundaki `<script>` içinde `WHATSAPP_NUMARASI` (ülke koduyla, `+` olmadan: `905519464044`) |
| Telefonlar | `tel:+90...` geçen satırlar ve görünen numaralar |
| Adres | İletişim bölümündeki `<address>` etiketi |
| Harita | Google Haritalar → işletme → Paylaş → **Harita yerleştir** → HTML'yi kopyala. Kodu `id="harita"` olan kutunun içine yapıştırın, altındaki `map-placeholder` bloğunu silin. |
| Ağırlık / et miktarı | Seçenekler bölümündeki radio butonlarında `data-canli` ve `data-et` değerleri |
| Büyükbaş fotoğrafı | Şu an Unsplash'ten yer tutucu. Kendi fotoğrafınızı `assets/img/` içine koyup `<img src=...>` adresini değiştirin. |
| Renkler | `<style>` başındaki `--red` (kırmızı), `--bg` (siyah zemin) gibi değişkenler. WhatsApp butonları `--wa` ile WhatsApp yeşilinde. |
| En üstteki fotoğraf | `assets/img/vitrin-genis-*` (masaüstü) ve `vitrin-mobil-*` (telefon). Her fotoğrafın birkaç boyutu var (`-720`, `-1200` gibi), hem AVIF hem WebP. Telefon ekranına yeten en küçüğünü indirir. Değiştirirken aynı adlarla ve aynı boyutlarda kaydedin. |
| WhatsApp önizleme görseli | `<head>` içindeki `og:image`. Site yayına girince tam adresle yazın: `https://KULLANICIADI.github.io/kefkir/assets/img/og-kefkir.jpg` |

## Slayt eklemek

Hero'daki her slayt üç parçadan oluşur: `.slides` içindeki bir `<figure class="slide">`, `.hero-texts` içindeki bir metin bloğu ve `.story-bars` içindeki bir `.bar` butonu. Üçünü de aynı sırayla ekleyin. `data-duration` slaytın ekranda kalma süresidir (milisaniye).

## Hız

- Açılışta sadece ilk ekrandaki iki fotoğraf iner: dükkân ve ilk slayt. Diğer slaytlar sırası gelince, Biz Kimiz video kapakları da sayfa yüklendikten sonra o bölüme yaklaşınca yüklenir.
- Fotoğraf inerken yerinde bulanık küçük bir önizlemesi durur, boş kutu görünmez. Bunlar `index.html` içindeki `data:image/jpeg;base64,...` satırları.
- Yazı tipi sayfanın açılmasını bekletmez, arkadan yüklenir.

## Medya

- En üstteki dükkân fotoğrafı, tesis, paket ve koyunlu fotoğraf ile videolar işletmenin kendi çekimleri. Dükkân tabelasından başka işletmenin adı, logosu ve telefonları silindi. Videolar web için küçültüldü, telefonun kaydettiği konum bilgileri silindi.
- Biz Kimiz'deki "Hikâyemiz" videosu (`assets/video/hikayemiz.mp4`): üstteki CapCut yazısı kırpıldı, görüntü büyütülüp netleştirildi, ses seviyesi dengelendi.
- Büyükbaş kartındaki fotoğraf: Unsplash (Haberdoedas), Unsplash lisansıyla.
