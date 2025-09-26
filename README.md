# 🚁 Drone Tabanlı Nesne Tespit Projesi (VisDrone)

## 📌 Proje Hakkında

Bu proje, **VisDrone veri seti** üzerinde derin öğrenme tabanlı nesne tespiti için geliştirilmiştir.  
Amaç, drone görüntülerinde nesneleri yüksek doğrulukla sınıflandırmak ve ileriye dönük **takip, anomaly detection ve trajectory prediction** gibi gelişmiş özelliklere temel oluşturmaktır.  

**Amaç:**
- Drone görüntülerinde nesneleri yüksek doğrulukla sınıflandırmak  
- Modelin odaklandığı bölgeleri analiz ederek açıklanabilirlik sağlamak  
- İleri adımda nesne takibi ve hareket tahmini sistemine temel oluşturmak  

**Katkı Alanları:**
- Güvenlik: Kalabalık izleme, şüpheli davranış tespiti  
- Arama-kurtarma: Afet bölgelerinde insan/araç tespiti  
- Trafik: Araç yoğunluğu ölçümü ve hareket tahmini  
- Otonom sistemler: Drone’un çevresini anlaması  

---

## 🗂 Dataset

**Kullanılan Dataset:** [VisDrone Dataset](https://www.kaggle.com/datasets/kushagrapandya/visdrone-dataset)

- Çeşitli nesneler içerir: pedestrian, people, bicycle, car, truck, bus, motor vb.  
- Train / Validation / Test olarak ayrılmıştır  

**Veri Ön İşleme:**
- Train/Val/Test split  
- Nesne sınıfları dağılımı ve örnek görsellerin bounding box çizimleri  
- Bozuk veri kontrolü (hata bulunmadı)  

**Data Augmentation (Albumentations):**
- Klasik: Rotation, Horizontal Flip  
- İleri: Color Jitter, Gaussian Blur, Cutout  
- Gerçek dünya simülasyonu: Noise, Brightness  

---

## 🧠 Model Geliştirme

### 1️⃣ Custom CNN  
- 9 katmanlı CNN + BatchNorm + Dropout  
- Eğitim/Validation split  
- **Sonuç:** ~%40.6 validation accuracy  

### 2️⃣ Transfer Learning  
- **ResNet50 (ImageNet pretrained)**  
- Son katman değiştirilerek VisDrone’a uyumlu hale getirildi  
- Eğitim sadece son katmanda yapıldı (feature extraction)  
- **Sonuç:** %45.2 validation accuracy  

---

## 📊 Model Değerlendirme

**Metrics:**
- Classification Report  
- Confusion Matrix  
- Accuracy/Loss grafikleri  
- Grad-CAM görselleri  

**Örnek Çıktılar:**
- Görseller üzerinde bounding box + sınıf tespiti  
- Grad-CAM görselleri → modelin odaklandığı bölgelerin görselleştirilmesi  

---

## ⚙️ Hiperparametre Optimizasyonu

- Adam, RMSprop, SGD karşılaştırması  
- Dropout oranı ve learning rate denemeleri  
- **En iyi sonuç:** ResNet50 + SGD → %45.2 val acc  

---

## 🖥 Teknolojiler & Araçlar

- Python, PyTorch  
- Albumentations, TorchCAM  
- OpenCV, Matplotlib, Seaborn  
- Sklearn (classification report, confusion matrix)  
- Kaggle Notebook (GPU ortamı)  

---

## 📁 Proje Akışı

1. **Dataset Analizi** → Sınıf dağılımı, görsellerin incelenmesi  
2. **Data Augmentation** → Albumentations ile çeşitlendirme  
3. **Custom CNN** → Sıfırdan model eğitimi  
4. **Transfer Learning** → ResNet50 ile feature extraction  
5. **Model Değerlendirme** → Accuracy, Loss, Confusion Matrix, Grad-CAM  
6. **HPO** → Optimizer ve dropout denemeleri  
7. **İleri Geliştirmeler** → YOLOv8, DeepSORT, Anomaly Detection, Edge AI  

---

## 🚀 Geliştirilecek Özellikler

- **YOLOv8 / Faster R-CNN** → Nesne tespiti  
- **DeepSORT / ByteTrack** → Nesne takibi ve ID atama  
- **Anomaly Detection** (LSTM/Transformer tabanlı)  
- **Trajectory Prediction** (gelecekteki konum tahmini)  
- **Edge AI entegrasyonu** (Jetson Nano / Raspberry Pi üzerinde gerçek zamanlı inference)  
- **Model Monitoring** (TensorBoard / Weights & Biases)  

---

## 📎 Sonuçlar

- Custom CNN ve ResNet50 ile temel başarı elde edildi  
- ResNet50 modeli daha dengeli ve yüksek doğruluk sağladı  
- Proje, **gerçek zamanlı drone tabanlı nesne tespiti ve ileri takip sistemleri** için sağlam bir temel oluşturdu  

---

## 🔗 Kaggle Notebook

👉 [Kaggle Notebook Linki](https://www.kaggle.com/code/damlaalper/deeplearningbootcamp)  

---
