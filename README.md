# Zikirmatik

Bu depo tek sayfalık zikirmatik uygulamasını ve aynı arayüzü WebView içinde çalıştıran Android projesini içerir. Aşağıdaki adımları izleyerek Android Studio yardımıyla APK oluşturabilirsiniz.

## Web sürümü

- `index.html` dosyası bağımsız olarak çalışır. Dosyayı herhangi bir tarayıcıda açarak sayaç, ses, titreşim, tema ve kayıt özelliklerini deneyebilirsiniz.

## Android projesi

Android kaynak kodu `android/` klasöründedir. Proje; web arayüzünü `app/src/main/assets/www/index.html` altına yerleştirerek WebView içerisinde yükler.

### Gereksinimler

- Android Studio Giraffe (veya daha yenisi)
- Android SDK 34
- En az Android 7.0 (API 24) cihaz ya da emülatör

### Kurulum ve APK üretimi

1. Depoyu klonlayın:
   ```bash
   git clone https://github.com/<kullanici-adi>/nfc-redirect.git
   cd nfc-redirect
   ```
2. Android Studio'da **File > Open** menüsünden `android/` klasörünü seçin.
3. Gradle senkronizasyonu tamamlandıktan sonra `app/src/main/assets/www/index.html` dosyasının web sürümüyle güncel olduğundan emin olun. Web arayüzünü güncellediğinizde bu dosyayı kök dizindeki `index.html` ile senkronize edin.
4. **Build > Build Bundle(s) / APK(s) > Build APK(s)** seçeneğini çalıştırın.
5. Android Studio derleme tamamlandığında sağ alt köşede üretilen APK'yı (`app-release.apk` veya `app-debug.apk`) açabileceğiniz bir bildirim gösterir. Dosya `android/app/build/outputs/apk/` dizininde yer alır.
6. APK'yı cihazınıza kopyalayıp yükleyin. İlk yüklemede dışarıdan APK yüklemeye izin vermeniz gerekebilir.

### Paket adı ve sürüm

- Paket adı: `com.example.zikirmatik`
- Sürüm numarası: 1.0 (versionCode 1)

Google Play Store'a yüklemeden önce paket adını kendi alan adınıza göre güncellemeniz, ikonları ve sürüm numaralarını üretim gereksinimlerinize göre ayarlamanız tavsiye edilir.

### Notlar

- WebView'de ses oynatımı kullanıcı etkileşimi gerektirir; sayaç butonuna dokunduğunuzda ses çıkar.
- Titreşim desteği fiziksel cihazlarda çalışır; emülatörlerde desteklenmeyebilir.
- Uygulama `localStorage` kullandığı için aynı cihazda kayıtlar korunur, fakat Android uygulaması ile web sürümü arasında veri paylaşımı yoktur.
