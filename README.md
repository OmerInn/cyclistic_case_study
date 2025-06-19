# cyclistic_case_study
# 🚲 Cyclistic Case Study: 5-Step Data Analysis

## 🧭 1. Ask – İş Problemi
- **Soru:** Casual kullanıcılar ile yıllık üyeler Cyclistic bisikletlerini nasıl farklı kullanıyor?
- **Hedef:** Bu farklardan yola çıkarak casual kullanıcıları üyeliğe dönüştürecek stratejiler belirlemek.

## 📦 2. Prepare – Veri Kaynağı
- **Kaynak:** Divvy 2019 Q1 & Divvy 2020 Q1 CSV dosyaları.
- **İlk işlemler:** Google Sheets üzerinde `ride_length` ve `day_of_week` sütunları eklendi.
- [Detaylar](./prepare/data_notes.md)

## 🧹 3. Process – Temizleme & Hazırlık
- R'de `lubridate`, `dplyr` paketleri ile veri temizlendi.
- `ride_length` saniyeye çevrildi, outlier'lar filtrelendi.
- [R kodları](./process/r/cleaning.R)

## 📊 4. Analyze – Analiz ve Görselleştirme
- Ortalama sürüş süresi ve sürüş sayısı `ggplot2` ile görselleştirildi.
- Casual kullanıcılar hafta sonu daha aktif. Üyeler işe gidip geliyor gibi görünüyor.
- [Görseller](./analyze/r/plots/)

## 📢 5. Share – Raporlama & Öneriler
- [Tam rapor PDF](./share/report/cyclistic_report.pdf)
- **3 Öneri:**
  1. Hafta sonu kampanyaları ile casual kullanıcıları hedefle
  2. İş saati içi teşviklerle üyeleri koru
  3. Mobil uygulamada özel bildirimler gönder
