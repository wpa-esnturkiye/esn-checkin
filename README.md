# ESN Check-in

Kapıda QR bilet okutma sayfası — ESN teması (`esn-tema/esn.css`, Poppins, ESN logosu).
Statik; veri Google Apps Script web app'inden `/exec?api=getTickets|checkIn` ile JSON olarak geliyor.

**Açma:** yalnız OC'nin kişisel linkiyle — `https://<bu sayfa>/#api=<Apps Script /exec>&k=<OC anahtarı>`.
Link google-EM menüsünden (OC'lere Check-in Linki Gönder) mailleniyor. Linksiz ya da geçersiz
anahtarla açılırsa kilitli ekran çıkar; sayfada değiştirilecek ayar yok. Okutan adı sunucuda anahtardan bulunur.

**İki sekme:** *QR Tara* (kamera açık, kesintisiz okur) · *Elle Giriş* (numara ya da isim; kamera kapanır).

| Dosya | Ne |
|---|---|
| `index.html` | Sayfa |
| `esn-tema/` | ESN tema CSS'i, Poppins fontları, logolar |
| `vendor/html5-qrcode.min.js` | QR kütüphanesi, sürüm 2.3.8 sabit |

Neden Apps Script içinde değil: Apps Script sayfayı kendi iframe'inde sunuyor ve kamera iznini
her dağıtıma vermiyor. Dışarıda barınan sayfada kamera her telefonda standart şekilde açılıyor.

**Sunucu:** her etkinliğin kendi google-EM Apps Script projesi (`Checkin.gs`) — okutmalar o etkinliğin
OC TRACK sheet'ine yazılır. Sunucu kodu bu repoda değil; içinde etkinlik sheet linkleri var.
Bilet QR'ı yalnız kodu taşır (`IZM-013`); eski biletlerin linkli QR'ı da okunur.
