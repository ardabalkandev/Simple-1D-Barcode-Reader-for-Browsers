# 1D Barkod Okuyucu

Bu proje, web tarayıcısı üzerinden EAN-8, EAN-13, Code128 gibi 1D (tek boyutlu) barkodları okumayı sağlar. Kullanıcı, cep telefonunun kamerasıyla barkodu tarayarak değerini ve türünü ekranda görebilir. Projede JavaScript tabanlı bir barkod kütüphanesi kullanılır ve mobil cihazın kamerasına tarayıcıdan erişim izni (HTTPS gerekliliği) aracılığıyla canlı tarama yapılır.

## Özellikler
- Canlı Önizleme: Barkodu kameraya gösterirken tarayıcıda canlı görüntü alınır.
- Desteklenen Formatlar:
- EAN-8
- EAN-13
- Code128
- Otomatik Tanıma: Barkod algılanır algılanmaz ekranda değeri (metin) ve barkod tipi gösterilir.
- Başlat/Durdur: Kolay kullanım için iki butonla kamerayı açıp kapatabilme.
- Mobil Uyumluluk: Modern akıllı telefonlardaki arka kamerayla test edilmeye uygundur.
## Kurulum ve Çalıştırma
1. Proje Dosyaları:
- Bu repo içerisindeki index.html (veya barcode.html gibi) dosyasını indir veya kopyala.
2. Sunucu Ayarı (HTTPS):
- Yerel Geliştirme:
- http://localhost üzerinden test ediyorsan, mobil tarayıcılar genellikle yerel geliştirme amaçlı kamera erişimine izin verir.
- Üretim Ortamı / Gerçek Sunucu:
- HTTPS üzerinden yayınlamak zorundasın. Tarayıcılar güvenlik amacıyla getUserMedia erişimini yalnızca güvenli bağlantılar (SSL sertifikalı domainler) veya localhost’a izin verir.
3. Tarayıcı İzinleri:
- Sayfayı ilk kez ziyaret ettiğinde tarayıcı kamera izni isteyecektir. “İzin Ver”i seçtiğinde tarama başlayabilir.
- Daha önce izni reddettiysen, tarayıcının ayarlar bölümünden siteye kamera izni vermen gerekebilir.
4. Kullanım:
- Projeyi sunucunda çalıştır ve HTTPS adresine git.
- “Kamerayı Başlat” veya benzeri butona tıklayarak canlı kamera akışını başlat.
- Barkodu kameraya net bir şekilde yaklaştır; Işık ve açı uygun olmalı.
- Barkod algılanınca ekranda değeri ve barkod tipi (EAN-8, EAN-13, Code128) gösterilir.
- “Kamerayı Durdur” ile taramayı durdur.

![Barkod Tarama Ekran Görüntüsü](./screenshot.png)

## Dikkat Edilmesi Gerekenler
- Işık ve Netlik: Karanlık veya parlama olan ortamlarda barkod zor okunabilir.
- Arka Kamera: facingMode: "environment" ayarı her cihazda doğru çalışmayabilir. Gerekirse facingMode: "user" ile ön kamerayı test edebilirsin.
- Barkod Boyutu: Kameraya çok yakın veya çok uzak tutmak sorun yaratabilir. Orta mesafede barkod net gözükmeli.
- Tarayıcı Desteği: getUserMedia API’si modern tarayıcıların çoğunda çalışır. Eski Android sürümlerinde veya iOS 11.2 öncesinde kısıtlamalar olabilir.

## Katkıda Bulunun
- Pull request veya issue açarak geliştirmelere katkıda bulunabilirsin.
- Yeni barkod formatları eklemek istersen, kullandığımız JS kütüphanesinin (örneğin Quagga, ZXing, vb.) desteklenen format listesine göz atarak ayar dosyalarında decoder/readers bölümüne yeni formatları ekleyebilirsin.

## İletişim
- Proje Sahibi: Arda (veya GitHub kullanıcı adın)
- İletişim için GitHub üzerinden mesaj atabilir veya e-posta gönderebilirsiniz.
