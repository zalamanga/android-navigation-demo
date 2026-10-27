# Android Navigation Demo

Latihan Java Android untuk berpindah di antara tiga fragment melalui bottom navigation. Source utama berasal dari NavApp4 lokal. Beranda, Dashboard, dan Notifikasi menampilkan teks latihan; repo ini belum mempunyai data produk, login, atau backend.

## Build dan jalankan

Gunakan JDK 17, Android SDK Platform 35, dan Android Studio yang mendukung AGP 8.8.2. Wrapper proyek memakai Gradle 8.10.2, minimum Android 7.0/API 24, dan target API 34. Lokasi SDK diatur di Android Studio atau `ANDROID_HOME`; `local.properties` milik mesin tidak disertakan.

```powershell
.\gradlew.bat :app:assembleDebug :app:lintDebug
adb install -r app\build\outputs\apk\debug\app-debug.apk
```

Buka aplikasi NavApp4 pada emulator atau perangkat, lalu pilih ketiga tab. Gradle dapat mengunduh dependency saat build pertama. SDK persiapan tersedia di `D:\DevTools\Android\Sdk`; gunakan `ANDROID_HOME` sesuai lokasi SDK milikmu. Cache Gradle dapat ditempatkan di drive D melalui `GRADLE_USER_HOME`.

## Alur source

| Berkas | Fungsi |
| --- | --- |
| `app/src/main/java/com/r/example/navapp4/MenuActivity.java` | Launcher, ViewBinding, dan penghubung bottom navigation |
| `app/src/main/java/com/r/example/navapp4/ui/` | Fragment dan ViewModel teks untuk setiap tab |
| `app/src/main/res/navigation/mobile_navigation.xml` | Tiga tujuan navigasi |
| `app/src/main/res/menu/bottom_nav_menu.xml` | Item tab dan ikon |
| `app/src/main/res/layout/activity_menu.xml` | Susunan navigasi dan host fragment |

Identitas warna, layout, ikon, dan applicationId `com.r.example.navapp4` dipertahankan. Activity Hello World yang tidak dipakai dan test contoh 2+2 tidak ikut ekspor ini. Versi drawer NavApp1 dan varian navapp2 tetap disimpan di folder sumber masing-masing.

## Status pemeriksaan

Pemeriksaan pada 27 Oktober 2026 berhasil menjalankan `assembleDebug`, `testDebugUnitTest`, dan `lintDebug` dengan JDK 17 serta SDK 35. APK debug terbentuk dan lint tidak menemukan error. Task unit test berstatus `NO-SOURCE` karena belum ada unit test khusus untuk demo ini. Rincian ada di [hasil pemeriksaan](BUILD-VERIFICATION.md).

UI belum dijalankan pada emulator atau perangkat, sehingga belum ada screenshot runtime lokal. Aplikasi ini dimaksudkan sebagai latihan Navigation Component.

Asal source dan catatan lisensi ada di [NOTICE.md](NOTICE.md).
