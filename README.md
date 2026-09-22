# ESN Check-in

Kapıda QR bilet okutma sayfası — ESN teması (`esn-tema/esn.css`, Poppins, ESN logosu).
Statik; veri Google Apps Script web app'inden `/exec?api=getTickets|checkIn` ile JSON olarak geliyor.

**Açma:** `https://<bu sayfa>/#api=<Apps Script /exec linki>` — ya da sayfadaki "Sunucu bağlantısı"
kartına /exec linkini yapıştır. `#` sonrası sunucuya gitmez, repoda durmaz; telefon bir kez
açınca hatırlar. Linki yalnız kapı ekibiyle paylaş.

**İki sekme:** *QR Tara* (kamera açık, kesintisiz okur) · *Elle Giriş* (numara ya da isim; kamera kapanır).

| Dosya | Ne |
|---|---|
| `index.html` | Sayfa |
| `esn-tema/` | ESN tema CSS'i, Poppins fontları, logolar |
| `vendor/html5-qrcode.min.js` | QR kütüphanesi, sürüm 2.3.8 sabit |

Neden Apps Script içinde değil: Apps Script sayfayı kendi iframe'inde sunuyor ve kamera iznini
her dağıtıma vermiyor. Dışarıda barınan sayfada kamera her telefonda standart şekilde açılıyor.

Sunucu kodu (Code.gs) bu repoda değil — içinde etkinlik sheet linkleri var.
