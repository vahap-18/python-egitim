## 🎯 6. Listeler ve Demetler

Python'da **listeler** ve **demetler**, birden fazla öğeyi bir arada tutmak için kullanılan veri yapılarıdır. Listeler değiştirilebilir (mutable) iken, demetler değiştirilemez (immutable). Şimdi bu veri yapılarını detaylı bir şekilde inceleyelim!

---

### 🔑 6.1 Listelerin Tanımlanması ve Kullanımı

Listeler, köşeli parantez `[]` içinde tanımlanır ve farklı veri türlerini bir arada tutabilir.

#### **Liste Tanımlama:**
```python
meyveler = ["elma", "muz", "çilek"]
sayilar = [1, 2, 3, 4, 5]
karisik_liste = [10, "Python", 3.14, True]
```

#### **Liste Öğelerine Erişim:**
```python
print(meyveler[0])  # Çıktı: elma
print(sayilar[2])   # Çıktı: 3
```
- Listelerde indeksleme 0'dan başlar. Yani ilk öğe `[0]`, ikinci öğe `[1]` şeklinde erişilir.

---

### 🔧 6.2 Demetlerin Tanımlanması ve Kullanımı

Demetler, normal parantez `()` içinde tanımlanır ve listeler gibi farklı veri türlerini bir arada tutabilir. Ancak demetler değiştirilemez (immutable).

#### **Demet Tanımlama:**
```python
meyveler = ("elma", "muz", "çilek")
sayilar = (1, 2, 3, 4, 5)
karisik_demet = (10, "Python", 3.14, True)
```

#### **Demet Öğelerine Erişim:**
```python
print(meyveler[0])  # Çıktı: elma
print(sayilar[2])   # Çıktı: 3
```
- Demetlerde de indeksleme 0'dan başlar. Ancak demetler değiştirilemez, bu yüzden öğeleri güncelleme veya silme işlemleri yapılamaz.

---

### 🔄 6.3 Liste ve Demet Metotları

Listeler ve demetler, farklı metotlara sahiptir. Bu metotlar, veri yapıları üzerinde çeşitli işlemler yapmayı sağlar.

#### **Liste Metotları:**
```python
meyveler = ["elma", "muz", "çilek"]

# Öğe ekleme
meyveler.append("üzüm")  # Listenin sonuna "üzüm" ekler
print(meyveler)  # Çıktı: ['elma', 'muz', 'çilek', 'üzüm']

# Öğe silme
meyveler.remove("muz")  # "muz" öğesini siler
print(meyveler)  # Çıktı: ['elma', 'çilek', 'üzüm']

# Öğe indeksi bulma
indeks = meyveler.index("çilek")
print(indeks)  # Çıktı: 1
```

#### **Demet Metotları:**
```python
meyveler = ("elma", "muz", "çilek")

# Öğe indeksi bulma
indeks = meyveler.index("muz")
print(indeks)  # Çıktı: 1

# Öğe sayısı bulma
sayi = meyveler.count("elma")
print(sayi)  # Çıktı: 1
```
- Demetler değiştirilemez olduğu için, öğe ekleme veya silme gibi işlemler yapılamaz. Ancak `index()` ve `count()` gibi metotlar kullanılabilir.

---

### 🎯 6.4 Listelerde Dilimleme ve İndeksleme

Listelerde dilimleme (slicing) ve indeksleme işlemleri, belirli öğelere erişmek veya alt listeler oluşturmak için kullanılır.

#### **İndeksleme:**
```python
meyveler = ["elma", "muz", "çilek", "üzüm", "kiraz"]
print(meyveler[0])  # Çıktı: elma
print(meyveler[-1]) # Çıktı: kiraz (son öğe)
```

#### **Dilimleme:**
```python
print(meyveler[1:3])  # Çıktı: ['muz', 'çilek'] (1. ve 2. indeksler)
print(meyveler[:3])   # Çıktı: ['elma', 'muz', 'çilek'] (baştan 3. indekse kadar)
print(meyveler[2:])   # Çıktı: ['çilek', 'üzüm', 'kiraz'] (2. indeksten sona kadar)
print(meyveler[::2])  # Çıktı: ['elma', 'çilek', 'kiraz'] (ikişer atlayarak)
```

---

### 🌍 6.5 Günlük Hayattan Örnekler

#### **Örnek 1: Alışveriş Listesi**
```python
alisveris_listesi = ["elma", "muz", "ekmek", "süt"]

# Yeni öğe ekleme
alisveris_listesi.append("yoğurt")
print(alisveris_listesi)  # Çıktı: ['elma', 'muz', 'ekmek', 'süt', 'yoğurt']

# Öğe silme
alisveris_listesi.remove("ekmek")
print(alisveris_listesi)  # Çıktı: ['elma', 'muz', 'süt', 'yoğurt']
```

#### **Örnek 2: Öğrenci Notları**
```python
ogrenci_notlari = [("Ali", 85), ("Veli", 90), ("Ayşe", 78)]

# En yüksek notu bulma
en_yuksek_not = max(ogrenci_notlari, key=lambda x: x[1])
print(f"En yüksek not: {en_yuksek_not[0]} - {en_yuksek_not[1]}")
# Çıktı: En yüksek not: Veli - 90
```

---

### 🖥️ Örnek Kod ve Çıktılar

```python
# Listeler ve Demetler Örneği
meyveler = ["elma", "muz", "çilek"]
sayilar = (1, 2, 3, 4, 5)

# Liste öğelerine erişim
print(meyveler[0])  # Çıktı: elma

# Demet öğelerine erişim
print(sayilar[2])   # Çıktı: 3

# Liste metotları
meyveler.append("üzüm")
print(meyveler)  # Çıktı: ['elma', 'muz', 'çilek', 'üzüm']

# Demet metotları
indeks = sayilar.index(3)
print(indeks)  # Çıktı: 2

# Dilimleme
print(meyveler[1:3])  # Çıktı: ['muz', 'çilek']
```