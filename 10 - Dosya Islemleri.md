# 📂 10 Python ile Dosya İşlemleri

Merhaba Python sever! 🎉 Bu bölümde, Python'un dosya işlemleri dünyasına adım atıyoruz. Dosyalar, veri saklamak ve yönetmek için harika bir yoldur. Kod yazarken karşımıza çıkacak olan dosya işlemleri, programlarımızın gücünü ve esnekliğini artırır. Hazır mısın? Hadi başlayalım! 🚀

---

## 📌 10.1 Dosya İşlemlerinin Önemi

Dosya işlemleri, bilgisayarlarda veri saklamak ve işlemek için hayati öneme sahiptir. Neden mi? İşte birkaç neden:

1. **Veri Saklama**: Programların çalıştığı sürede veri kaybetmemek için dosyalar kullanılır. Örneğin, bir oyun kaydedildiğinde veya kullanıcı ayarları dosyasında saklandığında.
  
2. **Veri Yönetimi**: Kullanıcıların verileri düzenlemesine ve işlemesine olanak tanır. Örneğin, bir metin dosyasına not alabiliriz.

3. **Geri Dönüşümlü İşlemler**: Eğer bir hata yaparsak, dosyadaki verileri geri yükleyerek işlemlerimizi kolayca geri alabiliriz.

Düşün ki, bir gün boyunca yaşadığın her şeyin notunu alıyorsun! İşte bu notlar, bir dosya olarak saklandığında daha sonra geri dönebilir ve hatırlayabilirsin!

---

## 🎯 10.2 Python'da Dosya İşlemleri ve Temel Kavramlar

Python’da dosya işlemleri oldukça basittir. Hemen bu temelleri öğrenelim! Python’da dosya açmak için `open()` fonksiyonunu kullanırız.

### 2.1 Dosya Açma ve Kapama

#### 1. open() Fonksiyonu ve Modlar

`open()` fonksiyonu ile dosya açarız ve bu dosyayı okumak, yazmak ya da eklemek için farklı modlar kullanabiliriz. İşte yaygın modlar:

- **read (r)**: Dosyayı okumak için açar. Dosya yoksa hata verir.
- **write (w)**: Dosyayı yazmak için açar. Dosya yoksa oluşturur, varsa üzerine yazar (silinerek).
- **append (a)**: Dosyayı eklemek için açar. Var olan dosyaya yeni içerik ekler.
- **binary (b)**: Dosya işlemlerini ikili (binary) modda yapar.
- **update (r+, w+, a+)**: Okuma ve yazma işlemlerini bir arada yapar.

**Örnek:**

```python
# Yazma Modunda Dosya Açma
dosya = open("ornek.txt", "w")
dosya.write("Merhaba, dosya işlemleri!")
dosya.close()  # Dosyayı kapatmayı unutma!
```

#### 2. Dosya Kapama (close() Fonksiyonu)

Dosyayı kullandıktan sonra mutlaka kapatmalısın. Bunun için `close()` fonksiyonunu kullanırız.

```python
dosya.close()
```

Unutma, dosyayı kapatmamak kaynak israfına neden olabilir. Düşün ki, bir kitap okuduktan sonra sayfalarını kapatmıyorsun; kitap sayfaları zarar görebilir.

---

## 📖 10.3 Dosya Okuma İşlemleri

Dosyaları okumak için birkaç farklı yöntemimiz var. Hadi bu yöntemlere bakalım!

### 1. read() Metodu ile Tam Dosya Okuma

`read()` metodu, dosyanın tamamını okuyarak bir string olarak döner.

```python
dosya = open("ornek.txt", "r")  # Okuma modunda açıyoruz
icerik = dosya.read()
print(icerik)
dosya.close()
```

**Çıktı:**
```
Merhaba, dosya işlemleri!
```

### 2. readline() ve readlines() Metotları

#### 2.1. readline()

`readline()` metodu, dosyadan bir satır okur. Her çağrıldığında bir sonraki satırı getirir.

```python
dosya = open("ornek.txt", "r")
satir = dosya.readline()
print(satir)  # İlk satırı okur
dosya.close()
```

#### 2.2. readlines()

`readlines()` metodu, dosyadaki tüm satırları bir liste halinde döner.

```python
dosya = open("ornek.txt", "r")
satirlar = dosya.readlines()
print(satirlar)  # Tüm satırları liste halinde döner
dosya.close()
```

**Çıktı:**
```
['Merhaba, dosya işlemleri!']
```

### 3. Dosyanın Belirli Kısımlarını Okuma

Dosyadan belirli bir kısmı okumak istiyorsan, `seek()` metodunu kullanabilirsin. Bu metot ile dosyanın nereye gideceğini belirleyebilirsin.

```python
dosya = open("ornek.txt", "r")
dosya.seek(10)  # 10. bayta git
icerik = dosya.read(5)  # 5 bayt oku
print(icerik)
dosya.close()
```

**Çıktı:**
```
dosya
```

### 4. Dosya Okuma İşlemlerinde Döngüler

Döngüler ile dosya içeriğini satır satır okuyabiliriz.

```python
dosya = open("ornek.txt", "r")
for satir in dosya:
    print(satir.strip())  # strip() ile satır sonundaki boşlukları temizle
dosya.close()
```

**Çıktı:**
```
Merhaba, dosya işlemleri!
```

---

Harika! Dosya işlemlerine devam edelim ve dosya yazma işlemleri ile dosya yolları ve yöneticilerini detaylı bir şekilde inceleyelim. Hazırsan, başlayalım! 🎉

---

## 📌 10.4 Dosya Yazma İşlemleri

### 1. write() Metodu ile Yazma

`write()` metodu, bir dosyaya yazmak için kullanılır. Bu metodu kullanarak, dosya açıldığı moduna bağlı olarak verileri dosyaya ekleyebiliriz.

**Örnek:**

```python
# Yazma modunda dosya açıyoruz
dosya = open("ornek_yazma.txt", "w")
dosya.write("Python ile dosya yazma işlemleri!\n")
dosya.write("Bu, ikinci satır.\n")
dosya.close()  # Unutma, dosyayı kapatmayı!
```

**Çıktı**: `ornek_yazma.txt` dosyasında şu içerikler olacak:
```
Python ile dosya yazma işlemleri!
Bu, ikinci satır.
```

### 2. writelines() Metodu

`writelines()` metodu, bir liste veya iterable nesnesindeki tüm satırları dosyaya yazmak için kullanılır. Her elemanın sonunda yeni bir satır oluşturulmaz, bu yüzden satır sonu karakterlerini (newline) eklemeyi unutma!

**Örnek:**

```python
satirlar = [
    "Birinci satır.\n",
    "İkinci satır.\n",
    "Üçüncü satır.\n"
]

dosya = open("ornek_writelines.txt", "w")
dosya.writelines(satirlar)
dosya.close()
```

**Çıktı**: `ornek_writelines.txt` dosyasında şu içerikler olacak:
```
Birinci satır.
İkinci satır.
Üçüncü satır.
```

### 3. Dosya Üzerine Yazma ve Dosyaya Ekleme

Bir dosyayı yazma modunda açtığımızda, dosyanın mevcut içeriği silinir ve yeni içerik yazılır. Eğer mevcut içeriğin üzerine yazmak istemiyorsan, dosyayı **append (ekleme)** modunda açabilirsin.

**Örnek:**

```python
# Append modunda dosya açıyoruz
dosya = open("ornek_yazma.txt", "a")  # Eklemek için açıyoruz
dosya.write("Bu, dosyaya eklenen yeni bir satır.\n")
dosya.close()
```

**Çıktı**: `ornek_yazma.txt` dosyasında içerik şu şekilde güncellenmiş olacak:
```
Python ile dosya yazma işlemleri!
Bu, ikinci satır.
Bu, dosyaya eklenen yeni bir satır.
```

---

## 📌 10.5 Dosya Yolları ve Yöneticileri

Artık dosya yazma işlemlerini öğrendin, şimdi dosya yolları ve dosya yöneticilerine bakalım. Dosyaların nerede olduğunu anlamak, dosya işlemlerinde çok önemlidir.

### 1. Dosya Yolları ve Dosya Sistemleri

Dosya yolları, bir dosyanın dosya sistemindeki konumunu belirtir. İki tür dosya yolu vardır:

- **Absolute Path (Mutlak Yol)**: Dosyanın bulunduğu tam konumu belirtir. Örneğin: `C:\Users\Kullanıcı\Documents\ornek.txt` veya `/home/kullanici/ornek.txt`.

- **Relative Path (Göreceli Yol)**: Mevcut çalışma dizinine göre dosyanın konumunu belirtir. Örneğin: `ornek.txt` veya `./ornek.txt`.

### 2. Absolute ve Relative Path'ler

- **Mutlak Yol Kullanımı**:
```python
dosya = open("C:/Users/Kullanıcı/Documents/ornek.txt", "r")
icerik = dosya.read()
print(icerik)
dosya.close()
```

- **Göreceli Yol Kullanımı**:
```python
dosya = open("./ornek.txt", "r")  # Mevcut dizinde dosyayı aç
icerik = dosya.read()
print(icerik)
dosya.close()
```

### 3. pathlib Modülü ile Dosya Yolu İşlemleri

Python 3.4 ile birlikte gelen `pathlib` modülü, dosya yolu işlemlerini daha kolay hale getirir. `Path` sınıfını kullanarak dosya yolları ile işlemler yapabiliriz.

**Örnek:**

```python
from pathlib import Path

# Dosya yolu oluşturma
dosya_yolu = Path("ornek.txt")

# Dosya var mı kontrol et
if dosya_yolu.exists():
    print(f"{dosya_yolu} mevcut!")
else:
    print(f"{dosya_yolu} mevcut değil, yeni bir dosya oluşturulacak.")
    dosya_yolu.touch()  # Dosyayı oluştur
```

**Çıktı**: Eğer `ornek.txt` dosyası mevcutsa:
```
ornek.txt mevcut!
```
Eğer mevcut değilse:
```
ornek.txt mevcut değil, yeni bir dosya oluşturulacak.
```

---

## 📌 10.6 with Anahtar Kelimesi ve Context Manager

### 1. with Anahtar Kelimesinin Kullanımı

`with` anahtar kelimesi, Python’da bir kaynak yönetim aracıdır. Genellikle dosya işlemlerinde kullanılır, çünkü dosyaları açarken ve kapatırken kodunuzu daha temiz ve yönetilebilir hale getirir. Normalde bir dosya açtığınızda, dosyayı kapatmayı unutursanız, bu bellek sızıntısına veya diğer sorunlara yol açabilir. 

**Örnek:**

```python
with open("ornek_with.txt", "w") as dosya:
    dosya.write("Bu dosya, with anahtar kelimesi kullanılarak açıldı.\n")
    dosya.write("Dosya otomatik olarak kapatılacak!")
```

- Burada, `open` fonksiyonu ile dosya açılıyor ve `as` anahtar kelimesi ile dosya nesnesine `dosya` ismi veriliyor.
- `with` bloğu sona erdiğinde, dosya otomatik olarak kapatılır. Bu, hata oluşsa bile güvenli bir yol sağlar.

### 2. Context Manager ile Dosya İşlemlerinin Yönetimi

Context manager, kaynakları yönetmek için kullanılan bir yapıdır. Kendi context manager'ınızı oluşturmak istiyorsanız, `__enter__` ve `__exit__` özel yöntemlerini tanımlamanız gerekir.

- **`__enter__`**: Context manager başlatıldığında çağrılır ve genellikle dosya açma işlemleri burada yapılır.
- **`__exit__`**: Context manager bloğu tamamlandığında çağrılır ve burada kaynakları temizleme, dosyayı kapatma gibi işlemler yapılır.

**Örnek:**

```python
class DosyaYazici:
    def __init__(self, dosya_adi):
        self.dosya_adi = dosya_adi

    def __enter__(self):
        self.dosya = open(self.dosya_adi, "w")
        return self.dosya

    def __exit__(self, exc_type, exc_value, traceback):
        self.dosya.close()

with DosyaYazici("ornek_context_manager.txt") as dosya:
    dosya.write("Context manager ile dosya yazma işlemi!\n")
```

- Bu örnekte `DosyaYazici` sınıfı bir context manager olarak işlev görür. `with` bloğu sona erdiğinde, dosya otomatik olarak kapatılır.

### 3. with Bloğu Dışında Dosya İşlemleri

`with` bloğu dışında dosya açıp kapatma işlemleri yapıyorsanız, her zaman dosyayı manuel olarak kapatmayı unutmamalısınız. 

**Hatalı Kullanım Örneği:**

```python
dosya = open("hatalı_dosya.txt", "w")
dosya.write("Bu dosya kapatılmadan bırakıldı!")  # Kapatma işlemi unutulursa bellek sızıntısı olur.
```

### Doğru Kullanım:

```python
dosya = open("dogru_dosya.txt", "w")
try:
    dosya.write("Bu dosya kapatılacak!")
finally:
    dosya.close()  # Her durumda dosyayı kapatmayı sağlıyoruz.
```

- Bu kullanımda, `try` bloğu içinde dosya yazma işlemi yapılır ve `finally` bloğunda dosya kapatılır. Bu sayede hata olsa bile dosya kapatılır.

---

## 📌 10.7 İkili (Binary) Dosya İşlemleri

İkili dosyalar, bilgisayarların verileri 0 ve 1 şeklinde sakladığı dosyalardır. Genellikle görüntü, ses ve video dosyaları ikili formatta olur. İkili dosyalarla çalışmak için `rb` (read binary) ve `wb` (write binary) modları kullanılır.

### 1. Binary Modda Dosya Açma ve Okuma/Yazma

İkili dosya açarken `wb` veya `rb` modları kullanılır:

- `wb`: Yazma modunda, dosya yoksa oluşturur, varsa içerik üzerine yazar.
- `rb`: Okuma modunda, dosya ikili olarak okunur.

**Örnek:**

```python
# İkili dosyaya yazma
with open("ornek_binary.bin", "wb") as dosya:
    veri = bytearray([0x00, 0xFF, 0x45, 0x78])  # Binary veriler
    dosya.write(veri)

# İkili dosyadan okuma
with open("ornek_binary.bin", "rb") as dosya:
    okunan_veri = dosya.read()
    print(list(okunan_veri))  # Okunan veriyi liste olarak göster
```

**Çıktı**:
```
[0, 255, 69, 120]
```

### 2. struct Modülü ile Binary Dosya İşlemleri

`struct` modülü, Python verilerini C dilindeki yapılarına dönüştürmeye yardımcı olur. Bu, ikili verilerle çalışırken önemlidir, çünkü verileri byte dizilerine dönüştürebilir veya tam tersini yapabilirsiniz.

**Örnek:**

```python
import struct

# İkili dosyaya yazma
with open("ornek_struct.bin", "wb") as dosya:
    # 1 adet tamsayı ve 1 adet float yazıyoruz
    dosya.write(struct.pack('if', 1, 3.14))  # 'if': int ve float formatı

# İkili dosyadan okuma
with open("ornek_struct.bin", "rb") as dosya:
    okunan_veri = dosya.read()
    veri = struct.unpack('if', okunan_veri)  # Okunan byte dizisini unpack yapıyoruz
    print(veri)  # (1, 3.14)
```

**Çıktı**:
```
(1, 3.14)
```

### 3. Görüntü, Ses ve Video Dosyalarının İşlenmesi

Görüntü, ses ve video dosyaları da ikili dosya işlemleri ile yönetilebilir. Örneğin, bir resmi okuma ve yazma işlemi şu şekilde yapılabilir:

**Örnek: Görüntü Okuma ve Yazma**

Görüntü dosyaları ile çalışmak için `PIL` (Pillow) kütüphanesini kullanabilirsin. 

```python
from PIL import Image

# Görüntü dosyası açma
görüntü = Image.open("ornek_resim.jpg")  # Resmi aç
görüntü.save("yeni_resim.png")  # Farklı formatta kaydet
```

- Bu örnekte, bir JPEG görüntüsü açılıyor ve PNG formatında kaydediliyor. Bu işlem, görüntü verisini değiştirmen ve farklı formatlarda kaydetmen için kullanışlıdır.

**Ses ve Video Dosyaları İçin Örnek Kullanım:**

Ses dosyalarını okumak ve yazmak için `wave` ve `pydub` gibi kütüphaneleri kullanabilirsin. Video dosyaları için `OpenCV` veya `moviepy` gibi kütüphaneler tercih edilir.

```python
# Ses dosyası okuma
from pydub import AudioSegment

ses = AudioSegment.from_file("ornek_ses.mp3")  # MP3 formatında ses dosyası açma
ses.export("yeni_ses.wav", format="wav")  # WAV formatında kaydet
```

### İkili Dosya İşlemlerinde Dikkat Edilmesi Gerekenler

- İkili dosyalar, metin dosyalarına göre daha karmaşık bir yapıya sahiptir. İçerikleri doğrudan okunamaz; bu nedenle, hangi tür verileri yazdığını ve okuduğunu bilmek önemlidir.
- İkili dosyalar genellikle belirli bir format veya protokole göre düzenlenmiştir. Bu nedenle, verileri doğru şekilde okumak ve yazmak için bu formatı anlamak gerekir.
- Hata kontrolü ve exception handling kullanmak, dosya işlemlerinde karşılaşabileceğin olası hataları yönetmek açısından önemlidir. Örneğin, dosyanın var olup olmadığını kontrol etmek için `os.path` modülünü kullanabilirsin.

---

## 📌 10.8 Dosya ve Dizin İşlemleri

### 1. os ve shutil Modülleri ile Dosya/Dizin İşlemleri

Python'da dosya ve dizin işlemleri yapmak için `os` ve `shutil` modülleri oldukça kullanışlıdır. Bu modüller, işletim sistemi ile etkileşimde bulunmanı sağlar ve dosya/dizin yönetimini kolaylaştırır.

**os Modülü**: Dosya ve dizinlerin yolunu bulmak, oluşturmak, silmek gibi temel işlemleri gerçekleştirir. 

**shutil Modülü**: Dosya ve dizinleri kopyalama, taşıma ve yeniden adlandırma gibi işlemleri yüksek seviyede yapmanı sağlar.

### 2. Dosya ve Dizin Oluşturma, Silme, Yeniden Adlandırma

#### a. Dosya Oluşturma

Dosya oluşturmak için `open()` fonksiyonunu kullanırız. Dosya modunu `'w'` (yazma) veya `'a'` (ekleme) olarak belirleyerek yeni bir dosya oluşturabiliriz.

```python
# Yeni bir dosya oluşturma
with open("yeni_dosya.txt", "w") as dosya:
    # 'with' bloğu, dosyanın otomatik olarak kapatılmasını sağlar.
    # 'w' modu ile dosya açıldığında eğer dosya yoksa oluşturulur, varsa üzerine yazılır.
    dosya.write("Bu, yeni oluşturulmuş bir dosya.")
```

#### b. Dizin Oluşturma

Dizin oluşturmak için `os.makedirs()` veya `os.mkdir()` fonksiyonunu kullanabiliriz.

- `os.makedirs()`: Birden fazla katmanı olan dizinleri oluşturur.
- `os.mkdir()`: Sadece belirtilen dizini oluşturur.

```python
import os

# Yeni bir dizin oluşturma
os.makedirs("yeni_dizin/sub_dizin", exist_ok=True)  
# 'exist_ok=True' ile dizin zaten varsa hata vermez, program akışına devam eder.
```

#### c. Dosya ve Dizin Silme

Dosya silmek için `os.remove()` fonksiyonunu kullanırız. Dizin silmek için ise `os.rmdir()` veya `shutil.rmtree()` kullanılır.

```python
# Dosya silme
os.remove("yeni_dosya.txt")  
# Belirtilen dosyayı siler. Eğer dosya yoksa hata verir.

# Dizin silme
os.rmdir("yeni_dizin")  
# Dizin boşsa siler, içinde dosya varsa hata verir.
# Veya alt dizinleriyle birlikte silmek için:
shutil.rmtree("yeni_dizin")  
# Dizin içindeki her şeyi siler, dikkatli kullanılmalıdır!
```

#### d. Dosya ve Dizin Yeniden Adlandırma

Dosyaların ve dizinlerin adını değiştirmek için `os.rename()` fonksiyonunu kullanırız.

```python
# Dosya yeniden adlandırma
os.rename("yeni_dosya.txt", "eski_dosya.txt")  
# 'yeni_dosya.txt' dosyasını 'eski_dosya.txt' olarak yeniden adlandırır.

# Dizin yeniden adlandırma
os.rename("eski_dizin", "yeni_dizin")  
# 'eski_dizin' dizinini 'yeni_dizin' olarak yeniden adlandırır.
```

### 3. Dosya ve Dizin Kopyalama ve Taşıma

#### a. Dosya Kopyalama

Dosya kopyalamak için `shutil.copy()` fonksiyonunu kullanabiliriz.

```python
shutil.copy("orijinal_dosya.txt", "kopya_dosya.txt")  
# 'orijinal_dosya.txt' dosyasını 'kopya_dosya.txt' olarak kopyalar.
# Kopyalama işlemi, içeriği olduğu gibi taşır.
```

#### b. Dizin Kopyalama

Dizin kopyalamak için `shutil.copytree()` fonksiyonunu kullanırız.

```python
shutil.copytree("orijinal_dizin", "yeni_dizin")  
# 'orijinal_dizin' dizinini 'yeni_dizin' adıyla kopyalar.
# Kopyalama işlemi, dizin içindeki her şeyi kopyalar.
```

#### c. Taşıma

Dosyaları ve dizinleri taşımak için `shutil.move()` fonksiyonunu kullanabiliriz.

```python
shutil.move("kopya_dosya.txt", "yeni_dizin/kopya_dosya.txt")  
# 'kopya_dosya.txt' dosyasını 'yeni_dizin' dizinine taşır.
# Taşıma işlemi, dosyayı eski yerinden kaldırır ve yeni yere ekler.
```

---

## 📌 10.9 JSON Dosyaları ile Çalışma

JSON (JavaScript Object Notation), veri alışverişi için yaygın olarak kullanılan bir formattır. Okunabilir bir yapıya sahiptir ve dil bağımsızdır, bu da onu verilerin depolanması ve iletilmesi için popüler bir seçim haline getirir.

### 1. JSON Formatı ve Yapısı

JSON formatı, veri yapısını anahtar-değer çiftleri ve diziler kullanarak temsil eder. Aşağıda basit bir JSON yapısı örneği bulunmaktadır:

```json
{
    "ad": "Ali",
    "yas": 30,
    "meslek": "Yazılımcı",
    "ilgi_alanları": ["Python", "Veri Bilimi", "Yapay Zeka"]
}
```

### 2. json Modülü ile JSON Dosyalarının Okunması ve Yazılması

Python'da JSON dosyalarını okumak ve yazmak için `json` modülünü kullanırız. JSON verilerini Python veri yapılarına (sözlük, liste vb.) dönüştürmek için `json.load()` ve `json.loads()` metodlarını, Python veri yapılarını JSON formatına dönüştürmek için `json.dump()` ve `json.dumps()` metodlarını kullanırız.

#### a. JSON Dosyasını Okuma

```python
import json

# JSON dosyasını okuma
with open("veriler.json", "r") as dosya:
    # 'with' ifadesi dosyanın otomatik olarak kapanmasını sağlar.
    veri = json.load(dosya)  
    # json.load(), dosyadan JSON verisini okur ve Python veri yapısına çevirir.
    print(veri)  # Okunan veriyi gösterir.
```

#### b. JSON Dosyasına Yazma

```python
import json

# Yazılacak veri
veri = {
    "ad": "Ayşe",
    "yas": 28,
    "meslek": "Mühendis",
    "ilgi_alanları": ["Matematik", "Fizik"]
}

# JSON dosyasına yazma
with open("yeni_veriler.json", "w") as dosya:
    json.dump(veri, dosya, indent=4)  
    # json.dump(), Python veri yapısını JSON formatında dosyaya yazar.
    # indent=4, dosyadaki JSON verisinin daha okunabilir olmasını sağlar.
```

### 3. JSON Serileştirme ve Deserileştirme

- **Serileştirme** (Serialization): Python veri yapılarını JSON formatına dönüştürme işlemidir. `json.dump()` veya `json.dumps()` ile gerçekleştirilir.

- **Deserileştirme** (Deserialization): JSON formatındaki veriyi Python veri yapılarına dönüştürme işlemidir. `json.load()` veya `json.loads()` ile gerçekleştirilir.

#### Örnek: Serileştirme

```python
import json

veri = {
    "ad": "Ali",
    "yas": 30
}

json_veri = json.dumps(veri)  
# json.dumps(), Python veri yapısını JSON formatına dönüştürür.
print(json_veri)  # Çıktı: {"ad": "Ali", "yas": 30}
```

#### Örnek: Deserileştirme

```python
import json

json_veri = '{"ad": "Ayşe", "yas": 28}'
veri = json.loads(json_veri)  
# json.loads(), JSON formatındaki veriyi Python veri yapısına çevirir.
print(veri)  # Çıktı: {'ad': 'Ayşe', 'yas': 28}
```

---

## 📌 10.10 CSV Dosyaları ile Çalışma

### 1. CSV Formatı ve Kullanım Alanları

CSV (Comma-Separated Values), verilerin satır ve sütunlar halinde saklandığı düz metin dosyası formatıdır. Her satır bir kaydı, her sütun ise bir özelliği temsil eder. CSV dosyaları, veri alışverişi ve depolama için oldukça yaygın bir biçimdir.

**Kullanım Alanları:**
- Veri analizi ve istatistiksel çalışmalar
- Veritabanlarından veri aktarımı
- Uygulama ve yazılımlar arası veri transferi

**Örnek bir CSV dosyası:**
```
ad,yas,meslek
Ali,30,Yazılımcı
Ayşe,28,Mühendis
Mehmet,25,Öğrenci
```

### 2. csv Modülü ile CSV Dosyalarının Okunması ve Yazılması

Python'da CSV dosyalarıyla çalışmak için `csv` modülünü kullanırız. Bu modül, CSV dosyalarını okumak ve yazmak için gerekli fonksiyonları içerir.

#### a. CSV Dosyasını Okuma

```python
import csv

# CSV dosyasını okuma
with open("veriler.csv", mode='r') as dosya:
    okuyucu = csv.reader(dosya)  # CSV dosyasını okuyucuya alırız.
    # Okuyucu, dosyayı satır satır okur ve her satırı bir liste olarak döner.
    
    # Başlık satırını atla
    next(okuyucu)
    
    for satir in okuyucu:
        # Her satırı yazdır
        print(f"Ad: {satir[0]}, Yaş: {satir[1]}, Meslek: {satir[2]}")
```

- `csv.reader(dosya)`: Dosyayı satır satır okur ve verileri liste halinde döndürür.
- `next(okuyucu)`: İlk satırı (başlık) atlamak için kullanılır.
- `for satir in okuyucu`: Her bir satırı döngü ile işleriz.

#### b. CSV Dosyasına Yazma

```python
import csv

# Yazılacak veri
veriler = [
    ["ad", "yas", "meslek"],
    ["Ali", 30, "Yazılımcı"],
    ["Ayşe", 28, "Mühendis"],
    ["Mehmet", 25, "Öğrenci"]
]

# CSV dosyasına yazma
with open("yeni_veriler.csv", mode='w', newline='') as dosya:
    yazar = csv.writer(dosya)
    yazar.writerows(veriler)  
    # writerows, çoklu satırları yazmak için kullanılır.
```

- `csv.writer(dosya)`: Yazıcı nesnesi oluşturur.
- `writerows(veriler)`: Çoklu satırları belirtilen dosyaya yazar. `newline=''` ifadesi, satır sonu sorunlarını önler.

### 3. Pandas Kütüphanesi ile CSV İşlemleri

Pandas kütüphanesi, veri analizi için güçlü bir araçtır ve CSV dosyalarıyla çalışmayı kolaylaştırır. CSV dosyalarını DataFrame yapısında kolayca okuyabilir ve yazabiliriz.

```python
import pandas as pd

# CSV dosyasını okuma
df = pd.read_csv("veriler.csv")
print(df)  # DataFrame yapısını yazdır

# CSV dosyasına yazma
df.to_csv("yeni_veriler_pandas.csv", index=False)  
# index=False ile DataFrame’in indeksini dosyaya yazmaz.
```

- `pd.read_csv()`: CSV dosyasını DataFrame olarak okur.
- `df.to_csv()`: DataFrame’i CSV dosyasına yazar.

---

## 📌 10.11 XML Dosyaları ile Çalışma

### 1. XML Formatı ve Yapısı

XML (eXtensible Markup Language), verilerin yapılandırılmış bir şekilde depolanmasına ve paylaşılmasına olanak tanıyan bir işaretleme dilidir. Veri elemanlarını tanımlamak için etiketler kullanır ve hiyerarşik bir yapıdadır.

**Örnek bir XML dosyası:**
```xml
<kisi>
    <ad>Ali</ad>
    <yas>30</yas>
    <meslek>Yazılımcı</meslek>
</kisi>
```

### 2. xml.etree.ElementTree Modülü ile XML İşlemleri

Python'da XML dosyalarıyla çalışmak için `xml.etree.ElementTree` modülünü kullanırız. Bu modül, XML verilerini okumak, yazmak ve manipüle etmek için basit bir arayüz sağlar.

#### a. XML Dosyasını Okuma

```python
import xml.etree.ElementTree as ET

# XML dosyasını okuma
tree = ET.parse("veriler.xml")  # XML dosyasını analiz eder.
root = tree.getroot()  # XML yapısının kök elemanını alır.

# Kök elemandaki her 'kisi' etiketini yazdır
for kisi in root.findall("kisi"):
    ad = kisi.find("ad").text
    yas = kisi.find("yas").text
    meslek = kisi.find("meslek").text
    print(f"Ad: {ad}, Yaş: {yas}, Meslek: {meslek}")
```

- `ET.parse()`: XML dosyasını okur ve bir `ElementTree` nesnesi döner.
- `tree.getroot()`: XML belgesinin kök elemanını döner.
- `root.findall()`: Belirtilen etiketleri (örneğin `kisi`) bulur.

#### b. XML Dosyasına Yazma

```python
import xml.etree.ElementTree as ET

# Yeni XML yapısını oluşturma
kisi = ET.Element("kisi")
ad = ET.SubElement(kisi, "ad")
ad.text = "Ayşe"
yas = ET.SubElement(kisi, "yas")
yas.text = "28"
meslek = ET.SubElement(kisi, "meslek")
meslek.text = "Mühendis"

# XML dosyasına yazma
tree = ET.ElementTree(kisi)
tree.write("yeni_veriler.xml")  
# Yeni XML verisini belirtilen dosyaya yazar.
```

- `ET.Element()`: Yeni bir XML etiketini (kök eleman) oluşturur.
- `ET.SubElement()`: Belirtilen elemanın altında yeni bir etiket oluşturur.
- `tree.write()`: XML ağacını belirtilen dosyaya yazar.

#### c. XML Dosyalarının Manipülasyonu

XML dosyalarını okuyup yazmanın yanı sıra, mevcut XML dosyalarını güncellemek veya eleman eklemek de mümkündür.

```python
# XML dosyasını okuma
tree = ET.parse("veriler.xml")
root = tree.getroot()

# Yeni bir 'kisi' ekleme
yeni_kisi = ET.Element("kisi")
ad = ET.SubElement(yeni_kisi, "ad")
ad.text = "Mehmet"
yas = ET.SubElement(yeni_kisi, "yas")
yas.text = "25"
meslek = ET.SubElement(yeni_kisi, "meslek")
meslek.text = "Öğrenci"

# Kök elemana yeni 'kisi'yi ekleme
root.append(yeni_kisi)

# Güncellenmiş XML'i kaydetme
tree.write("guncellenmis_veriler.xml")  
```

- `root.append()`: Mevcut kök elemana yeni bir eleman ekler.
- Güncellenmiş XML yapısını kaydeder.

---

## 📌 10.12 Excel Dosyaları ile Çalışma

### 1. openpyxl ve pandas Modülleri ile Excel İşlemleri

Python'da Excel dosyalarıyla çalışmak için en yaygın olarak kullanılan iki kütüphane `openpyxl` ve `pandas`'dır. `openpyxl`, Excel dosyalarını okuma ve yazma işlemleri için kullanılırken, `pandas`, verilerin daha karmaşık işlenmesi ve analizi için güçlü bir araçtır.

#### a. openpyxl ile Excel Dosyalarını Okuma ve Yazma

```python
from openpyxl import Workbook, load_workbook

# Yeni bir Excel dosyası oluşturma
workbook = Workbook()  # Yeni bir Workbook nesnesi oluştur
sheet = workbook.active  # Varsayılan çalışma sayfasını al

# Veri ekleme
sheet["A1"] = "Ad"
sheet["B1"] = "Yaş"
sheet["C1"] = "Meslek"

sheet.append(["Ali", 30, "Yazılımcı"])
sheet.append(["Ayşe", 28, "Mühendis"])
sheet.append(["Mehmet", 25, "Öğrenci"])

# Dosyayı kaydetme
workbook.save("veriler.xlsx")
```

- `Workbook()`: Yeni bir Excel dosyası (çalışma kitabı) oluşturur.
- `sheet["A1"] = "Ad"`: Belirtilen hücreye veri ekler.
- `sheet.append(...)`: Verileri yeni bir satıra ekler.
- `workbook.save(...)`: Dosyayı belirtilen isimle kaydeder.

#### b. Excel Dosyasını Okuma

```python
from openpyxl import load_workbook

# Varolan Excel dosyasını yükleme
workbook = load_workbook("veriler.xlsx")
sheet = workbook.active  # Aktif çalışma sayfasını al

# Verileri okuma
for row in sheet.iter_rows(min_row=2, values_only=True):  # 2. satırdan itibaren oku
    print(f"Ad: {row[0]}, Yaş: {row[1]}, Meslek: {row[2]}")
```

- `load_workbook(...)`: Varolan bir Excel dosyasını yükler.
- `iter_rows(...)`: Belirtilen satır aralığını döngü ile okur.

### 2. pandas ile Excel Dosyalarının Okunması ve Yazılması

`pandas`, Excel dosyalarını DataFrame olarak okuyup yazmak için oldukça kullanışlıdır.

#### a. Excel Dosyasını Okuma

```python
import pandas as pd

# Excel dosyasını okuma
df = pd.read_excel("veriler.xlsx")
print(df)  # DataFrame yapısını yazdır
```

- `pd.read_excel(...)`: Excel dosyasını DataFrame olarak okur.

#### b. Excel Dosyasına Yazma

```python
# Yeni veriler
yeni_veriler = pd.DataFrame({
    "Ad": ["Zeynep", "Can"],
    "Yaş": [26, 22],
    "Meslek": ["Tasarımcı", "Grafiker"]
})

# Excel dosyasına yazma
yeni_veriler.to_excel("yeni_veriler.xlsx", index=False)
```

- `pd.DataFrame(...)`: Yeni bir DataFrame oluşturur.
- `to_excel(...)`: DataFrame’i belirtilen Excel dosyasına yazar.

### 3. Çalışma Sayfaları ve Hücre İşlemleri

Excel dosyalarında birden fazla çalışma sayfası bulunabilir. `openpyxl` ile bu sayfalarda işlem yapabiliriz.

```python
from openpyxl import Workbook

# Yeni bir Excel dosyası oluşturma
workbook = Workbook()

# İki yeni çalışma sayfası ekleme
sheet1 = workbook.create_sheet("Sayfa1")
sheet2 = workbook.create_sheet("Sayfa2")

# Veri ekleme
sheet1["A1"] = "Ad"
sheet2["A1"] = "Meslek"

# Dosyayı kaydetme
workbook.save("coklu_sayfa.xlsx")
```

- `create_sheet(...)`: Yeni bir çalışma sayfası oluşturur.

---

## 📌 10.13 Hata Yönetimi ve Dosya İşlemleri

### 1. Dosya İşlemlerinde Hata Yönetimi

Dosya işlemleri sırasında çeşitli hatalarla karşılaşabiliriz. Bu hataları yönetmek için `try` ve `except` blokları kullanılır.

#### a. Dosya Açma Hatası Yönetimi

```python
try:
    with open("veriler.txt", "r") as dosya:
        veri = dosya.read()
except FileNotFoundError:
    print("Hata: Dosya bulunamadı!")
except IOError:
    print("Hata: Dosya okuma hatası!")
```

- `try`: Hata oluşma ihtimali olan kod bloğu.
- `except`: Belirli bir hata oluşursa ne yapılacağını belirten kod bloğu.

### 2. IOError ve OSError Hatalarının Yakalanması ve Yönetimi

`IOError` ve `OSError`, dosya işlemleri sırasında karşılaşabileceğimiz yaygın hatalardır. Bu hatalar, dosya sistemine erişim sorunları veya dosya bulunamadığında meydana gelir.

```python
try:
    # Geçersiz bir dosya adı ile dosya açmaya çalış
    with open("gecersiz_dosya.txt", "r") as dosya:
        veri = dosya.read()
except IOError as e:
    print(f"IOError: {e}")  # Hatanın detayını yazdır
except OSError as e:
    print(f"OSError: {e}")  # Hatanın detayını yazdır
```

- `IOError`: Giriş/çıkış hataları için.
- `OSError`: Sistemle ilgili hatalar için kullanılır.

### 3. Örnek Kullanım

Aşağıda bir dosya okuma işlemi sırasında hata yönetimi örneği verilmiştir:

```python
dosya_adi = "veriler.txt"

try:
    with open(dosya_adi, "r") as dosya:
        veri = dosya.read()
        print(veri)
except FileNotFoundError:
    print(f"{dosya_adi} bulunamadı, lütfen dosya adını kontrol edin.")
except IOError:
    print("Dosya okuma sırasında bir hata oluştu.")
```

- Kullanıcıdan alınan dosya adını kontrol eder.
- Hata durumunda kullanıcıya uygun bir mesaj verir.

---

## 📌 10.14 Büyük Dosyalar ve Verimlilik

### 1. Büyük Dosyalarla Çalışma Teknikleri

Büyük dosyalarla çalışırken, bellek sınırlarını zorlamamak ve işlemleri hızlı gerçekleştirmek için bazı teknikler kullanmalıyız. İşte büyük dosyalarla çalışma için yaygın teknikler:

#### a. Satır Satır Okuma

Büyük bir dosyayı belleğe tamamını yüklemek yerine, dosyayı satır satır okuyarak bellek tüketimini azaltabiliriz.

```python
with open("buyuk_dosya.txt", "r") as dosya:
    for satir in dosya:
        print(satir.strip())  # Satırı okur ve boşlukları temizler
```

Burada, dosyanın her satırını tek tek okumak, belleği verimli kullanmamızı sağlar.

#### b. Dosya Parçalama

Eğer bir dosya çok büyükse, bu dosyayı daha küçük parçalara bölmek mantıklı olabilir. Bu, işlemleri daha yönetilebilir hale getirir.

```python
import itertools

def dosyayi_parcala(dosya_adi, parca_boyutu):
    with open(dosya_adi, "r") as dosya:
        parca_no = 1
        while True:
            parca = list(itertools.islice(dosya, parca_boyutu))
            if not parca:  # Parça boşsa döngüden çık
                break
            with open(f"parca_{parca_no}.txt", "w") as parca_dosyasi:
                parca_dosyasi.writelines(parca)
            parca_no += 1

dosyayi_parcala("buyuk_dosya.txt", 100)  # Her parçada 100 satır
```

Burada, `itertools.islice` kullanarak belirli bir aralıkta dosyayı okuyabilir ve parça parça yazmayı sağlayarak işlem verimliliğimizi artırabiliriz.

### 2. Dosya İşlemlerinde Bellek Yönetimi

Bellek yönetimi, özellikle büyük dosyalarla çalışırken kritik öneme sahiptir. Bellek sızıntılarını önlemek ve performansı artırmak için aşağıdaki yöntemleri kullanabilirsiniz:

#### a. Belleği Optimize Etme

Büyük veri setlerini işlerken, gereksiz değişkenler oluşturmak yerine doğrudan işlemleri yapmalıyız.

```python
def bellek_optimize():
    with open("buyuk_dosya.txt", "r") as dosya:
        for satir in dosya:
            # Bellek kullanımını en aza indirge
            if "önemli" in satir:
                print(satir.strip())

bellek_optimize()
```

Yalnızca gerekli olan verileri işleyerek bellek kullanımını azaltmış oluruz.

### 3. Bellek Harici İşlemler ve Lazy Loading

Lazy loading, verilerin ihtiyaç duyulana kadar yüklenmemesi prensibidir. Bu, bellek verimliliğini artırır ve başlangıçta gereksiz yüklenmelerden kaçınır.

```python
def lazy_loading(dosya_adi):
    with open(dosya_adi, "r") as dosya:
        while True:
            satir = dosya.readline()
            if not satir:  # Dosyanın sonuna gelindi
                break
            yield satir.strip()  # Yalnızca gerekli satırı döner

for satir in lazy_loading("buyuk_dosya.txt"):
    print(satir)
```

`yield` ifadesi, işlevin çalışmasını durdurarak dışarıya veri döner; böylece yalnızca ihtiyaç duyulduğunda verileri yüklemiş oluruz.

---

## 📌 10.15 Dosya İşlemleri ve Güvenlik

### 1. Dosya İzinleri ve Erişim Kontrolleri

Dosyaların güvenliği, dosya izinleri ile sağlanır. Her dosyanın okuma, yazma ve yürütme izinleri vardır. Bu izinler, işletim sistemine göre değişebilir.

#### a. Python ile Dosya İzinlerini Ayarlama

```python
import os

# Dosya izni ayarlama
os.chmod("ornek.txt", 0o644)  # Okuma ve yazma izinleri
```

`os.chmod(...)` fonksiyonu, belirtilen dosyanın izinlerini değiştirir. `0o644` değeri, kullanıcı için okuma/yazma, grup ve diğerleri için ise yalnızca okuma iznini temsil eder.

### 2. Güvenli Dosya İşlemleri ve İzin Yönetimi

Güvenli dosya işlemleri, özellikle kullanıcı verileri ile çalışırken önemlidir. Kullanıcılara yalnızca gerekli izinleri vermek ve hassas verileri korumak gerekmektedir.

#### a. Dosya İzinlerini Kontrol Etme

```python
import os

dosya_adi = "ornek.txt"

if os.access(dosya_adi, os.R_OK):
    print(f"{dosya_adi} okuma iznine sahip.")
else:
    print(f"{dosya_adi} okuma izni yok.")
```

`os.access(...)` fonksiyonu, belirtilen dosyanın izinlerini kontrol eder.

### 3. Kötü Amaçlı Dosya Manipülasyonlarına Karşı Önlemler

Kötü amaçlı yazılımlar ve manipülasyonlar, veri güvenliğini tehdit eder. Bu nedenle aşağıdaki önlemler alınmalıdır:

#### a. Kullanıcı Girdisini Doğrulama

Kullanıcılardan alınan girdilerin doğrulanması, kötü niyetli verilerin işlenmesini önleyebilir.

```python
def dosya_islemi(dosya_adi):
    if not dosya_adi.endswith(".txt"):
        raise ValueError("Sadece .txt dosyaları ile çalışılabilir.")
    
    with open(dosya_adi, "r") as dosya:
        # Dosya okuma işlemleri
        veri = dosya.read()
        print(veri)

try:
    dosya_islemi("kotu_dosya.exe")
except ValueError as e:
    print(e)  # Geçersiz dosya türü hatası
```

Kullanıcıdan alınan dosya adının uzantısını kontrol ederek sadece belirli dosya türleri ile işlem yapılmasını sağlarız.

#### b. Dosya Yedekleme

Önemli dosyaların yedeklenmesi, veri kaybı riskini azaltır.

```python
import shutil

# Dosyayı yedekleme
shutil.copy("orijinal.txt", "yedeK_orijinal.txt")
print("Dosya yedeklendi.")
```

`shutil.copy(...)` fonksiyonu, belirtilen dosyanın yedeğini oluşturur.

---

## 📂 Python Dosya İşlemleri ile Gerçek Dünya Projeleri

Dosya işlemleri, yazılım projelerinde kritik bir role sahiptir. Gerçek dünya uygulamalarında yedekleme, loglama, veri saklama ve işleme gibi birçok alanda dosya işlemlerine ihtiyaç duyulur. Bu bölümde, dosya işlemlerini kullanarak üç farklı proje örneği üzerinde duracağız.

---

### 📌 6.16.1 **Veritabanı Yedekleme ve Geri Yükleme**  

Veritabanları, uygulamalar için hayati öneme sahiptir. Olası bir veri kaybına karşı yedekleme yapmak ve gerektiğinde bu yedeği geri yüklemek büyük önem taşır.  

**🔹 Senaryo:**  
Bir SQLite veritabanını (`veritabani.db`) belirli aralıklarla yedekleyip, ihtiyaç halinde yedekten geri yükleyen bir Python betiği yazalım.

#### ✅ **SQLite Veritabanını Yedekleme**
Python’un `shutil` modülü ile veritabanını güvenli bir şekilde yedekleyebiliriz.

```python
import shutil
import datetime

def veritabani_yedekle():
    tarih = datetime.datetime.now().strftime("%Y-%m-%d_%H-%M-%S")
    yedek_adi = f"veritabani_yedek_{tarih}.db"
    
    shutil.copy("veritabani.db", yedek_adi)  # Veritabanını kopyalayarak yedek al
    print(f"Veritabanı başarıyla yedeklendi: {yedek_adi}")

veritabani_yedekle()
```
📌 *Kod, mevcut veritabanını alarak zaman damgası içeren yeni bir dosya oluşturur ve orijinal veritabanının kopyasını çıkarır.*

---

#### ✅ **Veritabanını Yedekten Geri Yükleme**
Eğer bir hata veya veri kaybı yaşanırsa, daha önce alınan bir yedekten geri yükleme yapmak gerekebilir.

```python
def yedekten_geri_yukle(yedek_dosya):
    shutil.copy(yedek_dosya, "veritabani.db")
    print(f"{yedek_dosya} dosyasından veritabanı geri yüklendi.")

# Örnek kullanım:
# yedekten_geri_yukle("veritabani_yedek_2025-03-08_14-30-00.db")
```

📌 *Kullanıcı, geri yüklemek istediği yedek dosyanın adını parametre olarak girerek veritabanını eski haline getirebilir.*

---

### 📌 6.16.2 **Dosya İşlemleri ile Loglama**  

Uygulamalar çalışırken oluşan hataları ve önemli olayları takip etmek için log dosyaları oluşturmak gerekir. Loglama, hata ayıklama ve sistem izleme açısından büyük bir avantaj sağlar.

**🔹 Senaryo:**  
Bir Python programı çalıştığında, her önemli olayı veya hatayı bir log dosyasına yazan bir sistem tasarlayalım.

#### ✅ **Loglama Sistemi Oluşturma**
Python’un `logging` modülü ile detaylı loglar oluşturabiliriz.

```python
import logging

# Loglama yapılandırması
logging.basicConfig(
    filename="uygulama.log",
    level=logging.INFO,
    format="%(asctime)s - %(levelname)s - %(message)s",
)

def kritik_islem():
    try:
        logging.info("Kritik işlem başlatıldı.")
        # Burada kritik bir işlem yapılıyor
        sonuc = 10 / 0  # Hata yaratmak için bilinçli bir hata
    except Exception as e:
        logging.error(f"Hata oluştu: {e}")
    else:
        logging.info("Kritik işlem başarıyla tamamlandı.")

kritik_islem()
```

📌 *Kod, hata veya başarılı işlemleri `uygulama.log` dosyasına yazar. Hata oluşursa `ERROR`, başarılı olursa `INFO` seviyesinde log kaydı tutulur.*

---

### 📌 6.16.3 **Dosya İşlemleri ile Raporlama**

Dosya işlemleri, iş dünyasında raporlama süreçlerinde sıkça kullanılır. CSV formatı, raporlama için en yaygın kullanılan formatlardan biridir.

**🔹 Senaryo:**  
Bir şirketin günlük satışlarını kaydeden bir sistem oluşturalım. Bu sistem günlük satışları bir CSV dosyasına kaydedecek ve istenildiğinde rapor olarak çıktı alabilecek.

#### ✅ **Satışları Kaydetme**
Python’un `csv` modülü ile satış verilerini bir CSV dosyasına yazabiliriz.

```python
import csv

def satis_ekle(tarih, urun, miktar, fiyat):
    with open("satislar.csv", "a", newline="") as dosya:
        yazici = csv.writer(dosya)
        yazici.writerow([tarih, urun, miktar, fiyat])
        print(f"{urun} satışı kaydedildi.")

satis_ekle("2025-03-08", "Laptop", 2, 15000)
satis_ekle("2025-03-08", "Telefon", 5, 8000)
```

📌 *Kod, satış verilerini `satislar.csv` dosyasına ekler. `a` (append) modu sayesinde yeni veriler dosyanın sonuna eklenir.*

---

#### ✅ **Satış Raporu Oluşturma**
Kaydedilen satışları okuyarak bir rapor oluşturabiliriz.

```python
def satis_raporu():
    with open("satislar.csv", "r") as dosya:
        okuyucu = csv.reader(dosya)
        toplam_satis = 0
        print("📊 SATIŞ RAPORU 📊")
        print("-" * 40)
        for satir in okuyucu:
            tarih, urun, miktar, fiyat = satir
            miktar, fiyat = int(miktar), int(fiyat)
            toplam_satis += miktar * fiyat
            print(f"Tarih: {tarih}, Ürün: {urun}, Miktar: {miktar}, Toplam: {miktar * fiyat} TL")
        
        print("-" * 40)
        print(f"Toplam Satış: {toplam_satis} TL")

satis_raporu()
```

📌 *Kod, `satislar.csv` dosyasını okuyarak her satışın detaylarını ve toplam satış tutarını hesaplar.*