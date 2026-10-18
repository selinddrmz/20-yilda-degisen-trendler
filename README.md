# 20 Yılda Değişen Trendler — Scrollytelling

Bu proje, Kullanıcı Arayüzü Tasarımı dersi için Google Trends Dataset (2001–2020) üzerine hazırlanmış tek sayfalık, duyarlı bir veri hikâyesidir. Tasarım, sağlanan “20 Yılda Değişen Trendler” konsept PDF'sindeki koyu zemin ve pembe/turkuaz/lime renk paletinden esinlenir.

## Klasörler

- `site/`: HTML, CSS, JavaScript, görseller ve web sitesinin kullandığı JSON.
- `site/data/site_data.json`: temizlenmiş CSV'den üretilen özetler ve filtreleme için kayıtlar.
- `site/assets/charts/`: notebook'un sekiz gerçek grafik çıktısı; storyboard PDF'sinde referans olarak kullanılır.
- `data/raw/trends.csv`: kullanıcının sağladığı kaynak CSV kopyası.
- `data/processed/site_data.json`: web sitesinde kullanılan veri dosyasının kopyası.
- `notebooks/google_trends_analizi.ipynb`: kullanıcının sağladığı Jupyter analiz notebook'u.
- `notebooks/trends.csv`: notebook'un göreli dosya yolu ile sorunsuz çalışması için CSV kopyası.
- `docs/storyboard.pdf`: site akışının storyboard özeti.
- `docs/20 Yılda Değişen Trendler - Tasarım Referansı.pdf`: sağlanan tasarım referansı.

## Yerelde çalıştırma

JSON dosyasının `fetch()` ile yüklenebilmesi için siteyi doğrudan `file://` üzerinden açmayın. Python kuruluysa terminalde proje klasöründen:

```bash
python -m http.server 8000 --directory site
```

Sonra `http://localhost:8000` adresini açın. Alternatif olarak VS Code Live Server kullanılabilir; kök klasör olarak `site/` seçilmelidir.

## Yayınlama

`site/` klasörünün içeriğini GitHub Pages, Netlify veya Vercel üzerinde statik site olarak yayınlayabilirsiniz. Yayın sonrası canlı URL'yi README'ye ekleyin. LinkedIn `og:image` önizlemesi için `site/assets/og-image.svg` kullanılır; ödev yönergesi PNG 1200×627 istediği için teslimden önce bu SVG'yi 1200×627 PNG olarak dışa aktarıp `og:image` adresini güncelleyin.

## Veri kaynağı ve lisans

Google Trends Dataset (2001–2020), Dhruvil Dave, Kaggle: https://www.kaggle.com/dsv/1936665. Analiz notebook'unda lisans ODC Attribution (ODC-By) olarak belirtilmiştir. Yeniden dağıtım ve atıf koşullarını yayın öncesinde kaynak sayfasından doğrulayın.

## Veri yorumu

Bu veri seti toplam Google arama hacmini değil, trend kayıtlarını, konumu, yılı, kategoriyi, sıralamayı ve arama terimini içerir. Kayıt sayısı artışları doğrudan insanların daha çok arama yaptığı anlamına gelmez. Yıllar/ülkeler arasındaki kapsam farklılıkları yorumlanmalıdır. Tamamen yinelenen 10 satır, notebook'taki kararla uyumlu biçimde kaldırılmıştır.

## Yapay zekâ kullanım beyanı

Web arayüzünün iskeleti, CSS ve JavaScript etkileşimleri ChatGPT desteğiyle hazırlanmıştır. Öğrenci, veri analizini, yorumları ve kodu teslim etmeden önce kontrol etmeli; çalışmayı kendi sözleriyle açıklayabilmelidir.

## Kontrol edilmesi gerekenler teslimden önce

- `notebooks/` içindeki notebook'u açın; aynı klasördeki `trends.csv` ile Restart & Run All yapın. Notebook’un son hücresi JSON’u `notebooks/site_data.json`, `data/processed/site_data.json` ve `site/data/site_data.json` konumlarının üçüne birden yazar; site verisi analiz yeniden çalıştırıldığında senkron kalır.
- Lighthouse mobil Performans ve Erişilebilirlik raporlarını üretip ekran görüntülerini ekleyin.
- Siteyi 360 px, 768 px ve 1280 px genişliklerde kontrol edin.
- Gerçek canlı site bağlantısını, LinkedIn paylaşım metnini ve portfolyo kartını ekleyin.
- Kaynak lisansını ve erişim tarihini doğrulayın.


## Teslim belgeleri
- Görsel storyboard: `docs/storyboard.pdf`
- Tasarım kararları: `docs/tasarim_kararlari.pdf`
- LinkedIn taslak metni: `linkedin_paylasim_metni.txt`
- Bağlantı ve teslim kontrolü: `teslim.txt`
- Paylaşım görseli: `site/assets/og-image.png`

## Teslim durumu
Canlı yayın, herkese açık GitHub bağlantısı ve gerçek Lighthouse raporları bu pakette hazır/kanıtlanmış değildir; yayın ve tarayıcı testlerinden sonra tamamlanmalıdır. LinkedIn taslağındaki yer tutucular gerçek bağlantılarla değiştirilmelidir.


## Güncel düzeltmeler
- Storytelling akışı, notebook'taki sekiz grafik analizinin tamamını kapsar.
- Web grafikleri notebook ile aynı temizlenmiş veriden üretilir; son hücre JSON'u hem `data/processed/` hem `site/data/` klasörüne yazar.
- Japonca kategori adları CJK destekli yazı tipiyle çizilir; kaynak değerler değiştirilmez.
- Ülke-kategori grafikleri birbirinin alternatifi olarak açıklanır.
- Yorumlarda kayıt sayısı ile toplam arama hacmi birbirinden açıkça ayrılır.
- `docs/storyboard.pdf` sekiz grafik için güncel storyboard'dur.