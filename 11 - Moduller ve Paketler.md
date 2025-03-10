# 📌 11. Python Modülleri ile Çalışma

Python modülleri, büyük projeleri yönetilebilir parçalara ayırmak ve kod tekrarını azaltmak için kullanılan güçlü araçlar olan **modüller** Python projelerinde kod tekrarını önlemek, düzeni sağlamak ve geliştirmeyi kolaylaştırmak için kullanılır. Bu bölümde modüllerin ne olduğu, nasıl oluşturulduğu, içe aktarıldığı ve kullanıldığı üzerine kapsamlı bilgiler paylaşacağız.

---

## 🚀 11.1 Modüllere Giriş

### ✅ **Modül Nedir?**
Python’da **modül**, içeriğinde fonksiyonlar, değişkenler ve sınıflar bulunduran bir Python dosyasıdır. `.py` uzantılı herhangi bir dosya, başka bir dosya içinde kullanılmak üzere bir modül olarak çalıştırılabilir.

Python’un modüler yapısı sayesinde:
- **Büyük projeler daha küçük ve yönetilebilir parçalara bölünebilir.**
- **Kod tekrarından kaçınılır, daha okunaklı ve sürdürülebilir yazılım geliştirilir.**
- **Aynı kodları farklı projelerde tekrar tekrar kullanabiliriz.**
- **Bakımı kolaylaştırır ve takım çalışmasını daha verimli hale getirir.**

### ✅ **Modüllerin Kullanım Alanları**
- **Matematiksel hesaplamalar** için `math` modülü.
- **Dosya işlemleri** için `os` ve `shutil` modülleri.
- **Tarih ve saat işlemleri** için `datetime` modülü.
- **Web istekleri gönderme** için `requests` modülü.
- **Veri analizi** için `pandas` ve `numpy` gibi popüler üçüncü taraf modülleri.

### ✅ **Python Modül Sistemi**
Python’daki modüller üç ana kategoriye ayrılır:

1. **Yerleşik (Built-in) Modüller:**  
   Python ile birlikte gelen hazır modüllerdir. `math`, `random`, `os`, `sys` gibi modüller bu gruba girer.
   
2. **Üçüncü Taraf (Third-party) Modüller:**  
   Dışarıdan yüklenerek kullanılan modüllerdir. `numpy`, `pandas`, `matplotlib`, `requests` gibi modüller PyPI (Python Package Index) üzerinden yüklenebilir.

3. **Kendi Yazdığımız (User-defined) Modüller:**  
   Geliştiriciler tarafından özel ihtiyaçlara göre yazılan modüllerdir. Başka projelerde tekrar kullanılabilir.

---

## 🚀 11.2 Modül Oluşturma ve Kullanma

Python’da kendi modüllerimizi oluşturabiliriz. Bunun için `.py` uzantılı bir dosya oluşturmamız yeterlidir.

### ✅ **Basit Bir Modül Oluşturma**
Örneğin, matematiksel işlemler yapan bir modül oluşturalım.

📌 `matematik.py` adlı bir dosya oluşturalım:
```python
# Basit matematiksel işlemler içeren bir modül

def topla(a, b):
    return a + b

def carp(a, b):
    return a * b

def karesi(x):
    return x ** 2

pi = 3.14159  # Pi sayısı sabiti
```
📌 *Bu dosya, `topla()`, `carp()`, `karesi()` gibi fonksiyonları ve bir `pi` sabitini içeren bir Python modülüdür.*

Bu modülü başka bir Python dosyasında kullanabiliriz.

### ✅ **Modül İçe Aktarma (`import`)**
Oluşturduğumuz `matematik.py` modülünü başka bir dosyada çağırmak için `import` kullanırız.

📌 `main.py` dosyasında modülü içe aktaralım:
```python
import matematik  # matematik.py dosyasını içe aktarıyoruz

print(matematik.topla(5, 3))  # 5 + 3 = 8
print(matematik.carp(4, 2))  # 4 * 2 = 8
print(matematik.karesi(6))  # 6 ** 2 = 36
print(matematik.pi)  # 3.14159
```
📌 *Bu kod, `matematik.py` modülündeki fonksiyonları ve değişkenleri kullanarak işlemler yapar.*

---

### ✅ **Belirli Fonksiyonları İçe Aktarma (`from ... import ...`)**
Eğer bir modülden sadece belirli bir fonksiyon veya değişkeni kullanmak istiyorsak, tüm modülü çağırmak yerine sadece o fonksiyonları içe aktarabiliriz.

```python
from matematik import topla, pi  # Sadece topla() fonksiyonunu ve pi değişkenini içe aktar

print(topla(10, 20))  # 10 + 20 = 30
print(pi)  # 3.14159
```
📌 *Bu yöntem, gereksiz modül çağırmalarını önler ve kodu daha verimli hale getirir.*

---

### ✅ **Tüm İçeriği İçe Aktarma (`from ... import *`)**
Bir modüldeki tüm değişken ve fonksiyonları içe aktarmak için `*` sembolü kullanılabilir.

```python
from matematik import *  # Tüm içerikleri içe aktar

print(karesi(5))  # 5 ** 2 = 25
```
📌 *Ancak, bu yöntem bazı durumlarda değişken isimlerinin çakışmasına neden olabileceği için dikkatli kullanılmalıdır.*

---

### ✅ **Modül İsimlendirme Kuralları**
- **Küçük harfler ve alt çizgi (`_`) kullanılarak isimlendirilmelidir.**  
  ✅ `ornek_modul.py`  
  ❌ `OrnekModul.PY`
- **Python’un yerleşik modülleri ile çakışmamalıdır.**  
  ❌ `random.py` (Çünkü Python’un yerleşik `random` modülü vardır)
- **İsimler kısa ve açıklayıcı olmalıdır.**  
  ✅ `veri_isleme.py`  
  ❌ `x1.py`

---

### ✅ **Aliasing (`as` ile Kısayol Kullanımı)**
Modüllerin ismi uzun olursa, `as` anahtar kelimesi ile daha kısa isimler verilebilir.

```python
import matematik as m  # matematik modülüne "m" takma adı veriyoruz

print(m.karesi(7))  # 7 ** 2 = 49
```
📌 *Bu yöntem, kodu daha okunaklı hale getirir ve yazımı kolaylaştırır.*

---

### ✅ **Modüllerin Konumlandırılması ve Python’un Modül Yolu**
Python, modülleri aşağıdaki sırayla arar:
1. **Çalıştırılan Python dosyasının bulunduğu dizin**  
2. **PYTHONPATH ortam değişkeni ile belirtilen dizinler**  
3. **Python’un standart kütüphane dizinleri (site-packages vb.)**

Modülün hangi yollar içinde arandığını görmek için:

```python
import sys
print(sys.path)  # Python’un modül arama yollarını listeler
```
📌 *Eğer bir modülü çağırırken "ModuleNotFoundError" hatası alırsanız, ilgili modülün yukarıdaki yollardan birinde olmadığı anlamına gelir.*

---

## 📌 11.3 Modül İçeriğine Erişim

Bir modül içindeki fonksiyonlara, değişkenlere ve diğer öğelere nasıl erişileceğini öğrenmek, modülleri daha etkili kullanmak için önemlidir.

---

### ✅ **Modül İçindeki Fonksiyonlara ve Değişkenlere Erişim**

Daha önce oluşturduğumuz `matematik.py` modülü içinde aşağıdaki fonksiyonlar ve değişken vardı:

```python
def topla(a, b):
    return a + b

def carp(a, b):
    return a * b

pi = 3.14159  # Sabit değer
```

Bu modülün içeriğine erişmek için farklı yöntemler kullanılabilir.

📌 **Tam Modülü İçeri Aktarma (`import modul_adı`)**

```python
import matematik

print(matematik.topla(3, 5))  # 3 + 5 = 8
print(matematik.pi)  # 3.14159
```

📌 **Belirli Bir Fonksiyonu veya Değişkeni İçeri Aktarma (`from ... import ...`)**

```python
from matematik import topla, pi

print(topla(10, 2))  # 10 + 2 = 12
print(pi)  # 3.14159
```

📌 **Tüm İçeriği İçeri Aktarma (`from ... import *`)**  
Bu yöntemde, modül içindeki tüm öğelere direkt erişebiliriz. Ancak **isim çakışmalarına dikkat etmek gerekir**.

```python
from matematik import *

print(carp(4, 5))  # 4 * 5 = 20
print(pi)  # 3.14159
```

📌 **Aliasing (Kısayol Kullanımı)**
Uzun isimli modülleri daha kısa bir isimle çağırmak için `as` kullanılabilir.

```python
import matematik as m

print(m.topla(6, 7))  # 6 + 7 = 13
```

---

### ✅ **Modül İçeriklerini Listeleme (dir() ve help() Fonksiyonları)**

Bir modül içindeki kullanılabilir öğeleri görmek için `dir()` fonksiyonu kullanılabilir.

```python
import matematik
print(dir(matematik))  # ['__builtins__', '__cached__', '__doc__', '__file__', 'carp', 'pi', 'topla']
```

📌 **Modül Hakkında Detaylı Bilgi Almak (`help()`)**  
Bir modül veya fonksiyon hakkında daha fazla bilgi almak için `help()` fonksiyonu kullanılabilir.

```python
help(matematik)
```

---

## 📌 11.4 Modül ve Paketlerin Yönetimi

Python, modülleri belirli yollar içinde arar ve yükler. Bu yolları yöneterek kendi modüllerimizi ve paketlerimizi organize edebiliriz.

### ✅ **PYTHONPATH ve Modül Yolu**

Python, modülleri belirli dizinlerde arar. Bu dizinler, `sys.path` listesinde saklanır.

```python
import sys
print(sys.path)  # Python'un modül arama yollarını listeler
```

📌 **PYTHONPATH Ortam Değişkenini Kullanarak Modül Yolu Eklemek**
Bir modülü özel bir dizinde tutuyorsak, Python'un bu dizini görmesini sağlamak için aşağıdaki yöntemi kullanabiliriz:

```python
import sys
sys.path.append("/kendi_modullerim")
```

Böylece `/kendi_modullerim` klasöründeki modülleri Python dosyalarımızda kullanabiliriz.

---

### ✅ **modulename ve importlib Modülleri ile Modül Yönetimi**

📌 **Modülün Adını Dinamik Olarak Kullanma**
Bir modül ismi değişkene atanarak dinamik olarak içe aktarılabilir.

```python
modul_adi = "math"
modul = __import__(modul_adi)
print(modul.sqrt(16))  # 4.0
```

📌 **importlib ile Modülleri Yeniden Yükleme**
Modüller belleğe alındıktan sonra `import` işlemi tekrar çalıştırılsa bile aynı modülü yeniden yüklemez. Ancak `importlib` modülü ile bir modül manuel olarak yeniden yüklenebilir.

```python
import importlib
import matematik

importlib.reload(matematik)  # Modülü yeniden yükler
```

---

## 📌 11.5 Paketler (Packages)

Bir **paket**, birden fazla modülden oluşan ve belirli bir yapıya sahip dizinlerdir. Büyük projelerde kodları daha iyi organize etmek için paketler kullanılır.

---

### ✅ **Paket Nedir ve Ne İçin Kullanılır?**
Paketler, **aynı kategoriye ait modülleri bir araya getirmek** için kullanılır. Örneğin, veri işleme ile ilgili modülleri içeren bir paket oluşturulabilir.

Paketler genellikle **büyük projelerde** kod tekrarını azaltmak ve modülleri daha düzenli hale getirmek için kullanılır.

---

### ✅ **Paket Oluşturma ve Yapılandırma**
Bir Python paketi, içinde en az bir **modül** ve bir `__init__.py` dosyası bulunan bir klasördür.

📌 **Örnek bir paket yapısı:**
```
proje/
│
├── islem_paketi/
│   ├── __init__.py
│   ├── toplama.py
│   ├── carpma.py
│
└── main.py
```

Bu yapıda:
- **`__init__.py`**: Paketin bir Python paketi olduğunu belirtir.
- **`toplama.py`**: Toplama işlemleri için bir modüldür.
- **`carpma.py`**: Çarpma işlemleri için bir modüldür.

📌 **toplama.py içeriği:**
```python
def topla(a, b):
    return a + b
```

📌 **carpma.py içeriği:**
```python
def carp(a, b):
    return a * b
```

---

### ✅ **`__init__.py` Dosyasının Rolü**

Python 3.3’ten önce, `__init__.py` dosyası **bir dizinin Python paketi olduğunu belirtmek için zorunluydu**. Günümüzde ise bu dosya olmadan da paketler çalışabilir. Ancak, `__init__.py` dosyası içinde **paketin genel ayarlarını belirlemek** veya **alt modülleri otomatik olarak içe aktarmak** için kullanılır.

📌 **Basit bir `__init__.py` içeriği:**
```python
from .toplama import topla
from .carpma import carp
```

Böylece, `islem_paketi` içe aktarıldığında `topla()` ve `carp()` fonksiyonları doğrudan erişilebilir olur.

---

### ✅ **Alt Paketler ve İçe Aktarma**

Paket içinde **alt paketler** oluşturulabilir. Örneğin:

```
proje/
│
├── islem_paketi/
│   ├── __init__.py
│   ├── toplama.py
│   ├── carpma.py
│   ├── geometri/
│   │   ├── __init__.py
│   │   ├── daire.py
│   │   ├── dikdortgen.py
│
└── main.py
```

Burada **`geometri`** bir **alt paket** olarak oluşturulmuştur.

📌 **Modülleri içe aktarma:**
```python
from islem_paketi.geometri.daire import alan_hesapla
```

---


## 📌 11.6 Paket Yapısı ve İhtiyaçlar

Python projeleri büyüdükçe, kodların düzenli olması ve modüler bir yapı kazanması gerekir. **Paketleme**, kodların tekrar kullanılabilirliğini artırır ve farklı projelerde yeniden kullanılmasını kolaylaştırır.

---

### ✅ **Paket Klasör Yapısı**

Bir Python paketi, **klasörler ve modüllerden oluşan bir yapıdır**. Paket, Python'un modülleri sistematik şekilde organize etmesine olanak tanır.

**📌 Basit bir paket yapısı:**
```
proje/
│
├── benim_paketim/
│   ├── __init__.py
│   ├── mod1.py
│   ├── mod2.py
│
└── main.py
```

📌 **Dosyaların Görevleri:**
- **`benim_paketim/`** → Paketi içeren klasör.
- **`__init__.py`** → Paketi tanımlayan dosya.
- **`mod1.py`** ve **`mod2.py`** → Paket içindeki modüller.
- **`main.py`** → Paketi kullanan ana program.

---

### ✅ **Paket İsimlendirme ve Dizin Yapıları**

Paket isimleri:
- Küçük harf olmalı.
- Anlamlı ve açıklayıcı olmalı.
- Özel karakter ve boşluk içermemeli.

**📌 Örnek kötü isimlendirmeler:**
```
1MyPackage/  ❌ (Rakamla başlamamalı)
My-Package/  ❌ (Tire yerine alt çizgi kullan)
my package/  ❌ (Boşluk kullanılmamalı)
```

**📌 Önerilen isimlendirme:**
```
my_package/ ✅
```

**📌 Büyük projelerde önerilen yapı:**
```
proje/
│
├── src/
│   ├── benim_paketim/
│   │   ├── __init__.py
│   │   ├── mod1.py
│   │   ├── mod2.py
│
├── tests/
│   ├── test_mod1.py
│
├── setup.py
├── README.md
└── requirements.txt
```

- **`src/`** → Paketlerin tutulduğu ana dizin.
- **`tests/`** → Test dosyalarının bulunduğu klasör.
- **`setup.py`** → Paket yönetimi dosyası.
- **`requirements.txt`** → Gerekli bağımlılıkları içeren dosya.

---

### ✅ **Sürüm Yönetimi ve Paket Yönetimi Dosyaları (`setup.py`)**

📌 **`setup.py`** Python paketlerini **PyPI'ye yüklemek** ve dağıtmak için kullanılan bir betik dosyasıdır.

**Örnek bir `setup.py` dosyası:**
```python
from setuptools import setup, find_packages

setup(
    name="benim_paketim",
    version="1.0.0",
    packages=find_packages(),
    install_requires=[
        "numpy>=1.21.0",
        "pandas>=1.3.0"
    ],
    author="Senin İsmin",
    description="Bu paket, örnek bir Python paketidir.",
    url="https://github.com/kullanici/benim_paketim",
)
```

📌 **Açıklamalar:**
- `name` → Paket ismi.
- `version` → Paket sürümü.
- `packages=find_packages()` → Paketleri otomatik keşfeder.
- `install_requires` → Paket bağımlılıklarını belirler.
- `author`, `description`, `url` → Paket bilgileri.

📌 **Paketin yüklenmesi:**
```bash
pip install .
```

---

## 📌 11.7 Üçüncü Taraf Paketler

Python ekosisteminde binlerce üçüncü taraf paketi bulunmaktadır. Bunlar genellikle **PyPI (Python Package Index)** üzerinden yönetilir.

---

### ✅ **Python Paket Kataloğu (PyPI) ve `pip`**

**📌 PyPI (Python Package Index):**
- Python'un resmi **paket deposudur**.
- Üçüncü taraf kütüphaneleri içerir.
- Paketleri yüklemek ve yönetmek için kullanılır.

**📌 `pip` Nedir?**
- Python’un varsayılan **paket yöneticisidir**.
- Paketleri indirir, yükler ve günceller.

---

### ✅ **pip ile Paket Kurulumu ve Güncellenmesi**

📌 **Bir paket yükleme:**
```bash
pip install requests
```

📌 **Belirli bir sürümü yükleme:**
```bash
pip install requests==2.26.0
```

📌 **Paketleri güncelleme:**
```bash
pip install --upgrade requests
```

📌 **Tüm bağımlılıkları yükleme (`requirements.txt`):**
```bash
pip install -r requirements.txt
```

📌 **Yüklü paketleri listeleme:**
```bash
pip list
```

📌 **Bir paketi kaldırma:**
```bash
pip uninstall requests
```

---

### ✅ **Virtual Environments ve Paket Yönetimi**

📌 **Virtual Environment (Sanal Ortam) Nedir?**
- Projeler arasında paket bağımsızlığı sağlar.
- Farklı projelerin **farklı paket sürümleri** kullanmasına izin verir.
- Sistemdeki Python kurulumuna zarar vermeden çalışır.

📌 **Sanal ortam oluşturma:**
```bash
python -m venv benim_ortamim
```

📌 **Sanal ortamı etkinleştirme:**
- Windows:
  ```bash
  benim_ortamim\Scripts\activate
  ```
- Mac/Linux:
  ```bash
  source benim_ortamim/bin/activate
  ```

📌 **Sanal ortamı devre dışı bırakma:**
```bash
deactivate
```

---

## 📌 11.8 Paket ile Projeleri Yönetme

Bir projeyi tam anlamıyla bir **paket** olarak yönetmek, kod paylaşımını ve dağıtımını kolaylaştırır.

---

### ✅ **Proje Yapılandırması ve Paketleme**

Paketlerin dağıtıma uygun hale getirilmesi için genellikle şu dosyalar kullanılır:

📌 **Gerekli dosyalar:**
- `setup.py`
- `requirements.txt`
- `README.md`

📌 **Tüm bağımlılıkları listeleme:**
```bash
pip freeze > requirements.txt
```

📌 **Tüm bağımlılıkları yükleme:**
```bash
pip install -r requirements.txt
```

---

### ✅ **Proje Dağıtımı ve Yükleme (`pip install`)**

📌 **Paketin `.tar.gz` olarak oluşturulması:**
```bash
python setup.py sdist
```

📌 **PyPI’ye yükleme (`twine` ile):**
```bash
pip install twine
twine upload dist/*
```

📌 **Kendi paketimizi yüklemek:**
```bash
pip install benim_paketim.tar.gz
```

---

### ✅ **Paket Testi ve Doğrulama**

📌 **Paketin doğru çalıştığını test etmek için:**
```bash
python -c "import benim_paketim; print(benim_paketim.__version__)"
```

📌 **Testler için `pytest` kullanımı:**
```bash
pip install pytest
pytest tests/
```

---


## 📌 11.9 Modül ve Paket Testi

Kod yazarken en büyük risklerden biri **hataları fark etmeden kullanıma sunmaktır**.  
Bu yüzden testler yazmak, kodun düzgün çalıştığını doğrulamanın en iyi yollarından biridir.  

Python'da modüller ve paketler için **unittest**, **pytest** ve **doctest** gibi test araçları kullanılır.

---

### ✅ **Unit Testlerle Modül Testi (`unittest` ve `pytest`)**

📌 **Unit Test (Birim Test) nedir?**  
- Küçük kod parçalarının **doğru çalıştığını** test eder.  
- **Fonksiyon veya sınıf** bazında testler yazılır.  
- Değişiklik yapıldığında **kodun bozulmadığını** garantiler.  
- **unittest ve pytest** kütüphaneleri ile uygulanır.

---

#### 🛠 **`unittest` Modülü ile Test Yazma**  
Python'un dahili test kütüphanesidir. Daha çok **geleneksel test yapıları** kullanır.

📌 **Örnek: `unittest` ile fonksiyon testi**  
```python
import unittest  # Test kütüphanesini ekliyoruz
from my_package.module1 import toplama  # Test edilecek fonksiyonu içe aktarıyoruz

class TestToplama(unittest.TestCase):  # unittest.TestCase sınıfını miras alıyoruz
    def test_pozitif_sayilar(self):  
        self.assertEqual(toplama(3, 5), 8)  # Beklenen sonuç: 8

    def test_negatif_sayilar(self):  
        self.assertEqual(toplama(-2, -4), -6)  # Beklenen sonuç: -6

if __name__ == "__main__":
    unittest.main()  # Testleri çalıştır
```

1. `unittest.TestCase` sınıfından yeni bir test sınıfı oluşturduk.  
2. `assertEqual()` ile **gerçek sonucu** ve **beklenen sonucu** karşılaştırdık.  
3. `unittest.main()` ile tüm testleri otomatik çalıştırdık.  

✅ **Testleri çalıştırma:**  
```bash
python -m unittest discover
```

---

#### 🛠 **`pytest` Modülü ile Test Yazma**  
`pytest`, **daha okunaklı ve esnek** test yazmak için geliştirilmiş popüler bir kütüphanedir.

📌 **Örnek: `pytest` ile fonksiyon testi**  
```python
import pytest
from my_package.module1 import toplama

def test_toplama():
    assert toplama(3, 5) == 8  # Doğru sonucu bekliyoruz
    assert toplama(-2, -4) == -6  # Doğru sonucu bekliyoruz
```

- **unittest gibi sınıf tanımlamaya gerek yoktur**.  
- **`assert` ifadesi** ile doğrudan **gerçek** ve **beklenen** sonucu karşılaştırırız.  
- `pytest` ile testler daha kısa ve okunaklı olur.  

✅ **Testleri çalıştırma:**  
```bash
pytest
```

✅ **Hatalı testler için detaylı hata mesajları sağlar.**  

---

### ✅ **Mocking (Sahte Veri Kullanımı)**  
Bazen **gerçek API veya veri tabanını test etmek istemeyiz**. Bunun yerine sahte (mock) veriler kullanırız.

📌 **Örnek: `unittest.mock` ile API çağrısını taklit etme**  
```python
from unittest.mock import patch
import my_package.api  # API çağrısı yapan modülü içe aktarıyoruz

def test_api_cagrisi():
    with patch("my_package.api.get_data") as mock_get:  # API çağrısını sahte hale getiriyoruz
        mock_get.return_value = {"sonuc": "basarili"}
        assert my_package.api.get_data() == {"sonuc": "basarili"}  # Beklenen sonucu test ediyoruz
```

- `patch()` fonksiyonu ile **gerçek API çağrısını** engelleyip **sahte bir dönüş değeri** belirledik.  
- Böylece test sırasında **internete bağlanmadan** doğru sonucu test edebildik.

---

## 📌 11.10 Modül ve Paket Dokümantasyonu  

Kodun sadece **çalışması değil, anlaşılması** da önemlidir!  
Bu yüzden **iyi bir dokümantasyon**, uzun vadede **bakımı kolaylaştırır**.

---

### ✅ **Docstring ile Fonksiyon Açıklamaları**

📌 **İyi bir docstring yazımı:**  
```python
def toplama(a, b):
    """
    İki sayıyı toplar.

    Parametreler:
    a (int, float): Birinci sayı
    b (int, float): İkinci sayı

    Dönüş:
    int, float: Toplam sonucu
    """
    return a + b
```

✅ **Dokümantasyonu çağırma:**  
```python
print(toplama.__doc__)
```

---

### ✅ **Sphinx ile Profesyonel Dokümantasyon**

📌 **Sphinx, Python kodları için HTML, PDF gibi belgeler üretir.**  

✅ **Kurulum:**  
```bash
pip install sphinx
```

✅ **Dokümantasyon oluşturma:**  
```bash
sphinx-quickstart
sphinx-build -b html source/ build/
```

✅ **Alternatif Araçlar:**  
- **MkDocs** → Markdown tabanlı belgeleme.  
- **pdoc** → Hızlı ve basit Python dokümantasyonu.

---

## 📌 11.11 Modül ve Paket Optimizasyonu  

Kodun **hızlı, verimli ve düşük bellek kullanımlı** olması için optimizasyon yapmak gerekir.

---

### ✅ **Performans Ölçümü (`cProfile`)**  
Kodun yavaş çalışan yerlerini analiz etmek için kullanılır.

📌 **Örnek: `cProfile` ile hız ölçme**  
```bash
python -m cProfile my_script.py
```

---

### ✅ **`timeit` ile Zaman Ölçümü**  

📌 **Örnek: Bir fonksiyonun çalışma süresini ölçme**  
```python
import timeit

def test():
    return sum(range(1000000))

print(timeit.timeit(test, number=10))  # 10 kez çalıştırarak ortalama süreyi hesaplar
```

✅ **Kodun hangi bölümlerinin optimize edilmesi gerektiğini belirlemeye yardımcı olur.**

---

### ✅ **Bellek Optimizasyonu (`gc` Modülü)**  

📌 **Gereksiz bellek kullanımını temizleme:**  
```python
import gc
gc.collect()  # Kullanılmayan nesneleri temizler
```

---

### ✅ **Gereksiz Modül Yüklenmesini Önleme**  
📌 **Modülü gerektiğinde yükleme:**  
```python
import sys

if "numpy" not in sys.modules:
    import numpy
```

✅ **Bellek tasarrufu sağlar.**

---


## 📌 11.12 Güvenlik ve Modül Yönetimi  

Python'da **modüller ve paketler**, büyük projeleri yönetmeyi kolaylaştırır. Ancak, **dışarıdan gelen paketler güvenlik riskleri içerebilir**.  

Bu yüzden **güvenli paket yönetimi**, kötü amaçlı yazılımlara karşı önlem almak için hayati önem taşır.  

---

### ✅ **Güvenli Modül ve Paket Kullanımı**  

Bir modülü projeye dahil etmeden önce **güvenli olup olmadığını kontrol etmek gerekir**.  

📌 **Güvenli kullanım için ipuçları:**  
✔ **Resmi kaynaklardan yükleyin**: `PyPI (Python Package Index)` gibi güvenilir yerlerden paket indirin.  
✔ **Şüpheli paketleri tarayın**: Paket kodlarını manuel inceleyerek **zararlı kodları tespit edebilirsiniz**.  
✔ **İzinleri kontrol edin**: Bazı paketler **gereksiz izinler isteyebilir** (örneğin, dosya okuma/yazma, internet erişimi).  
✔ **Güncellemeleri takip edin**: Güvenlik açıklarını kapatmak için **kullandığınız paketleri güncelleyin**.  

---

### ✅ **Kötü Amaçlı Paketlerin Önlenmesi**  

Bazı kötü niyetli kişiler, **meşhur Python paketlerine benzeyen zararlı paketler** oluşturabilirler.  

📌 **Örneğin:**  
- Gerçek paket: `numpy`  
- Sahte paket: `nampy` (kötü amaçlı yazılım içeriyor olabilir)  

📌 **Zararlı paketleri önlemek için:**  
✔ **İlk olarak paketin PyPI sayfasını kontrol edin**:  
```bash
pip show package_name
```
✔ **Paketin SHA256 hash değerini kontrol edin:**  
```bash
pip hash package_name.tar.gz
```
✔ **Paketin GitHub veya resmi web sitesini araştırın.**  

✅ **Şüpheli paketleri kullanmamak için `pip install` yerine `pip install --no-binary :all:` tercih edebilirsiniz**.  
Bu sayede **paketleri doğrudan kaynak kodundan derleyerek** daha güvenli hale getirebilirsiniz.  

---

### ✅ **Paket Yönetiminde Güvenlik İpuçları**  

1️⃣ **Sanal ortam (`venv`) kullanın**  
Her proje için bağımsız bir **sanal ortam** oluşturmak, paket çakışmalarını ve güvenlik risklerini azaltır.  
```bash
python -m venv my_project_env
source my_project_env/bin/activate  # (Windows'da: my_project_env\Scripts\activate)
```

2️⃣ **Paket sürümlerini kilitleyin**  
Sürüm değişiklikleri bazen **güvenlik açıklarına yol açabilir**. `requirements.txt` dosyasında paketlerin kesin sürümlerini belirterek riskleri azaltabilirsiniz.  
```bash
pip freeze > requirements.txt
```
Geri yüklemek için:  
```bash
pip install -r requirements.txt
```

3️⃣ **Sahte modüllerden kaçının**  
Eğer bir paketi PyPI dışında bir kaynaktan yüklüyorsanız, **önce kodlarını manuel inceleyin**.  

4️⃣ **Paketleri tarayın**  
`pip-audit` gibi araçlar ile güvenlik açıklarını analiz edebilirsiniz.  
```bash
pip install pip-audit
pip-audit
```

---

## 📌 11.13 İleri Düzey Modül ve Paket Konuları  

Python'da **modül ve paket yönetimi** sadece `import` ile sınırlı değildir.  
Daha ileri seviye yöntemler ile modülleri **dinamik olarak yükleyebilir, özel içe aktarma teknikleri kullanabilirsiniz**.  

---

### ✅ **Metaclass Kullanımı**  

📌 **Metaclass nedir?**  
Python'da **sınıfları oluşturan sınıflardır**. Yani **sınıfların kendisi de bir nesnedir** ve `type` ile yaratılır.  

📌 **Örnek: Metaclass ile sınıf oluşturma**  
```python
class MetaTip(type):
    def __new__(cls, name, bases, attrs):
        print(f"{name} sınıfı oluşturuluyor...")
        return super().__new__(cls, name, bases, attrs)

class Ornek(metaclass=MetaTip):
    pass
```
✅ **Çalıştırınca:**  
```bash
Ornek sınıfı oluşturuluyor...
```

📌 **Ne işe yarar?**  
- **Otomatik validasyonlar ekleyebilirsiniz.**  
- **Sınıf içeriğini değiştirebilirsiniz.**  
- **Kendi dinamik sınıf sisteminizi geliştirebilirsiniz.**  

---

### ✅ **Dinamik Modül Yükleme ve Çalıştırma**  

Python'da **modülleri program çalışırken yüklemek mümkündür**.  
Bu, özellikle **plugin sistemleri** gibi **dinamik yapılar** için kullanışlıdır.

📌 **Örnek: `importlib` ile modül yükleme**  
```python
import importlib

modul_adi = "math"
math_modul = importlib.import_module(modul_adi)

print(math_modul.sqrt(16))  # 4.0
```

📌 **Gerçek dünya kullanım senaryoları:**  
- **Eklenti (plugin) sistemleri geliştirmek**  
- **Modülleri program akışına göre yüklemek**  
- **Dışarıdan belirlenen kodları çalıştırmak**  

---

### ✅ **Sıralı Yükleme ve Gelişmiş İçe Aktarma**  

Bazı durumlarda **modülleri belirli bir sıraya göre yüklemek** gerekebilir.  
Python, modülleri **önce önbellekten (`sys.modules`) kontrol eder**, sonra dizinleri tarar.

📌 **Örnek: `sys.path` ile özel modül yolu ekleme**  
```python
import sys

sys.path.append("/custom_modules/")  # Özel bir dizinden modül yükleme
import ozel_modul
```

✅ **Bu teknik özellikle projeye özel modüller eklerken kullanışlıdır.**

---

## 📌 11.14 Modül ve Paketlerle İlgili Proje Örnekleri  

Teorik bilgileri pratiğe dökmek için **bazı örnek projeler** inceleyelim.  

---

### ✅ **1. Modüler Bir Web Scraper (İnternet Tarayıcı)**  

**Amaç:** Farklı sitelerden veri çekebilen **modüler bir scraper** oluşturmak.  

📌 **Proje Yapısı:**  
```
web_scraper/
│── scrapers/
│   ├── base_scraper.py
│   ├── amazon_scraper.py
│   ├── twitter_scraper.py
│── utils/
│   ├── logger.py
│── main.py
```

📌 **Kod Örneği:**  
```python
# base_scraper.py
class BaseScraper:
    def fetch(self, url):
        raise NotImplementedError("Bu metot alt sınıflarda uygulanmalıdır!")

# amazon_scraper.py
from base_scraper import BaseScraper

class AmazonScraper(BaseScraper):
    def fetch(self, url):
        print(f"Amazon'dan veri çekiliyor: {url}")
```

✅ **Modüler yapı sayesinde kolayca yeni scraper'lar ekleyebiliriz!**  

---

### ✅ **2. Loglama Sistemi İçeren Modüler Uygulama**  

📌 **Amaç:** Farklı işlemleri loglayan **dinamik bir modül sistemi** oluşturmak.  

📌 **Örnek Kullanım:**  
```python
from utils.logger import log_yaz

log_yaz("Sistem başlatıldı!", "INFO")
log_yaz("Hata oluştu!", "ERROR")
```

📌 **Kod:**  
```python
# logger.py
import datetime

def log_yaz(mesaj, seviye="INFO"):
    zaman = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    print(f"[{zaman}] {seviye}: {mesaj}")
```

✅ **Gerçek projelerde modüler yapının nasıl kullanılacağını gördük.**  