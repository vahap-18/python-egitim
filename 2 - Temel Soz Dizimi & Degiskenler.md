# 🐍 Python'a Giriş - Bölüm 2: Temel Sözdizimi ve Değişkenler

Merhaba Python meraklısı! Eğer buradaysan, Python'un temellerini iyice kavramaya hazırsın demektir. Bir programlama dili öğrenirken en önemli adımlardan biri **sözdizimini** (syntax) anlamaktır. Python’un temiz ve okunabilir yapısıyla bunu öğrenmek oldukça keyifli olacak! Hadi başlayalım!

---

## 📌 2.1 Python'da Temel Sözdizimi

Python, öğrenmesi kolay ve okunaklı bir dildir. Ancak her dilin belirli yazım kuralları vardır. Python’da **girintileme**, **satır sonları** ve **yorum satırları** çok önemlidir.

### 📝 Satır Sonu ve Girintileme

Python, **diğer birçok programlama dilinden farklı olarak** kod bloklarını süslü parantez `{}` yerine girintileme ile belirler. Bu yüzden girintiye dikkat etmezsen hata alırsın.

✅ **Doğru Kullanım:**
```python
if True:
    print("Girintiye dikkat etmek önemli!")
```

❌ **Yanlış Kullanım:**
```python
if True:
print("Bu hata verir!")  # IndentationError ❌
```
**Girintileme için genellikle 4 boşluk (ya da 1 tab) kullanılır.** Python girintilemeyi kod bloklarını ayırt etmek için zorunlu kılar.

Girintileme hataları Python’da en sık karşılaşılan hatalardan biridir. Eğer farklı editörlerde kod yazarken hata alırsan, tab ve boşlukların karışmadığından emin olmalısın. **PEP 8** standardına göre **dört boşluk** kullanımı önerilir.

Girintileme kullanımı, yalnızca `if` bloklarında değil, fonksiyon tanımlamalarında, döngülerde ve diğer yapılar için de gereklidir:
```python
def merhaba():
    print("Merhaba, Dünya!")
```

---

### 🗨️ Python'da Yorum Satırları

Kod yazarken **yorum satırları** eklemek, kodu anlaşılır hale getirmek için harika bir yöntemdir. Python'da yorumlar `#` işaretiyle başlar.

✅ **Tek Satırlık Yorumlar:**
```python
# Bu bir yorum satırıdır
print("Python öğreniyoruz!")
```

✅ **Çok Satırlı Yorumlar:**
```python
"""
Bu birden fazla satır içeren bir açıklamadır.
Genellikle büyük açıklamalar veya dokümantasyon için kullanılır.
"""
print("Çok satırlı yorumları da kullanabiliriz!")
```

**Unutma:** Çok satırlı yorumlar aslında bir **string** objesidir, ancak bir değişkene atanmadığında yorum gibi çalışır.

Python'da yorumlar, **diğer programcılar tarafından kodunun anlaşılmasını kolaylaştırmak** için kullanılır. Kodun uzun vadede okunaklı ve sürdürülebilir olması için yorum eklemek iyi bir alışkanlıktır.

---

### 📜 Python'da Temel Yazım Kuralları

Python, temiz ve okunabilir bir sözdizimine sahiptir. İşte temel kurallar:

✅ **Büyük-küçük harf duyarlıdır:** `variable`, `Variable` ve `VARIABLE` farklı değişkenlerdir.
✅ **Satır sonlarında noktalı virgül (;) gerekmez:** Python, her satırın sonunda otomatik olarak satır sonunu algılar.
✅ **Bir satıra birden fazla komut yazılabilir:** Eğer gerekiyorsa `;` kullanarak bir satıra birden fazla komut yazabilirsin.
```python
print("Merhaba"); print("Python")  # Çalışır ama önerilmez
```
✅ **Uzun satırlar `\` ile bölünebilir:**
```python
uzun_metin = "Bu çok uzun bir metindir ve " \
            "iki satırda yazılabilir."
```
✅ **Parantez içinde yazılan uzun ifadeler `\` olmadan bölünebilir:**
```python
toplam = (
    5 + 10 + 15 +
    20 + 25 + 30
)
```

Python'da **daha okunabilir kod yazmak için** PEP 8 yönergelerine uymak faydalı olacaktır. Özellikle **boşluk kullanımı**, **değişken isimlendirme**, ve **girintileme** gibi konulara dikkat etmek, kodun uzun vadede okunmasını kolaylaştıracaktır.

---

Anladım! O zaman daha akıcı ve madde madde bir anlatım tarzıyla devam edelim. Soru-cevap formatı yerine, direkt olarak bilgiyi aktaracağım. İşte yeniden düzenlenmiş hali:

---

## 📌 2.2 Değişkenler ve Veri Tipleri

Python’da **değişkenler**, bir veriyi saklamak için kullanılan isimlendirilmiş alanlardır. Python değişkenleri **dinamik olarak tanımlanır**, yani bir veri türü belirtmene gerek yoktur. Python, türü otomatik olarak belirler. Bu, Python'u öğrenmeyi kolaylaştıran en büyük özelliklerden biridir. Hadi, bu konuyu daha detaylı inceleyelim!

---

### 🔹 Değişken Tanımlama ve İsimlendirme Kuralları

Python’da değişken isimleri belirli kurallara uymalıdır. Bu kuralları bilmek, hem hata yapmamanı sağlar hem de kodunuzun daha okunabilir olmasına yardımcı olur. İşte dikkat etmen gerekenler:

- **Harf (a-z, A-Z), rakam (0-9) ve alt çizgi (_) içerebilir.**  
  Örneğin: `isim`, `yas_25`, `kullanici_adi`

- **Bir harf veya alt çizgi (_) ile başlamalıdır.**  
  Örneğin: `_isim`, `yas`, `kullanici1`  
  ❌ Geçersiz örnek: `1yas` (rakamla başlayamaz)

- **Büyük/küçük harf duyarlıdır:**  
  `yas`, `Yas` ve `YAS` farklı değişkenlerdir. Python, büyük-küçük harf ayrımı yapar.  
  ```python
  yas = 25
  Yas = 30
  print(yas)  # Çıktı: 25
  print(Yas)  # Çıktı: 30
  ```

- **Python’un özel anahtar kelimeleri değişken adı olarak kullanılamaz.**  
  `if`, `else`, `for`, `def` gibi kelimeler Python'un anahtar kelimeleridir. Bunları değişken adı olarak kullanamazsın.  
  ```python
  def = 10  # ❌ Geçersiz çünkü 'def' Python'un anahtar kelimesidir.
  ```

- **İsimlendirme için `snake_case` önerilir:**  
  Python'da değişken isimlendirme için `snake_case` (kelimeler arasında alt çizgi) kullanılır. Bu, kodun daha okunabilir olmasını sağlar.  
  ```python
  kullanici_adi = "Ali"
  dogum_yili = 1995
  ```

---

### 🔹 Temel Veri Tipleri

Python'da birçok farklı veri türü vardır. Her veri türü, farklı türdeki verileri saklamak için kullanılır. İşte en yaygın olanlar:

---

### 🔢 1. Sayılar (Numbers)

Python'da sayılar üç ana türde olabilir:

- **Integer (`int`)**: Tam sayılar. Örneğin: `10`, `-5`, `1000`  
  Kullanım alanı: Sayma işlemlerinde, döngülerde, indekslemede.

- **Float (`float`)**: Ondalıklı sayılar. Örneğin: `3.14`, `-0.5`, `2.0`  
  Kullanım alanı: Matematiksel hesaplamalarda, ölçümlerde.

- **Complex (`complex`)**: Karmaşık sayılar. Örneğin: `3 + 4j`  
  Kullanım alanı: Bilimsel hesaplamalarda, mühendislik uygulamalarında.

**Örnek Kullanım:**
```python
sayi1 = 10  # int
sayi2 = 3.14  # float
sayi3 = 2 + 3j  # complex

print(sayi1)  # Çıktı: 10
print(sayi2)  # Çıktı: 3.14
print(sayi3)  # Çıktı: (2+3j)
```

**Farkları:**
- **Integer** tam sayıları, **Float** ondalıklı sayıları, **Complex** ise karmaşık sayıları temsil eder.

---

### 🔤 2. Diziler (Strings, Lists, Tuples)

Diziler, birden fazla veriyi bir arada tutmak için kullanılır. Python'da üç temel dizi türü vardır:

- **String (`str`)**: Metinsel veriler. Tırnak içinde yazılır (`"Merhaba"` veya `'Dünya'`).  
  Kullanım alanı: Metin işlemlerinde, kullanıcı girdilerinde.  
  **Örnek:**
  ```python
  isim = "Python"
  print(isim)  # Çıktı: Python
  ```

- **List (`list`)**: Değiştirilebilir (mutable) diziler. Köşeli parantez `[]` içinde yazılır.  
  Kullanım alanı: Veri koleksiyonlarında, sıralı verilerde.  
  **Örnek:**
  ```python
  yaslar = [20, 25, 30]
  print(yaslar)  # Çıktı: [20, 25, 30]
  ```

- **Tuple (`tuple`)**: Değiştirilemez (immutable) diziler. Normal parantez `()` içinde yazılır.  
  Kullanım alanı: Değiştirilmesini istemediğin verilerde.  
  **Örnek:**
  ```python
  dogum_gunleri = (2000, 1995, 1998)
  print(dogum_gunleri)  # Çıktı: (2000, 1995, 1998)
  ```

**Farkları:**
- **List** değiştirilebilir, **Tuple** değiştirilemez.
- **String** sadece metin verileri içerir.

---

### 📦 3. Sözlükler (Dictionaries)

Sözlükler, **anahtar-değer (key-value) çiftleri** içeren veri yapılarıdır. Anahtarlar benzersiz olmalıdır ve değerler farklı türlerde olabilir.

**Kullanım Alanı:** Anahtar-değer çiftlerinin olduğu durumlarda (örneğin, kullanıcı bilgileri).  
**Örnek:**
```python
kisi = {"isim": "Ali", "yas": 25, "meslek": "Mühendis"}
print(kisi["isim"])  # Çıktı: Ali
print(kisi["yas"])   # Çıktı: 25
```

**Farkları:**
- Sözlükler, anahtar-değer çiftleriyle çalışır. Listeler ve Tuple'lar gibi sıralı değildir.

---

### 🎭 4. Kümeler (Sets)

Kümeler, **benzersiz elemanlar içeren sırasız koleksiyonlardır**. Aynı elemandan birden fazla olamaz.

**Kullanım Alanı:** Benzersiz verileri saklamak için (örneğin, kullanıcı ID'leri).  
**Örnek:**
```python
sayilar = {1, 2, 3, 4, 4, 5}
print(sayilar)  # Çıktı: {1, 2, 3, 4, 5}
```

**Farkları:**
- Kümeler, sırasız ve benzersiz elemanlar içerir. Listeler ve Tuple'lar gibi sıralı değildir.

---

### ⚡ 5. Boolean (Mantıksal) Değerler

Boolean veri türü, **True** veya **False** değerlerini alır. Genellikle koşullu ifadelerde kullanılır.

**Kullanım Alanı:** Koşullu ifadelerde, mantıksal karşılaştırmalarda.  
**Örnek:**
```python
aktif_mi = True
print(aktif_mi)  # Çıktı: True
```

**Farkları:**
- Boolean sadece `True` veya `False` değerlerini alır. Diğer veri tipleri gibi çeşitli verileri saklamaz.

---

### Örnek Kod ve Çıktılar 🖥️

```python
# Değişkenler ve Veri Tipleri Örneği
isim = "Python"
versiyon = 3.9
ozellikler = ["basit", "hızlı", "güçlü"]
bilgi = {"isim": isim, "versiyon": versiyon, "ozellikler": ozellikler}

print("İsim:", isim)
print("Versiyon:", versiyon)
print("Özellikler:", ozellikler)
print("Bilgi:", bilgi)
```

**Çıktı:**
```
İsim: Python
Versiyon: 3.9
Özellikler: ['basit', 'hızlı', 'güçlü']
Bilgi: {'isim': 'Python', 'versiyon': 3.9, 'ozellikler': ['basit', 'hızlı', 'güçlü']}
```