# 15 Python ile Görüntü İşleme** 🖼️

## 15.1. Giriş ve Temel Kavramlar**

### **Görüntü İşlemenin Tanımı ve Önemi**
Görüntü işleme, dijital görüntüler üzerinde bilgisayarlar tarafından gerçekleştirilen işlemlerdir. Bu işlemler, görüntülerin analiz edilmesi, değiştirilmesi veya yorumlanması amacıyla yapılır. Görüntü işleme, günümüzde birçok alanda kullanılmaktadır:

- **Tıbbi Görüntü Analizi**: MRI, X-ray gibi tıbbi görüntülerin işlenmesi ve hastalıkların teşhisinde kullanılması.
- **Yüz Tanıma**: Güvenlik sistemleri, akıllı telefonlar ve sosyal medya platformları için yüz tanıma teknolojisi.
- **Nesne Algılama**: Otonom araçlar, drone'lar ve güvenlik kameraları için nesne algılama.
- **Sanat ve Tasarım**: Resim düzenleme yazılımları (örneğin Photoshop) ve sanatsal uygulamalar.

Görüntü işleme, bilgisayarların gerçek dünyayı daha iyi anlamasını sağlar ve bu sayede insan hayatını kolaylaştırır.


### **Görüntü İşleme Uygulamaları**
Görüntü işleme, pek çok farklı alanda uygulanabilir. İşte bazı örnekler:

1. **Tıbbi Görüntüleme**:
   - Tıbbi görüntülerde tümörlerin veya kırıkların tespiti.
   - Örnek: Bir MRI görüntüsünde beyin dokusunun analizi.

2. **Otonom Araçlar**:
   - Yol işaretlerini algılama ve engellerden kaçınma.
   - Örnek: Bir arabanın kamera görüntülerini analiz ederek yol çizgilerini takip etmesi.

3. **Güvenlik Sistemleri**:
   - Yüz tanıma ve hareket algılama.
   - Örnek: Bir binaya girişte yüz tanıma ile kimlik doğrulama.

4. **E-ticaret ve Perakende**:
   - Ürün fotoğraflarının otomatik olarak düzenlenmesi.
   - Örnek: Bir e-ticaret sitesinde ürün resimlerinin arka planını temizleme.

5. **Drone ve Uydu Görüntüleri**:
   - Tarım alanlarının izlenmesi veya afet bölgelerinin haritalanması.
   - Örnek: Bir drone'un çektiği görüntüleri analiz ederek hasar tespiti.


### **Temel Görüntü İşleme Kavramları**
Görüntü işlemeyle çalışırken bilmeniz gereken temel kavramlar şunlardır:

1. **Piksel (Pixel)**:
   - Piksel, bir görüntünün en küçük birimidir. Her piksel, bir renk değeri taşır.
   - Örneğin, bir RGB görüntüsünde her piksel, kırmızı (Red), yeşil (Green) ve mavi (Blue) renk kanallarının birleşimiyle oluşturulur.

2. **Renk Uzayları**:
   - Renk uzayları, renklerin nasıl temsil edildiğini belirler. En yaygın renk uzayları şunlardır:
     - **RGB (Red, Green, Blue)**: Kırmızı, yeşil ve mavi renklerin kombinasyonuyla oluşturulan renk uzayı.
     - **Grayscale**: Gri tonlamalı görüntüler için kullanılan renk uzayı. Her piksel, 0 (siyah) ile 255 (beyaz) arasında bir değer alır.
     - **HSV (Hue, Saturation, Value)**: Renk tonu, doygunluk ve parlaklık değerlerine göre tanımlanan renk uzayı.
     - **CMYK (Cyan, Magenta, Yellow, Black)**: Matbaacılıkta kullanılan renk uzayı.

3. **Görüntü Formatları**:
   - Görüntüler, farklı formatlarda saklanabilir. En yaygın formatlar şunlardır:
     - **JPEG**: Sıkıştırılmış bir format. Fotoğraflar için idealdir.
     - **PNG**: Şeffaflığı destekleyen bir format. Grafikler ve logoslar için idealdir.
     - **BMP**: Basit ve sıkıştırılmamış bir format.
     - **TIFF**: Yüksek kaliteli görüntüler için kullanılan bir format.

4. **Çözünürlük ve Boyut**:
   - **Çözünürlük**: Bir görüntünün genişlik ve yüksekliğini piksel cinsinden ifade eder. Örneğin, 1920x1080 çözünürlüğü, görüntüde yatayda 1920 piksel, dikeyde 1080 piksel olduğunu gösterir.
   - **Boyut**: Görüntünün diskte kapladığı alanı ifade eder. Çözünürlük arttıkça boyut da büyür.


### **Python'un Görüntü İşlemede Neden Tercih Edildiği**
Python, görüntü işleme için tercih edilen bir dil olmasının birkaç nedeni vardır:

1. **Zengin Kütüphane Desteği**:
   - OpenCV, Pillow, NumPy, Matplotlib gibi güçlü kütüphaneler, görüntü işleme süreçlerini kolaylaştırır.

2. **Kolay Öğrenme Eğrisi**:
   - Python, basit ve okunabilir bir sözdizimine sahiptir. Bu, yeni başlayanlar için idealdir.

3. **Topluluk Desteği**:
   - Python, dünya çapında geniş bir topluluğa sahiptir. Bu, sorun yaşarken yardım alabileceğiniz anlamına gelir.

4. **Derin Öğrenme Entegrasyonu**:
   - TensorFlow ve PyTorch gibi derin öğrenme kütüphaneleriyle entegrasyon, gelişmiş görüntü işleme projeleri geliştirmenizi sağlar.


---


## 15.2. Python ve Görüntü İşleme Araçları**

### **Kullanılan Kütüphaneler**
Python'da görüntü işleme için birçok güçlü kütüphane bulunmaktadır. İşte en yaygın kullanılanlar:

1. **OpenCV**:
   - En popüler görüntü işleme kütüphanesi.
   - Gerçek zamanlı görüntü işleme, nesne algılama, yüz tanıma gibi gelişmiş işlemler için idealdir.

   ```bash
   pip install opencv-python  # OpenCV kütüphanesini yükler
   ```

   - Bu komut, OpenCV'yi projenize kurar.

2. **Pillow (PIL)**:
   - Basit görüntü işlemleri için kullanılır.
   - Resim boyutlandırma, kesme, filtre uygulama gibi temel işlemler için idealdir.

   ```bash
   pip install pillow  # Pillow kütüphanesini yükler
   ```

   - Pillow, Python Imaging Library (PIL)'in güncellenmiş halidir.

3. **NumPy**:
   - Görüntü verilerini matris olarak işlemek için kullanılır.
   - Matematiksel işlemler için güçlü bir araçtır.

   ```bash
   pip install numpy  # NumPy kütüphanesini yükler
   ```

   - NumPy, görüntüleri piksel değerleriyle manipüle etmek için sıkça kullanılır.

4. **Matplotlib**:
   - Görüntüleri görselleştirmek için kullanılır.
   - Grafik çizme ve analiz yapmak için idealdir.

   ```bash
   pip install matplotlib  # Matplotlib kütüphanesini yükler
   ```

   - Matplotlib, görüntülerin renk dağılımlarını veya histogramlarını analiz etmek için kullanılır.

5. **Scikit-image**:
   - Bilimsel görüntü işleme için tasarlanmış bir kütüphanedir.
   - Segmentasyon, kenar tespiti gibi ileri düzey işlemler için idealdir.

   ```bash
   pip install scikit-image  # Scikit-image kütüphanesini yükler
   ```

   - Scikit-image, bilimsel araştırmalar ve karmaşık görüntü işleme projeleri için tercih edilir.


### **Kurulum ve İlk Adımlar**
Bu kütüphaneleri kurduktan sonra, aşağıdaki kodlarla temel işlemlere başlayabilirsiniz:

```python
import cv2  # OpenCV kütüphanesini içe aktarır
import numpy as np  # NumPy kütüphanesini içe aktarır
from PIL import Image  # Pillow kütüphanesini içe aktarır
import matplotlib.pyplot as plt  # Matplotlib kütüphanesini içe aktarır

# Örnek bir görüntüyü yükle
image = cv2.imread("example.jpg")  # "example.jpg" adlı bir görüntüyü yükler
print("Görüntü Boyutu:", image.shape)  # Görüntünün boyutlarını yazdırır

# Görüntüyü göster
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # OpenCV BGR formatını RGB'ye dönüştürür
plt.title("Görüntü")  # Başlık ekler
plt.show()  # Görüntüyü ekranda gösterir
```

- Bu kod, bir görüntüyü yükler, boyutlarını yazdırır ve ekranda gösterir.


---


## 15.3. Görüntü Okuma, Yazma ve Temel İşlemler**

### **Görüntü Okuma ve Gösterme**
Bir görüntüyü okumak ve ekranda göstermek için aşağıdaki kodu kullanabilirsiniz:

```python
import cv2

# Görüntüyü oku
image = cv2.imread("example.jpg")  # "example.jpg" dosyasını yükle

# Görüntüyü göster
cv2.imshow("Image", image)  # Görüntüyü bir pencerede gösterir
cv2.waitKey(0)  # Kullanıcıdan bir tuş basmasını bekler
cv2.destroyAllWindows()  # Pencereyi kapatır
```

- `cv2.imread`, bir görüntüyü yükler. `cv2.imshow`, görüntünün ekranda gösterilmesini sağlar.


### **Görüntü Kaydetme**
İşlenmiş bir görüntüyü kaydetmek için aşağıdaki kodu kullanabilirsiniz:

```python
cv2.imwrite("output.jpg", image)  # İşlenmiş görüntüyü "output.jpg" olarak kaydeder
```

- `cv2.imwrite`, bir görüntüyü belirtilen dosya adıyla kaydeder.


### **Görüntü Özellikleri**
Bir görüntünün özelliklerini (boyut, piksel sayısı, veri tipi) öğrenmek için aşağıdaki kodu kullanabilirsiniz:

```python
print("Boyut:", image.shape)  # Görüntünün yükseklik, genişlik ve kanal sayısını yazdırır
print("Piksel Sayısı:", image.size)  # Toplam piksel sayısını yazdırır
print("Veri Tipi:", image.dtype)  # Görüntünün veri tipini yazdırır (genellikle uint8)
```

- `image.shape`, görüntünün boyutlarını; `image.size`, toplam piksel sayısını; `image.dtype`, veri tipini gösterir.


### **Görüntü Yeniden Boyutlandırma**
Bir görüntüyü yeniden boyutlandırmak için aşağıdaki kodu kullanabilirsiniz:

```python
resized = cv2.resize(image, (300, 300))  # Görüntüyü 300x300 boyutuna yeniden boyutlandırır
cv2.imshow("Resized Image", resized)  # Yeniden boyutlandırılmış görüntüyü gösterir
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.resize`, bir görüntüyü belirtilen boyuta yeniden boyutlandırır.


### **Renk Dönüşümleri**
Bir görüntüyü farklı renk uzaylarına dönüştürmek için aşağıdaki kodu kullanabilirsiniz:

```python
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Görüntüyü gri tonlamaya dönüştürür
hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)    # Görüntüyü HSV renk uzayına dönüştürür

cv2.imshow("Grayscale", gray)  # Gri tonlamalı görüntüyü gösterir
cv2.imshow("HSV", hsv)         # HSV görüntüsünü gösterir
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.cvtColor`, bir görüntüyü farklı renk uzaylarına dönüştürür.


---


## 15.4. Temel Görüntü İşleme Teknikleri**

### **Parlaklık ve Kontrast Ayarı**
Görüntülerde parlaklık ve kontrast ayarı, görüntünün görünümünü iyileştirmek veya belirli özelliklerini vurgulamak için kullanılır. Parlaklık, görüntünün genel aydınlanma seviyesini kontrol ederken, kontrast, pikseller arasındaki renk farklılıklarını artırır veya azaltır.

- **Parlaklık Artırma**:
  Parlaklık artışı, her pikselin değerine sabit bir sayı eklenerek yapılır. Örneğin, tüm piksellerin değerini 50 artırırsanız, görüntü daha aydınlık hale gelir.

- **Kontrast Ayarlama**:
  Kontrast ayarı, piksellerin değerlerini bir çarpanla genişletmek veya daraltmak anlamına gelir. Çarpan 1'den büyükse kontrast artar, 1'den küçükse azalır.

```python
import cv2
import numpy as np

# Görüntüyü yükle
image = cv2.imread("example.jpg")

# Parlaklık ve kontrast değerleri
alpha = 1.5  # Kontrast kontrolü (1: orijinal, >1: artan kontrast)
beta = 50    # Parlaklık kontrolü (0: orijinal, >0: artan parlaklık)

# Parlaklık ve kontrastı ayarla
adjusted = cv2.convertScaleAbs(image, alpha=alpha, beta=beta)

# Sonuçları göster
cv2.imshow("Original", image)  # Orijinal görüntüyü göster
cv2.imshow("Adjusted", adjusted)  # Ayarlanmış görüntüyü göster
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.convertScaleAbs`, görüntünün parlaklık ve kontrastını ayarlar. `alpha` parametresi kontrastı, `beta` parametresi ise parlaklığı kontrol eder.


### **Görüntü Kesme (Cropping)**
Görüntü kesme, bir görüntünün belirli bir bölgesini çıkarmak için kullanılan bir işlemdir. Bu işlem, ilgilenilen bölgeyi (Region of Interest - ROI) odaklamak veya gereksiz kısımları atmak için kullanılır.

- **Kesme İşlemi Nasıl Yapılır?**
  Görüntü, bir matris olarak temsil edilir. Matrisin belirli satır ve sütunlarını seçerek, istenen bölgeyi elde edebilirsiniz. Örneğin, `[y1:y2, x1:x2]` ifadesi, `y1` ile `y2` arasındaki satırları ve `x1` ile `x2` arasındaki sütunları seçer.

```python
# Görüntüyü yükle
image = cv2.imread("example.jpg")

# Kesilecek bölgeyi tanımla (y1:y2, x1:x2)
cropped = image[50:200, 100:300]  # 50-200 piksel yükseklik, 100-300 piksel genişlik

# Sonuçları göster
cv2.imshow("Original", image)  # Orijinal görüntüyü göster
cv2.imshow("Cropped", cropped)  # Kesilmiş görüntüyü göster
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `image[y1:y2, x1:x2]`, görüntünün belirli bir bölgesini keser. Bu işlem, özellikle yüz tespiti veya plaka tanıma gibi uygulamalarda kullanılır.


### **Görüntü Döndürme ve Çevirme**
Görüntü döndürme ve çevirme işlemleri, görüntünün yönelimini değiştirmek için kullanılır. Döndürme, bir açı etrafında dönüş yaparken, çevirme yatay veya dikey eksende aynalama işlemidir.

- **Döndürme**:
  Döndürme işlemi için bir dönüş matrisi oluşturulur. Bu matris, görüntünün merkezini ve dönme açısını belirler.

- **Çevirme**:
  Çevirme işlemi, görüntünün yatay veya dikey eksende aynalanmasını sağlar. Örneğin, bir görüntüyü yatay olarak çevirmek, sağdaki nesneleri sola taşır.

```python
# Görüntüyü yükle
image = cv2.imread("example.jpg")

# Döndürme matrisi oluştur
(height, width) = image.shape[:2]
center = (width // 2, height // 2)
rotation_matrix = cv2.getRotationMatrix2D(center, 45, 1.0)  # 45 derece döndür

# Görüntüyü döndür
rotated = cv2.warpAffine(image, rotation_matrix, (width, height))

# Görüntüyü yatay olarak çevir
flipped = cv2.flip(image, 1)  # 1: yatay, 0: dikey, -1: hem yatay hem dikey

# Sonuçları göster
cv2.imshow("Original", image)  # Orijinal görüntüyü göster
cv2.imshow("Rotated", rotated)  # Döndürülmüş görüntüyü göster
cv2.imshow("Flipped", flipped)  # Yatay olarak çevrilmiş görüntüyü göster
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.getRotationMatrix2D`, bir dönüş matrisi oluşturur. `cv2.warpAffine`, bu matrisi kullanarak görüntüyü döndürür. `cv2.flip`, görüntünün yatay veya dikey eksende çevrilmesini sağlar.


### **Görüntü Bulanıklaştırma (Blurring)**
Bulanıklaştırma, görüntünün detaylarını yumuşatmak veya gürültüyü azaltmak için kullanılır. En yaygın bulanıklaştırma teknikleri şunlardır:

- **Ortalama Bulanıklaştırma (Averaging)**:
  Pikselin komşu piksellerinin ortalamasını alır.

- **Gaussian Bulanıklaştırma**:
  Komşu piksellerin ağırlıklı ortalamasını alır. Kenarları daha iyi korur.

- **Median Bulanıklaştırma**:
  Komşu piksellerin medyanını alır. Gürültüyü etkili bir şekilde azaltır.

```python
# Görüntüyü yükle
image = cv2.imread("example.jpg")

# Ortalama bulanıklaştırma
average_blur = cv2.blur(image, (5, 5))  # 5x5 boyutunda bir kernel kullanır

# Gaussian bulanıklaştırma
gaussian_blur = cv2.GaussianBlur(image, (5, 5), 0)  # 5x5 boyutunda bir kernel kullanır

# Median bulanıklaştırma
median_blur = cv2.medianBlur(image, 5)  # 5x5 boyutunda bir kernel kullanır

# Sonuçları göster
cv2.imshow("Original", image)  # Orijinal görüntüyü göster
cv2.imshow("Average Blur", average_blur)  # Ortalama bulanıklaştırılmış görüntüyü göster
cv2.imshow("Gaussian Blur", gaussian_blur)  # Gaussian bulanıklaştırılmış görüntüyü göster
cv2.imshow("Median Blur", median_blur)  # Median bulanıklaştırılmış görüntüyü göster
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.blur`, ortalama bulanıklaştırma; `cv2.GaussianBlur`, Gaussian bulanıklaştırma; `cv2.medianBlur`, median bulanıklaştırma yapar.


---


## 15.5. İleri Görüntü İşleme Teknikleri**

### **Kenar Tespiti (Edge Detection)**
Kenar tespiti, bir görüntünün kenarlarını (nesne sınırlarını) belirlemek için kullanılır. En yaygın kenar tespiti yöntemleri şunlardır:

- **Canny Edge Detector**:
  İki eşik değeri kullanarak kenarları tespit eder. Hassas ve etkili bir yöntemdir.

- **Sobel Operatörü**:
  X ve Y yönlerinde gradyan hesaplayarak kenarları tespit eder.

```python
# Görüntüyü yükle ve gri tonlamaya dönüştür
image = cv2.imread("example.jpg")
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Canny kenar tespiti
canny_edges = cv2.Canny(gray, 100, 200)  # Eşik değerleri: 100 ve 200

# Sobel kenar tespiti
sobel_x = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=3)  # X yönünde gradyan
sobel_y = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=3)  # Y yönünde gradyan
sobel_edges = cv2.magnitude(sobel_x, sobel_y)  # X ve Y gradyanlarının büyüklüğü

# Sonuçları göster
cv2.imshow("Original", image)  # Orijinal görüntüyü göster
cv2.imshow("Canny Edges", canny_edges)  # Canny kenarlarını göster
cv2.imshow("Sobel Edges", sobel_edges.astype(np.uint8))  # Sobel kenarlarını göster
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.Canny`, Canny kenar tespiti yapar. `cv2.Sobel`, X ve Y yönlerinde gradyan hesaplar.


### **Nesne Algılama ve Takibi**
Nesne algılama, bir görüntüdeki belirli nesneleri tanımlamak için kullanılır. Örneğin, bir görüntüdeki yüzleri veya arabaları tespit edebilirsiniz.

- **Haar Cascade Classifier**:
  OpenCV'nin hazır yüz tespit modelini kullanır.

```python
# Haar Cascade modelini yükle
face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + "haarcascade_frontalface_default.xml")

# Görüntüyü yükle ve gri tonlamaya dönüştür
image = cv2.imread("example.jpg")
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Yüz tespiti yap
faces = face_cascade.detectMultiScale(gray, scaleFactor=1.1, minNeighbors=5)

# Tespit edilen yüzleri işaretle
for (x, y, w, h) in faces:
    cv2.rectangle(image, (x, y), (x+w, y+h), (255, 0, 0), 2)  # Mavi dikdörtgen çiz

# Sonucu göster
cv2.imshow("Face Detection", image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.CascadeClassifier`, yüz tespiti için hazır bir model kullanır. `detectMultiScale`, yüzleri tespit eder.


---


### 15.6. Görüntü Filtreleme ve İyileştirme**

#### **Filtreler (Gaussian Blur, Median Blur)**
Filtreler, görüntülerdeki gürültüyü azaltmak veya belirli özellikleri vurgulamak için kullanılır. En yaygın filtreler şunlardır:

- **Gaussian Blur**:
  Gaussian bulanıklaştırma, komşu piksellerin ağırlıklı ortalamasını alır. Bu yöntem, kenarları korurken gürültüyü etkili bir şekilde azaltır.

- **Median Blur**:
  Median bulanıklaştırma, komşu piksellerin medyanını alır. Bu yöntem, özellikle tuz-biber gürültüsü gibi rastgele gürültüleri azaltmada etkilidir.

```python
import cv2

# Görüntüyü yükle
image = cv2.imread("example.jpg")

# Gaussian bulanıklaştırma
gaussian_blur = cv2.GaussianBlur(image, (5, 5), 0)  # 5x5 boyutunda bir kernel kullanır

# Median bulanıklaştırma
median_blur = cv2.medianBlur(image, 5)  # 5x5 boyutunda bir kernel kullanır

# Sonuçları göster
cv2.imshow("Original", image)  # Orijinal görüntüyü göster
cv2.imshow("Gaussian Blur", gaussian_blur)  # Gaussian bulanıklaştırılmış görüntüyü göster
cv2.imshow("Median Blur", median_blur)  # Median bulanıklaştırılmış görüntüyü göster
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.GaussianBlur`, Gaussian bulanıklaştırma yapar. `cv2.medianBlur`, median bulanıklaştırma yapar. Her iki yöntem de gürültüyü azaltır ancak farklı senaryolarda tercih edilir.


#### **Görüntü Keskinleştirme (Sharpening)**
Keskinleştirme, görüntünün detaylarını vurgulamak için kullanılır. Özellikle bulanık görüntülerde nesnelerin kenarlarını netleştirmek için uygulanır.

- **Kernel Kullanımı**:
  Keskinleştirme işlemi için özel bir kernel (filtre matrisi) kullanılır. Bu kernel, orijinal görüntüye eklenerek keskinleştirme sağlanır.

```python
import cv2
import numpy as np

# Görüntüyü yükle
image = cv2.imread("example.jpg")

# Keskinleştirme kerneli
kernel = np.array([[0, -1, 0],
                   [-1, 5, -1],
                   [0, -1, 0]])

# Keskinleştirme uygula
sharpened = cv2.filter2D(image, -1, kernel)

# Sonuçları göster
cv2.imshow("Original", image)  # Orijinal görüntüyü göster
cv2.imshow("Sharpened", sharpened)  # Keskinleştirilmiş görüntüyü göster
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.filter2D`, özel bir kernel kullanarak görüntüyü filtreler. Burada kullanılan kernel, görüntüyü keskinleştirir.


#### **Gürültü Giderme (Noise Reduction)**
Gürültü giderme, görüntülerdeki istenmeyen bozulmaları azaltmak için kullanılır. En yaygın yöntemlerden biri, Gaussian veya Median bulanıklaştırma kullanmaktır.

```python
# Görüntüyü yükle
image = cv2.imread("noisy_image.jpg")

# Gürültüyü azaltmak için Gaussian bulanıklaştırma
denoised = cv2.GaussianBlur(image, (5, 5), 0)

# Sonuçları göster
cv2.imshow("Noisy Image", image)  # Gürültülü görüntüyü göster
cv2.imshow("Denoised", denoised)  # Gürültüsüz görüntüyü göster
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.GaussianBlur`, gürültüyü azaltmak için kullanılır. Özellikle düşük kaliteli görüntülerde etkilidir.


#### **Morfolojik İşlemler (Erosion, Dilation)**
Morfolojik işlemler, görüntülerdeki nesnelerin şekillerini değiştirmek için kullanılır. En yaygın morfolojik işlemler şunlardır:

- **Erosion (Aşındırma)**:
  Nesnelerin sınırlarını daraltır. Küçük nesneleri tamamen ortadan kaldırabilir.

- **Dilation (Genişletme)**:
  Nesnelerin sınırlarını genişletir. Küçük delikleri doldurabilir.

```python
import cv2
import numpy as np

# Görüntüyü yükle ve gri tonlamaya dönüştür
image = cv2.imread("binary_image.jpg", cv2.IMREAD_GRAYSCALE)

# Yapısal eleman (kernel) oluştur
kernel = np.ones((5, 5), np.uint8)

# Erosion uygula
eroded = cv2.erode(image, kernel, iterations=1)

# Dilation uygula
dilated = cv2.dilate(image, kernel, iterations=1)

# Sonuçları göster
cv2.imshow("Original", image)  # Orijinal görüntüyü göster
cv2.imshow("Eroded", eroded)  # Aşındırılmış görüntüyü göster
cv2.imshow("Dilated", dilated)  # Genişletilmiş görüntüyü göster
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.erode`, nesnelerin sınırlarını daraltır. `cv2.dilate`, nesnelerin sınırlarını genişletir. Bu işlemler, özellikle ikili (binary) görüntülerde kullanılır.


---


## 15.7. Nesne Algılama ve Tanıma**

### **Yüz Tespiti (Face Detection)**
Yüz tespiti, bir görüntüdeki yüzleri tanımlamak için kullanılır. OpenCV'nin hazır Haar Cascade modeli, bu işlemi gerçekleştirmek için kullanılabilir.

```python
import cv2

# Haar Cascade modelini yükle
face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + "haarcascade_frontalface_default.xml")

# Görüntüyü yükle ve gri tonlamaya dönüştür
image = cv2.imread("people.jpg")
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Yüz tespiti yap
faces = face_cascade.detectMultiScale(gray, scaleFactor=1.1, minNeighbors=5)

# Tespit edilen yüzleri işaretle
for (x, y, w, h) in faces:
    cv2.rectangle(image, (x, y), (x+w, y+h), (255, 0, 0), 2)  # Mavi dikdörtgen çiz

# Sonucu göster
cv2.imshow("Face Detection", image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.CascadeClassifier`, yüz tespiti için hazır bir model kullanır. `detectMultiScale`, yüzleri tespit eder ve dikdörtgenlerle işaretler.


### **Nesne Tespiti (Object Detection)**
Nesne tespiti, bir görüntüdeki belirli nesneleri tanımlamak için kullanılır. Örneğin, bir görüntüdeki arabaları veya kedileri tespit edebilirsiniz.

- **Şablon Eşleştirme (Template Matching)**:
  Şablon eşleştirme, bir görüntüde belirli bir şablonu aramak için kullanılır. Bu yöntem, küçük ölçekli projelerde faydalıdır.

```python
import cv2
import numpy as np

# Görüntüyü ve şablonu yükle
image = cv2.imread("large_image.jpg")
template = cv2.imread("template.jpg")

# Şablonun boyutlarını al
h, w = template.shape[:2]

# Şablon eşleştirme uygula
result = cv2.matchTemplate(image, template, cv2.TM_CCOEFF_NORMED)
min_val, max_val, min_loc, max_loc = cv2.minMaxLoc(result)

# Eşleşen bölgeyi işaretle
top_left = max_loc
bottom_right = (top_left[0] + w, top_left[1] + h)
cv2.rectangle(image, top_left, bottom_right, (0, 255, 0), 2)

# Sonucu göster
cv2.imshow("Object Detection", image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

- `cv2.matchTemplate`, bir görüntüde belirli bir şablonu arar. Eşleşen bölgeyi dikdörtgenle işaretler.


### **OCR (Optical Character Recognition)**
OCR, bir görüntüdeki metinleri tanımak ve dijital metne çevirmek için kullanılır. Tesseract, OCR için en yaygın kullanılan araçtır.

```bash
pip install pytesseract
```

```python
import cv2
import pytesseract

# Tesseract'in yolunu belirt (Windows için gerekli olabilir)
pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"

# Görüntüyü yükle
image = cv2.imread("text_image.jpg")

# Görüntüden metin çıkar
text = pytesseract.image_to_string(image)

# Metni yazdır
print("Çıkarılan Metin:", text)
```

- `pytesseract.image_to_string`, bir görüntüdeki metni çıkarır. Bu işlem, faturaları veya belgeleri dijitalleştirmek için kullanılır.

---


## 15.8. Derin Öğrenme ile Görüntü İşleme**

### **Derin Öğrenme Temelleri**
Derin öğrenme, makine öğrenmesinin bir alt dalıdır ve özellikle görüntü işleme alanında devrim yaratmıştır. Derin öğrenme modelleri, katmanlı sinir ağları (neural networks) kullanarak karmaşık desenleri öğrenir ve tahminler yapar.

- **Neden Derin Öğrenme?**
  - Geleneksel yöntemlere göre daha yüksek doğruluk sağlar.
  - Büyük veri setleri üzerinde etkilidir.
  - Özellikle görüntü sınıflandırma, nesne algılama ve segmentasyon gibi görevlerde başarılıdır.

- **Temel Kavramlar**:
  - **Yapay Sinir Ağları (ANN)**: Basit bir sinir ağı modelidir.
  - **Katmansal Yapı**: Giriş katmanı, gizli katmanlar ve çıkış katmanı.
  - **Eğitim Süreci**: Model, veri üzerinde eğitilir ve hata oranını minimize eder.


### **CNN (Convolutional Neural Networks) ile Görüntü Sınıflandırma**
CNN'ler, görüntü işleme için özel olarak tasarlanmış derin öğrenme modelleridir. CNN'ler, görüntülerdeki desenleri otomatik olarak öğrenir ve sınıflandırır.

- **CNN'nin Çalışma Prensibi**:
  - **Convolution Layer**: Görüntüdeki özellikleri çıkarır (örneğin kenarlar, köşeler).
  - **Pooling Layer**: Veriyi küçültür ve önemli özellikleri korur.
  - **Fully Connected Layer**: Çıkarılan özellikleri sınıflandırır.

```python
import tensorflow as tf
from tensorflow.keras import layers, models

# Basit bir CNN modeli oluştur
model = models.Sequential([
    layers.Conv2D(32, (3, 3), activation='relu', input_shape=(64, 64, 3)),  # Convolution layer
    layers.MaxPooling2D((2, 2)),  # Pooling layer
    layers.Conv2D(64, (3, 3), activation='relu'),
    layers.MaxPooling2D((2, 2)),
    layers.Flatten(),  # Veriyi düzleştir
    layers.Dense(64, activation='relu'),  # Fully connected layer
    layers.Dense(10, activation='softmax')  # Çıkış katmanı
])

# Modeli derle
model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])

# Model özeti
model.summary()
```

- Bu kod, basit bir CNN modeli oluşturur. `Conv2D`, özellik çıkarma; `MaxPooling2D`, veriyi küçültür; `Dense`, sınıflandırma yapar.


### **Pre-trained Modeller (ResNet, VGG, YOLO)**
Pre-trained modeller, büyük veri setleri üzerinde eğitilmiş hazır modellerdir. Bu modeller, transfer learning (aktarım öğrenme) ile kendi projelerinizde kullanılabilir.

- **Popüler Pre-trained Modeller**:
  - **VGG16**: Basit ve etkili bir model.
  - **ResNet**: Derin ağlar için tasarlanmıştır.
  - **YOLO**: Gerçek zamanlı nesne algılama için kullanılır.

```python
from tensorflow.keras.applications import VGG16
from tensorflow.keras.preprocessing import image
from tensorflow.keras.applications.vgg16 import preprocess_input, decode_predictions
import numpy as np

# VGG16 modelini yükle
model = VGG16(weights='imagenet')

# Görüntüyü yükle ve ön işleme yap
img_path = "cat.jpg"
img = image.load_img(img_path, target_size=(224, 224))  # Görüntüyü yeniden boyutlandır
x = image.img_to_array(img)  # NumPy dizisine dönüştür
x = np.expand_dims(x, axis=0)  # Batch boyutu ekleyerek (1, 224, 224, 3) yap
x = preprocess_input(x)  # Ön işleme yap

# Tahmin yap
preds = model.predict(x)
print('Tahmin:', decode_predictions(preds, top=3)[0])  # En iyi 3 tahmini yazdır
```

- Bu kod, VGG16 modelini kullanarak bir görüntüyü sınıflandırır. `decode_predictions`, tahminleri insan okunabilir formata çevirir.


### **TensorFlow ve PyTorch ile Görüntü İşleme**
TensorFlow ve PyTorch, derin öğrenme için en popüler kütüphanelerdir. Her iki kütüphane de güçlü araçlar sunar.

- **TensorFlow ile Basit Bir Model**:
  ```python
  import tensorflow as tf

  # Basit bir model oluştur
  model = tf.keras.Sequential([
      tf.keras.layers.Dense(128, activation='relu', input_shape=(784,)),
      tf.keras.layers.Dense(10, activation='softmax')
  ])

  # Modeli derle
  model.compile(optimizer='adam',
                loss='sparse_categorical_crossentropy',
                metrics=['accuracy'])
  ```

- **PyTorch ile Basit Bir Model**:
  ```python
  import torch
  import torch.nn as nn

  # Basit bir model tanımla
  class SimpleModel(nn.Module):
      def __init__(self):
          super(SimpleModel, self).__init__()
          self.fc1 = nn.Linear(784, 128)
          self.fc2 = nn.Linear(128, 10)

      def forward(self, x):
          x = torch.relu(self.fc1(x))
          x = self.fc2(x)
          return x

  model = SimpleModel()
  print(model)
  ```

- TensorFlow ve PyTorch, farklı API'ler sunar ancak her ikisi de güçlüdür. Seçim, kişisel tercihlere bağlıdır.


## 15.9. Proje Geliştirme ve Pratik Örnekler**

### **Basit Projeler**
1. **Resim Editörü Uygulaması**:
   - Kullanıcıların resimleri yükleyip filtre uygulayabileceği bir uygulama geliştirin.
   - OpenCV veya Pillow kullanarak parlaklık, kontrast ve bulanıklaştırma işlemleri ekleyin.

2. **Yüz Tanıma Sistemi**:
   - Haar Cascade veya Dlib kullanarak bir yüz tanıma sistemi oluşturun.
   - Gerçek zamanlı kamera beslemesiyle yüzleri tespit edin.

3. **Plaka Tanıma Sistemi**:
   - OCR (Tesseract) kullanarak araç plakalarını tanıyın.
   - Görüntü işleme teknikleriyle plakayı tespit edin ve metni çıkarın.

---

### **Gelişmiş Projeler**
1. **Tıbbi Görüntü Analizi**:
   - MRI veya X-ray görüntülerinde hastalık teşhisi yapmak için bir CNN modeli eğitin.
   - TensorFlow veya PyTorch kullanarak modeli geliştirin.

2. **Drone Görüntü İşleme**:
   - Drone'lar tarafından çekilen görüntülerde nesne algılama yapın.
   - YOLO veya Faster R-CNN gibi modelleri kullanın.

3. **Gerçek Zamanlı Nesne Algılama**:
   - Kamera beslemesiyle gerçek zamanlı nesne algılama uygulaması geliştirin.
   - OpenCV ve pre-trained modeller (örneğin MobileNet) kullanın.