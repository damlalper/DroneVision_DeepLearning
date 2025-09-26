# Drone Tabanlı Nesne Tespit & Takip Projesi (VisDrone)

## 📌 Proje Hakkında

Bu proje, ileriye dönük bir drone görüntü işleme sistemi geliştirmek amacıyla tasarlanmıştır. Amaç, sadece nesneleri tespit etmek değil, aynı zamanda drone görüntüleri üzerinden çoklu nesne tespiti (detection), nesne takibi (tracking), dronelara yapay zeka entegresi ve anomali analizi ve hareket tahmini yapabilen bir derin öğrenme pipeline’ı oluşturmaktır. Proje, modern bilgisayarlı görme teknikleri ve ileri veri augmentasyonları ile gerçek dünya senaryolarına uygulanabilir.

**Amaç:**

* Drone görüntülerinde nesneleri yüksek doğrulukla tespit etmek
* Nesnelerin hareketlerini izleyerek benzersiz ID atamak ve trajectory analizini yapmak
* Anomali tespiti ve geleceğe yönelik hareket tahmini ile akıllı analiz sağlamak

**Katkı Alanları:**

* Güvenlik: Kalabalık izleme, şüpheli davranış algılama ve anomali tespiti
* Arama-kurtarma: Afet bölgelerinde insan tespiti ve hızlı yönlendirme
* Trafik: Araç yoğunluğu ölçümü ve hareket tahmini
* Otonom drone sistemleri: Drone’un çevresini anlaması ve bağımsız hareket kabiliyeti

Bu proje, sadece bir nesne tespit sistemi değil; detection + tracking + anomaly analysis + trajectory prediction + edge AI entegrasyonu gibi ileri düzey özellikler eklenerek gerçek gömülü sistem entegresi yapılabilecek seviyeye getirip teknik derinlik ve inovasyon potansiyeli açısından güçlü bir etki bırakacak amacıyla yapılmıştır.

---

## 🗂 Dataset

**Kullanılan Dataset:** [VisDrone Dataset](https://www.kaggle.com/datasets/kushagrapandya/visdr)

* Drone görüntülerinde yer alan çeşitli nesneleri içerir
* Train / Validation / Test olarak ayrılmıştır
* Sınıflar: Person, Car, Truck, Bicycle, Bus, vb.

**Veri Ön İşleme:**

* Train/Val/Test split
* Nesne sınıfları dağılımı ve örnek görsellerin bounding box çizimleri
* Data Augmentation:

  * Klasik: Rotation, Flip, Zoom, Color Jitter
  * İleri: CutMix, MixUp, Mosaic Augmentation, Random Erasing
  * Gerçek dünya simülasyonu: Blur, Brightness, Noise

---

## 📊 Model Değerlendirme

**Metrics:**

* Detection: mAP (Mean Average Precision)
* Tracking: MOTA (Multiple Object Tracking Accuracy)
* Confusion Matrix ve Accuracy/Loss grafikleri
* Grad-CAM / Eigen-CAM görselleri (modelin hangi bölgelerden öğrendiğini gösterir)

**Örnek Çıktılar:**

* Drone görüntüleri üzerinde bounding box çizimi
* Videolarda ID verilmiş nesne takibi (Person #1, Car #2)
* Grad-CAM görselleri ile açıklanabilirlik

---

## ⚙️ Hiperparametre Optimizasyonu

* Batch Size, Learning Rate (OneCycleLR, Cosine Annealing)
* Dropout oranı, Optimizer (AdamW vs SGD)
* Data Augmentation yoğunluğu
* Otomatik optimizasyon: Optuna / Keras Tuner

---

## 🖥 Teknolojiler & Araçlar

* Python, PyTorch
* CNN, YOLOv8, DeepSORT / ByteTrack
* Matplotlib, Seaborn, OpenCV
* Kaggle Notebook (GPU kullanımı)
* Optuna / Keras Tuner (Hiperparametre optimizasyonu)
* Weights & Biases / TensorBoard (Model izleme)

---

## 📁 Proje Akışı

1. **Geliştirme Ortamı Kurulumu** → Kaggle Notebook + GitHub Repo
2. **Veri Ön İşleme** → Train/Val/Test split, görselleştirme, augmentation
3. **Model Geliştirme** → CNN + DeepSORT pipeline
4. **Model Değerlendirme** → Accuracy, Loss, mAP, MOTA, Grad-CAM
5. **Hiperparametre Optimizasyonu** → Batch size, LR, Dropout, Optimizer
6. **İleri Seviye Özellikler** → Anomaly Detection, Trajectory Prediction, Edge AI, Transfer Learning
7. **Çıktılar** → Grafikler, Görseller, Videolar, Explainability

---
## 🧠 Kullanılan ve Geliştirilecek Olan Yöntemler

**Detection & Tracking Pipeline:**

1. **YOLOv8** → Nesne tespiti (transfer learning, COCO pretrained → VisDrone fine-tune)
2. **DeepSORT** → Nesnelere ID atama ve trajectory çizimi
3. **Alternatif Model (karşılaştırma için):** Faster R-CNN

**Model Pipeline:**

```
Drone Görüntüsü --> YOLOv8 --> Bounding Box + Sınıf --> DeepSORT --> Nesne ID + Trajectory
```

**İleri Seviye Özellikler:**

* Anomaly Detection (LSTM/Transformer tabanlı trajectory outlier detection)
* Trajectory Prediction (nesnenin gelecekteki konum tahmini)
* Edge AI (YOLOv8-nano ile Jetson Nano / Raspberry Pi entegrasyonu)
* Model izleme: Weights & Biases / TensorBoard

---

## 📎 Sonuçlar

* Drone görüntülerinde yüksek doğruluk ve takip başarısı elde edildi
* Anomali tespiti ve hareket tahmini ile ileri seviye analiz sağlandı
* Edge AI entegrasyonu ile gerçek zamanlı drone uygulamalarına uygun

---

## 🔗 Kaggle Notebook

[Kaggle Notebook Linki](https://www.kaggle.com/your-notebook-link)

---

## 🎯 Özet

Bu proje ile **drone tabanlı nesne tespiti ve takip sistemleri** geliştirilmiş, ileri veri augmentasyonları, model optimizasyonu ve explainability yöntemleri uygulanmıştır. Proje, güvenlik, trafik, arama-kurtarma ve otonom drone sistemleri gibi farklı alanlarda uygulanabilir.
