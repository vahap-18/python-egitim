## 🎯 7. Sözlükler ve Kümeler 

Python'da **sözlükler** ve **kümeler**, verileri farklı şekillerde organize etmek için kullanılan veri yapılarıdır. Sözlükler, anahtar-değer çiftlerini tutarken, kümeler benzersiz öğeleri tutar. Şimdi bu veri yapılarını detaylı bir şekilde inceleyelim!

---

### 🔑 7.1 Sözlüklerin Tanımlanması ve Kullanımı

Sözlükler, süslü parantez `{}` içinde tanımlanır ve anahtar-değer çiftlerini tutar. Anahtarlar benzersiz olmalıdır ve değerler herhangi bir veri türünde olabilir.

#### **Sözlük Tanımlama:**
```python
ogrenci = {
    "isim": "Ali",
    "yas": 20,
    "bolum": "Bilgisayar Mühendisliği"
}
```

#### **Sözlük Öğelerine Erişim:**
```python
print(ogrenci["isim"])  # Çıktı: Ali
print(ogrenci.get("yas"))  # Çıktı: 20
```
- Sözlük öğelerine, anahtarlar kullanılarak erişilir. `get()` metodu, anahtar bulunamazsa `None` döndürür.

---

### 🔧 7.2 Kümelerin Tanımlanması ve Kullanımı

Kümeler, süslü parantez `{}` içinde tanımlanır ve benzersiz öğeleri tutar. Kümelerde sıralama yoktur ve öğeler tekrar edemez.

#### **Küme Tanımlama:**
```python
meyveler = {"elma", "muz", "çilek"}
sayilar = {1, 2, 3, 4, 5}
```

#### **Küme Öğelerine Erişim:**
```python
for meyve in meyveler:
    print(meyve)
```
- Kümelerde indeksleme yoktur, bu yüzden öğelere doğrudan erişilemez. Ancak döngülerle öğeler üzerinde gezinebilirsiniz.

---

### 🔄 7.3 Sözlük ve Küme Metotları

Sözlükler ve kümeler, farklı metotlara sahiptir. Bu metotlar, veri yapıları üzerinde çeşitli işlemler yapmayı sağlar.

#### **Sözlük Metotları:**
```python
ogrenci = {
    "isim": "Ali",
    "yas": 20,
    "bolum": "Bilgisayar Mühendisliği"
}

# Anahtarları listeleme
print(ogrenci.keys())  # Çıktı: dict_keys(['isim', 'yas', 'bolum'])

# Değerleri listeleme
print(ogrenci.values())  # Çıktı: dict_values(['Ali', 20, 'Bilgisayar Mühendisliği'])

# Anahtar-değer çiftlerini listeleme
print(ogrenci.items())  # Çıktı: dict_items([('isim', 'Ali'), ('yas', 20), ('bolum', 'Bilgisayar Mühendisliği')])

# Öğe ekleme
ogrenci["numara"] = 12345
print(ogrenci)  # Çıktı: {'isim': 'Ali', 'yas': 20, 'bolum': 'Bilgisayar Mühendisliği', 'numara': 12345}

# Öğe silme
ogrenci.pop("yas")
print(ogrenci)  # Çıktı: {'isim': 'Ali', 'bolum': 'Bilgisayar Mühendisliği', 'numara': 12345}
```

#### **Küme Metotları:**
```python
meyveler = {"elma", "muz", "çilek"}

# Öğe ekleme
meyveler.add("üzüm")
print(meyveler)  # Çıktı: {'elma', 'muz', 'çilek', 'üzüm'}

# Öğe silme
meyveler.remove("muz")
print(meyveler)  # Çıktı: {'elma', 'çilek', 'üzüm'}

# Küme birleştirme
diger_meyveler = {"kiraz", "şeftali"}
meyveler.update(diger_meyveler)
print(meyveler)  # Çıktı: {'elma', 'çilek', 'üzüm', 'kiraz', 'şeftali'}
```

---

### 🎯 7.4 Sözlüklerde ve Kümelerde Dilimleme ve İndeksleme

Sözlükler ve kümeler, listeler gibi dilimleme ve indeksleme işlemlerini desteklemez. Ancak sözlüklerde anahtarlar kullanılarak öğelere erişilebilir.

#### **Sözlüklerde Erişim:**
```python
ogrenci = {
    "isim": "Ali",
    "yas": 20,
    "bolum": "Bilgisayar Mühendisliği"
}

print(ogrenci["isim"])  # Çıktı: Ali
print(ogrenci.get("yas"))  # Çıktı: 20
```

#### **Kümelerde Erişim:**
```python
meyveler = {"elma", "muz", "çilek"}

for meyve in meyveler:
    print(meyve)
```
- Kümelerde indeksleme yoktur, bu yüzden öğelere doğrudan erişilemez. Ancak döngülerle öğeler üzerinde gezinebilirsiniz.

---

### 🌍 7.5 Günlük Hayattan Örnekler

#### **Örnek 1: Öğrenci Bilgileri**
```python
ogrenci = {
    "isim": "Ali",
    "yas": 20,
    "bolum": "Bilgisayar Mühendisliği"
}

# Öğrenci bilgilerini güncelleme
ogrenci["numara"] = 12345
print(ogrenci)  # Çıktı: {'isim': 'Ali', 'yas': 20, 'bolum': 'Bilgisayar Mühendisliği', 'numara': 12345}
```

#### **Örnek 2: Benzersiz Öğeleri Bulma**
```python
sayilar = [1, 2, 2, 3, 4, 4, 5]
benzersiz_sayilar = set(sayilar)
print(benzersiz_sayilar)  # Çıktı: {1, 2, 3, 4, 5}
```
- `set()` fonksiyonu, bir listedeki benzersiz öğeleri bulmak için kullanılır.

---

### 🖥️ Örnek Kod ve Çıktılar

```python
# Sözlükler ve Kümeler Örneği
ogrenci = {
    "isim": "Ali",
    "yas": 20,
    "bolum": "Bilgisayar Mühendisliği"
}

# Sözlük öğelerine erişim
print(ogrenci["isim"])  # Çıktı: Ali

# Küme tanımlama ve öğe ekleme
meyveler = {"elma", "muz", "çilek"}
meyveler.add("üzüm")
print(meyveler)  # Çıktı: {'elma', 'muz', 'çilek', 'üzüm'}

# Küme birleştirme
diger_meyveler = {"kiraz", "şeftali"}
meyveler.update(diger_meyveler)
print(meyveler)  # Çıktı: {'elma', 'muz', 'çilek', 'üzüm', 'kiraz', 'şeftali'}
```