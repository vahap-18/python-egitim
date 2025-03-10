## 13.1 Makine Öğrenmesine Giriş  

Makine öğrenmesi, bilgisayarların açıkça programlanmadan öğrenmesini sağlayan bir yapay zeka dalıdır. Geleneksel programlama yöntemlerinden farklı olarak, makine öğrenmesi sistemleri büyük miktarda veri kullanarak örüntüleri öğrenir ve bu bilgilere dayanarak tahminler yapar.  

### Makine Öğrenmesi Nedir?  

Makine öğrenmesi (ML), algoritmaların büyük veri kümelerinden öğrenerek kararlar almasını veya tahminlerde bulunmasını sağlayan bir tekniktir. ML, verilerdeki örüntüleri öğrenmek ve gelecekteki olayları tahmin etmek için istatistik ve matematiksel modeller kullanır.  

💡 **Örnek:**  
- Bir e-ticaret sitesinin, kullanıcıların alışveriş geçmişine dayanarak onlara kişiselleştirilmiş ürün önerileri sunması.  
- Spam filtrelerinin, gelen e-postaların spam olup olmadığını anlamak için makine öğrenmesi tekniklerini kullanması.  

### Makine Öğrenmesi ile Yapay Zeka Arasındaki Farklar  

Makine öğrenmesi, yapay zekanın bir alt dalıdır. Yapay zeka (AI), makinelerin insan benzeri bilişsel işlevleri gerçekleştirmesini sağlarken, makine öğrenmesi bunu verilerden öğrenerek yapar.  

| **Özellik**             | **Yapay Zeka (AI)**        | **Makine Öğrenmesi (ML)** |
|-------------------------|---------------------------|---------------------------|
| Tanım                   | Makinelerin akıllı davranışlar sergilemesi. | Makinelerin verilerden öğrenmesi. |
| Çalışma Prensibi        | Kural tabanlı sistemlerden derin öğrenmeye kadar geniş bir yelpazeyi kapsar. | Algoritmalar, verilerden örüntüler öğrenir. |
| Kullanım Alanı          | Oyun oynayan AI, konuşma tanıma, robotik. | Öneri sistemleri, görüntü tanıma, doğal dil işleme. |

### Makine Öğrenmesinin Kullanım Alanları ve Uygulamaları  

Makine öğrenmesi birçok sektörde aktif olarak kullanılmaktadır:  

🔹 **Sağlık:** Hastalık tahmini, tıbbi görüntü analizi, ilaç keşfi.  
🔹 **Finans:** Dolandırıcılık tespiti, hisse senedi fiyat tahmini.  
🔹 **E-ticaret:** Kişiselleştirilmiş öneri sistemleri, fiyat tahmini.  
🔹 **Otonom Araçlar:** Görüntü işleme ile nesne tanıma ve sürüş algoritmaları.  
🔹 **Sosyal Medya:** Kullanıcıların ilgi alanlarına göre içerik önerme.  

### Makine Öğrenmesi Türleri  

Makine öğrenmesi, öğrenme yöntemine bağlı olarak üç ana türe ayrılır:  

#### 🏷 1. Denetimli Öğrenme (Supervised Learning)  
Denetimli öğrenmede model, etiketli (labeled) veri seti üzerinde eğitilir. Model, giriş ve çıkış verileri arasındaki ilişkileri öğrenir.  

📌 **Örnek:**  
- E-postaların spam olup olmadığını belirleme (etiketler: spam / spam değil).  
- Bir evin fiyatını, oda sayısı ve lokasyon gibi özelliklere bağlı olarak tahmin etme.  

```python
from sklearn.linear_model import LinearRegression
import numpy as np

# Örnek veri seti (metrekare ve fiyat)
X = np.array([[50], [60], [70], [80], [90]])  # Metrekare cinsinden ev büyüklüğü
y = np.array([100000, 120000, 140000, 160000, 180000])  # Ev fiyatları

# Modelin eğitilmesi
model = LinearRegression()
model.fit(X, y)

# 75 metrekarelik bir evin fiyatını tahmin etme
print("Tahmin edilen fiyat:", model.predict([[75]]))
```

#### 🔍 2. Denetimsiz Öğrenme (Unsupervised Learning)  
Denetimsiz öğrenmede, verilerde etiketler bulunmaz. Model, verinin iç yapısını keşfetmeye çalışır.  

📌 **Örnek:**  
- Müşteri segmentasyonu (benzer satın alma alışkanlıklarına sahip müşterileri gruplama).  
- Anomali tespiti (örneğin kredi kartı dolandırıcılığı tespiti).  

```python
from sklearn.cluster import KMeans
import numpy as np

# Örnek müşteri verisi (alışveriş harcamaları)
X = np.array([[100, 200], [400, 500], [50, 80], [500, 600], [300, 400]])

# K-means ile 2 kümeye ayırma
kmeans = KMeans(n_clusters=2)
kmeans.fit(X)

# Küme etiketlerini yazdır
print("Müşteri kümeleri:", kmeans.labels_)
```

#### 🔄 3. Yarı Denetimli Öğrenme (Semi-Supervised Learning)  
Bu yöntem, hem etiketli hem de etiketsiz verileri kullanarak öğrenir. Etiketli veri az olduğunda ancak etiketsiz veri fazla olduğunda kullanılır.  

📌 **Örnek:**  
- Büyük bir veri setindeki az miktarda etiketli veriyle konuşma tanıma sistemlerinin eğitilmesi.  
- Web sitelerindeki yorumların "olumlu" ya da "olumsuz" olarak sınıflandırılması.  

---

## 13.2 Makine Öğrenmesi Temelleri  

Makine öğrenmesi modellerinin başarısı, verinin doğru hazırlanmasına ve modellenmesine bağlıdır.  

### Eğitim ve Test Veri Setleri  

Veri setleri genellikle üçe ayrılır:  

1️⃣ **Eğitim Seti (Training Set)**: Modelin öğrenmesini sağlamak için kullanılır.  
2️⃣ **Test Seti (Test Set)**: Modelin performansını değerlendirmek için kullanılır.  
3️⃣ **Doğrulama Seti (Validation Set)**: Modelin hiperparametrelerini optimize etmek için kullanılır.  

### Özellikler (Features) ve Etiketler (Labels)  

- **Özellikler (Features):** Modelin öğrenmesi için kullanılan bağımsız değişkenlerdir. Örneğin, bir evin fiyatını tahmin etmek için evin metrekare büyüklüğü, oda sayısı gibi faktörler birer özelliktir.  
- **Etiketler (Labels):** Modelin tahmin etmeye çalıştığı bağımlı değişkendir. Örneğin, ev fiyatı bir etikettir.  

### Veri Ön İşleme ve Temizlik  

Veri bilimi projelerinde verilerin işlenmesi, modelin başarısını doğrudan etkiler. Veri temizleme süreci şunları içerir:  

✔ Eksik değerlerin doldurulması veya çıkarılması.  
✔ Aykırı değerlerin tespiti ve düzeltilmesi.  
✔ Verilerin ölçeklendirilmesi (Normalization, Standardization).  
✔ Kategorik değişkenlerin sayısal hale getirilmesi (One-Hot Encoding).  

```python
import pandas as pd
from sklearn.preprocessing import StandardScaler

# Örnek veri seti
df = pd.DataFrame({'yaş': [20, 25, 30, 35, 40], 'maaş': [2000, 2500, 3000, 4000, 5000]})

# Verilerin ölçeklendirilmesi
scaler = StandardScaler()
df_scaled = scaler.fit_transform(df)

print("Ölçeklendirilmiş veri:\n", df_scaled)
```

### Özellik Mühendisliği  

Özellik mühendisliği, modelin performansını artırmak için yeni özellikler oluşturmaktır.  

📌 **Örnek:**  
- Bir e-ticaret sitesinde, kullanıcının en son alışveriş yaptığı zamana dayalı olarak "aktif kullanıcı" özelliği ekleme.  
- Zaman serisi verilerinde geçmiş trendlere dayalı yeni değişkenler oluşturma.  

---

## 13.3 Denetimli Öğrenme  

Denetimli öğrenme, makine öğrenmesinin bir alt dalıdır ve bu yöntemde model, etiketli verilerle eğitilir. Etiketli veri, giriş verileriyle birlikte bilinen sonuçları içeren veri setleridir. Bu süreç, modelin öğrenmesini ve doğru tahminler yapmasını sağlamak için kullanılır. Denetimli öğrenme genellikle iki ana problem türü üzerinde çalışır: sınıflandırma ve regresyon.  

### Sınıflandırma Problemleri  

Sınıflandırma problemleri, belirli sınıflara ait olan verileri tahmin etmek için kullanılır. Örneğin, bir e-postanın spam olup olmadığını belirlemek bir sınıflandırma problemidir. 📨 İşte en yaygın kullanılan sınıflandırma algoritmaları:  

- **Lojistik Regresyon:** Lojistik regresyon, ikili sınıflandırma problemlerinde kullanılır. Giriş özelliklerinin bir lineer kombinasyonu olarak bir olasılık tahmini yapar ve bu olasılığı bir sigmoid fonksiyonu ile dönüştürerek sonucu [0, 1] aralığına çeker. 

  ```python
  from sklearn.linear_model import LogisticRegression

  # Lojistik regresyon modeli oluşturma
  model = LogisticRegression()
  model.fit(X_train, y_train)  # Modeli eğitim verisi ile eğitme
  predictions = model.predict(X_test)  # Tahmin yapma
  ```

- **Karar Ağaçları:** Karar ağaçları, veriyi belirli özelliklere göre bölerek sınıflandırma yapan bir modeldir. Her dal, bir özelliği temsil eder ve yaprak düğümleri, sonuç sınıflarını gösterir. Anlaşılır ve yorumlanabilir olması nedeniyle sıklıkla kullanılır. 

  ```python
  from sklearn.tree import DecisionTreeClassifier

  # Karar ağaçları modeli oluşturma
  model = DecisionTreeClassifier()
  model.fit(X_train, y_train)
  predictions = model.predict(X_test)
  ```

- **Destek Vektör Makineleri (SVM):** SVM, verileri sınıflandırmak için en uygun ayrım çizgisini bulur. Bu çizgi, farklı sınıflar arasındaki en büyük marjini sağlamak için belirlenir. Özellikle yüksek boyutlu verilerde etkili bir sınıflandırma sağlar.

  ```python
  from sklearn.svm import SVC

  # SVM modeli oluşturma
  model = SVC(kernel='linear')  # Doğrusal çekirdek
  model.fit(X_train, y_train)
  predictions = model.predict(X_test)
  ```

- **K-Nearest Neighbors (KNN):** KNN, sınıflandırma yaparken, tahmin edilen örneğin komşularının sınıf bilgilerini kullanır. Belirli bir k değerine göre, en yakın k komşunun çoğunluğuna göre sınıf tahmini yapılır.

  ```python
  from sklearn.neighbors import KNeighborsClassifier

  # KNN modeli oluşturma
  model = KNeighborsClassifier(n_neighbors=3)  # K değeri
  model.fit(X_train, y_train)
  predictions = model.predict(X_test)
  ```

- **Naive Bayes:** Naive Bayes, olasılıklara dayalı bir sınıflandırma algoritmasıdır. Özelliklerin bağımsız olduğunu varsayarak çalışır ve her özelliğin, sınıfın belirlenmesine katkısını değerlendirir. Genellikle metin sınıflandırma ve spam tespiti gibi alanlarda kullanılır. 

  ```python
  from sklearn.naive_bayes import GaussianNB

  # Naive Bayes modeli oluşturma
  model = GaussianNB()
  model.fit(X_train, y_train)
  predictions = model.predict(X_test)
  ```

### Regresyon Problemleri  

Regresyon problemleri, sürekli bir değeri tahmin etmek için kullanılır. Örneğin, bir evin fiyatını tahmin etmek bir regresyon problemidir. İşte yaygın regresyon algoritmaları:  

- **Doğrusal Regresyon:** Doğrusal regresyon, bağımsız değişkenlerle bağımlı değişken arasındaki doğrusal ilişkiyi modellemek için kullanılır. Bu model, verilere en uygun düz bir çizgi çizer.  

  ```python
  from sklearn.linear_model import LinearRegression

  # Doğrusal regresyon modeli oluşturma
  model = LinearRegression()
  model.fit(X_train, y_train)
  predictions = model.predict(X_test)
  ```

- **Polinomsal Regresyon:** Polinomsal regresyon, doğrusal regresyondan daha karmaşık bir ilişkiyi modellemek için kullanılır. Bağımsız değişkenlerin yüksek dereceli polinomlarını kullanarak daha esnek bir model oluşturur.  

  ```python
  from sklearn.preprocessing import PolynomialFeatures
  from sklearn.linear_model import LinearRegression

  # Polinomsal özellikler oluşturma
  poly = PolynomialFeatures(degree=2)  # 2. derece polinom
  X_poly = poly.fit_transform(X_train)

  # Polinomsal regresyon modeli oluşturma
  model = LinearRegression()
  model.fit(X_poly, y_train)
  predictions = model.predict(poly.transform(X_test))
  ```

- **Ridge ve Lasso Regresyon:** Ridge ve Lasso, düzenlileştirilmiş regresyon teknikleridir. Ridge regresyon, modelin karmaşıklığını azaltmak için L2 normu kullanırken, Lasso regresyonu L1 normunu kullanarak bazı katsayıları sıfırlayabilir. Bu özellik, modelin genel performansını artırır ve aşırı öğrenmeyi engeller.  

  ```python
  from sklearn.linear_model import Ridge, Lasso

  # Ridge regresyon modeli oluşturma
  ridge_model = Ridge(alpha=1.0)  # Alpha, düzenlileştirme parametresi
  ridge_model.fit(X_train, y_train)

  # Lasso regresyon modeli oluşturma
  lasso_model = Lasso(alpha=0.1)
  lasso_model.fit(X_train, y_train)
  ```

Bu algoritmalar, veri analizi ve makine öğrenmesi projelerinde yaygın olarak kullanılır ve farklı uygulama alanlarında güçlü sonuçlar elde etmeyi sağlar. Doğru algoritmanın seçimi, veri kümesinin özelliklerine ve problemin doğasına bağlıdır.

---

## 13.4 Denetimsiz Öğrenme  

Denetimsiz öğrenme, makine öğrenmesinin bir dalı olup, veri kümesi üzerinde etiketlenmemiş verilerle çalışır. Bu durumda, model, verinin iç yapısını anlamaya çalışır ve doğal gruplar veya desenler bulur. Denetimsiz öğrenme genellikle iki ana yöntemle gerçekleştirilir: kümeleme ve boyut indirgeme.  

### Kümeleme (Clustering)  

Kümeleme, benzer özelliklere sahip verilerin gruplar halinde organize edilmesini sağlar. Bu yöntem, veri kümesinin yapısını anlamak ve verileri gruplamak için kullanılır. İşte yaygın kümeleme algoritmaları:  

- **K-Means:** K-Means, en yaygın kümeleme algoritmalarından biridir. Bu algoritma, veri kümesini K sayıda kümeye böler. İlk olarak, K tane rastgele merkez seçilir ve ardından her veri noktası en yakın merkeze atanır. Merkezler güncellenir ve süreç, merkezler değişmeyene kadar tekrarlanır. K-Means, hız ve verimlilik açısından oldukça etkilidir, ancak K sayısının önceden belirlenmesi gerekmektedir.

  ```python
  from sklearn.cluster import KMeans
  import matplotlib.pyplot as plt

  # K-Means modeli oluşturma
  kmeans = KMeans(n_clusters=3)  # 3 kümeye ayırma
  kmeans.fit(X)  # X, veri kümesi

  # Küme merkezlerini ve etiketleri alma
  centers = kmeans.cluster_centers_
  labels = kmeans.labels_

  # Kümeleme sonuçlarını görselleştirme
  plt.scatter(X[:, 0], X[:, 1], c=labels)
  plt.scatter(centers[:, 0], centers[:, 1], color='red', marker='X')  # Merkezler
  plt.show()
  ```

- **Hierarchical Clustering:** Hiyerarşik kümeleme, verileri bir ağaç yapısı şeklinde organize eder. Bu yöntem, verilerin benzerliğine göre, alt kümeler oluşturur ve bu alt kümeleri daha büyük kümelere birleştirir. İki ana yaklaşım vardır: agglomeratif (aşağıdan yukarıya) ve divisive (yukarıdan aşağıya).

  ```python
  from scipy.cluster.hierarchy import dendrogram, linkage
  import matplotlib.pyplot as plt

  # Hiyerarşik kümeleme
  Z = linkage(X, method='ward')  # Ward metodu
  dendrogram(Z)  # Dendrogram çizimi
  plt.show()
  ```

- **DBSCAN:** DBSCAN, yoğunluk tabanlı bir kümeleme algoritmasıdır. Verinin yoğun olduğu bölgeleri bulur ve bu bölgelerdeki noktaları kümelere ayırır. Ayrıca, gürültü ve anomali tespiti için de etkilidir. K-Means’in aksine, DBSCAN küme sayısını önceden belirlemez, bu da onu daha esnek kılar.

  ```python
  from sklearn.cluster import DBSCAN

  # DBSCAN modeli oluşturma
  dbscan = DBSCAN(eps=0.5, min_samples=5)  # eps, komşuluk yarıçapı
  labels = dbscan.fit_predict(X)  # Küme etiketlerini alma
  ```

### Boyut İndirgeme (Dimensionality Reduction)  

Boyut indirgeme, yüksek boyutlu verilerin daha düşük boyutlu bir temsilini oluşturmak için kullanılır. Bu, verinin daha kolay görselleştirilmesi ve analiz edilmesi açısından önemlidir. İşte iki yaygın boyut indirgeme yöntemi:  

- **Principal Component Analysis (PCA):** PCA, verinin en fazla varyansını temsil eden bileşenleri bulur. Bu bileşenler, orijinal veri kümesinin daha düşük boyutlu bir temsilini sağlar. PCA, genellikle veri ön işleme ve görselleştirme aşamalarında kullanılır.

  ```python
  from sklearn.decomposition import PCA

  # PCA ile boyut indirgeme
  pca = PCA(n_components=2)  # 2 boyuta indirgeme
  X_reduced = pca.fit_transform(X)  # Veri dönüşümü
  ```

- **t-Distributed Stochastic Neighbor Embedding (t-SNE):** t-SNE, özellikle yüksek boyutlu verilerin görselleştirilmesi için etkili bir yöntemdir. Bu teknik, verinin yapısını koruyarak benzer veri noktalarını yakınlaştırır ve yüksek boyutlu verileri daha düşük boyutlara indirger.

  ```python
  from sklearn.manifold import TSNE

  # t-SNE ile boyut indirgeme
  tsne = TSNE(n_components=2)
  X_tsne = tsne.fit_transform(X)  # Veri dönüşümü
  ```

### Anomali Tespiti (Anomaly Detection)  

Anomali tespiti, normal dağılımdan sapmalar gösteren verilerin belirlenmesini sağlar. Bu, dolandırıcılık tespiti, ağ güvenliği ve sağlık alanlarında önemli bir rol oynar. Anomali tespiti için çeşitli yöntemler kullanılabilir, bunlar arasında istatistiksel yöntemler, denetimsiz öğrenme teknikleri ve makine öğrenmesi algoritmaları bulunur. Örneğin, bir veri kümesindeki belirli bir eşiğin altındaki veya üstündeki değerler anomali olarak kabul edilebilir.

```python
from sklearn.ensemble import IsolationForest

# Anomali tespiti için Isolation Forest kullanma
model = IsolationForest(contamination=0.1)  # Anomali oranı
model.fit(X)  # Modeli eğitme
predictions = model.predict(X)  # Tahmin yapma
```

Denetimsiz öğrenme, veri kümesinin doğal yapısını keşfetmek ve veriler arasındaki ilişkileri anlamak için güçlü bir araçtır. Bu yöntemler, veri analizi ve makine öğrenmesi projelerinde önemli rol oynar.

---

## 13.6 Derin Öğrenme  

Derin öğrenme, makine öğrenmesinin bir alt dalıdır ve karmaşık verileri modellemek için çok katmanlı yapay sinir ağları kullanır. Bu yöntem, büyük veri kümeleri ile etkili bir şekilde çalışabilmesi ve yüksek doğrulukta sonuçlar verebilmesi nedeniyle son yıllarda popülerlik kazanmıştır. 

### Yapay Sinir Ağları (Artificial Neural Networks, ANN)  

Yapay sinir ağları, biyolojik sinir ağlarından esinlenerek geliştirilmiş matematiksel modellerdir. ANN'ler, birbirine bağlı nöronlar (düğüm noktaları) ile oluşturulmuş katmanlardan oluşur. Bu ağlar, girdi verilerini alır, işleyerek çıktı üretir. Sinir ağları, özellikle karmaşık veri setlerini öğrenme yetenekleri sayesinde çok sayıda uygulama alanında kullanılır.

### Konvolüsyonel Sinir Ağları (Convolutional Neural Networks, CNN)  

CNN'ler, özellikle görüntü işleme ve bilgisayarla görme alanlarında etkili olan bir yapay sinir ağı türüdür. Konvolüsyonel katmanlar, girdi verilerindeki özellikleri çıkarmak için filtreler (kernel) kullanarak çalışır. Bu yöntem, görüntülerdeki nesneleri ve desenleri tanımak için idealdir.  

- **CNN Mimarileri ve Katmanları:** Tipik bir CNN mimarisi, konvolüsyon katmanları, havuzlama katmanları (pooling), ve tam bağlantılı katmanlardan oluşur. Konvolüsyon katmanları, giriş verilerinden özellikleri çıkarmak için kullanılırken, havuzlama katmanları, veri boyutunu azaltarak işlem süresini kısaltır.

- **Uygulama Alanları:** CNN'ler, görüntü tanıma (örneğin, yüz tanıma) ve nesne tespiti (örneğin, otonom araçlarda nesne algılama) gibi alanlarda yaygın olarak kullanılır. Aşağıda basit bir CNN örneği verilmiştir:  

```python
import tensorflow as tf
from tensorflow.keras import layers, models

# CNN modeli oluşturma
model = models.Sequential()
model.add(layers.Conv2D(32, (3, 3), activation='relu', input_shape=(64, 64, 3)))  # Konvolüsyon katmanı
model.add(layers.MaxPooling2D((2, 2)))  # Havuzlama katmanı
model.add(layers.Flatten())  # Veriyi düzleştirme
model.add(layers.Dense(64, activation='relu'))  # Tam bağlantılı katman
model.add(layers.Dense(10, activation='softmax'))  # Çıktı katmanı

model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
```

### Tekrarlayan Sinir Ağları (Recurrent Neural Networks, RNN)  

RNN'ler, ardışık verilerle (zaman serisi verileri, metin gibi) çalışmak için tasarlanmış bir yapay sinir ağı türüdür. RNN'ler, geçmiş bilgileri hatırlama yetenekleri sayesinde zaman bağımlılığı olan verileri analiz edebilir.

- **LSTM ve GRU Hücreleri:** LSTM (Long Short-Term Memory) ve GRU (Gated Recurrent Unit), RNN'lerin gelişmiş sürümleridir. Bu yapılar, uzun dönemli bağımlılıkları öğrenmek için daha etkilidir. LSTM'ler, hücre durumlarını ve kapı mekanizmalarını kullanarak bilgiyi korur veya unutur. GRU'lar ise daha basit bir yapıya sahiptir ve LSTM'lere benzer şekilde çalışır.  

- **Uygulama Alanları:** RNN'ler, doğal dil işleme (örneğin, dil modelleme, makine çevirisi) ve zaman serisi analizi (örneğin, borsa fiyat tahmini) gibi alanlarda kullanılır. Aşağıda bir LSTM modeli örneği verilmiştir:  

```python
from tensorflow.keras import layers, models

# LSTM modeli oluşturma
model = models.Sequential()
model.add(layers.LSTM(50, input_shape=(timesteps, features)))  # LSTM katmanı
model.add(layers.Dense(1))  # Çıktı katmanı

model.compile(optimizer='adam', loss='mean_squared_error')
```

### Generative Adversarial Networks (GANs)  

GAN'ler, bir generatif model ve bir diskriminatif model içeren iki aşamalı bir yapıdır. Bu iki model, birbirlerine karşı yarışır; generatif model, gerçek verilere benzer yeni veriler üretmeye çalışırken, diskriminatif model ise gerçek verileri sahte verilerden ayırt etmeye çalışır. Bu rekabet, zamanla generatif modelin daha kaliteli veriler üretmesine neden olur.

GAN'ler, görüntü, ses ve video gibi çeşitli veri türlerini üretmek için kullanılabilir. Örneğin, GAN'ler, yeni sanat eserleri veya fotoğraflar yaratmak için kullanılabilir. Aşağıda basit bir GAN yapısı verilmiştir:  

```python
from tensorflow.keras import layers, models

# Generator model
generator = models.Sequential()
generator.add(layers.Dense(128, activation='relu', input_shape=(noise_dim,)))  # Giriş gürültüsü
generator.add(layers.Dense(784, activation='sigmoid'))  # Çıkış (örneğin, 28x28 boyutunda görüntü)

# Discriminator model
discriminator = models.Sequential()
discriminator.add(layers.Dense(128, activation='relu', input_shape=(784,)))  # Girdi (28x28 görüntü)
discriminator.add(layers.Dense(1, activation='sigmoid'))  # Çıktı (gerçek/sahte)

# GAN modeli
gan = models.Sequential([generator, discriminator])
```

Derin öğrenme, karmaşık verileri anlamak ve analiz etmek için etkili bir yöntem sunar. Bu alan, makine öğrenmesinin en heyecan verici ve hızlı gelişen bölümlerinden biridir ve görüntü işleme, doğal dil işleme ve daha birçok alanda devrim yaratmıştır.

---

## 13.7 Model Değerlendirme ve Seçim  

Model değerlendirme, bir makine öğrenmesi modelinin başarısını ölçmek için kullanılan teknikler ve yöntemler bütünüdür. Doğru değerlendirme ve seçim, başarılı bir model geliştirmek için kritik öneme sahiptir.

### Model Performans Ölçütleri  

Modelin performansını değerlendirmek için çeşitli ölçütler kullanılır. Bu ölçütler, modelin tahminlerinin ne kadar doğru olduğunu anlamaya yardımcı olur:  

- **Doğruluk (Accuracy):** Modelin doğru tahminlerinin, toplam tahminlere oranını gösterir. Yüksek doğruluk, modelin genel başarısını gösterir, ancak dengesiz veri setlerinde yanıltıcı olabilir.  

- **Kesinlik (Precision):** Modelin pozitif sınıf olarak tahmin ettiği örneklerin ne kadarının gerçekten pozitif olduğunu ölçer. Yüksek kesinlik, yanlış pozitif oranını azaltmaya yardımcı olur.  

- **Duyarlılık (Recall):** Gerçek pozitif örneklerin ne kadarının model tarafından doğru tahmin edildiğini gösterir. Yüksek duyarlılık, yanlış negatif oranını azaltır.  

- **F1 Skoru:** Kesinlik ve duyarlılığı bir araya getirerek her iki ölçütün dengeli bir şekilde değerlendirilmesine olanak tanır. Özellikle dengesiz veri setlerinde önemli bir ölçüttür.  

- **ROC (Receiver Operating Characteristic) Eğrisi ve AUC (Area Under Curve):** ROC eğrisi, modelin farklı eşik değerleri için doğru pozitif oranını (TPR) ve yanlış pozitif oranını (FPR) gösterir. AUC, ROC eğrisinin altındaki alanı ölçerek modelin genel başarısını değerlendirir. AUC değeri 0.5 ile 1 arasında değişir; 1, mükemmel bir model iken, 0.5, rastgele tahmin eder. 

### Çapraz Doğrulama (Cross-Validation)  

Çapraz doğrulama, modelin doğruluğunu artırmak için kullanılan bir tekniktir. Bu yöntem, veri kümesini farklı alt gruplara ayırarak modelin eğitim ve test edilmesine olanak tanır. Yaygın olarak kullanılan k-katlı çapraz doğrulama, veri kümesinin k parçaya bölündüğü ve her bir parçanın sırasıyla test seti olarak kullanıldığı bir yöntemdir. Bu şekilde, modelin genelleme yeteneği daha iyi değerlendirilir.

```python
from sklearn.model_selection import cross_val_score
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier()
scores = cross_val_score(model, X, y, cv=5)  # 5-katlı çapraz doğrulama
print("Çapraz Doğrulama Skorları:", scores)
```

### Overfitting ve Underfitting  

- **Overfitting:** Modelin eğitim verisine aşırı uyum sağlaması durumudur. Model, eğitim setindeki gürültüyü ve hataları öğrenir ve bu da genel performansını düşürür. Overfitting'i önlemek için düzenleme teknikleri ve daha fazla veri kullanılabilir.  

- **Underfitting:** Modelin eğitim verisini yeterince öğrenmemesi durumudur. Model basit kalır ve karmaşık ilişkileri yakalayamaz. Yetersiz özellikler veya çok basit bir model kullanımı underfitting'e yol açabilir. 

### Hiperparametre Ayarı (Hyperparameter Tuning)  

Hiperparametreler, modelin öğrenme sürecini kontrol eden ve eğitim öncesinde ayarlanması gereken parametrelerdir. Hiperparametre ayarı, modelin performansını artırmak için önemlidir. En yaygın yöntemlerden bazıları şunlardır:  

- **Grid Search:** Belirli bir hiperparametre aralığında en iyi modeli bulmak için sistematik bir yaklaşım kullanır. Her bir kombinasyon için model eğitilir ve sonuçlar karşılaştırılır.  

- **Random Search:** Hiperparametre alanını rastgele arayarak en iyi modelin bulunmasını sağlar. Bu yöntem, özellikle büyük parametre uzaylarında daha etkilidir.  

- **Bayesian Optimization:** Hiperparametrelerin değerlerini belirlemek için probabilistik bir model kullanarak daha verimli bir arama gerçekleştirir.

Aşağıda basit bir grid search örneği verilmiştir:  

```python
from sklearn.model_selection import GridSearchCV
from sklearn.ensemble import RandomForestClassifier

param_grid = {'n_estimators': [50, 100, 200], 'max_depth': [None, 10, 20]}
grid_search = GridSearchCV(RandomForestClassifier(), param_grid, cv=5)
grid_search.fit(X_train, y_train)

print("En iyi hiperparametreler:", grid_search.best_params_)
```

Model değerlendirme ve seçim süreci, başarılı bir makine öğrenmesi projesinin temel taşlarından biridir. Doğru yöntem ve ölçütlerin kullanılması, daha iyi sonuçlar elde etmeye yardımcı olur.

---

## 13.8 Modelin Dağıtımı ve Uygulama  

Modelin dağıtımı, eğitilen bir makine öğrenmesi modelinin gerçek dünya uygulamalarında kullanılabilmesi için gerekli olan süreçtir. Bu aşama, modelin kullanıma hazır hale getirilmesi, entegrasyonu ve performansının izlenmesini içerir. 

### Modelin Dağıtımı ve Entegrasyonu  

Modelin dağıtımı, genellikle bir sunucu ortamında veya bulut platformunda gerçekleştirilir. Bu süreçte aşağıdaki adımlar izlenir:  

1. **Modelin İhracı:** Eğitimden sonra modelin, kullanılabilir bir formatta (örneğin, pickle veya joblib gibi) kaydedilmesi gerekir. Bu, modelin daha sonra yüklenebilmesi için önemlidir.  
   
   ```python
   import joblib

   # Modeli kaydetme
   joblib.dump(model, 'model.pkl')
   ```

2. **Sunucu Ortamı Kurulumu:** Modelin çalışacağı bir sunucu ortamı hazırlanır. Bu ortam, modelin çalışabilmesi için gerekli kütüphanelerin ve bağımlılıkların yüklü olduğu bir altyapıdır.  

3. **Entegrasyon:** Model, mevcut uygulama veya sistemle entegre edilerek kullanıma sunulur. Bu entegrasyon, genellikle bir API (Uygulama Programlama Arayüzü) üzerinden gerçekleştirilir.  

### Model Servisleri ve API'ler  

Model servisleri, kullanıcıların modelle etkileşimde bulunmasını sağlamak için kullanılır. Bir API aracılığıyla, dış sistemlerin veya uygulamaların modelle veri gönderip almasını mümkün kılar. Yaygın kullanılan araçlardan bazıları:  

- **Flask:** Python tabanlı, hafif bir web çerçevesidir ve makine öğrenmesi modellerini kolayca bir API olarak dağıtmak için idealdir.  

- **FastAPI:** Modern, hızlı (yüksek performanslı) bir web çerçevesidir ve asenkron programlama desteği ile hız sağlar.  

```python
from flask import Flask, request, jsonify
import joblib

app = Flask(__name__)
model = joblib.load('model.pkl')  # Modeli yükle

@app.route('/predict', methods=['POST'])
def predict():
    data = request.get_json(force=True)  # JSON verisini al
    prediction = model.predict([data['features']])  # Tahmin yap
    return jsonify({'prediction': prediction.tolist()})  # Sonucu JSON olarak döndür

if __name__ == '__main__':
    app.run(debug=True)
```

### Gerçek Zamanlı ve Batch İşleme  

Modeller, uygulamalarda genellikle iki farklı işleme türü ile kullanılır:  

1. **Gerçek Zamanlı İşleme:** Kullanıcılardan gelen veriler anlık olarak işlenir ve sonuçlar hemen döndürülür. Örneğin, bir öneri sistemi kullanıcının tercihlerine anlık olarak yanıt verir.  

2. **Batch İşleme:** Veriler belirli zaman dilimlerinde toplanır ve topluca işlenir. Bu yöntem, büyük veri setleriyle çalışırken daha verimli olabilir ve genellikle planlı süreçlerde kullanılır. Örneğin, günlük raporlama veya haftalık analizlerde batch işleme tercih edilebilir.  

---

## 13.9 Python Kütüphaneleri ve Araçları  

Python, makine öğrenmesi ve veri bilimi için birçok güçlü kütüphaneye sahiptir. Bu kütüphaneler, veri işleme, model oluşturma ve sonuçların görselleştirilmesi gibi birçok aşamada yardımcı olur.

### NumPy ve Pandas ile Veri İşleme  

- **NumPy:** Sayısal hesaplamalar için temel bir kütüphanedir. N-dimensional array (N boyutlu diziler) yapılarını kullanarak matematiksel işlemleri hızlandırır.  
- **Pandas:** Veri analizi ve manipülasyonu için güçlü bir kütüphanedir. DataFrame yapısı ile veri setlerini kolayca işler ve analiz eder.  

### Scikit-Learn ile Makine Öğrenmesi  

**Scikit-Learn**, makine öğrenmesi uygulamaları için yaygın olarak kullanılan bir Python kütüphanesidir. Denetimli ve denetimsiz öğrenme algoritmalarını içerir ve model değerlendirme, hiperparametre ayarı gibi birçok araç sunar. Kullanımı oldukça basittir ve geniş bir dokümantasyona sahiptir.  

### TensorFlow ve Keras ile Derin Öğrenme  

- **TensorFlow:** Google tarafından geliştirilen, büyük ölçekli makine öğrenmesi ve derin öğrenme uygulamaları için bir kütüphanedir. Karmaşık yapay sinir ağları oluşturmak için kullanılır.  
- **Keras:** TensorFlow'un üstünde çalışan yüksek seviyeli bir API'dir. Kullanıcı dostu arayüzü sayesinde derin öğrenme modellerinin hızlıca geliştirilmesine olanak tanır.  

### PyTorch ile Derin Öğrenme  

**PyTorch**, Facebook tarafından geliştirilmiş bir derin öğrenme kütüphanesidir. Dinamik grafik yapısı sayesinde, model geliştirme sürecinde daha fazla esneklik sunar. Araştırma ve uygulama alanlarında yaygın olarak kullanılmaktadır.  

### XGBoost ve LightGBM ile Hızlandırılmış Öğrenme  

- **XGBoost:** Hızlı ve verimli bir boosting algoritmasıdır. Performansı artırmak için birçok optimizasyon ve düzenleme tekniği sunar. Genellikle yarışmalarda sıklıkla tercih edilir.  
- **LightGBM:** Microsoft tarafından geliştirilen bir başka boosting algoritmasıdır. Büyük veri setleri üzerinde daha hızlı sonuçlar almak için tasarlanmıştır ve yüksek verimlilik sağlar.  

Bu kütüphaneler, makine öğrenmesi ve veri bilimi projelerinde etkili bir şekilde kullanılabilir ve başarıyla uygulama geliştirme sürecini hızlandırabilir.

---

## 13.10 Yapay Zeka ve Etik  

Yapay zeka (YZ), birçok fayda sağlasa da beraberinde bazı etik sorunlar ve zorluklar da getirir. Bu nedenle, YZ sistemlerinin tasarımı ve uygulanması sırasında etik kaygılar göz önünde bulundurulmalıdır.

### Yapay Zekanın Etik Sorunları  

Yapay zeka uygulamaları, karar verme süreçlerinde insan müdahalesini azalttığı için çeşitli etik sorunları gündeme getirmektedir. Örneğin, bir YZ sistemi bir kişiyi işten çıkaracak bir karar veriyorsa, bu kararın nasıl alındığı, hangi verilere dayandığı ve bu süreçte insan faktörünün nasıl göz önünde bulundurulduğu önemlidir. Etik sorunlar arasında ayrımcılık, insan hakları ihlalleri ve hesap verebilirlik gibi konular yer alır.  

### Veri Gizliliği ve Güvenlik  

Yapay zeka sistemleri genellikle büyük miktarda veriye ihtiyaç duyar. Bu veriler, kullanıcıların özel bilgilerini içerebilir ve bu durum veri gizliliği endişelerini beraberinde getirir. Kişisel verilerin nasıl toplandığı, saklandığı ve kullanıldığı konusunda şeffaflık sağlanmalıdır. Ayrıca, YZ sistemlerinin güvenliği de büyük önem taşır; zayıf noktalar, kötü niyetli saldırılara yol açabilir.  

### Yapay Zeka Sistemlerinin Adalet ve Şeffaflığı  

Yapay zeka sistemlerinin kararları genellikle karmaşık algoritmalarla belirlenir. Bu nedenle, bu sistemlerin adil ve şeffaf bir şekilde çalıştığından emin olunması gerekir. Adalet, sistemlerin belirli gruplara karşı ayrımcılık yapmadığından ve tüm bireyleri eşit şekilde değerlendirdiğinden emin olmak için önemlidir. Şeffaflık ise, kullanıcıların sistemin nasıl çalıştığını anlamalarına ve algoritmaların karar verme süreçlerini sorgulamalarına olanak tanır.

---

## 13.11 İleri Düzey Konular ve Araştırmalar  

Yapay zeka alanında sürekli bir gelişim ve araştırma süreci yaşanmaktadır. Bu nedenle, ileri düzey konular ve araştırma alanları, YZ'nin gelecekteki yönelimleri ve potansiyeli hakkında önemli bilgiler sunmaktadır.  

### Güçlü Yapay Zeka (AGI) ve Zayıf Yapay Zeka (Narrow AI)  

- **Güçlü Yapay Zeka (AGI):** İnsan benzeri genel zeka yeteneklerine sahip olan bir yapay zeka türüdür. AGI, farklı görevleri anlayıp gerçekleştirebilme kapasitesine sahip olmalıdır. Yani, genel bir zeka düzeyine ulaşmayı hedefler.  
- **Zayıf Yapay Zeka (Narrow AI):** Belirli bir görev veya problem üzerinde uzmanlaşmış YZ sistemlerini ifade eder. Örneğin, bir dil çevirmeni veya görüntü tanıma sistemi gibi. Zayıf YZ, belirli alanlarda yüksek performans sergiler, ancak genel zeka yetenekleri yoktur.  

### Yapay Zeka ve Robotik  

Yapay zeka ve robotik arasındaki ilişki, otonom sistemlerin gelişiminde büyük önem taşır. YZ, robotlara öğrenme, algılama ve karar verme yetenekleri kazandırarak, karmaşık görevleri yerine getirebilmelerini sağlar. Örneğin, otomatik sürüş sistemleri, YZ kullanarak çevresini algılar ve güvenli bir şekilde yol alır.

### Yapay Zeka Araştırma Yönelimleri ve Trendler  

Yapay zeka alanındaki araştırmalar, genellikle aşağıdaki yönelimlere odaklanmaktadır:  

- **Derin Öğrenme:** Yeni mimarilerin geliştirilmesi ve daha etkili modellerin oluşturulması üzerine çalışmalar.  
- **Doğa Dili İşleme (NLP):** İnsan dilinin anlaşılması ve işlenmesi için yeni tekniklerin geliştirilmesi.  
- **Otonom Sistemler:** Otonom araçlar ve robotlar üzerine araştırmalar.  
- **Güvenli ve Şeffaf YZ:** Yapay zeka sistemlerinin güvenliği ve şeffaflığı üzerine çalışmalar.  

Bu alanlar, yapay zekanın gelişiminde kritik öneme sahip olup, gelecekteki uygulamaları ve potansiyeli belirleyecektir.