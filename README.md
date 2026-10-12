# Kütüphane Yönetim Sistemi — 2 Haftalık C++ Çalışması

Bu projede geçen yıl gördüğün C++ ve nesneye yönelik programlama konularını tekrar ederken, çalışan bir konsol uygulaması geliştireceğiz. Her oturum sonunda küçük bir Git commit'i oluşturacağız.

## Proje fikri

Kütüphanedeki kitapları ve üyeleri yönetebilen; kitap ödünç verme, iade alma ve mevcut durumu listeleme işlemlerini yapan bir uygulama. Son aşamada verileri dosyada saklayıp temel testler ekleyeceğiz.

## 14 günlük yol haritası

1. **Kurulum ve tekrar:** C++ programının yapısı, derleme/çalıştırma, Git deposu ve ilk commit.
2. **Fonksiyonlar ve veri:** Fonksiyonlar, `std::string`, `std::vector`; kitap kayıtlarını listeleme.
3. **Sınıf ve nesne:** `Book` sınıfı, alanlar, kurucu ve metotlar.
4. **Kapsülleme:** Erişim belirleyicileri, doğrulama, getter/setter kararı.
5. **Üyeler:** `Member` sınıfı ve üye kayıtları.
6. **İlişkiler:** Üye ve kitapları birlikte yönetme; ödünç alma kuralı.
7. **İş mantığı:** Ödünç verme ve iade senaryoları; hata durumları.
8. **Ara değerlendirme:** Kod düzenleme, küçük hata düzeltmeleri ve Git geçmişini inceleme.
9. **Kalıtım ve polimorfizm:** Uygunsa farklı materyal türleri; neden gerektiğini tartışma.
10. **Dosyalara ayırma:** Başlık ve kaynak dosyaları (`.h` / `.cpp`), include düzeni.
11. **Kalıcı kayıt:** Kitap ve üye verilerini dosyaya yazma/okuma.
12. **Hata yönetimi ve test:** Geçersiz girdi ve temel otomatik testler.
13. **GitHub:** Repo oluşturma, remote ekleme, push ve README'yi iyileştirme.
14. **Son tur:** Özellikleri gözden geçirme, temiz commit/push ve öğrendiklerini özetleme.

Her gün yaklaşık 60–90 dakika hedefleyelim. Bir oturum kaçarsa takvimi sıkıştırmak yerine kaldığımız yerden devam ederiz.

## Gün 1 — Başlangıç

### Hedefler

- C++ dosyasını derleyip çalıştırmak.
- `main`, `std::cout` ve basit bir fonksiyonu hatırlamak.
- Git çalışma ağacını, staging alanını ve commit'i ilk kez kullanmak.

### İlk görev

`main.cpp` içindeki `TODO` bölümünü tamamla:

1. `printWelcome` fonksiyonu kütüphane uygulamasına hoş geldin mesajı yazsın.
2. `main` bu fonksiyonu çağırsın ve ardından uygulamanın ilk sürümünün çalıştığını belirten bir satır yazdırsın.
3. Derle ve çalıştır. Örneğin MinGW g++ varsa terminalde:

   ```powershell
   g++ -std=c++17 -Wall -Wextra -pedantic main.cpp -o library_app.exe
   .\library_app.exe
   ```

   MSVC kullanıyorsan VS Code'da Developer PowerShell açıp `cl /EHsc /std:c++17 main.cpp` kullanabilirsin.

### Git alıştırması

Değişiklikten sonra terminalde sırayla çalıştır ve her komutun ne yaptığını gözlemle:

```powershell
git status
git add README.md main.cpp .gitignore
git status
git commit -m "chore: start library manager project"
git log --oneline
```

`git add` commit'e dahil edilecek dosyaları seçer; `git commit` seçilen hâli kaydeder. GitHub'a henüz bağlamıyoruz; önce yerel akışı öğreniyoruz.

## Geliştirme ilkeleri

- Her oturumda önce sen dene; takıldığın yerde birlikte küçük adımlarla ilerleyelim.
- Bir commit tek ve anlaşılır bir değişikliği anlatsın.
- Yeni kavramı projede kullanmadan önce kısa örnekle hatırlayalım.
- Projeyi büyütürken çalışan hâli koruyalım.
