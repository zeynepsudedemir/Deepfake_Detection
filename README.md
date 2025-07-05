
# 🎙️ Deepfake Ses Tespiti Projesi

Bu proje, bir ses kaydının **gerçek mi yoksa deepfake mi** olduğunu tespit etmeye yönelik bir derin öğrenme modelini içerir. Projede CNN + LSTM mimarisi kullanılarak ses sinyallerinden anlamlı örüntüler çıkarılır ve sınıflandırma yapılır.

##  Projenin Amacı

Günümüzde deepfake teknolojileri ses üzerinde de kullanılmakta ve insanları yanıltabilecek derecede gerçekçi sahte sesler üretilebilmektedir. Bu proje, bu tür sahte sesleri tespit edebilen bir yapay zeka modeli geliştirmeyi amaçlar.

##  Kullanılan Teknolojiler

- **Python**
- **NumPy, Librosa, Pandas**
- **TensorFlow / Keras**
- **CNN (Conv1D) + LSTM mimarisi**
- **Matplotlib, Seaborn** (veri görselleştirme için)
- **Jupyter Notebook / VS Code**

##  Veri Seti

- **Deepfake Voice Detection Dataset**
- Gerçek ve sahte ses örneklerinden oluşmaktadır
- Ses dosyaları `.wav` formatındadır
- Sesler MFCC (Mel-Frequency Cepstral Coefficients) öz nitelikleri ile temsil edilir

##  Model Mimarisi

Model, şu katmanlardan oluşur:

- Conv1D → MaxPooling → Dropout
- LSTM
- Dense (fully connected) katmanlar
- Çıkış katmanı: Binary sınıflandırma (`real` vs `fake`)

## Başarı Durumu
Eğitim Doğruluğu: %99

Test Doğruluğu: %98

AUC, Precision, Recall gibi metrikler de hesaplandı.

## 📊 Model Performansı

Modelin test verisi üzerindeki sonuçları aşağıdaki gibidir:

### 🔹 Karışıklık Matrisi (Confusion Matrix)


|                 | Tahmin: Gerçek (0) | Tahmin: Sahte (1) |
|-----------------|--------------------|--------------------|
| **Gerçek (0)**  | 1780 (True Negative) | 14 (False Positive) |
| **Sahte (1)**   | 9 (False Negative)    | 1731 (True Positive) |

---

### 🔹 Sınıflandırma Raporu

| Sınıf            | Precision | Recall | F1-Score | Support |
|------------------|-----------|--------|----------|---------|
| 0 – Gerçek Ses   | 0.99      | 0.99   | 0.99     | 1794    |
| 1 – Sahte Ses    | 0.99      | 0.99   | 0.99     | 1740    |
| **Accuracy**     | —         | —      | **0.99** | 3534    |
| **Macro Avg.**   | 0.99      | 0.99   | 0.99     | 3534    |
| **Weighted Avg.**| 0.99      | 0.99   | 0.99     | 3534    |

---

### 📈 Yorum

Model, hem gerçek hem de sahte sesleri **%99 doğruluk** ile başarıyla sınıflandırmaktadır.

- **Precision, Recall ve F1-Score** değerlerinin tümü 0.99, bu da modelin dengeli ve yüksek performanslı olduğunu gösterir.
- Karışıklık matrisine göre **yalnızca 14 yanlış pozitif** ve **9 yanlış negatif** örnek bulunmaktadır.
- Bu sonuçlar, modelin hem sahte sesleri tespit etmede **duyarlı** hem de **yanlış alarmları düşük** tuttuğunu göstermektedir.

