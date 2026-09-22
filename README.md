# ESN Check-in

Kapıda QR bilet okutma sayfası. Statik tek dosya (`index.html`); veri Google Apps Script
web app'inden `/exec?api=getTickets|checkIn` ile JSON olarak geliyor.

**Açma:** `https://<bu sayfa>/#api=<Apps Script /exec linki>` — `#` sonrası sunucuya gitmez,
repoda durmaz; telefon bir kez açınca hatırlar. Linki yalnız kapı ekibiyle paylaş.

Neden Apps Script içinde değil: Apps Script sayfayı kendi iframe'inde sunuyor ve kamera iznini
her dağıtıma vermiyor. Dışarıda barınan sayfada kamera her telefonda standart şekilde açılıyor.

Sunucu kodu (Code.gs) bu repoda değil — içinde etkinlik sheet linkleri var.
