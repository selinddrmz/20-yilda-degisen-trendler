# 20 Yılda Değişen Trendler — Scrollytelling

Bu proje, Kullanıcı Arayüzü Tasarımı dersi için Google Trends Dataset (2001–2020) üzerine hazırlanmış tek sayfalık, duyarlı bir veri hikâyesidir. Tasarım, “20 Yılda Değişen Trendler” konseptindeki koyu zemin ve pembe/turkuaz/lime renk paletinden esinlenir.

## Canlı site ve kaynak kodları

- **Canlı site:** https://20-yilda-degisen-trendler.vercel.app/
- **GitHub deposu:** Bu README'nin bulunduğu herkese açık depo bağlantısını kullanın.
- **Yayın platformu:** Vercel

## Klasörler

- `site/`: HTML, CSS, JavaScript, görseller ve web sitesinin kullandığı JSON.
- `site/data/site_data.json`: temizlenmiş CSV'den üretilen özetler ve filtreleme için kayıtlar.
- `site/assets/charts/`: notebook'un sekiz grafik çıktısı.
- `data/raw/trends.csv`: kaynak CSV kopyası.
- `data/processed/site_data.json`: web sitesinde kullanılan veri dosyasının kopyası.
- `notebooks/google_trends_analizi.ipynb`: Jupyter analiz notebook'u.
- `notebooks/trends.csv`: notebook'un göreli dosya yolu ile çalışması için CSV kopyası.
- `docs/storyboard.pdf`: site akışının storyboard özeti.
- `docs/20 Yılda Değişen Trendler - Tasarım Referansı.pdf`: tasarım referansı.

## Yerelde çalıştırma

JSON dosyasının `fetch()` ile yüklenebilmesi için siteyi doğrudan `file://` üzerinden açmayın. Python kuruluysa proje klasöründen şu komutu çalıştırın:

```bash
python -m http.server 8000 --directory site
```

Ardından `http://localhost:8000` adresini açın. Alternatif olarak VS Code Live Server kullanılabilir; kök klasör olarak `site/` seçilmelidir.

## Yayınlama

Site Vercel üzerinde yayımlanmıştır: https://20-yilda-degisen-trendler.vercel.app/

Canlı sitede ülke ve yıl filtreleri elle test edilmiş; seçim yapıldığında gösterilen sonuçların değiştiği gözlemlenmiştir. Kaynak dosyalarda değişiklik yapıldığında, güncellemelerin canlıya yansıması için GitHub deposuna gönderilmesi ve Vercel dağıtımının tamamlanması gerekir.

## Lighthouse kontrolü

Canlı site için alınan Lighthouse ekran görüntüsünde şu puanlar görülmektedir:

- **Performans:** 99/100
- **Erişilebilirlik:** 96/100

Puan ekran görüntüsünü `docs/lighthouse/` klasöründe saklayın. Bu puanlar alınan test çalıştırmasının sonucudur; Lighthouse sonuçları cihaz, ağ ve tarayıcı koşullarına göre değişebilir. Teslimde mobil cihaz ayarı kullanıldığını doğrulayın ve varsa ayrıntılı rapor ekran görüntülerini de ekleyin.

## Veri kaynağı ve lisans

Google Trends Dataset (2001–2020), Dhruvil Dave, Kaggle: https://www.kaggle.com/dsv/1936665

Analiz notebook'unda lisans ODC Attribution (ODC-By) olarak belirtilmiştir. Yeniden dağıtım ve atıf koşullarını kaynak sayfasından doğrulayın.

## Veri yorumu

Bu veri seti toplam Google arama hacmini değil; trend kayıtlarını, konumu, yılı, kategoriyi, sıralamayı ve arama terimini içerir. Kayıt sayısındaki artış, tek başına insanların daha fazla arama yaptığı anlamına gelmez. Yıllar ve ülkeler arasındaki kapsam farklılıkları yorumlanmalıdır. Tamamen yinelenen 10 satır, notebook'taki kararla uyumlu biçimde kaldırılmıştır.

## Yapay zekâ kullanım beyanı

Web arayüzünün iskeleti, CSS ve JavaScript etkileşimleri ChatGPT desteğiyle hazırlanmıştır. Veri analizi, yorumlar ve kod teslimden önce öğrenci tarafından kontrol edilmeli; çalışma öğrenci tarafından açıklanabilmelidir.

## Teslim öncesi son kontrol

- [ ] Notebook'u `notebooks/` klasöründe açıp `trends.csv` ile Restart & Run All yapın; hücrelerin hatasız tamamlandığını doğrulayın.
- [ ] Lighthouse testinin Mobile ayarında çalıştırıldığını doğrulayın; puan ve ayrıntı ekran görüntülerini ekleyin.
- [ ] Siteyi 360 px, 768 px ve 1280 px genişliklerde kontrol edin.
- [ ] GitHub deposunun herkese açık olduğunu doğrulayın.
- [ ] `teslim.txt` içindeki canlı site ve GitHub bağlantılarını kontrol edin.
- [ ] Ödev yönergesinde isteniyorsa LinkedIn paylaşım metni/görselini ve portfolyo bağlantısını ekleyin.
- [ ] Kaynak lisansını ve erişim tarihini doğrulayın.

## Teslim belgeleri

- Storyboard: `docs/storyboard.pdf`
- Tasarım kararları: `docs/tasarim_kararlari.pdf` (dosya adının arşivdeki gerçek adla aynı olduğunu doğrulayın)
- LinkedIn taslak metni: `linkedin_paylasim_metni.txt` (varsa)
- Bağlantı ve teslim kontrolü: `teslim.txt`
- Paylaşım görseli: `site/assets/og-image.png` (varsa)

## Güncel düzeltmeler

- Hikâye akışı, notebook'taki sekiz grafik analizini kapsayacak şekilde hazırlanmıştır.
- Web grafikleri temizlenmiş veriden üretilir; notebook'un son hücresi JSON dosyalarını günceller.
- Japonca kategori adları için CJK destekli yazı tipi kullanılır; kaynak değerler değiştirilmez.
- Ülke-kategori grafikleri birbirinin alternatifi olarak açıklanır.
- Yorumlarda kayıt sayısı ile toplam arama hacmi birbirinden ayrılır.
