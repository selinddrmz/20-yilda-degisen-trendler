# Storyboard — 20 Yılda Değişen Trendler

## Araştırma sorusu
2001–2020 döneminde Google Trends veri setindeki trend kayıtları yıllara, kategorilere ve konumlara göre nasıl dağılmıştır?

## Scrollytelling akışı

1. **Yıllara göre kayıt dağılımı** — yıllık kayıt sayıları; 2005'te 10 ve 2016'da 3.040 kayıt.
2. **En sık görülen 10 kategori** — tüm temizlenmiş veri setindeki kategori kayıt sayıları.
3. **Dört kategorinin yıllara göre dağılımı** — People, Movies, TV Shows ve Songs.
4. **Global kayıtların yıllara göre dağılımı** — yalnızca `location == Global` satırları.
5. **Tekrarlanan birincilik terimleri** — Global veride `rank == 1` olan satırlarda query tekrar sayısı.
6. **Terimlerin yıllara göre birincilik kayıtları** — American Idol, Britney Spears, Eminem, The Simpsons, Whitney Houston ve World Cup.
7. **Ülkelere göre öne çıkan kategoriler** — en fazla kaydı bulunan beş ülkenin her birindeki ilk beş kategori.
8. **Ülke–kategori kayıt sayıları** — 7. grafikteki aynı 25 ülke-kategori birleşiminin etiketli yatay çubuk görünümü.

## Görsel ve veri kararları
- Web grafikleri, Jupyter notebook'taki aynı temizlenmiş `trends.csv` verisinden üretilir.
- Japonca kategori adları kaynak metin olarak korunur. Matplotlib grafikleri CJK destekli yazı tipiyle yeniden üretilir; kaynak verideki kategori değerleri değiştirilmez.
- 7. ve 8. grafik aynı analizden türeyen iki farklı görünüm olarak açıklanır; farklı analizlermiş gibi sunulmaz.
- Kayıt sayısı toplam Google arama hacmi değildir. Yıllar arası kayıt sayısı farkı, kullanıcıların daha fazla veya daha az arama yaptığı şeklinde yorumlanmaz.
- Temizleme özeti: 26.955 ham satır, 10 tamamen yinelenen satır kaldırıldı, 26.945 temiz satır; temiz veri setinde eksik hücre yok.

## Teknik akış
`notebooks/google_trends_analizi.ipynb` → `data/processed/site_data.json` ve `site/data/site_data.json` → `site/index.html` + `site/css/styles.css` + `site/js/app.js`.

Notebook'un son hücresi JSON'u üç konuma da yazar; böylece analiz yeniden çalıştırıldığında web sitesinin kullandığı veri dosyası güncellenir.