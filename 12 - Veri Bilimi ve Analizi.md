## 📌 12.1 Veri Bilimine Giriş

Veri bilimi, geniş bir veri kümesinden anlamlı bilgilerin çıkarılması için çeşitli teknikler ve yöntemler kullanan bir disiplindir. Temel olarak, veri analizi ve istatistikten makine öğrenimine kadar birçok alana yayılmaktadır.

### ✅ **Veri Bilimi Nedir ve Temel Kavramlar**

- **Veri Bilimi**: Disiplinler arası bir alan olup, veri analizi, istatistik ve bilgi teknolojilerini bir araya getirir. Veri bilimi, verileri analiz ederek karar alma süreçlerine katkıda bulunur.
- **Temel Kavramlar**:
  - **Veri**: Çeşitli biçimlerde (sayısal, metin, görsel vb.) bulunan bilgiler.
  - **Modelleme**: Verilerin anlamlı bir şekilde yapılandırılması için kullanılan teknikler.
  - **Makine Öğrenimi**: Bilgisayarlara verilerden öğrenme yeteneği kazandırma süreci.

---

### ✅ **Veri Biliminin Uygulama Alanları**

Veri bilimi, birçok sektörde kullanılmaktadır:
- **Finans**: Risk analizi, piyasa trendlerinin tahmini.
- **Pazarlama**: Müşteri davranışlarının analizi, hedef kitle oluşturma.
- **Sağlık**: Hastalık tahminleri, tedavi sonuçlarının değerlendirilmesi.
- **E-ticaret**: Satış tahminleri, stok yönetimi.

Bu alanlardaki uygulamalar, işletmelerin daha etkili stratejiler geliştirmesine ve rekabet avantajı sağlamasına yardımcı olur.

---

### ✅ **Veri Bilimi Süreci ve Adımları**

Veri bilimi süreci genellikle şu adımları içerir:
1. **Veri Toplama**: Verilerin çeşitli kaynaklardan toplanması.
2. **Veri Temizleme**: Eksik, hatalı veya tutarsız verilerin düzeltilmesi.
3. **Veri Keşfi**: Verilerin analizi ve görselleştirilmesi.
4. **Modelleme**: Veri setinin özelliklerine göre uygun modelin seçilmesi ve oluşturulması.
5. **Sonuçların Yorumlanması**: Analiz edilen verilerden elde edilen bilgilerin değerlendirilmesi ve karar süreçlerine entegre edilmesi.

Bu adımlar, veri bilimi projelerinin başarısını artırır.

---

### ✅ **Veri Bilimi ve İstatistik Arasındaki Farklar**

- **Amaç**: İstatistik, genellikle veri kümesine dayalı hipotezleri test etmek için kullanılırken, veri bilimi daha geniş bir perspektifle verilerden değerli bilgiler çıkarma sürecine odaklanır.
- **Veri Türleri**: İstatistik çoğunlukla yapılandırılmış verilerle çalışırken, veri bilimi hem yapılandırılmış hem de yapılandırılmamış verilerle ilgilenir.
- **Araçlar**: İstatistiksel analiz için genellikle R veya SPSS gibi yazılımlar kullanılırken, veri biliminde Python, R ve SQL gibi programlama dilleri tercih edilir.

---

## 📌 12.2 Veri Toplama ve Veri Kaynakları

Veri toplama, veri bilimi sürecinin başlangıç noktasıdır. Doğru veri toplama yöntemleri, analiz sonuçlarının güvenilirliğini artırır.

### ✅ **Veri Toplama Yöntemleri**

#### 📋 **Anketler ve Formlar**
Anketler, belirli bir grubun görüşlerini toplamak için kullanılan yaygın bir yöntemdir. Hedefli verilerin toplanmasını sağlar. 

- **Püf Noktası**: Anketlerin kısa, anlaşılır ve hedefe yönelik olması önemlidir. Katılımcıların motivasyonunu artırmak için bazı ödüller de sunulabilir.

#### 🌐 **Web Kazıma (Web Scraping)**
Web kazıma, internette bulunan verilerin programatik olarak toplanmasını sağlar. HTML yapısını analiz ederek verileri çıkarır.

##### Örnek: Python ile web kazıma
```python
import requests  # HTTP istekleri yapmak için
from bs4 import BeautifulSoup  # HTML dökümanlarını analiz etmek için

# Web sayfasını al
response = requests.get("http://acodex.com.tr")  # Belirtilen URL'ye istek gönder

# HTML içeriğini çözümleme
soup = BeautifulSoup(response.text, 'html.parser')  # Gelen HTML yanıtını parse et

# Başlıkları çıkar
for title in soup.find_all('h1'):  # Tüm 'h1' etiketlerini bul
    print(title.text)  # Başlıkların metin içeriklerini yazdır
```
Bu kod, belirtilen web sayfasındaki tüm başlıkları alır. Kullanım alanları arasında piyasa analizi, içerik toplama ve araştırmalar yer alır.

- **Püf Noktası**: Web kazıma yaparken sitenin kullanım şartlarına dikkat edin ve aşırı yüklememeye özen gösterin.

#### 🔗 **API'ler ve Veri Tabanları**
API'ler, farklı sistemler arasında veri paylaşımını sağlayan arayüzlerdir. Veri tabanları ise yapılandırılmış verilerin saklandığı sistemlerdir.

##### Örnek: Twitter API ile veri toplama
```python
import tweepy  # Twitter API ile etkileşim için

# Twitter API ile kimlik doğrulama
auth = tweepy.OAuth1UserHandler(consumer_key, consumer_secret, access_token, access_token_secret)
api = tweepy.API(auth)  # API nesnesini oluştur

# Kullanıcının tweetlerini al
tweets = api.user_timeline(screen_name="acodex.official", count=10)  # Belirtilen kullanıcıdan son 10 tweeti al (Tweeter hesabım yok :))

# Tweetleri yazdır
for tweet in tweets:  
    print(tweet.text)  # Her bir tweetin metin içeriğini yazdır
```
Bu örnek, Twitter API'si kullanarak bir kullanıcının en son tweetlerini toplar. API'ler, verilerin sistematik ve hızlı bir şekilde alınmasını sağlar.

- **Püf Noktası**: API belgelerini dikkatlice inceleyin ve kullanılabilir sınırları (rate limits) kontrol edin.

---

### ✅ **Veri Kaynakları ve Veri Türleri**

#### 🗂️ **Yapısal ve Yapısal Olmayan Veriler**
- **Yapısal Veriler**: Tablo formatında düzenlenmiş, genellikle SQL veritabanlarında bulunan verilerdir. Analizi kolaydır.
- **Yapısal Olmayan Veriler**: Metin dosyaları, e-postalar ve sosyal medya gönderileri gibi düzenlenmemiş veri türleridir. Analiz için ön işleme gerek duyabilir.

#### 📄 **İçerik ve Meta Veriler**
- **İçerik Verileri**: Gerçek bilgiler veya veriler.
- **Meta Veriler**: Verilerin nasıl toplandığı, formatı ve kaynağı gibi bilgileri içeren verilerdir. Örneğin, bir resmin boyutları veya oluşturulma tarihi.

---


## 📌 12.3 Veri Temizleme ve Ön İşleme

Veri temizleme, veri analizi veya makine öğrenimi süreçlerinin en önemli adımlarından biridir. Hatalı veya eksik veriler, modelin doğruluğunu olumsuz yönde etkileyebilir.

### ✅ **Veri Temizleme Adımları**

#### ⚠️ **Eksik Veri İşleme**
Veri setinde eksik değerlerin bulunması yaygın bir durumdur. Bu eksik veriler, bir veri kümesinin analiz edilmesini zorlaştırabilir. 

##### Eksik Verilerle Baş Etme Yöntemleri
1. **Satır veya Sütun Silme**: 
   - Eksik verilerin bulunduğu satır veya sütunları tamamen kaldırmak. 
   - Kullanımı: Küçük veri setlerinde etkili olabilir ama büyük veri setlerinde önemli verilerin kaybına neden olabilir.
   ```python
   df.dropna()  # Tüm eksik değerlere sahip satırları kaldırır.
   ```

2. **Eksik Verileri Doldurma**:
   - Ortalamasını, medyanını veya modunu kullanarak eksik verileri doldurmak. 
   - Kullanımı: Bilgiyi kaybetmemek için ideal bir yaklaşımdır.
   ```python
   df['column_name'].fillna(df['column_name'].mean(), inplace=True)  # Ortalama ile doldurma
   ```

3. **Tahmin Etme**:
   - Makine öğrenimi algoritmaları kullanarak eksik verileri tahmin etme. 
   - Kullanımı: Bu yöntem, eksik verilerin önemli olduğu durumlarda kullanılır.
   ```python
   from sklearn.impute import SimpleImputer
   imputer = SimpleImputer(strategy='mean')
   df['column_name'] = imputer.fit_transform(df[['column_name']])
   ```

#### 🚨 **Hatalı Veri ve Anomaliler**
Veri setinde yer alan hatalı veriler veya aşırı değerler (outliers), analizlerin güvenilirliğini etkileyebilir. Bu veriler, çoğu zaman yanlış ölçüm veya veri girişi sonucunda oluşur.

##### Hatalı Verilerin Belirlenmesi
- **İstatistiksel Analiz**: Verilerin temel istatistikleri (ortalama, standart sapma) ile normal dışı değerleri belirleme.
- **Görselleştirme**: Box plot veya scatter plot gibi grafikler kullanarak aşırı değerleri gözlemleme.

##### Hatalı Verilerin Düzeltme Yöntemleri
1. **Düzeltme**: Hatalı veriyi mantıklı bir değerle değiştirme.
   ```python
   df.loc[df['column_name'] > 100, 'column_name'] = 100  # Aşırı değeri düzeltiyor.
   ```

2. **Silme**: Aşırı değerleri içeren satırların silinmesi.
   ```python
   df = df[df['column_name'] <= 100]  # 100'den büyük değerleri kaldırma.
   ```

#### ✅ **Veri Dönüşüm ve Normalizasyon**
Veri dönüşümü, verilerin analiz ve modelleme süreçleri için uygun hale getirilmesi işlemidir. Normalizasyon ise verileri belirli bir aralığa çekmek anlamına gelir.

- **Normalizasyon**: Özellikle makine öğrenimi algoritmalarında verilerin aynı ölçeğe çekilmesi gerektiğinde kullanılır.
```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()
df['normalized_column'] = scaler.fit_transform(df[['column_name']])
```
Bu işlem, tüm değerleri 0 ile 1 arasında bir aralığa çeker.

- **Standardizasyon**: Verilerin ortalamasını 0 ve standart sapmasını 1 olacak şekilde dönüştürme.
```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
df['standardized_column'] = scaler.fit_transform(df[['column_name']])
```

#### ✅ **Özellik Seçimi ve Özellik Mühendisliği**
Veri setindeki en önemli özelliklerin belirlenmesi, modelin başarısını artırabilir. Özellik mühendisliği, verilerden yeni özellikler oluşturmayı içerir.

- **Özellik Seçimi**: En önemli özellikleri belirlemek için teknikler kullanma (örneğin, karar ağaçları, korelasyon matrisleri).
- **Özellik Mühendisliği**: Mevcut verilerden yeni bilgiler elde etme.
```python
df['income_per_age'] = df['income'] / df['age']  # Yeni özellik oluşturma
```

#### ✅ **Veri Tipleri ve Dönüşümleri**
Veri türleri, veri işleme ve analizde kritik bir rol oynar. Python’da yaygın veri türleri şunlardır:
- **Integer**: Tam sayılar
- **Float**: Kesirli sayılar
- **String**: Metin verileri
- **Boolean**: True/False değerleri

Veri türlerini değiştirmek, analitik süreçte esneklik sağlar.
```python
df['column_name'] = df['column_name'].astype(int)  # Veri tipini tam sayıya dönüştürme
```

---

## 📌 12.4 Veri Görselleştirme

Veri görselleştirme, karmaşık verileri görsel hale getirerek daha anlaşılır hale getirir. İyi bir görselleştirme, verilerdeki desenleri, eğilimleri ve anormallikleri hızlıca anlamayı sağlar.

### ✅ **Veri Görselleştirmenin Önemi**
- **Hızlı Anlayış**: Veriler görsel olarak sunulduğunda, karmaşık ilişkileri ve eğilimleri daha hızlı kavrayabiliriz.
- **İletişim**: Verileri başkalarına anlatmanın en etkili yolu görselleştirmelerdir.
- **Hataların Tespiti**: Görselleştirme, verilerdeki hataları veya anomalileri gözle görmek için yararlıdır.

### ✅ **Görselleştirme Araçları ve Kütüphaneleri**

#### 📊 **Matplotlib**
Python’un en popüler görselleştirme kütüphanesidir. Çizgi grafikleri, çubuk grafikleri ve histogramlar gibi temel grafik türleri oluşturmak için kullanılır.

##### Örnek: Basit Çizgi Grafiği
```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [10, 20, 25, 30, 35]

plt.plot(x, y, color='blue', marker='o', linestyle='-', linewidth=2)  # Çizgi grafiği
plt.title("Basit Çizgi Grafiği")
plt.xlabel("X Ekseni")
plt.ylabel("Y Ekseni")
plt.grid(True)  # Izgara çizgilerini açma
plt.show()
```
Bu kod, x ve y değerleri ile basit bir çizgi grafiği oluşturur. Grafikte kullanılan `marker` ve `linestyle` gibi parametrelerle grafik estetik olarak iyileştirilir.

#### 📈 **Seaborn**
Seaborn, Matplotlib üzerine inşa edilmiş bir kütüphanedir ve daha estetik ve karmaşık grafikler oluşturmayı sağlar.

##### Örnek: Seaborn ile Dağılım Grafiği
```python
import seaborn as sns
import pandas as pd

data = {'age': [25, 32, 47, 54, 23],
        'income': [50000, 60000, 75000, 80000, 45000]}
df = pd.DataFrame(data)

sns.scatterplot(x='age', y='income', data=df)
plt.title("Yaş ve Gelir Dağılımı")
plt.xlabel("Yaş")
plt.ylabel("Gelir")
plt.show()
```
Bu grafik, yaş ve gelir arasındaki ilişkiyi görselleştirir. Seaborn, estetik ayarları otomatik olarak yaparak daha şık görseller oluşturur.

#### 📊 **Plotly**
Dinamik ve etkileşimli grafikler oluşturmak için kullanılan bir kütüphanedir. Web tabanlı uygulamalar için ideal bir seçimdir.

##### Örnek: Plotly ile Çizgi Grafiği
```python
import plotly.express as px

data = {'Year': [2020, 2021, 2022],
        'Sales': [150, 200, 300]}
df = pd.DataFrame(data)

fig = px.line(df, x='Year', y='Sales', title='Yıllık Satışlar')
fig.show()  # Etkileşimli grafik gösterimi
```
Bu kod, yıllık satışları içeren etkileşimli bir çizgi grafiği oluşturur.

### ✅ **Temel Grafik Türleri**

#### 📊 **Histogramlar**
Veri dağılımını gösterir ve veri setinin nasıl dağıldığını anlamaya yardımcı olur. Histogramlar, belirli bir aralıkta kaç adet veri noktası olduğunu gösterir.

##### Örnek: Histogram Oluşturma
```python
import numpy as

 np

data = np.random.randn(1000)  # Normal dağılımlı rastgele veriler
plt.hist(data, bins=30, alpha=0.7, color='blue')  # Histogram
plt.title("Histogram")
plt.xlabel("Değerler")
plt.ylabel("Frekans")
plt.grid(True)  # Izgara çizgileri
plt.show()
```
Bu histogram, normal dağılıma sahip 1000 veri noktasının dağılımını gösterir.

#### 📈 **Çizgi Grafikler**
Zamansal verilerin değişimini göstermek için kullanılır. Verilerin sürekli değişimini anlamak için idealdir.

#### 📊 **Dağılım Grafikleri (Scatter Plot)**
İki değişken arasındaki ilişkiyi gösterir. Aşırı değerler ve trendleri tespit etmek için kullanılır.

### 📊 **Pasta Grafikler**
Kategorik verilerin yüzdelerini göstermek için kullanılır. Ancak, çok fazla kategori olduğunda yanıltıcı olabilir, bu yüzden dikkatli kullanılmalıdır.

##### Örnek: Pasta Grafiği Oluşturma
```python
labels = ['A', 'B', 'C', 'D']
sizes = [15, 30, 45, 10]

plt.pie(sizes, labels=labels, autopct='%1.1f%%')  # Pasta grafiği
plt.title("Pasta Grafiği")
plt.axis('equal')  # Eşit eksen oranları
plt.show()
```
Bu kod, dört kategori arasındaki yüzdeleri gösteren bir pasta grafiği oluşturur.

#### 📊 **İleri Düzey Görselleştirme Teknikleri**
- **Heatmaps**: Veri yoğunluğunu gösteren renkli matrislerdir. Özellikle korelasyon matrisleri için yararlıdır.
- **Box Plots**: Verilerin medyanını, çeyreklerini ve aşırı değerlerini görselleştirmek için kullanılır.
- **Violin Plots**: Dağılımın yoğunluğunu ve medyanını aynı anda gösterir, verinin dağılımına dair daha fazla bilgi sunar.

---


## 📌 12.5 İstatistiksel Analiz

İstatistiksel analiz, veri kümesinin özelliklerini anlamak ve karar vermek için veri setlerinden bilgi çıkarma sürecidir. Bu süreçte, temel istatistik kavramlarından istatistiksel dağılımlara kadar birçok önemli kavram ele alınır.

### ✅ **Temel İstatistik Kavramları**

#### ⚖️ **Ortalama, Medyan, Mod**
- **Ortalama**: Veri kümesindeki tüm değerlerin toplamının, değer sayısına bölünmesiyle elde edilen değerdir.
  ```python
  import numpy as np

  data = [10, 20, 30, 40, 50]
  mean = np.mean(data)  # Ortalama hesaplama
  print("Ortalama:", mean)  # Çıktı: Ortalama: 30.0
  ```

- **Medyan**: Veri kümesinin ortasında yer alan değerdir. Veri sıralandığında, ortada kalan değeri temsil eder.
  ```python
  median = np.median(data)  # Medyan hesaplama
  print("Medyan:", median)  # Çıktı: Medyan: 30.0
  ```

- **Mod**: En sık tekrar eden değerdir. Birden fazla modlu veri setleri de olabilir.
  ```python
  from scipy import stats

  mode = stats.mode(data)  # Mod hesaplama
  print("Mod:", mode.mode[0])  # Çıktı: Mod: 10
  ```

#### 📊 **Varyans ve Standart Sapma**
- **Varyans**: Verilerin ortalamadan ne kadar uzaklaştığını gösteren bir ölçüdür. Yüksek varyans, verilerin geniş bir aralıkta dağıldığını gösterir.
  ```python
  variance = np.var(data)  # Varyans hesaplama
  print("Varyans:", variance)  # Çıktı: Varyans: 200.0
  ```

- **Standart Sapma**: Varyansın kareköküdür ve verinin ortalamadan ne kadar sapma gösterdiğini ölçer.
  ```python
  std_deviation = np.std(data)  # Standart sapma hesaplama
  print("Standart Sapma:", std_deviation)  # Çıktı: Standart Sapma: 14.142135623730951
  ```

### ✅ **İstatistiksel Dağılımlar**

İstatistiksel dağılımlar, veri kümesinin dağılımını ve olasılıklarını anlamaya yardımcı olur.

#### 📈 **Normal Dağılım**
Normal dağılım, en yaygın dağılım türlerinden biridir. Çan şeklinde bir dağılım gösterir ve birçok doğal olayı modellemek için kullanılır.

#### 🟠 **Binom Dağılımı**
Başarı ve başarısızlık gibi iki sonucun olduğu deneylerde (örneğin, bir paranın atılması) kullanılır. Binom dağılımı, belirli bir sayıda başarı elde etme olasılığını hesaplar.

#### 🔵 **Poisson Dağılımı**
Belirli bir zaman diliminde veya alanda belirli bir olayın gerçekleşme olasılığını hesaplamak için kullanılır (örneğin, bir dükkanda belirli bir süre içinde gelen müşteri sayısı).

### ✅ **Hipotez Testleri ve P-Değerleri**

Hipotez testleri, verilerin anlamlılığını değerlendirmek için kullanılır. Bir hipotez, genellikle iki tür olur: null (H0) ve alternatif (H1) hipotezler.

#### 📝 **T-Testi**
İki grup arasındaki ortalama farkını test eder. Örneğin, iki farklı ilaç grubunun etkilerinin karşılaştırılması.
```python
from scipy import stats

group1 = [20, 21, 19, 24, 22]
group2 = [30, 31, 29, 28, 32]
t_stat, p_value = stats.ttest_ind(group1, group2)  # İki grup için t-testi
print("T-İstatistiği:", t_stat, "p-değeri:", p_value)
```

#### 📊 **Ki-Kare Testi**
Kategorik verilerin bağımsızlığını test etmek için kullanılır. Örneğin, bir ürünün tercih edilme oranının cinsiyete göre değişip değişmediğini test etmek.
```python
contingency_table = [[10, 20], [20, 30]]
chi2_stat, p_value, dof, expected = stats.chi2_contingency(contingency_table)
print("Ki-Kare İstatistiği:", chi2_stat, "p-değeri:", p_value)
```

#### 📈 **ANOVA (Varyans Analizi)**
Üç veya daha fazla grubun ortalamalarının karşılaştırılması için kullanılır. Örneğin, üç farklı ürünün satışlarının karşılaştırılması.
```python
group1 = [20, 21, 19]
group2 = [30, 31, 29]
group3 = [40, 41, 39]
f_stat, p_value = stats.f_oneway(group1, group2, group3)  # ANOVA testi
print("F-İstatistiği:", f_stat, "p-değeri:", p_value)
```

---

## 📌 12.6 Veri Analizi ve Modelleme

Veri analizi, verileri anlamak ve içgörü elde etmek için gerçekleştirilen bir süreçtir. Bu süreçte çeşitli yöntemler ve modeller kullanılır.

### ✅ **Veri Analizinin Temel Yöntemleri**
Veri analizi, gözlemleme, açıklayıcı istatistik ve modelleme gibi çeşitli yöntemleri içerir. Analiz süreci, verilerin toplanmasından başlar ve içgörü elde edilmesiyle sonuçlanır.

### ✅ **Regresyon Analizi**
Veri analizi sürecinde, bağımlı ve bağımsız değişkenler arasındaki ilişkiyi incelemek için regresyon analizi kullanılır.

#### 📉 **Doğrusal Regresyon**
Bir bağımsız değişken ile bir bağımlı değişken arasındaki ilişkiyi modellemek için kullanılır. Doğrusal bir ilişki varsayıldığında basit doğrusal regresyon kullanılır.
```python
from sklearn.linear_model import LinearRegression

X = [[1], [2], [3], [4]]  # Bağımsız değişken
y = [1, 3, 2, 3]  # Bağımlı değişken

model = LinearRegression()
model.fit(X, y)  # Modeli eğitme
print("Katsayı:", model.coef_, "Intercept:", model.intercept_)
```

#### 📊 **Çoklu Regresyon**
Birden fazla bağımsız değişkenin bir bağımlı değişken üzerindeki etkisini modellemek için kullanılır. 
```python
import pandas as pd

data = pd.DataFrame({
    'X1': [1, 2, 3, 4],
    'X2': [2, 3, 4, 5],
    'y': [1, 3, 2, 3]
})

model = LinearRegression()
model.fit(data[['X1', 'X2']], data['y'])  # Çoklu regresyon modeli
print("Katsayılar:", model.coef_)
```

### ✅ **Sınıflandırma Analizi**
Sınıflandırma analizi, verileri belirli sınıflara ayırmak için kullanılan bir tekniktir. 

### 🔍 **Lojistik Regresyon**
İkili sonuçlar (0 veya 1) üreten bir modeldir. Örneğin, bir e-posta mesajının spam olup olmadığını sınıflandırmak için kullanılır.
```python
from sklearn.linear_model import LogisticRegression

X = [[0], [1], [2], [3]]
y = [0, 0, 1, 1]  # İkili sınıflar

model = LogisticRegression()
model.fit(X, y)  # Lojistik regresyon modeli
print("Katsayılar:", model.coef_)
```

#### 🌳 **Karar Ağaçları**
Veri setini ağaç yapısında sınıflandırır. Her bir dal, bir karar noktasıdır ve sonuca ulaşmak için izlenen yoldur.
```python
from sklearn.tree import DecisionTreeClassifier

X = [[0], [1], [2], [3]]
y = [0, 0, 1, 1]

model = DecisionTreeClassifier()
model.fit(X, y)  # Karar ağaçları modeli
```

#### 🚀 **Destek Vektör Makineleri (SVM)**
Veri noktalarını en iyi ayıran hiper düzlemi bulmaya çalışır. Özellikle karmaşık ve yüksek boyutlu verilerde etkilidir.
```python
from sklearn import svm

X = [[0], [1], [2], [3]]
y = [0, 0, 1, 1]

model = svm.S

VC()
model.fit(X, y)  # SVM modeli
```

### ✅ **Kümeleme ve Segmentasyon**
Verileri benzerliklerine göre gruplandırma işlemidir. 

### 🔵 **K-Means Kümeleme**
Verileri k sayıda kümeye ayırmak için kullanılır. Her bir küme, veri noktalarının ortalaması ile temsil edilir.
```python
from sklearn.cluster import KMeans

data = [[1, 2], [1, 4], [1, 0], [4, 2], [4, 0]]
kmeans = KMeans(n_clusters=2, random_state=0).fit(data)  # K-Means kümeleme
print("Küme merkezleri:", kmeans.cluster_centers_)
```

#### 📊 **Hierarchical Clustering**
Veri kümesinin hiyerarşik bir yapıda gruplandırılmasını sağlar. Ağaç yapısı olarak görselleştirilebilir.

### ✅ **Zaman Serisi Analizi**
Zaman serisi analizi, verilerin zaman içindeki değişimini incelemek için kullanılır. Özellikle finansal verilerde, hava durumu tahminlerinde ve birçok farklı alanda kullanılır.

Zaman serisi analizi, verilerin zaman dilimlerine göre düzenlenmesini ve trendlerin, mevsimselliğin ve döngülerin incelenmesini içerir.

---


## 📌 12.7 Makine Öğrenmesi ve Veri Bilimi

Makine öğrenmesi, bilgisayar sistemlerinin verilerden otomatik olarak öğrenme ve tahminlerde bulunma yeteneğidir. Veri bilimi, makine öğrenmesini uygulamak ve veri analizi yapmak için gerekli araçlar ve yöntemler sağlar.

### ✅ **Makine Öğrenmesi Temelleri**

Makine öğrenmesi, belirli bir görev için algoritmalar geliştirmek amacıyla verilere dayalı olarak öğrenme yöntemlerini içerir. Temel bileşenleri şunlardır:

- **Veri**: Modelin eğitilmesi için kullanılan bilgi kümesi.
- **Algoritma**: Verilerden öğrenme sürecini yöneten matematiksel yöntem.
- **Model**: Algoritmanın, verilerden öğrendiği ve tahmin yapmak için kullandığı yapı.

Makine öğrenmesi genellikle iki ana gruba ayrılır: denetimli ve denetimsiz öğrenme.

#### 🔍 **Denetimli Öğrenme**

Denetimli öğrenme, etiketlenmiş veriler kullanılarak modelin eğitilmesi anlamına gelir. Bu tür öğrenme, modelin belirli bir girdi ile ona karşılık gelen bir çıktıyı öğrenmesini sağlar. Örneğin, bir e-postanın spam olup olmadığını belirlemek için etiketlenmiş veriler kullanılır. Temel adımlar:

1. **Veri Toplama**: Eğitim için gerekli verilerin toplanması.
2. **Öznitelik Seçimi**: Modelin daha iyi öğrenmesini sağlamak için önemli özelliklerin seçilmesi.
3. **Model Eğitimi**: Seçilen verilerle modelin eğitilmesi.

```python
from sklearn.linear_model import LogisticRegression

# Özellikler ve etiketler
X = [[1, 0], [0, 1], [1, 1], [0, 0]]  # Özellikler
y = [1, 0, 1, 0]  # Etiketler (1: spam, 0: değil)

# Modelin oluşturulması ve eğitilmesi
model = LogisticRegression()
model.fit(X, y)
```
Yukarıdaki kod, iki özellik ile spam olup olmadığını belirleyen basit bir lojistik regresyon modelinin nasıl eğitileceğini gösterir. Özellikler ve etiketler kullanılarak model eğitildiğinde, model yeni verilere tahmin yapma yeteneğine sahip olur.

#### 🔎 **Denetimsiz Öğrenme**

Denetimsiz öğrenme, etiketlenmemiş veriler üzerinde modelin çalıştığı ve içgörüler elde etmeye çalıştığı bir yöntemdir. Örneğin, K-means algoritması, benzer özelliklere sahip verileri gruplamak için kullanılır. Temel adımlar:

1. **Veri Toplama**: Etiketlenmemiş verilerin toplanması.
2. **Model Seçimi**: Veri kümesine uygun bir algoritmanın seçilmesi.
3. **Model Eğitimi**: Modelin veriler üzerinde çalıştırılması.

```python
from sklearn.cluster import KMeans

# Etiketlenmemiş veri kümesi
data = [[1, 2], [1, 4], [1, 0], [4, 2], [4, 0]]

# K-means ile kümeleme
kmeans = KMeans(n_clusters=2, random_state=0).fit(data)
print("Küme merkezleri:", kmeans.cluster_centers_)
```
Bu kod, K-means algoritması ile verileri iki kümeye ayırır ve her kümenin merkezini hesaplar.

### ✅ **Model Seçimi ve Değerlendirme**

Model seçimi, en uygun algoritmanın belirlenmesi sürecidir. Modeller genellikle şu metriklerle değerlendirilir:

- **Doğruluk (Accuracy)**: Doğru tahminlerin toplam tahminlere oranıdır.
- **Hassasiyet (Precision)**: Pozitif tahminlerin gerçekte pozitif olanların oranıdır.
- **Duyarlılık (Recall)**: Gerçek pozitiflerin tahmin edilen pozitifler içindeki oranıdır.

Modeli değerlendirmek için k-fold çapraz doğrulama yöntemi kullanılabilir. Bu yöntem, verileri k alt kümeye böler ve her alt küme bir test seti olarak kullanılırken kalanlar eğitim seti olarak kullanılır.

```python
from sklearn.model_selection import cross_val_score
from sklearn.ensemble import RandomForestClassifier

# Modelin oluşturulması
model = RandomForestClassifier()
scores = cross_val_score(model, X, y, cv=5)  # 5 katlı çapraz doğrulama
print("Doğruluk Skorları:", scores)
```
Bu kod, Random Forest modeli ile 5 katlı çapraz doğrulama yaparak doğruluk skorlarını hesaplar.

#### ✅ **Hiperparametre Ayarı**

Hiperparametreler, modelin eğitim sürecini etkileyen parametrelerdir. Bu parametrelerin optimize edilmesi, model performansını önemli ölçüde artırabilir. Genellikle Grid Search veya Random Search kullanılarak ayarlanır.

```python
from sklearn.model_selection import GridSearchCV

param_grid = {'n_estimators': [10, 50, 100]}
grid_search = GridSearchCV(RandomForestClassifier(), param_grid, cv=5)
grid_search.fit(X, y)  # Hiperparametre ayarı
print("En iyi parametreler:", grid_search.best_params_)
```
Yukarıdaki kod, Random Forest modelinin en iyi hiperparametrelerini bulmak için Grid Search kullanır.

### ✅ **Model Performansını Artırma**

Modelin performansını artırmak için aşağıdaki stratejiler kullanılabilir:
- **Özellik Mühendisliği**: Yeni özellikler oluşturmak veya mevcut özellikleri dönüştürmek.
- **Toplama Yöntemleri**: Farklı modellerin bir araya getirilmesi (örneğin, bagging, boosting).
- **Daha Fazla Veri Kullanma**: Modelin eğitilmesi için daha fazla veri toplayarak genel performansı artırmak.

---

## 📌 12.8 Büyük Veri ve Dağıtık Sistemler

Büyük veri, geleneksel veri işleme yazılımlarının yönetemeyeceği büyüklükte ve karmaşıklıkta verileri ifade eder. Dağıtık sistemler, bu verileri işlemek için tasarlanmıştır.

### ✅ **Büyük Veri Kavramı ve Özellikleri**

Büyük veri, genellikle 3V (Hacim, Hız, Çeşitlilik) ile tanımlanır:
- **Hacim**: Veri miktarının büyüklüğü; terabyte ve petabyte düzeyinde verileri içerir.
- **Hız**: Verinin toplama, işleme ve analiz etme hızıdır; anlık veri akışı gerektiren uygulamalar.
- **Çeşitlilik**: Farklı kaynaklardan ve formatlardan gelen verilerin çeşitliliğidir (yapısal, yarı yapısal, yapısal olmayan).

### ✅ **Dağıtık Sistemler ve Araçlar**

Dağıtık sistemler, verilerin işlenmesi için birden fazla bilgisayarın bir arada çalıştığı sistemlerdir. Bu sistemler, büyük veri kümelerinin işlenmesini kolaylaştırır.

#### 🛠️ **Hadoop**
Hadoop, büyük veri işleme ve depolama için açık kaynaklı bir framework'tür. Aşağıdaki bileşenleri içerir:
- **HDFS (Hadoop Distributed File System)**: Verileri dağıtık bir şekilde depolar, böylece veriler birden fazla makinede saklanabilir.
- **MapReduce**: Verileri işlemek için kullanılan bir programlama modeli; verileri paralel olarak işler.

Örnek bir MapReduce uygulaması:
```python
# MapReduce uygulaması örneği
from mrjob.job import MRJob

class MRWordCount(MRJob):
    def mapper(self, _, line):
        for word in line.split():
            yield word, 1

    def reducer(self, word, counts):
        yield word, sum(counts)

if __name__ == '__main__':
    MRWordCount.run()
```
Bu kod, metindeki kelime sayısını hesaplamak için MapReduce yöntemi kullanır.

#### ⚡ **Apache Spark**
Apache Spark, Hadoop'dan daha hızlı veri işleme yeteneklerine sahip popüler bir açık kaynaklı büyük veri işleme motorudur. Bellek içi veri işleme yeteneği ile yüksek hız sunar. Aşağıda Spark ile veri analizi yapma örneği:

```python
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("Büyük Veri Uygulaması").getOrCreate()
df = spark.read.csv("data.csv")  # CSV dosyasını yükleme
df.show()  # Veri çerçevesini gösterme
```
Bu kod, bir CSV dosyasını Spark ile yükler ve verileri görüntüler. Spark, büyük veri analizini hızlandırır.

### ✅ **Veri İşleme ve Analizinde Büyük Veri Kullanımı**

Büyük veri analitiği, büyük veri kümesi üzerinde gerçekleştirilen analizlerdir. Spark ve Hadoop gibi araçlar, verilerin daha hızlı işlenmesini ve analiz edilmesini sağlar. Bu süreçler, iş zekası uygulamaları, makine öğrenimi modelleri ve veri görselleştirme için kritik öneme sahiptir.

Büyük veri analitiği, şirketlerin daha doğru tahminlerde bulunmasına ve daha iyi kararlar almasına olanak tanır. Örneğin, müşteri davranışını analiz ederek hedefli pazarlama stratejileri geliştirebilirler.

---


## 📌 12.9 Zaman Serisi Analizi

Zaman serisi analizi, zamanla değişen verilerin analizi için kullanılan istatistiksel bir yöntemdir. Zaman serileri genellikle finansal veriler, hava durumu verileri, ekonomik göstergeler gibi zamanla değişen olayları anlamak için kullanılır.

### ✅ **Zaman Serisi Nedir?**

Zaman serisi, belirli bir zaman diliminde düzenli aralıklarla toplanmış verilerdir. Bu veriler genellikle aşağıdaki bileşenleri içerir:

1. **Trend**: Zaman içindeki genel eğilim, artış veya azalma gösterir.
2. **Mevsimsellik**: Belirli dönemlerde tekrarlanan döngüsel değişimlere işaret eder.
3. **Duyarlılık**: Verilerin rastgele dalgalanmasını gösterir.

### ✅ **Zaman Serisi Analizinde Kullanılan Yöntemler**

#### 🛠️ **ARIMA (Otoregresif Entegre Hareketli Ortalama)**

ARIMA, zaman serisi verilerinin tahmini için yaygın olarak kullanılan bir yöntemdir. Bu model, üç bileşen içerir:

- **AR (Otoregresif)**: Geçmiş verilerin etkisini içerir.
- **I (Entegre)**: Verinin durağan hale getirilmesi için fark alma işlemini temsil eder.
- **MA (Hareketli Ortalama)**: Hataların ortalamasını kullanarak tahminlerde bulunur.

Zaman serisi verilerini ARIMA modeliyle analiz etmek için aşağıdaki gibi bir kod kullanılabilir:

```python
import pandas as pd
from statsmodels.tsa.arima.model import ARIMA

# Zaman serisi verisinin yüklenmesi
data = pd.read_csv('time_series_data.csv', parse_dates=['date'], index_col='date')

# ARIMA modelinin oluşturulması ve eğitilmesi
model = ARIMA(data['value'], order=(1, 1, 1))
model_fit = model.fit()

# Tahminlerin yapılması
forecast = model_fit.forecast(steps=5)
print("Gelecek 5 adım için tahminler:", forecast)
```

Bu kod, bir zaman serisi verisini kullanarak ARIMA modelini oluşturur ve gelecekteki beş veri noktası için tahminler yapar.

#### 📈 **Mevsimsel Dekompozisyon**

Zaman serisi verilerini analiz etmek için bir diğer yöntem de mevsimsel dekompozisyondur. Bu yöntem, zaman serisini trend, mevsimsellik ve rastgele bileşenlere ayırır. Bu sayede, her bir bileşeni ayrı ayrı analiz etmek mümkün olur.

```python
from statsmodels.tsa.seasonal import seasonal_decompose

# Zaman serisi verisinin dekompozisyonu
decomposition = seasonal_decompose(data['value'], model='additive')
decomposition.plot()
```

Bu kod, zaman serisi verisinin bileşenlerini görselleştirir, böylece verinin genel eğilimi ve mevsimsel etkileri daha iyi anlaşılır.

---

## 📌 12.10 Model Değerlendirme ve Doğrulama

Model değerlendirme, oluşturulan modelin ne kadar iyi performans gösterdiğini belirlemek için kullanılan yöntemlerdir. Bu süreç, modelin genelleme yeteneğini anlamaya yardımcı olur.

### ✅ **Model Değerlendirme Yöntemleri**

#### 🔍 **Karmaşıklık ve Aşırı Uydurma**

Aşırı uydurma, modelin eğitim verisine aşırı uyum sağlaması ve test verisinde zayıf performans göstermesi durumudur. Modelin karmaşıklığı, bu sorunu artırabilir. Bu nedenle, model değerlendirmesi yaparken karmaşıklık ve aşırı uydurmanın göz önünde bulundurulması önemlidir.

#### 📊 **Kayıp Fonksiyonları**

Kayıp fonksiyonu, modelin tahmin hatalarını ölçen bir ölçüttür. İki yaygın kayıp fonksiyonu şunlardır:

- **Mean Squared Error (MSE)**: Tahminlerin gerçekteki değerlerden ne kadar uzak olduğunu ölçer.
  
```python
from sklearn.metrics import mean_squared_error

# Gerçek değerler ve tahminler
y_true = [3, -0.5, 2, 7]
y_pred = [2.5, 0.0, 2, 8]

# MSE hesaplama
mse = mean_squared_error(y_true, y_pred)
print("MSE:", mse)
```

- **Log Loss**: Sınıflandırma problemlerinde kullanılır ve modelin tahmin ettiği olasılıkların gerçek etiketlerle olan uyumunu ölçer.

#### 📈 **Çapraz Doğrulama**

Çapraz doğrulama, modelin farklı veri parçaları üzerinde test edilmesini sağlayarak modelin genelleme yeteneğini artırır. K-fold çapraz doğrulama, en yaygın kullanılan yöntemlerden biridir. Veri seti K alt kümeye bölünür ve her bir alt küme test verisi olarak kullanılırken kalan alt kümeler eğitim seti olarak kullanılır.

```python
from sklearn.model_selection import cross_val_score
from sklearn.ensemble import RandomForestRegressor

model = RandomForestRegressor()
scores = cross_val_score(model, X, y, cv=5)
print("Çapraz Doğrulama Skorları:", scores)
```

---

## 📌 12.11 Proje Yönetimi ve Veri Bilimi

Veri bilimi projeleri genellikle karmaşık ve disiplinler arasıdır. Bu projelerin başarıyla yönetilmesi için aşağıdaki adımlar önemlidir:

### ✅ **Proje Tanımlama**

Projenin kapsamının ve hedeflerinin belirlenmesi kritik öneme sahiptir. Proje tanımlarken şu soruları yanıtlamak önemlidir:

- Proje neyi başarmayı amaçlıyor?
- Hangi veriler kullanılacak?
- Hedef kitle kim?

### ✅ **Veri Toplama ve Ön İşleme**

Veri toplama ve ön işleme süreci, veri bilimi projelerinin en önemli aşamalarından biridir. Verilerin temizlenmesi, düzeltilmesi ve dönüştürülmesi, analizin kalitesini artırır. Aşağıda bazı veri ön işleme adımları verilmiştir:

- **Veri Temizleme**: Eksik ve hatalı verilerin giderilmesi.
- **Veri Dönüşümü**: Verilerin uygun formatlara dönüştürülmesi.
- **Öznitelik Seçimi**: Modelin eğitimi için en önemli özelliklerin belirlenmesi.

#### 📊 **Model Geliştirme ve Test Etme**

Model geliştirme aşamasında, uygun algoritmalar seçilir ve bu algoritmalar ile model eğitilir. Modelin test edilmesi ise yukarıda belirtilen değerlendirme yöntemleri kullanılarak gerçekleştirilir.

#### 📈 **Sonuçların Sunumu**

Sonuçların etkili bir şekilde sunulması, projenin başarısını artırır. Görselleştirme araçları kullanarak elde edilen sonuçların grafiksel olarak sunulması, bilgiyi daha anlaşılır hale getirir.