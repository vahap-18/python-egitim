## 🎯 5. Fonksiyonlar 

Python'da **fonksiyonlar**, belirli bir işlevi yerine getirmek için kullanılan yeniden kullanılabilir kod bloklarıdır. Fonksiyonlar, kodunuzu daha modüler, okunabilir ve yönetilebilir hale getirir. Şimdi fonksiyonlarla ilgili tüm detayları inceleyelim!

---

### 🔑 5.1 Fonksiyon Tanımlama ve Çağırma

Fonksiyonlar, `def` anahtar kelimesiyle tanımlanır. Fonksiyon tanımlandıktan sonra, ismiyle çağrılarak kullanılır.

#### **Fonksiyon Tanımlama:**
```python
def merhaba_de():
    print("Merhaba Dünya!")
```

#### **Fonksiyon Çağırma:**
```python
merhaba_de()
```
- `merhaba_de()` fonksiyonu çağrıldığında, "Merhaba Dünya!" mesajı ekrana yazdırılır.

---

### 🔧 5.2 Parametreler ve Argümanlar

Fonksiyonlar, parametreler alarak daha esnek hale getirilebilir. **Parametreler**, fonksiyon tanımında belirtilen değişkenlerdir. **Argümanlar** ise fonksiyon çağrılırken bu parametrelere verilen değerlerdir.

#### **Parametreli Fonksiyon:**
```python
def selam_ver(isim):
    print(f"Merhaba, {isim}!")
```

#### **Fonksiyon Çağırma:**
```python
selam_ver("Ali")
```
- `isim` parametresine "Ali" argümanı verilir ve "Merhaba, Ali!" mesajı ekrana yazdırılır.

---

### 🎯 5.3 Varsayılan Parametre Değerleri

Fonksiyonlara varsayılan değerler atanabilir. Bu, fonksiyon çağrılırken belirli bir parametre için argüman verilmezse, varsayılan değerin kullanılmasını sağlar.

#### **Varsayılan Parametre:**
```python
def selam_ver(isim="Misafir"):
    print(f"Merhaba, {isim}!")
```

#### **Fonksiyon Çağırma:**
```python
selam_ver()          # Çıktı: Merhaba, Misafir!
selam_ver("Ali")     # Çıktı: Merhaba, Ali!
```
- `isim` parametresine argüman verilmezse, varsayılan değer olan "Misafir" kullanılır.

---

### 🔑 5.4 Anahtar Kelime Argümanları

Fonksiyon çağrılırken, parametre isimleri belirtilerek argümanlar verilebilir. Bu, özellikle çok sayıda parametreye sahip fonksiyonlarda kullanışlıdır.

#### **Anahtar Kelime Argümanları:**
```python
def bilgileri_goster(ad, yas, sehir):
    print(f"Ad: {ad}, Yaş: {yas}, Şehir: {sehir}")
```

#### **Fonksiyon Çağırma:**
```python
bilgileri_goster(ad="Ali", yas=25, sehir="Ankara")
```
- Parametre isimleri belirtilerek argümanlar verilir. Bu, sıralamanın önemli olmadığı anlamına gelir.

---

### 🔄 5.5 Geri Dönüş Değerleri (`return`)

Fonksiyonlar, `return` ifadesiyle bir değer döndürebilir. Bu değer, fonksiyonun çağrıldığı yerde kullanılabilir.

#### **Geri Dönüş Değeri:**
```python
def topla(a, b):
    return a + b
```

#### **Fonksiyon Çağırma:**
```python
sonuc = topla(3, 5)
print(sonuc)  # Çıktı: 8
```
- `topla` fonksiyonu, iki sayının toplamını döndürür ve bu değer `sonuc` değişkenine atanır.

---

### 🎭 5.6 Lambda Fonksiyonları

Lambda fonksiyonları, tek satırda tanımlanabilen küçük ve anonim fonksiyonlardır. Genellikle basit işlemler için kullanılır.

#### **Lambda Fonksiyonu:**
```python
kare = lambda x: x ** 2
```

#### **Lambda Fonksiyonunu Kullanma:**
```python
print(kare(5))  # Çıktı: 25
```
- `lambda x: x ** 2` ifadesi, bir sayının karesini hesaplayan bir fonksiyon tanımlar.

---

### 🌍 5.7 Günlük Hayattan Örnekler

#### **Örnek 1: Hesap Makinesi Fonksiyonu**
```python
def hesap_makinesi(islem, a, b):
    if islem == "topla":
        return a + b
    elif islem == "cikar":
        return a - b
    elif islem == "carp":
        return a * b
    elif islem == "bol":
        return a / b
    else:
        return "Geçersiz işlem!"
```

#### **Fonksiyon Çağırma:**
```python
sonuc = hesap_makinesi("topla", 10, 5)
print(sonuc)  # Çıktı: 15
```
- `hesap_makinesi` fonksiyonu, verilen işleme göre iki sayı üzerinde işlem yapar ve sonucu döndürür.

---

#### **Örnek 2: Lambda ile Sıralama**
```python
ogrenciler = [("Ali", 25), ("Veli", 20), ("Ayşe", 22)]
ogrenciler.sort(key=lambda x: x[1])  # Yaşa göre sırala
print(ogrenciler)
```
- `lambda x: x[1]` ifadesi, öğrencileri yaşlarına göre sıralamak için kullanılır.

---

### 🖥️ Örnek Kod ve Çıktılar

```python
# Fonksiyonlar Örneği
def selam_ver(isim="Misafir"):
    return f"Merhaba, {isim}!"

print(selam_ver())          # Çıktı: Merhaba, Misafir!
print(selam_ver("Ali"))     # Çıktı: Merhaba, Ali!

# Lambda Fonksiyonu Örneği
kare = lambda x: x ** 2
print(kare(4))              # Çıktı: 16

# Geri Dönüş Değeri Örneği
def topla(a, b):
    return a + b

sonuc = topla(10, 20)
print(sonuc)                # Çıktı: 30
```