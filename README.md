# urun-ayristirma-projesi
Selam! Bu proje, aslında üniversitedeki bir ödev için hazırladığım ama üzerinde çalışırken kalite kontrol süreçlerine olan bakış açımı değiştiren küçük bir simülasyon.

Üretim hatlarında kalite kontrol süreçlerinin ne kadar kritik olduğunu hepimiz biliyoruz. Ben de "Peki, basit bir kamera görüntüsüyle hatalı veya farklı renkteki bir ürünü nasıl otomatik olarak ayıklayabiliriz?" sorusundan yola çıkarak, makine öğrenmesine ihtiyaç duymadan, saf görüntü işleme teknikleriyle bir çözüm üretmeye çalıştım.

İşin Mutfağında Ne Var?
Projeyi tamamen Python kullanarak geliştirdim. Temel kütüphanelerim şunlar:

OpenCV (cv2): Görüntüleri işlemek, renk uzaylarını değiştirmek ve nesneleri bulmak için ana motorum.

NumPy: Matris işlemlerini hızlıca halletmek için.

Matplotlib: Sonuçları görselleştirip "Bakın, sistem gerçekten çalışıyor!" diyebilmek için kullandığım araç.

Nasıl Çalışıyor?
Aslında sistemin mantığı oldukça basit ama etkili:

Renk Uzayı Dönüşümü: Görseli BGR'dan HSV'ye çektim. (Çünkü ışık değişimlerinden en az etkilenen ve renkleri gerçekten "renk" olarak ayıran uzay burası.)

Renk Maskeleme: Kırmızı kapsülleri seçmek için iki aşamalı bir maske kullandım.

Temizlik: Morfolojik "Opening" işlemiyle görseldeki o sinir bozucu gürültüleri ve küçük parlama noktalarını temizledim.

Kontur Analizi: Son adımda nesnelerin sınırlarını (konturlarını) bulup onları bir kutu içine aldım ve üzerine "Hap" etiketini yapıştırdım.

### Projeden Görüntüler

| Orijinal Görsel | Maskelenmiş Hali | Tespit Sonucu |
| :---: | :---: | :---: |
| <img src="BURAYA_ORIJINAL_GORSEL_LINKINI_YAPISTIR" width="300"> | <img src="BURAYA_MASKE_GORSEL_LINKINI_YAPISTIR" width="300"> | <img src="BURAYA_SONUC_GORSEL_LINKINI_YAPISTIR" width="300"> |
Neden Bu Proje Benim İçin Önemli?
Bir Junior QA / SDET adayı olarak, kodun sadece "yazılması" değil, "doğrulanması" ve "hata bulması" üzerine kurulu sistemlere hep ilgim vardı. Bu proje, bir yazılımın gerçek dünyadaki fiziksel bir veriyi nasıl işlediğini ve hataları nasıl tespit edebileceğini anlamamı sağladı.

Çalıştırmak İstersen
Bilgisayarında Python kuruluysa, sadece şu komutu çalıştırıp kütüphaneleri yüklemen yeterli:

pip install opencv-python numpy matplotlib

Ardından Jupyter Notebook dosyasını açıp hücreleri çalıştırman yeterli olacaktır.
