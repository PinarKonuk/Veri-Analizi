# Veri-Analizi
# ✈️ Airline Passenger Satisfaction Analysis

Bu proje, bir havayolu şirketine ait yolcu memnuniyet verilerini kullanarak memnuniyet düzeyini etkileyen faktörleri incelemeyi amaçlamaktadır. Python kullanılarak yapılan bu analiz, temel istatistiksel özetler, eksik değer incelemesi, aykırı değer tespiti, görselleştirme ve değişkenler arası ilişki analizlerini içermektedir.

---

## 📌 Proje Amacı

Havayolu hizmetleri kapsamında toplanmış olan yolcu verilerini analiz ederek:
- Yolcu memnuniyetini etkileyen faktörleri ortaya çıkarmak
- Eksik verileri uygun şekilde ele almak
- Aykırı değerleri belirlemek
- Görsel analizlerle öngörüleri desteklemek

---

## 📁 Kullanılan Veri Seti

Veri seti: **Airline Passenger Satisfaction**  
- Toplam satır sayısı: 103,904  
- Sütun sayısı: 25  
- Hedef değişken: `satisfaction` (categorical: *satisfied* / *neutral or dissatisfied*)  
- Sayısal ve kategorik değişkenler birlikte yer almaktadır.

  ![Veri Yapısı](images/airline_data.png)

---

## 🔍 Ana Analiz Adımları

### 1. Veri Setinin Tanıtımı ve Ön İşleme
- `Unnamed: 0` sütunu veri dışı bırakıldı
- `satisfaction` sütunu `satisfaction_encoded` olarak sayısal forma dönüştürüldü (0/1)

### 2. İstatistiksel Özetler
- Ortalama, medyan, standart sapma gibi özetler hesaplandı
- Simetrik/çarpık dağılım yapıları değerlendirildi

![İstatistiksel Özet](images/istatistik.png)

### 3. Eksik Değer Analizi
- `Arrival Delay in Minutes` değişkeninde %0.3 oranında eksik veri bulundu
- **Medyan ile doldurma** stratejisi tercih edildi (dağılım çarpık olduğu için)
📊 **Eksik Veri Görselleştirmesi:**

![Eksik Veri Görselleştirme](images/missing_values.png)

### 4. Aykırı Değer (Outlier) Analizi
- IQR yöntemi ile aykırı değerler belirlendi
- Boxplot grafikleri ile sayısal değişkenlerdeki uç değerler görselleştirildi

  ![Outlier Analizi](images/outlier.png)
  
📊 **Boxplot – Sayısal Değişkenler:**

![Boxplot - Tüm Sayısal Değişkenler](images/boxplot_all.png)

### 5. Görselleştirme
- Sayısal değişkenler için histogram ve KDE grafikleri
- Kategorik değişkenler için çubuk grafikleri
- `satisfaction` ile yaş, uçuş mesafesi, hizmet puanları arasındaki ilişkiler (boxplot / violinplot / countplot)
📊 **Memnuniyet – Yaş İlişkisi:**

![Age vs Satisfaction](images/age_vs_satisfaction.png)

📊 **Memnuniyet – Uçuş Mesafesi (Violinplot):**

![Flight Distance vs Satisfaction](images/flight_distance_vs_satisfaction.png)

📊 **Seyahat Tipi ve Memnuniyet:**

![Type of Travel vs Satisfaction](images/type_of_travel_vs_satisfaction.png)

📊 **Uçuş Sınıfı ve Memnuniyet:**

![Class vs Satisfaction](images/class_vs_satisfaction.png)


### 6. Korelasyon Analizi
- Sayısal değişkenler arasında korelasyon matrisi çizildi
- `satisfaction_encoded` ile olan ilişkiler incelendi
📊 **Korelasyon Matrisi:**

![Correlation Heatmap](images/correlation_matrix.png)
---

## 📷 Örnek Görseller

- Sayısal ve kategorik dağılımlar
- Memnuniyet durumuna göre hizmet kalitesi karşılaştırmaları
- Eksik değer dağılımı bar chart
- Korelasyon matrisi heatmap

---

## 🛠️ Kullanılan Kütüphaneler
- pandas
- numpy
- matplotlib
- seaborn

---

## 📁 Çalışma Dosyası

Proje Jupyter Notebook dosyası:  
📄 `Proje.ipynb`

---

## ✍️ Not

Bu analiz, istatistiksel çıkarım ve veri ön işleme sürecine odaklanmaktadır. Modelleme (makine öğrenmesi) adımı bilinçli olarak kapsam dışında bırakılmıştır.
