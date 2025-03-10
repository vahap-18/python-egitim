## 🎯 4 Kontrol Yapıları 

Python'da **kontrol yapıları**, programın akışını belirli koşullara veya tekrarlara göre yönetmek için kullanılır. Bu yapılar, programlarımızın daha esnek ve dinamik olmasını sağlar. Şimdi bu yapıları adım adım inceleyelim.

---

### 🔑 4.1 Koşullu İfadeler (`if`, `elif`, `else`)

Koşullu ifadeler, belirli bir durumun doğru (`True`) veya yanlış (`False`) olmasına göre farklı kod bloklarını çalıştırır. Python'da `if`, `elif` ve `else` anahtar kelimeleri kullanılır.

#### **`if` Kullanımı:**
```python
yas = 18
if yas >= 18:
    print("Ehliyet alabilirsiniz.")
```
- `if` ifadesi, belirli bir koşulun doğru olup olmadığını kontrol eder. Eğer koşul doğruysa (`True`), `if` bloğu içindeki kod çalıştırılır. Örnekte, `yas` değişkeni 18'e eşit veya büyükse, "Ehliyet alabilirsiniz." mesajı ekrana yazdırılır.

---

#### **`if-else` Kullanımı:**
```python
yas = 16
if yas >= 18:
    print("Ehliyet alabilirsiniz.")
else:
    print("Ehliyet alamazsınız.")
```
- `else` ifadesi, `if` koşulu yanlışsa (`False`) çalıştırılır. Örnekte, `yas` değişkeni 18'den küçükse, "Ehliyet alamazsınız." mesajı ekrana yazdırılır.

---

#### **`if-elif-else` Kullanımı:**
```python
yas = 20
if yas < 18:
    print("Ehliyet alamazsınız.")
elif yas == 18:
    print("Ehliyet almak için tam yaşındasınız.")
else:
    print("Ehliyet alabilirsiniz.")
```
- `elif` (else if), birden fazla koşulu kontrol etmek için kullanılır. Örnekte, `yas` değişkeni 18'den küçükse, "Ehliyet alamazsınız." mesajı; 18'e eşitse, "Ehliyet almak için tam yaşındasınız." mesajı; 18'den büyükse, "Ehliyet alabilirsiniz." mesajı ekrana yazdırılır.

---

#### **Örnek: Kullanıcıdan Yaş Bilgisi Alma**
```python
yas = int(input("Yaşınızı girin: "))

if yas < 18:
    print("Ehliyet alamazsınız.")
elif yas == 18:
    print("Ehliyet almak için tam yaşındasınız.")
else:
    print("Ehliyet alabilirsiniz.")
```
- Kullanıcıdan yaş bilgisi alınır ve bu bilgiye göre ehliyet durumu kontrol edilir. Girilen yaşa bağlı olarak uygun mesaj ekrana yazdırılır.

---

### 🔄 4.2 Döngüler

Döngüler, belirli bir işlemi birden fazla kez tekrarlamak için kullanılır. Python'da iki temel döngü türü vardır: `for` ve `while`.

#### **`for` Döngüsü:**
```python
for i in range(5):
    print(i)
```
- `for` döngüsü, belirli bir aralıkta veya koleksiyonda (liste, demet, string vb.) tekrarlama yapar. Örnekte, 0'dan 4'e kadar olan sayılar ekrana yazdırılır.

---

#### **`while` Döngüsü:**
```python
sayi = 0
while sayi < 5:
    print(sayi)
    sayi += 1
```
- `while` döngüsü, belirli bir koşul doğru olduğu sürece tekrarlama yapar. Örnekte, `sayi` değişkeni 5'ten küçük olduğu sürece döngü devam eder ve her adımda `sayi` değişkeni bir artırılır.

---

#### **Örnek: 1'den 10'a Kadar Olan Sayıları Yazdırma**
```python
for i in range(1, 11):
    print(i)
```
- `range(1, 11)` fonksiyonu, 1'den 10'a kadar olan sayıları üretir. `for` döngüsü bu sayıları tek tek ekrana yazdırır.

---

### 🔧 4.3 Döngü Kontrol İfadeleri

Döngülerin akışını kontrol etmek için `break`, `continue` ve `pass` ifadeleri kullanılır.

#### **`break` Kullanımı:**
```python
for i in range(10):
    if i == 5:
        break
    print(i)
```
- `break` ifadesi, döngüyü aniden sonlandırır. Örnekte, `i` değişkeni 5'e eşit olduğunda döngü sonlandırılır ve sadece 0'dan 4'e kadar olan sayılar yazdırılır.

---

#### **`continue` Kullanımı:**
```python
for i in range(10):
    if i % 2 == 0:
        continue
    print(i)
```
- `continue` ifadesi, döngünün o anki adımını atlar ve bir sonraki adıma geçer. Örnekte, `i` değişkeni çift sayıysa `continue` çalışır ve sadece tek sayılar yazdırılır.

---

#### **`pass` Kullanımı:**
```python
for i in range(10):
    if i % 2 == 0:
        pass
    else:
        print(i)
```
- `pass` ifadesi, bir kod bloğunu boş bırakmak için kullanılır. Örnekte, `i` değişkeni çift sayıysa hiçbir şey yapılmaz, tek sayıysa ekrana yazdırılır.

---

#### **Örnek: 1'den 10'a Kadar Olan Tek Sayıları Yazdırma**
```python
for i in range(1, 11):
    if i % 2 == 0:
        continue
    print(i)
```
- `continue` kullanarak çift sayılar atlanır ve sadece tek sayılar yazdırılır.

---

### 📐 4.4 Girintilerin Önemi

Python'da **girintiler**, kod bloklarını belirlemek için kullanılır. Diğer programlama dillerinde `{}` veya `begin-end` gibi yapılar kullanılırken, Python'da girintiler kullanılır. Bu, kodun daha okunabilir olmasını sağlar.

#### **Doğru Girinti Kullanımı:**
```python
if 5 > 2:
    print("Beş, ikiden büyüktür!")
```
- Girintiler, `if` bloğunun nerede başlayıp nerede bittiğini belirler. Girinti yanlışsa Python hata verir.

---

#### **Yanlış Girinti Kullanımı:**
```python
if 5 > 2:
print("Beş, ikiden büyüktür!")  # Hata! Girinti eksik.
```
- Girinti olmadığı için Python bu kodu çalıştırmaz ve `IndentationError` hatası verir.

---

#### **Örnek: Girintilerin Doğru Kullanımı**
```python
for i in range(3):
    if i == 1:
        print("i, 1'e eşit.")
    else:
        print("i, 1'e eşit değil.")
```
- Girintiler sayesinde `if` ve `else` blokları net bir şekilde ayrılır ve kodun okunabilirliği artar.

---

### 🌍 4.5 Günlük Hayattan Örnekler

#### **Örnek 1: Alışveriş Listesi**
```python
alisveris_listesi = ["elma", "muz", "ekmek", "süt"]

for urun in alisveris_listesi:
    if urun == "ekmek":
        print("Ekmek alındı!")
    else:
        print(f"{urun} alınacak.")
```
- Alışveriş listesindeki her bir ürün kontrol edilir. Eğer ürün "ekmek" ise "Ekmek alındı!" mesajı, diğer ürünler için ise "ürün alınacak." mesajı yazdırılır.

---

#### **Örnek 2: ATM İşlemleri**
```python
bakiye = 1000

while True:
    print(f"Mevcut bakiyeniz: {bakiye} TL")
    islem = input("İşlem seçin (Çekme/Yatırma/Çıkış): ")

    if islem == "Çekme":
        miktar = int(input("Çekmek istediğiniz miktarı girin: "))
        if miktar > bakiye:
            print("Yetersiz bakiye!")
        else:
            bakiye -= miktar
            print(f"{miktar} TL çekildi. Yeni bakiye: {bakiye} TL")
    elif islem == "Yatırma":
        miktar = int(input("Yatırmak istediğiniz miktarı girin: "))
        bakiye += miktar
        print(f"{miktar} TL yatırıldı. Yeni bakiye: {bakiye} TL")
    elif islem == "Çıkış":
        print("Çıkış yapılıyor...")
        break
    else:
        print("Geçersiz işlem!")
```
- Kullanıcıdan işlem seçmesi istenir. Seçilen işleme göre bakiye güncellenir veya programdan çıkılır.

---

### 🖥️ Örnek Kod ve Çıktılar

```python
# Kontrol Yapıları Örneği
sayi = int(input("Bir sayı girin: "))

if sayi > 0:
    print("Sayı pozitif.")
elif sayi < 0:
    print("Sayı negatif.")
else:
    print("Sayı sıfır.")

for i in range(1, 6):
    if i == 3:
        continue
    print(i)

while True:
    cevap = input("Çıkmak için 'q' tuşuna basın: ")
    if cevap == 'q':
        break
```
- Kullanıcıdan bir sayı alınır ve bu sayının pozitif, negatif veya sıfır olup olmadığı kontrol edilir. Ardından 1'den 5'e kadar olan sayılar yazdırılır (3 hariç). Son olarak, kullanıcı 'q' tuşuna basana kadar program çalışmaya devam eder.