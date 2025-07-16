

# Yüzey Aşınma Asistanı 🔧📉

Endüstriyel yüzeylerdeki **aşınma takibini** sensör verilerine ve makine öğrenmesi tabanlı modele dayalı olarak yapan bir **gerçek zamanlı izleme uygulaması**.

## 🎯 Proje Amacı

Bazı sektörlerde yüksek sıcaklık ve mesafeye bağlı olarak yüzey kalınlıklarında zamanla aşınma oluşur. Bu proje:

- **DHT11 sıcaklık sensörü** ve **HC-SR04 mesafe sensörü** kullanarak veri toplar.
- Kalınlık azalmasını tahmin etmek için **lineer bir model** kullanır.
- Kritik seviyeye ulaşmadan kullanıcıyı uyarır.
- Tüm verileri kaydeder ve grafik olarak sunar.

## 🛠️ Kullanılan Teknolojiler

- **Python (PyQt5)** – Masaüstü arayüz geliştirme
- **scikit-learn** – Lineer regresyon modeli
- **Matplotlib** – Gerçek zamanlı grafik çizimi
- **Arduino Uno + DHT11 + HC-SR04** – Sıcaklık ve mesafe sensörü
- **Serial (PySerial)** – Arduino ile iletişim
- **Pandas / NumPy** – Veri analizi ve kayıt işlemleri

## 🔌 Donanım Bağlantıları

### HC-SR04 Mesafe Sensörü:
- VCC → 5V  
- GND → GND  
- TRIG → Arduino Pin 9  
- ECHO → Arduino Pin 10  

### DHT11 Sıcaklık Sensörü:
- VCC → 5V  
- GND → GND  
- DATA → Arduino Pin 2  

> Arduino, sensör verilerini şu formatta seri porttan gönderir:  
> `Sıcaklık: 28.0°C | Mesafe: 12.5cm`

## 🧠 Model Eğitimi

Sentetik veri ile 1000 örnek üretildi. Kullanılan formül:


- `k` değeri lineer regresyon ile öğrenildi.
- MAE: ~0.19 cm  
- RMSE: ~0.50 cm

## 🖥️ Arayüz Özellikleri

- Başlangıç kalınlığı ve kritik eşik kullanıcı tarafından girilir.
- Gerçek zamanlı sıcaklık, mesafe ve tahmini kalınlık gösterilir.
- Kritik aşınma uyarısı verilir.
- Ne zaman kritik seviyeye ulaşılacağı tahmin edilir.
- Kalınlık değişimi zaman ekseninde grafikle görselleştirilir.


