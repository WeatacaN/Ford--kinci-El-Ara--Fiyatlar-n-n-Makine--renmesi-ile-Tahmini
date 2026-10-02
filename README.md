# Ford İkinci El Araç Fiyat Tahmini 🚗💰

Bu proje, makine öğrenmesi algoritmaları kullanılarak İngiltere ikinci el araç piyasasındaki Ford marka araçların özelliklerine (yıl, kilometre, motor hacmi, vites tipi vb.) göre adil pazar değerini tahmin etmeyi amaçlamaktadır. 

## 📌 Kullanılan Teknolojiler
* **Python:** Veri manipülasyonu ve modelleme
* **Pandas & NumPy:** Veri analizi ve ön işleme
* **Scikit-Learn:** Makine öğrenmesi algoritmaları (Linear Regression, Random Forest)
* **Matplotlib & Seaborn:** Veri görselleştirme (EDA)

## 📊 Veri Seti
Çalışmada kullanılan veri seti, Kaggle'daki açık kaynaklı "100,000 UK Used Dataset" üzerinden alınmış olup 17.965 adet Ford marka araç ilanını içermektedir.

## 🚀 Proje Adımları
1. **Keşifçi Veri Analizi (EDA):** Fiyat dağılımı, vites tipine göre fiyat farklılıkları ve kilometre/fiyat korelasyonu (yıl: +0.64, kilometre: -0.53) incelenmiştir.
2. **Veri Ön İşleme:** Kategorik değişkenler (vites tipi, yakıt türü) One-Hot Encoding ile sayısallaştırılmış ve eğitim verilerindeki sayısal özellikler StandardScaler ile ölçeklendirilmiştir.
3. **Modelleme & Karşılaştırma:** Doğrusal Regresyon (Linear Regression) temel (baseline) model olarak kurulmuş, ardından karmaşık ve doğrusal olmayan ilişkileri daha iyi öğrenen Rastgele Orman (Random Forest Regressor) algoritması ile kıyaslanmıştır.

## 📈 Model Performansı
* **Linear Regression MAE:** £1.368,83
* **Random Forest MAE:** £860,47
* **R² Skoru (Random Forest):** 0.930

Random Forest modeli, değişkenler arasındaki doğrusal olmayan ilişkileri daha iyi yakalayarak hata oranını ortalama %37 oranında düşürmüştür. Modelin özellik önemi (feature importance) analizine göre bir Ford aracın fiyatını belirleyen en önemli 3 değişken sırasıyla: **Üretim Yılı (~%48)**, **Motor Hacmi (~%25)** ve **Kilometre (~%7)** olarak saptanmıştır. Hata analizi sonucunda, modelin en çok nadir bulunan ve yüksek fiyatlı (uç değer) lüks/spor segment araçları tahmin etmede zorlandığı görülmüştür.
