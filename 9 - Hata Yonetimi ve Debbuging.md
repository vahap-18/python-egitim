## 9.1 Hata Yönetimine Giriş  
Hata yönetimi, bir programın beklenmedik durumlarla başa çıkabilmesini sağlamak için kritik bir beceridir. Yazılım geliştirirken, kodun her zaman mükemmel şekilde çalışacağını varsaymak gerçekçi değildir. Kullanıcı girdilerindeki hatalar, ağ bağlantısı problemleri veya yanlış değişken kullanımları gibi pek çok durum hata oluşmasına neden olabilir. İşte bu noktada, hata yönetimi devreye girer ve programın çökmesini önleyerek daha sağlam ve kullanıcı dostu bir yazılım geliştirmemizi sağlar.  

Hatalar üç ana kategoriye ayrılır:  

### Sözdizimsel Hatalar (Syntax Errors)  
Bu hatalar, Python’un yazım kurallarına uymadığımızda ortaya çıkar. Program, hata içeren kodu çalıştırmaz ve doğrudan bir hata mesajı verir.  

Örnek:  
```python
print("Merhaba Dünya"  # Parantez kapanmadığı için SyntaxError oluşur.
```
Bu hata, Python tarafından `SyntaxError: unexpected EOF while parsing` gibi bir mesajla bildirilir.  

### Çalışma Zamanı Hataları (Runtime Errors)  
Kod sözdizimsel olarak doğru olabilir, ancak çalışma sırasında beklenmedik bir durum nedeniyle hata verebilir. Örneğin, bir değişken tanımlanmadan önce kullanılırsa veya sıfıra bölme işlemi yapılırsa çalışma zamanı hatası meydana gelir.  

Örnek:  
```python
sayi = 5 / 0  # ZeroDivisionError oluşur çünkü bir sayı sıfıra bölünemez.
```
Bu hata, `ZeroDivisionError: division by zero` şeklinde ekrana yazdırılır.  

### Mantıksal Hatalar (Logical Errors)  
Mantıksal hatalar, kodun çalışmasını engellemez ancak beklenen sonucu vermez. Bu tür hatalar en tehlikelisidir çünkü program çalışmaya devam eder ancak yanlış sonuçlar üretebilir.  

Örnek:  
```python
def karesini_al(sayi):
    return sayi * 3  # Doğru olması gereken işlem sayi * sayi olmalıydı.

print(karesini_al(4))  # Beklenen çıktı 16, ancak 12 döndürülür.
```
Kod herhangi bir hata mesajı vermez ancak yanlış bir sonuç üretir. Bu tür hataları yakalamak için test ve hata ayıklama (debugging) teknikleri gereklidir.  

Hata yönetimi, yazılımın güvenilir olmasını ve beklenmedik durumlarla başa çıkmasını sağlar. Programların çökmesini engellemek, kullanıcı deneyimini iyileştirmek ve veri kaybını önlemek için iyi bir hata yönetimi uygulamak gereklidir.  

---

## 9.2 İstisnalar (Exceptions)  

İstisnalar, bir programın normal akışını bozan özel durumlar veya hatalardır. Çalışma zamanı hataları genellikle istisnalar olarak adlandırılır ve Python’da özel bir mekanizma ile ele alınabilir.  

Örneğin, sıfıra bölme işlemi bir istisnadır:  
```python
sayi = 10 / 0  # ZeroDivisionError hatası oluşur.
```
Python, çalışma zamanında bu hatayı fark eder ve programın çökmesini önlemek için `ZeroDivisionError` istisnasını yükseltir.  

İstisnaların yönetilmesi için `try-except` bloğu kullanılır. Bu blok sayesinde, hatanın meydana gelmesi durumunda programın çökmesi yerine belirlenen bir işlem gerçekleştirilir.  

Örnek:  
```python
try:
    sayi = int(input("Bir sayı girin: "))
    sonuc = 10 / sayi
    print("Sonuç:", sonuc)
except ZeroDivisionError:
    print("Hata: Bir sayı sıfıra bölünemez!")
except ValueError:
    print("Hata: Lütfen geçerli bir sayı girin!")
```
Bu kod parçası, kullanıcının sıfır girmesi durumunda `ZeroDivisionError`, geçersiz bir giriş yapması durumunda `ValueError` hatalarını yakalayarak programın çökmesini önler.  

Python’da birçok yerleşik istisna türü vardır:  

- `ZeroDivisionError` – Sıfıra bölme hatası  
- `ValueError` – Geçersiz veri tipi girdisi  
- `IndexError` – Liste veya dizi sınırları dışına çıkma  
- `KeyError` – Sözlükte bulunmayan bir anahtara erişim  
- `FileNotFoundError` – Dosyanın bulunamaması  

İstisna yönetimi, programların dayanıklı ve güvenilir olmasını sağlamak için gereklidir. Kullanıcıların beklenmedik hatalarla karşılaştığında anlamlı geri bildirimler almasını ve programın sağlıklı bir şekilde devam etmesini sağlar.

---

## 9.3 İstisna İşleme (Exception Handling)  

Hata yönetiminin temel taşlarından biri, istisnaları yakalayarak programın çökmesini önlemektir. Python'da istisnaları yönetmek için `try`, `except`, `finally` ve `else` blokları kullanılır. Bu yapı sayesinde beklenmeyen hatalar programın akışını bozmaz ve daha güvenilir bir kod yazılmış olur.  

### **try ve except Blokları**  

`try` bloğu, çalıştırılması muhtemel hata verebilecek kodu içerir. Eğer bir hata meydana gelirse, `except` bloğunda bu hatayı yakalayıp yönetebiliriz.  

Örnek:  
```python
try:
    sayi = int(input("Bir sayı girin: "))  # Kullanıcıdan giriş al
    sonuc = 10 / sayi  # Sayıyı 10’a böl
    print("Sonuç:", sonuc)
except ZeroDivisionError:  # Sıfıra bölme hatasını yakala
    print("Hata: Bir sayı sıfıra bölünemez!")
except ValueError:  # Geçersiz giriş hatasını yakala
    print("Hata: Lütfen bir sayı girin!")
```
Bu kodda, kullanıcı sıfır girerse `ZeroDivisionError`, geçersiz bir giriş yaparsa `ValueError` yakalanır ve program çökmez.  

### **finally Bloğu**  

`finally` bloğu, hata oluşsa da oluşmasa da çalıştırılmasını istediğimiz kodları içerir. Genellikle dosya kapatma, kaynak serbest bırakma gibi işlemler için kullanılır.  

Örnek:  
```python
try:
    dosya = open("veriler.txt", "r")  # Dosya açılır
    icerik = dosya.read()
    print(icerik)
except FileNotFoundError:
    print("Hata: Dosya bulunamadı!")
finally:
    print("Dosya kapatılıyor...")
    dosya.close()  # Dosya hatasız da olsa hata olsa da kapatılır.
```

### **else Bloğu**  

`else` bloğu, `try` bloğu hatasız çalıştığında devreye girer. Hata meydana gelirse `else` bloğu çalışmaz.  

Örnek:  
```python
try:
    sayi = int(input("Bir sayı girin: "))
    sonuc = 10 / sayi
except ZeroDivisionError:
    print("Hata: Sıfıra bölme yapılamaz!")
except ValueError:
    print("Hata: Geçerli bir sayı girin!")
else:
    print("İşlem başarılı, sonuç:", sonuc)  # Eğer hata yoksa burası çalışır.
```
Burada, kullanıcı hatasız bir giriş yaparsa `else` bloğu devreye girerek sonucu ekrana yazdırır.  

### **Çoklu except Blokları**  

Farklı türde hatalar yakalanabilir. Birden fazla hata yakalamak için birden çok `except` bloğu kullanılabilir.  

Örnek:  
```python
try:
    liste = [1, 2, 3]
    print(liste[5])  # Listede olmayan bir indekse erişmeye çalışıyoruz.
except IndexError:
    print("Hata: Liste sınırlarını aştınız!")
except Exception as e:
    print(f"Beklenmeyen bir hata oluştu: {e}")
```
Burada, `IndexError` yakalanmazsa `Exception` bloğu devreye girer.  

### **Genel except Bloğu ve Özel İstisnalar**  

Tüm hataları yakalamak için `except Exception` kullanılabilir. Ancak bu, belirli hataları yakalamak yerine tüm istisnaları kapsadığı için önerilen bir yöntem değildir.  

```python
try:
    sayi = int(input("Bir sayı girin: "))
    sonuc = 10 / sayi
except Exception as e:
    print(f"Bir hata oluştu: {e}")
```
Bu, oluşabilecek herhangi bir hatayı yakalayarak hata mesajını ekrana yazdırır. Ancak spesifik hataları yakalamak her zaman daha iyi bir yaklaşımdır.  

---

## 9.4 Kendi İstisnalarınızı Tanımlama  

Python, yerleşik istisnaların dışında, özel istisnalar tanımlamamıza da olanak tanır. Bazen belirli bir iş mantığı için özel hata türleri oluşturmak isteyebiliriz.  

### **Özel İstisna Sınıfları Oluşturma**  

Özel bir istisna tanımlamak için bir sınıf oluştururuz ve `Exception` sınıfından türetiriz.  

Örnek:  
```python
class NegatifSayiHatasi(Exception):  # Exception sınıfından türetiyoruz
    def __init__(self, mesaj="Negatif sayılar geçerli değildir!"):
        self.mesaj = mesaj
        super().__init__(self.mesaj)

try:
    sayi = int(input("Bir sayı girin: "))
    if sayi < 0:
        raise NegatifSayiHatasi  # Özel istisnayı fırlatıyoruz
    print("Girilen sayı:", sayi)
except NegatifSayiHatasi as e:
    print("Hata:", e)
```
Burada, kullanıcı negatif bir sayı girdiğinde `NegatifSayiHatasi` istisnası fırlatılıyor ve özel hata mesajı ekrana yazdırılıyor.  

### **raise Anahtar Kelimesi ile İstisna Fırlatma**  

`raise` anahtar kelimesi, manuel olarak bir istisna fırlatmak için kullanılır.  

Örnek:  
```python
def yas_kontrol(yas):
    if yas < 18:
        raise ValueError("18 yaşından küçükler sisteme kayıt olamaz!")
    print("Kayıt başarılı.")

try:
    yas_kontrol(16)
except ValueError as hata:
    print("Hata:", hata)
```
Bu kodda, `yas_kontrol` fonksiyonu 18 yaşından küçükler için bir `ValueError` istisnası fırlatıyor.  

Özel istisnalar tanımlamak, kodun daha okunabilir ve yönetilebilir olmasını sağlar. Kendi hata sınıflarımızı oluşturduğumuzda, belirli hataları daha spesifik bir şekilde ele alabiliriz.  

**Sonuç:**  

İstisna yönetimi, yazılım geliştirme sürecinde hataları ele almak ve programın beklenmeyen durumlar karşısında çökmesini önlemek için kritik bir tekniktir. `try-except` yapısı sayesinde hataları yakalayabilir, `finally` bloğuyla gerekli işlemleri yapabilir ve `raise` ile kendi özel istisnalarımızı tanımlayabiliriz. Bu teknikleri doğru kullanarak daha güvenilir ve kullanıcı dostu uygulamalar geliştirebiliriz.

---

## 🚨 9.5 Hata Mesajları ve Hata Takibi  

Program yazarken hatalar kaçınılmazdır. Tıpkı günlük hayatta yanlış bir telefon numarası çevirdiğimizde veya bir kapıyı yanlış anahtarla açmaya çalıştığımızda olduğu gibi, kod yazarken de bazen işler ters gidebilir. Önemli olan, bu hataları nasıl tespit edip düzelttiğimizdir.  

Python, hata oluştuğunda bize bir "hata mesajı" (traceback) verir. Bu mesaj, hatanın nerede olduğunu ve neden kaynaklandığını anlamamıza yardımcı olur. Ama kabul edelim, hata mesajları bazen korkutucu görünebilir. Hiç endişelenme! Şimdi bunları anlamanın yollarını birlikte keşfedeceğiz.  

---

### 🧐 **Hata Mesajlarını Anlama ve Yorumlama**  

Bir hata olduğunda Python ekrana bir hata mesajı (traceback) yazdırır. Peki, bu mesaj ne anlama geliyor? Gel, bir örnekle bakalım:  

### **Örnek: Sıfıra Bölme Hatası**  
```python
def bolme(x, y):
    return x / y  # Burada y sıfır olursa hata alırız!

print(bolme(10, 0))  # Sıfıra bölme hatası verecek
```
Bu kodu çalıştırırsan şu hatayı alırsın:  
```
ZeroDivisionError: division by zero
```
Yani Python diyor ki:  
_"Kardeşim, bir sayıyı sıfıra bölemezsin! Matematik buna izin vermez."_  

Bu mesajın içindeki `ZeroDivisionError`, hatanın türünü gösterir. Eğer programımızı geliştirmek istiyorsak, bu hataları yakalayıp yönetmemiz gerekir.  

---

### 🔍 **traceback Modülü ile Hata Takibi**  

Bazı hatalar direkt gözümüze batmaz, özellikle de büyük projelerde. İşte burada `traceback` modülü devreye girer.  

Bu modül, programımız çöktüğünde detaylı bir hata geçmişi (stack trace) sağlar. Şimdi bir örnekle inceleyelim:  

```python
import traceback

def hata_veren_fonksiyon():
    sayi = int("Merhaba")  # Burada hata olacak

try:
    hata_veren_fonksiyon()
except Exception as e:
    print("Bir hata meydana geldi:")
    traceback.print_exc()  # Hata geçmişini yazdır
```
Bu kodu çalıştırdığında, Python sana hatanın **hangi satırda** ve **neden** olduğunu detaylıca gösterecektir.  

---

### 📝 **Hata Günlükleri (Logging) ve Kayıt Tutma**  

Gerçek dünyada büyük projeler geliştirirken, hataları sadece ekrana yazdırmak yetmez. Çünkü kullanıcıların karşılaştığı hataları takip etmek ve ileride çözüm üretmek için bunları bir dosyaya kaydetmek gerekir.  

Bunun için Python’un `logging` modülü kullanılır.  

#### **Örnek: Hataları Bir Dosyaya Kaydetmek**  
```python
import logging

# Hata günlüğü ayarları
logging.basicConfig(filename="hatalar.log", level=logging.ERROR, format="%(asctime)s - %(levelname)s - %(message)s")

try:
    sonuc = 10 / 0
except ZeroDivisionError as e:
    logging.error("Sıfıra bölme hatası: %s", e)
```
Bu kod çalıştırıldığında, hata mesajı **hatalar.log** dosyasına kaydedilir. Bu sayede, program kapansa bile hataları inceleyebiliriz.  

---

## 🛠️ 9.6 Debugging Araçları ve Teknikleri  

Hataları yakalamak kadar onları çözmek de önemlidir. Bunun için farklı hata ayıklama (debugging) teknikleri kullanabiliriz.  

---

### **🖨️ 1. Print Tabanlı Debugging**  

En basit debugging yöntemi, `print()` fonksiyonunu kullanarak değişkenlerin değerlerini ekrana yazdırmaktır.  

#### **Örnek: Print Kullanarak Hata Ayıklama**  
```python
def carp(a, b):
    print(f"a: {a}, b: {b}")  # Değişkenlerin değerlerini kontrol et
    return a * b

print(carp(5, "2"))  # Burada hata olacak!
```
Burada, `print()` fonksiyonunu kullanarak `a` ve `b` değişkenlerinin değerlerini görebiliyoruz. Ancak bu yöntem her zaman yeterli olmaz. Büyük projelerde daha gelişmiş araçlar kullanmalıyız.  

---

### **🐞 2. Python Debugger (pdb) Kullanımı**  

Python’un yerleşik hata ayıklama aracı `pdb` ile kodu adım adım çalıştırabilir ve değişkenleri anlık olarak inceleyebiliriz.  

#### **Örnek: pdb ile Hata Ayıklama**  
```python
import pdb

def bolme(a, b):
    pdb.set_trace()  # Debugger'ı başlat
    return a / b

print(bolme(10, 2))
```
Bu kodu çalıştırdığında **pdb arayüzüne girilir** ve şu komutları kullanabilirsin:  
- `n` → Bir sonraki satıra geç  
- `s` → Bir fonksiyonun içine gir  
- `p değişken_adı` → Bir değişkenin değerini gör  
- `q` → Debug modundan çık  

Bunu kullanarak programın **satır satır nasıl çalıştığını** gözlemleyebilirsin!  

---

### **💻 3. IDE'lerin Debugging Araçları**  

Bugün kullanılan modern kod editörleri (IDE'ler), hata ayıklamayı kolaylaştıran özellikler sunar.  

#### **🔹 PyCharm**  
- Kodda bir satıra **breakpoint (kesme noktası)** koyarak, program o satıra gelince durmasını sağlayabilirsin.  
- O anda değişkenlerin değerlerini görebilir, kodu adım adım çalıştırabilirsin.  

#### **🔹 Visual Studio Code (VS Code)**  
- VS Code’un hata ayıklama panelini kullanarak kodun hangi satırda hata verdiğini görebilirsin.  
- Kod çalışırken değişkenlerin değerlerini anlık olarak inceleyebilirsin.  

#### **🔹 Jupyter Notebook**  
- `%debug` komutunu kullanarak hata noktalarına girip değişkenleri kontrol edebilirsin.  

Örnek:  
```python
def hata_veren_fonksiyon():
    return 10 / 0

%debug
hata_veren_fonksiyon()
```
Bu komut sayesinde kodu satır satır inceleyebilirsin.  

---

## 🛠 9.7 pdb Modülü ile Debugging  

Kod yazarken bazen neyin yanlış gittiğini anlamak için satır satır inceleme yapmak gerekebilir. İşte burada **Python Debugger (pdb) modülü** devreye girer.  

pdb, **kodun belirli noktalarında durmamızı, değişkenleri incelememizi ve satır satır çalıştırmamızı sağlayan bir hata ayıklama aracıdır**. Büyük IDE'ler (VS Code, PyCharm gibi) görsel hata ayıklama araçları sunsa da, `pdb` modülü komut satırından kullanılabilir ve hafif projelerde oldukça işlevseldir.  

---

### 🧐 **pdb Modülüne Giriş**  

pdb'yi kullanmak için `import pdb` diyerek başlıyoruz. Ardından, kodun hata verdiği yerleri veya kontrol etmek istediğimiz noktaları adım adım incelemek için **breakpoint koyabiliriz**.  

Basit bir örnekle başlayalım:  

```python
import pdb

def faktoriyel(n):
    pdb.set_trace()  # Burada debug moduna gireceğiz
    if n == 0:
        return 1
    else:
        return n * faktoriyel(n - 1)

print(faktoriyel(5))
```
Bu kodu çalıştırdığımızda, `pdb.set_trace()` satırına gelindiğinde Python **debug moduna girer** ve biz de aşağıdaki komutları kullanarak adım adım kodu inceleyebiliriz.  

---

### 🔎 **Temel pdb Komutları**  

pdb modülü içinde birkaç temel komut kullanarak kodu satır satır inceleyebiliriz. İşte en yaygın kullanılan pdb komutları:  

| Komut | Açıklama |
|--------|----------------------------------------------------------|
| `n` (next) | Bir sonraki satıra geç |
| `s` (step) | Bir fonksiyonun içine gir |
| `c` (continue) | Debugging'i devam ettir ve çık |
| `q` (quit) | Debugging'i sonlandır |
| `p değişken` | Belirtilen değişkenin değerini yazdır |
| `l` (list) | Kodun çevresindeki birkaç satırı göster |
| `b satır_numarası` | Belirli bir satıra breakpoint (kesme noktası) ekle |
| `r` (return) | Mevcut fonksiyondan çık |

**Örnek Kullanım:**  
Yukarıdaki faktöriyel fonksiyonunu debug modunda çalıştırırken şu komutları deneyebilirsin:  

1️⃣ `l` → Çevredeki kod satırlarını listele.  
2️⃣ `p n` → `n` değişkeninin değerini ekrana yazdır.  
3️⃣ `n` → Bir sonraki satıra geç.  
4️⃣ `s` → Fonksiyonun içine girerek adım adım ilerle.  
5️⃣ `q` → Debugging modundan çık.  

---

### 🛑 **breakpoint() Fonksiyonu Kullanımı**  

Python 3.7 ve sonrasında `pdb.set_trace()` kullanmak yerine daha modern bir yöntem olan `breakpoint()` fonksiyonunu kullanabiliriz.  

```python
def topla(a, b):
    breakpoint()  # Python 3.7+ ile önerilen yöntem
    return a + b

print(topla(10, 20))
```
Bu yöntem, kod hata ayıklama (debugging) sürecini **daha okunaklı ve kolay hale getirir**.  

---

## 🏆9.8 İleri Debugging Teknikleri  

Daha karmaşık projelerde, `print()` veya basit debugging yöntemleri yeterli olmayabilir. Daha gelişmiş stratejiler kullanarak **hataları daha hızlı ve etkili bir şekilde çözebiliriz**.  

---

### 🧐 **Hata Ayıklamada İpuçları ve En İyi Uygulamalar**  

✅ **Hata mesajlarını iyi analiz et:**  
Eğer programın hata veriyorsa, traceback (hata mesajı) içindeki **son satıra** odaklan. Python genellikle hatanın sebebini son satırda söyler.  

✅ **Hata türlerini iyi bil:**  
Örneğin:  
- `TypeError`: Yanlış veri tipi kullanımı  
- `ValueError`: Geçersiz değer hatası  
- `IndexError`: Liste veya dizi indeksinin dışına çıkma  
- `KeyError`: Sözlükte olmayan bir anahtara erişmeye çalışma  

✅ **İşin içine logging kat:**  
Hataları sadece ekrana yazdırmak yerine **dosyaya kaydetmek**, özellikle büyük projelerde çok yardımcı olur.  

```python
import logging

logging.basicConfig(filename="app.log", level=logging.DEBUG, format="%(asctime)s - %(levelname)s - %(message)s")

def bolme(x, y):
    try:
        sonuc = x / y
        return sonuc
    except ZeroDivisionError:
        logging.error("Sıfıra bölme hatası oluştu!")
        return None

bolme(10, 0)
```
Bu şekilde hata mesajları `app.log` dosyasına kaydedilir ve daha sonra analiz edilebilir.  

---

### 🔥 **Karmaşık Hataların Çözümü İçin Stratejiler**  

📌 **Böl ve fethet yaklaşımı:**  
Kodun tamamına değil, **küçük parçalarına odaklan**. Sorun yaşadığın kodu tek başına çalıştırarak hatayı izole etmeye çalış.  

📌 **Kodu adım adım çalıştır:**  
Eğer bir fonksiyon içinde hata alıyorsan, fonksiyonu **küçük parçalar halinde** çalıştırarak hatanın nerede olduğunu bulabilirsin.  

📌 **Geçici olarak try-except kullan:**  
Bazen programın tamamen çökmesini önlemek için geçici olarak `try-except` blokları ekleyebilirsin. Ancak bu yöntemi **hataları gizlemek için değil**, **nedenini anlamak için** kullan.  

---

### 🎯 **Conditional Breakpoints ve Watch Expressions**  

Bazı durumlarda, kodun sadece belirli bir koşul sağlandığında durmasını isteyebiliriz. İşte burada **koşullu breakpointler (Conditional Breakpoints)** devreye girer.  

**Örnek:**  
```python
import pdb

def test(n):
    for i in range(n):
        if i == 3:
            pdb.set_trace()  # Yalnızca i = 3 olduğunda dur
        print(f"i: {i}")

test(5)
```
Bu kod çalıştırıldığında, `i` değişkeni **3 olduğunda debug moduna girilir**. Böylece sadece ilgilendiğimiz durumda kodu inceleyebiliriz.  

#### 🔥 **Watch Expressions Kullanımı**  
Eğer belirli bir değişkenin değerini **her adımda** takip etmek istiyorsan, IDE’lerde **watch expressions** kullanabilirsin. Örneğin:  
- PyCharm ve VS Code’da belirli değişkenleri **"Watch" sekmesine ekleyerek** her değişiklikte inceleyebilirsin.  
- `pdb` kullanıyorsan, her adımda `p değişken_adı` yazarak takip edebilirsin.  

---

## 🛠 9.9 Hata Yönetimi ve Testler  

Kod yazarken hataları yakalamak kadar **bunların tekrar yaşanmasını önlemek** de önemlidir. Bunun için **birim testleri (unit tests)** kullanarak kodumuzu sistematik bir şekilde test edebiliriz. **Hata yönetimiyle testleri bir arada kullanarak**, kodumuzun **hatalara karşı dayanıklı ve güvenilir** olmasını sağlayabiliriz.  

---

### 🔍 **Hata Yönetimi ve Birim Testleri**  

Birim testleri, **küçük kod parçalarını (fonksiyonlar, metotlar) bağımsız olarak test etmeyi amaçlar**. Bir fonksiyonun beklenen çıktıyı verdiğinden emin olmak için testler yazabiliriz.  

Örneğin, basit bir bölme fonksiyonu yazalım ve bunun için test yazalım:  

```python
def bolme(x, y):
    if y == 0:
        raise ValueError("Bir sayı sıfıra bölünemez!")
    return x / y
```

Bu fonksiyon, sıfıra bölme hatasını **ValueError** fırlatarak önler. Şimdi bunun için test yazalım:  

```python
import unittest

class TestBolmeFonksiyonu(unittest.TestCase):

    def test_normal_bolme(self):
        self.assertEqual(bolme(10, 2), 5)

    def test_sifira_bolme(self):
        with self.assertRaises(ValueError):
            bolme(10, 0)

if __name__ == "__main__":
    unittest.main()
```

#### 🛠 **unittest ve pytest ile İstisna Test Etme**  

`unittest` Python'un dahili test modülüdür, ancak daha modern bir alternatif olarak `pytest` kullanılabilir.  

```python
import pytest

def test_bolme():
    assert bolme(10, 2) == 5

def test_sifira_bolme():
    with pytest.raises(ValueError):
        bolme(10, 0)
```

`pytest` komutuyla testleri çalıştırabiliriz. `pytest`, **daha az kod yazmayı sağlayan ve okunaklı hata mesajları veren** bir test kütüphanesidir.  

---

### 🎯 **Test Kapsamı ve Hata Yönetimi**  

Her test, sadece bir özelliği kapsamalıdır. **Hata yönetimi testlerinde şu unsurlara dikkat edilmelidir:**  

✅ **Negatif testler yaz:** Yani hatalı girişlerin nasıl karşılandığını test et.  
✅ **Gerçekçi senaryoları test et:** Örneğin, bir API çağrısı yapan kod yazıyorsan **bağlantı hataları ve zaman aşımı gibi durumları** test etmelisin.  
✅ **Kod kapsama oranını artır:** `coverage.py` gibi araçlarla **hangi kodların test edildiğini ve edilmediğini** kontrol edebilirsin.  

---

## 🔐 9.10 Hata Yönetimi ve Güvenlik  

Hata mesajları, genellikle sistem hakkında **hassas bilgiler** içerebilir. Yanlış yönetildiğinde, bir hata mesajı saldırganlara sistem hakkında bilgi verebilir!  

---

### 🛡 **Güvenli Kod Yazımı ve Hata Yönetimi**  

Kod yazarken güvenliği artırmak için bazı temel ilkeleri göz önünde bulundurmalıyız:  

✅ **Genel hata mesajlarını kullanıcıya gösterme!** Kullanıcı dostu, ancak fazla bilgi içermeyen mesajlar kullan.  
✅ **Hata mesajlarında dosya yolları ve sistem bilgileri olmasın.**  
✅ **Hata yönetimini saldırılara açık hale getirme!** Özellikle **SQL Injection ve XSS saldırılarına karşı güvenli hata yönetimi** sağla.  

**Güvensiz hata mesajı örneği:**  

```python
try:
    baglanti = veritabani_ac()
except Exception as e:
    print(f"Hata: {e}")  # BU YANLIŞ!
```

Bu hata mesajı, saldırganın sistem hakkında fazla bilgi edinmesine sebep olabilir.  

**Daha güvenli bir hata yönetimi:**  

```python
import logging

logging.basicConfig(filename="errors.log", level=logging.ERROR)

try:
    baglanti = veritabani_ac()
except Exception:
    logging.exception("Veritabanı bağlantı hatası oluştu.")
    print("Bir hata meydana geldi, lütfen daha sonra tekrar deneyin.")  # Kullanıcıya gösterilecek mesaj
```

Burada **hata detaylarını bir log dosyasına yazdırıyoruz**, ancak kullanıcıya genel bir mesaj gösteriyoruz.  

---

### 🗄 **İstisnaların Kullanıcıya Bildirilmesi ve Loglama Stratejileri**  

Hataları sadece yakalamak yetmez, **bunları izlememiz ve analiz etmemiz gerekir**. Bunun için **loglama (logging)** kullanabiliriz.  

Örneğin, **hata seviyelerine göre loglama** yapabiliriz:  

```python
import logging

logging.basicConfig(filename="app.log", level=logging.DEBUG)

logging.debug("Bu sadece debug amaçlı bir mesajdır.")
logging.info("Genel bilgi mesajı.")
logging.warning("Dikkat edilmesi gereken bir durum var!")
logging.error("Bir hata meydana geldi!")
logging.critical("Sistem çöküyor!")
```

**Log seviyeleri şunlardır:**  
- `DEBUG`: Detaylı hata ayıklama mesajları  
- `INFO`: Genel çalışma bilgileri  
- `WARNING`: Potansiyel tehlikeler  
- `ERROR`: Hata mesajları  
- `CRITICAL`: Ciddi hatalar, sistemin çalışmasını durdurabilir  

---

## ⚡9.11 Profiling ve Performans Analizi  

Kod yazarken **yalnızca doğruluğu değil, performansı da önemlidir**. Kodun yavaş çalışmasını engellemek için **profiling (profil analizi)** yaparak hangi kısımların **çok fazla işlem süresi aldığını** tespit edebiliriz.  

---

### 🎯 **Profiling Nedir ve Neden Gereklidir?**  

Profiling, **bir programın hangi bölümlerinin en fazla işlem süresi aldığını analiz etmeye yarayan bir tekniktir**.  

Örneğin:  
- **Kodun en yavaş bölümlerini bulmak**  
- **Performans darboğazlarını (bottleneck) belirlemek**  
- **Hangi fonksiyonun en fazla çağrıldığını görmek**  

---

### ⏳ **cProfile ve timeit Modülleri ile Profiling**  

**`cProfile` kullanımı:**  

`cProfile`, Python'un yerleşik performans analiz modülüdür.  

```python
import cProfile

def agir_hesaplama():
    toplam = 0
    for i in range(1, 1000000):
        toplam += i
    return toplam

cProfile.run("agir_hesaplama()")
```

Bu komut, **hangi fonksiyonun ne kadar sürede çalıştığını** detaylı bir şekilde raporlar.  

**`timeit` kullanımı:**  

`timeit` modülü, **küçük kod parçalarının ne kadar sürede çalıştığını ölçmek için kullanılır**.  

```python
import timeit

kod = """
toplam = 0
for i in range(1, 1000000):
    toplam += i
"""

print(timeit.timeit(kod, number=10))  # 10 kez çalıştır ve ortalama süreyi hesapla
```

---

### 🚀 **Performans Sorunlarını Tespit Etme ve Giderme**  

Kod performansını artırmak için:  
✅ **Gereksiz döngüleri ortadan kaldır**  
✅ **Alternatif veri yapıları kullan** (`list` yerine `set` veya `dict` kullanmak bazen daha hızlıdır)  
✅ **Dahili fonksiyonları kullan** (örn. `sum()` kullanmak `for` döngüsünden daha hızlıdır)  
✅ **Çok fazla fonksiyon çağrısı yapmaktan kaçın**  

---

## 🏗 9.12 Hata Yönetimi ve Kapsamlı Uygulamalar  

Hata yönetimi, küçük projelerde basit bir `try-except` bloğu ile çözülebilir. Ancak **büyük projelerde işler karmaşık hale gelir**. Bir projede **farklı modüller, mikro servisler, veri tabanları ve dış servisler** olabilir. Hata yönetiminin **tutarlı ve sürdürülebilir olması** için **iyi bir mimariye sahip olmamız gerekir**.  

---

### 🏢 **Büyük Ölçekli Projelerde Hata Yönetimi**  

Bir projede **hata yönetiminin planlı bir şekilde yapılması gerekir**. Gelişigüzel `try-except` blokları yerine, **modüler ve katmanlı bir hata yönetimi** tercih edilir.  

Örneğin:  

- **Veri tabanı hataları** → Bağlantı hataları, zaman aşımı, SQL hataları  
- **Ağ hataları** → API çağrılarında bağlantı kopmaları, zaman aşımı  
- **İş mantığı hataları** → Kullanıcı girişleri, eksik veriler  

Bu hataları **farklı seviyelerde yakalayıp yönetebiliriz**:  

1️⃣ **Düşük Seviye Hata Yönetimi (Fonksiyon ve Modül Bazında Hata Yönetimi)**  
- Her modül **kendi hatalarını yakalar ve uygun bir tepki verir**.  

```python
def veri_tabani_baglan():
    try:
        baglanti = veritabani_ac()
        return baglanti
    except ConnectionError:
        raise Exception("Veritabanına bağlanırken hata oluştu.")
```

2️⃣ **Orta Seviye Hata Yönetimi (Servis Katmanı Hata Yönetimi)**  
- **Bir modülün hatasını, uygulama genelinde nasıl ele alacağımızı tanımlarız.**  

```python
def kullanici_girisi(kullanici_adi, sifre):
    try:
        baglanti = veri_tabani_baglan()
        return baglanti.kullanici_dogrula(kullanici_adi, sifre)
    except Exception as e:
        logging.error(f"Giriş sırasında hata: {str(e)}")
        raise Exception("Giriş yapılamadı, lütfen tekrar deneyin.")
```

3️⃣ **Üst Seviye Hata Yönetimi (Global Hata Yönetimi)**  
- **Hataları yakalayıp merkezi bir log sistemine kaydederiz.**  

```python
try:
    app.run()
except Exception as e:
    logging.critical(f"Sistem hatası oluştu: {str(e)}")
    print("Sistemsel bir hata meydana geldi, lütfen destek ekibiyle iletişime geçin.")
```

---

### 🔄 **Modüler Hata Yönetimi ve Katmanlı Yaklaşımlar**  

Büyük projelerde **hata yönetimini belirli modüllere dağıtarak** kontrolü daha kolay hale getirebiliriz. **Her modül kendi hata yönetiminden sorumlu olur** ve **üst seviyelere sadece anlamlı hatalar iletilir**.  

**Örneğin:**  

✅ **Veri tabanı modülü** → Bağlantı ve sorgu hatalarını ele alır  
✅ **İş mantığı modülü** → Yanlış girişler, eksik parametreleri kontrol eder  
✅ **API modülü** → Dış servis çağrılarındaki hataları yönetir  

Bu yöntem, **bir hata olduğunda sorunun nereden kaynaklandığını daha kolay anlamamızı sağlar** ve **kodu daha sürdürülebilir hale getirir**.  

---

### 🌍 **Gerçek Dünya Uygulamaları ve Örnekler**  

Bir e-ticaret sitesinde hata yönetimi nasıl olmalıdır?  

🚚 **Sipariş sistemi:** Ödeme hataları, stok hataları, teslimat problemleri  
💳 **Ödeme işlemleri:** Banka bağlantı hataları, zaman aşımı sorunları  
📡 **API çağrıları:** Kargo firması, ödeme sağlayıcısı gibi dış sistemlerden alınan hatalar  

Bu gibi sistemlerde hata yönetimini **iyi bir loglama ve hata izleme mekanizmasıyla birleştirmek** gerekir.  

---

## 🛠 9.13 Kütüphaneler ve Araçlar  

Python, **gelişmiş hata yönetimi ve hata izleme** için kullanabileceğimiz birkaç güçlü kütüphane sunar. Şimdi bunları inceleyelim!  

---

### 📜 **logging Modülü ile Gelişmiş Hata Günlüğü**  

Daha önce de gördüğümüz `logging` modülü, **hataları anlamak ve takip etmek için** en önemli araçlardan biridir.  

```python
import logging

logging.basicConfig(filename="app.log", level=logging.ERROR,
                    format="%(asctime)s - %(levelname)s - %(message)s")

try:
    1 / 0
except ZeroDivisionError:
    logging.error("Sıfıra bölme hatası!")
```

Bu kod **hata mesajlarını bir dosyaya yazdırır**, böylece geçmiş hataları inceleyebiliriz.  

---

### 📡 **Sentry ile Hata İzleme ve Raporlama**  

Sentry, **hataları otomatik olarak takip eden ve bildiren** bir araçtır. Özellikle büyük projelerde **anlık hata takibi yapmak için çok kullanışlıdır**.  

**Kurulum:**  

```bash
pip install sentry-sdk
```

**Kullanımı:**  

```python
import sentry_sdk

sentry_sdk.init(
    dsn="SENTRY_DSN_URL",  # Buraya kendi Sentry DSN adresinizi girin
    traces_sample_rate=1.0
)

try:
    1 / 0
except ZeroDivisionError:
    sentry_sdk.capture_exception()
```

Sentry, **hatayı otomatik olarak algılar, kaydeder ve size bildirim yollar**.  

---

### ⚙ **faulthandler Modülü ile Derinlemesine Hata Analizi**  

Python'un `faulthandler` modülü, **karmaşık ve derin hataları analiz etmek için kullanılır**. Özellikle **programın neden çöktüğünü anlamak için kullanışlıdır**.  

**Kullanımı:**  

```python
import faulthandler

faulthandler.enable()

def sonsuz_dongu():
    while True:
        pass

sonsuz_dongu()
```

Bu kod çalıştırıldığında **Python, hangi satırda sıkışıp kaldığını gösteren bir rapor üretir**.  

---

🚀 **Özet**  

✅ **Büyük projelerde hata yönetimi katmanlı bir şekilde yapılmalıdır.**  
✅ **Modüler hata yönetimi**, her modülün kendi hatalarını yönetmesini sağlar.  
✅ **Hataları merkezi bir loglama sistemine yazmak**, hata takibini kolaylaştırır.  
✅ **Sentry gibi hata izleme araçları**, hataları anlık olarak tespit edip bildirir.  
✅ **faulthandler**, çökmeleri analiz etmek için kullanılır.  

Kodunun **sadece çalışması değil, sağlam ve hatalara karşı dayanıklı olması da önemlidir**. 

Bu teknikleri projelerine uygularsan **daha güvenilir, sürdürülebilir ve kaliteli yazılımlar geliştirebilirsin**! 