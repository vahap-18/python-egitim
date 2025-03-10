## 🎯 3.1 Operatörler ve İfadeler 🐍

Python'da operatörler, değişkenler ve değerler üzerinde işlemler yapmak için kullanılır. Bu operatörler, matematiksel hesaplamalardan mantıksal karşılaştırmalara kadar birçok işlemi gerçekleştirmemizi sağlar. Hadi, bu operatörleri tek tek inceleyelim ve nasıl kullanıldıklarını öğrenelim!

---

### 🔢 1. Aritmetik Operatörler

Aritmetik operatörler, matematiksel işlemler yapmak için kullanılır. İşte en yaygın aritmetik operatörler:

- **Toplama (`+`)**: İki sayıyı toplar.
  ```python
  print(5 + 3)  # Çıktı: 8
  ```

- **Çıkarma (`-`)**: İki sayıyı çıkarır.
  ```python
  print(10 - 4)  # Çıktı: 6
  ```

- **Çarpma (`*`)**: İki sayıyı çarpar.
  ```python
  print(7 * 2)  # Çıktı: 14
  ```

- **Bölme (`/`)**: İki sayıyı böler ve sonucu ondalıklı sayı olarak verir.
  ```python
  print(10 / 2)  # Çıktı: 5.0
  ```

- **Tam Bölme (`//`)**: İki sayıyı böler ve sonucu tam sayı olarak verir.
  ```python
  print(10 // 3)  # Çıktı: 3
  ```

- **Mod Alma (`%`)**: İki sayının bölümünden kalanı verir.
  ```python
  print(10 % 3)  # Çıktı: 1
  ```

- **Üs Alma (`**`)**: Bir sayının üssünü alır.
  ```python
  print(2 ** 3)  # Çıktı: 8
  ```

---

### 🔄 2. Karşılaştırma Operatörleri

Karşılaştırma operatörleri, iki değeri karşılaştırmak için kullanılır. Sonuç olarak `True` veya `False` döner.

- **Eşitlik (`==`)**: İki değer eşit mi?
  ```python
  print(5 == 5)  # Çıktı: True
  ```

- **Eşit Değil (`!=`)**: İki değer eşit değil mi?
  ```python
  print(5 != 3)  # Çıktı: True
  ```

- **Büyüktür (`>`)**: Soldaki değer sağdakinden büyük mü?
  ```python
  print(10 > 5)  # Çıktı: True
  ```

- **Küçüktür (`<`)**: Soldaki değer sağdakinden küçük mü?
  ```python
  print(3 < 2)  # Çıktı: False
  ```

- **Büyük Eşit (`>=`)**: Soldaki değer sağdakinden büyük veya eşit mi?
  ```python
  print(10 >= 10)  # Çıktı: True
  ```

- **Küçük Eşit (`<=`)**: Soldaki değer sağdakinden küçük veya eşit mi?
  ```python
  print(5 <= 3)  # Çıktı: False
  ```

---

### 🔗 3. Mantıksal Operatörler

Mantıksal operatörler, birden fazla koşulu birleştirmek için kullanılır. Sonuç olarak `True` veya `False` döner.

- **Ve (`and`)**: Tüm koşullar doğruysa `True` döner.
  ```python
  print(5 > 3 and 10 < 20)  # Çıktı: True
  ```

- **Veya (`or`)**: En az bir koşul doğruysa `True` döner.
  ```python
  print(5 > 3 or 10 > 20)  # Çıktı: True
  ```

- **Değil (`not`)**: Koşulun tersini alır.
  ```python
  print(not(5 > 3))  # Çıktı: False
  ```

---

### 📝 4. Atama Operatörleri

Atama operatörleri, bir değişkene değer atamak için kullanılır. Ayrıca, atama işlemi sırasında matematiksel işlemler de yapabilirsin.

- **Temel Atama (`=`)**: Değişkene değer atar.
  ```python
  x = 10
  print(x)  # Çıktı: 10
  ```

- **Topla ve Ata (`+=`)**: Değişkenin değerini artırır ve atar.
  ```python
  x = 5
  x += 3  # x = x + 3
  print(x)  # Çıktı: 8
  ```

- **Çıkar ve Ata (`-=`)**: Değişkenin değerini azaltır ve atar.
  ```python
  x = 10
  x -= 4  # x = x - 4
  print(x)  # Çıktı: 6
  ```

- **Çarp ve Ata (`*=`)**: Değişkenin değerini çarpar ve atar.
  ```python
  x = 2
  x *= 3  # x = x * 3
  print(x)  # Çıktı: 6
  ```

- **Böl ve Ata (`/=`)**: Değişkenin değerini böler ve atar.
  ```python
  x = 10
  x /= 2  # x = x / 2
  print(x)  # Çıktı: 5.0
  ```

---

### 🔍 5. Bit Düzeyinde Operatörler

Bit düzeyinde operatörler, sayıların bitlerini işlemek için kullanılır. Genellikle düşük seviyeli programlamada kullanılır.

- **Ve (`&`)**: İki sayının bitlerini karşılaştırır ve her ikisi de `1` ise `1` döner.
  ```python
  print(5 & 3)  # Çıktı: 1
  ```

- **Veya (`|`)**: İki sayının bitlerini karşılaştırır ve en az biri `1` ise `1` döner.
  ```python
  print(5 | 3)  # Çıktı: 7
  ```

- **XOR (`^`)**: İki sayının bitlerini karşılaştırır ve farklı ise `1` döner.
  ```python
  print(5 ^ 3)  # Çıktı: 6
  ```

- **Değil (`~`)**: Sayının bitlerini tersine çevirir.
  ```python
  print(~5)  # Çıktı: -6
  ```

- **Sola Kaydırma (`<<`)**: Sayının bitlerini sola kaydırır.
  ```python
  print(5 << 1)  # Çıktı: 10
  ```

- **Sağa Kaydırma (`>>`)**: Sayının bitlerini sağa kaydırır.
  ```python
  print(5 >> 1)  # Çıktı: 2
  ```

---

### 🔎 6. Kimlik ve Üyelik Operatörleri

Kimlik ve üyelik operatörleri, değişkenlerin kimliğini veya bir koleksiyonun içinde olup olmadığını kontrol eder.

- **Kimlik Operatörü (`is`)**: İki değişken aynı nesneye mi işaret ediyor?
  ```python
  x = [1, 2, 3]
  y = x
  print(x is y)  # Çıktı: True
  ```

- **Kimlik Değil Operatörü (`is not`)**: İki değişken farklı nesnelere mi işaret ediyor?
  ```python
  x = [1, 2, 3]
  y = [1, 2, 3]
  print(x is not y)  # Çıktı: True
  ```

- **Üyelik Operatörü (`in`)**: Bir değer, bir koleksiyonun içinde mi?
  ```python
  liste = [1, 2, 3]
  print(2 in liste)  # Çıktı: True
  ```

- **Üyelik Değil Operatörü (`not in`)**: Bir değer, bir koleksiyonun içinde değil mi?
  ```python
  liste = [1, 2, 3]
  print(4 not in liste)  # Çıktı: True
  ```

---

### Örnek Kod ve Çıktılar 🖥️

```python
# Operatörler ve İfadeler Örneği
x = 10
y = 3

# Aritmetik Operatörler
print("Toplama:", x + y)  # Çıktı: 13
print("Çarpma:", x * y)   # Çıktı: 30

# Karşılaştırma Operatörleri
print("x > y:", x > y)    # Çıktı: True

# Mantıksal Operatörler
print("x > 5 and y < 5:", x > 5 and y < 5)  # Çıktı: True

# Atama Operatörleri
x += 5
print("x += 5:", x)  # Çıktı: 15

# Bit Düzeyinde Operatörler
print("x & y:", x & y)  # Çıktı: 3

# Kimlik ve Üyelik Operatörleri
liste = [1, 2, 3]
print("2 in liste:", 2 in liste)  # Çıktı: True
```

**Çıktı:**
```
Toplama: 13
Çarpma: 30
x > y: True
x > 5 and y < 5: True
x += 5: 15
x & y: 3
2 in liste: True
```

---


## 🎯 3.2 Tip Dönüşümleri 

Python'da **tip dönüşümleri**, bir veri türünü başka bir veri türüne dönüştürmek için kullanılır. Bu, özellikle farklı veri türleriyle çalışırken veya kullanıcı girdilerini işlerken oldukça kullanışlıdır. Hadi, bu dönüşümleri nasıl yapacağımızı öğrenelim!

---

### 🔄 Veri Tipi Dönüşüm Fonksiyonları

Python'da tip dönüşümleri için birçok yerleşik fonksiyon bulunur. İşte en yaygın olanlar:

- **`int()`**: Bir değeri tam sayıya (`int`) dönüştürür.
- **`float()`**: Bir değeri ondalıklı sayıya (`float`) dönüştürür.
- **`str()`**: Bir değeri metin dizisine (`str`) dönüştürür.
- **`list()`**: Bir değeri listeye (`list`) dönüştürür.
- **`tuple()`**: Bir değeri demete (`tuple`) dönüştürür.
- **`set()`**: Bir değeri kümeye (`set`) dönüştürür.
- **`dict()`**: Bir değeri sözlüğe (`dict`) dönüştürür.

---

### 🔢 Sayısal Dönüşümler

Sayısal dönüşümler, bir sayıyı başka bir sayı türüne dönüştürmek için kullanılır. Örneğin, bir tam sayıyı ondalıklı sayıya veya tam sayıya çevirebilirsin.

#### **Tam Sayıya Dönüştürme (`int()`)**
```python
x = 10.5
y = int(x)  # Ondalıklı sayıyı tam sayıya dönüştürür.
print(y)  # Çıktı: 10
```

#### **Ondalıklı Sayıya Dönüştürme (`float()`)**
```python
x = 10
y = float(x)  # Tam sayıyı ondalıklı sayıya dönüştürür.
print(y)  # Çıktı: 10.0
```

#### **Metin Dizisine Dönüştürme (`str()`)**
```python
x = 10
y = str(x)  # Tam sayıyı metin dizisine dönüştürür.
print(y)  # Çıktı: "10"
```

---

### 🔤 Dizi ve Sözlük Dönüşümleri

Dizi ve sözlük dönüşümleri, bir veri yapısını başka bir veri yapısına dönüştürmek için kullanılır. Örneğin, bir listeyi demete veya bir sözlüğe dönüştürebilirsin.

#### **Listeye Dönüştürme (`list()`)**
```python
x = (1, 2, 3)  # Demet (tuple)
y = list(x)  # Demeti listeye dönüştürür.
print(y)  # Çıktı: [1, 2, 3]
```

#### **Demete Dönüştürme (`tuple()`)**
```python
x = [1, 2, 3]  # Liste
y = tuple(x)  # Listeyi demete dönüştürür.
print(y)  # Çıktı: (1, 2, 3)
```

#### **Kümeye Dönüştürme (`set()`)**
```python
x = [1, 2, 2, 3]  # Liste
y = set(x)  # Listeyi kümeye dönüştürür.
print(y)  # Çıktı: {1, 2, 3}
```

#### **Sözlüğe Dönüştürme (`dict()`)**
```python
x = [("isim", "Ali"), ("yas", 25)]  # Liste içinde demetler
y = dict(x)  # Listeyi sözlüğe dönüştürür.
print(y)  # Çıktı: {'isim': 'Ali', 'yas': 25}
```

---

### Örnek Kod ve Çıktılar 🖥️

```python
# Tip Dönüşümleri Örneği
x = 10.5
y = int(x)  # Ondalıklı sayıyı tam sayıya dönüştürür.
print("int(x):", y)  # Çıktı: 10

x = 10
y = float(x)  # Tam sayıyı ondalıklı sayıya dönüştürür.
print("float(x):", y)  # Çıktı: 10.0

x = 10
y = str(x)  # Tam sayıyı metin dizisine dönüştürür.
print("str(x):", y)  # Çıktı: "10"

x = (1, 2, 3)  # Demet (tuple)
y = list(x)  # Demeti listeye dönüştürür.
print("list(x):", y)  # Çıktı: [1, 2, 3]

x = [1, 2, 3]  # Liste
y = tuple(x)  # Listeyi demete dönüştürür.
print("tuple(x):", y)  # Çıktı: (1, 2, 3)

x = [1, 2, 2, 3]  # Liste
y = set(x)  # Listeyi kümeye dönüştürür.
print("set(x):", y)  # Çıktı: {1, 2, 3}

x = [("isim", "Ali"), ("yas", 25)]  # Liste içinde demetler
y = dict(x)  # Listeyi sözlüğe dönüştürür.
print("dict(x):", y)  # Çıktı: {'isim': 'Ali', 'yas': 25}
```

**Çıktı:**
```
int(x): 10
float(x): 10.0
str(x): 10
list(x): [1, 2, 3]
tuple(x): (1, 2, 3)
set(x): {1, 2, 3}
dict(x): {'isim': 'Ali', 'yas': 25}
```

---


## 🎯 3.3 Giriş ve Çıkış İşlemleri 

Python'da **giriş ve çıkış işlemleri**, programlarımızın kullanıcıyla etkileşim kurmasını sağlar. Kullanıcıdan veri almak, bu verileri işlemek ve sonuçları ekrana yazdırmak için kullanılan temel araçlardır. Hadi, bu işlemleri detaylı bir şekilde inceleyelim!

---

### 🔑 Kullanıcıdan Giriş Alma (`input()`)

Python'da kullanıcıdan veri almak için `input()` fonksiyonu kullanılır. Bu fonksiyon, kullanıcının girdiği veriyi bir **string** olarak döndürür. Eğer sayısal bir değer almak istiyorsanız, tip dönüşümü yapmanız gerekir.

#### **`input()` Fonksiyonu Parametreleri:**
- **prompt (isteğe bağlı):** Kullanıcıya gösterilecek mesaj. Bu parametre, kullanıcıdan ne tür bir giriş beklediğinizi belirtmenizi sağlar.

#### **Temel Kullanım:**
```python
isim = input("Adınızı girin: ")
print("Merhaba,", isim)
```

#### **Sayısal Giriş Alma:**
```python
yas = int(input("Yaşınızı girin: "))
print("Yaşınız:", yas)
```

#### **Örnek:**
```python
# Kullanıcıdan iki sayı alıp toplama
sayi1 = int(input("Birinci sayıyı girin: "))
sayi2 = int(input("İkinci sayıyı girin: "))
toplam = sayi1 + sayi2
print("Toplam:", toplam)
```

**Çıktı:**
```
Birinci sayıyı girin: 5
İkinci sayıyı girin: 10
Toplam: 15
```

---

### 🖥️ Ekrana Çıktı Verme (`print()`)

Python'da ekrana çıktı vermek için `print()` fonksiyonu kullanılır. Bu fonksiyon, verilen değerleri ekrana yazdırır. Birden fazla değer yazdırmak isterseniz, virgülle ayırabilirsiniz.

#### **`print()` Fonksiyonu Parametreleri:**
- **`*objects`:** Yazdırılacak değerler. Birden fazla değer virgülle ayrılarak verilebilir.
- **`sep` (isteğe bağlı):** Değerler arasına konulacak ayırıcı. Varsayılan değeri bir boşluktur (` `).
- **`end` (isteğe bağlı):** Yazdırma işlemi sonrasında eklenen karakter. Varsayılan değeri yeni satırdır (`\n`).
- **`file` (isteğe bağlı):** Çıktının yazdırılacağı dosya. Varsayılan değer `sys.stdout` (ekran) olarak ayarlanmıştır.
- **`flush` (isteğe bağlı):** Çıktının hemen yazdırılıp yazdırılmayacağını belirler. Varsayılan değer `False`'dur.

#### **Temel Kullanım:**
```python
print("Merhaba Dünya!")
```

#### **Birden Fazla Değer Yazdırma:**
```python
isim = "Ali"
yas = 25
print("Adı:", isim, "Yaşı:", yas)
```

#### **`sep` Parametresi Kullanımı:**
```python
print("Python", "Programlama", "Dili", sep="-")
# Çıktı: Python-Programlama-Dili
```

#### **`end` Parametresi Kullanımı:**
```python
print("Merhaba", end=" ")
print("Dünya")
# Çıktı: Merhaba Dünya
```

#### **Örnek:**
```python
# Kullanıcıdan alınan bilgileri ekrana yazdırma
isim = input("Adınızı girin: ")
yas = int(input("Yaşınızı girin: "))
print("Adınız:", isim, "Yaşınız:", yas, sep=" | ", end="!\n")
```

**Çıktı:**
```
Adınızı girin: Ali
Yaşınızı girin: 25
Adınız: | Ali | Yaşınız: | 25!
```

---

### 🎨 Formatlı Çıktı (String Formatting)

Python'da formatlı çıktı vermek için birden fazla yöntem bulunur. Bu yöntemler, metin içinde değişkenleri daha okunabilir bir şekilde yerleştirmenizi sağlar.

#### **1. `format()` Metodu:**
```python
isim = "Ali"
yas = 25
print("Adı: {}, Yaşı: {}".format(isim, yas))
```

#### **2. f-string (Python 3.6 ve sonrası):**
```python
isim = "Ali"
yas = 25
print(f"Adı: {isim}, Yaşı: {yas}")
```

#### **3. Eski Stil (`%` Operatörü):**
```python
isim = "Ali"
yas = 25
print("Adı: %s, Yaşı: %d" % (isim, yas))
```

#### **Örnek:**
```python
# Kullanıcıdan alınan bilgileri formatlı bir şekilde yazdırma
isim = input("Adınızı girin: ")
yas = int(input("Yaşınızı girin: "))

# format() metodu ile
print("Adı: {}, Yaşı: {}".format(isim, yas))

# f-string ile
print(f"Adı: {isim}, Yaşı: {yas}")

# Eski stil ile
print("Adı: %s, Yaşı: %d" % (isim, yas))
```

**Çıktı:**
```
Adınızı girin: Ali
Yaşınızı girin: 25
Adı: Ali, Yaşı: 25
Adı: Ali, Yaşı: 25
Adı: Ali, Yaşı: 25
```

---

### Örnek Kod ve Çıktılar 🖥️

```python
# Giriş ve Çıkış İşlemleri Örneği
isim = input("Adınızı girin: ")
yas = int(input("Yaşınızı girin: "))

# Ekrana çıktı verme
print("Adınız:", isim, "Yaşınız:", yas)

# Formatlı çıktı verme
print("Adı: {}, Yaşı: {}".format(isim, yas))
print(f"Adı: {isim}, Yaşı: {yas}")
print("Adı: %s, Yaşı: %d" % (isim, yas))
```

**Çıktı:**
```
Adınızı girin: Ali
Yaşınızı girin: 25
Adınız: Ali Yaşınız: 25
Adı: Ali, Yaşı: 25
Adı: Ali, Yaşı: 25
Adı: Ali, Yaşı: 25
```