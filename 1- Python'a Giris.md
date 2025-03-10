# 🐍 Python'a Giriş

Merhaba Python sever! Eğer bu satırları okuyorsan, demek ki Python öğrenmeye karar verdin. Harika bir tercih yaptın! Python, hem acemiler hem de profesyoneller için mükemmel bir dil. Peki neden bu kadar popüler? Hadi birlikte keşfedelim!

---

## 📌 1.1 Python Nedir?

Python, 1991 yılında **Guido van Rossum** tarafından geliştirilen, basit ve okunabilir sözdizimiyle dikkat çeken **yüksek seviyeli** bir programlama dilidir. Ana felsefesi şudur:

> **"Kod okunabilir olmalıdır!"** ✨

Peki, Python neden bu kadar seviliyor?

✅ **Kolay okunur ve yazılır** - İngilizce gibi doğal bir dil yapısına sahiptir.  
✅ **Öğrenmesi hızlıdır** - Yeni başlayanlar için ideal bir dildir.  
✅ **Dinamik tür tanımlama** - `int`, `str`, `float` gibi veri tipleriyle uğraşmazsın, Python senin yerine halleder.  
✅ **Platform bağımsızdır** - Windows, Mac ve Linux'ta çalışır.  
✅ **Geniş kütüphane desteği** - Veri bilimi, yapay zeka, web geliştirme gibi birçok alanda güçlü kütüphanelere sahiptir.

📌 **Kısa bir Python kodu nasıl görünür?**

```python
print("Merhaba Python!")
```

Ve çıktısı:
```
Merhaba Python!
```
İşte bu kadar! 

---

## 🎯 1.2 Python Nerelerde Kullanılır?

Python **her yerde!** Gerçekten. İşte bazı kullanım alanları:

- **📊 Veri Bilimi & Makine Öğrenmesi** → `pandas`, `numpy`, `scikit-learn`, `tensorflow`
- **🌐 Web Geliştirme** → `Django`, `Flask`, `FastAPI`
- **🛡️ Siber Güvenlik** → `requests`, `BeautifulSoup`, `scapy`
- **🎮 Oyun Geliştirme** → `Pygame`, `Godot`
- **🤖 Yapay Zeka** → `OpenAI`, `transformers`
- **🔧 Otomasyon & Script Yazımı** → Günlük işleri otomatikleştirmek için birebir!

💡 **Eğer tekrar eden sıkıcı bir iş varsa, muhtemelen Python ile otomatik hale getirebilirsin!**

---

## 🕰️ 1.3 Python'un Kısa Tarihçesi

Python’un adını **bir yılandan değil**, *Monty Python's Flying Circus* adlı komedi şovundan aldığını biliyor muydun?

| Yıl | Gelişme |
|-----|---------|
| **1991** | Python 1.0 yayınlandı |
| **2000** | Python 2.0 geldi, ancak Python 3 ile uyumsuz oldu |
| **2008** | Python 3.0 çıktı, büyük değişiklikler yapıldı |
| **Günümüz** | Python 3.11+ sürümleriyle güçlenmeye devam ediyor! |

Bugün **Python 3** kullanıyoruz ve güncellemeleri takip etmek önemli!

---

## ⚙️ 1.4 Python Kurulumu & Çalışma Ortamı

Python’u kurmak için işletim sistemine göre aşağıdaki yöntemlerden birini kullanabilirsin:

### 🔹 Windows
[Python’un resmi web sitesine](https://www.python.org/) git, en son sürümü indir ve "Add to PATH" seçeneğini işaretleyerek kur.

### 🔹 macOS
Terminal’i aç ve şu komutu çalıştır:
```bash
brew install python
```

### 🔹 Linux (Ubuntu/Debian)
```bash
sudo apt update && sudo apt install python3
```

**Kurulum başarılı mı?** Kontrol etmek için şu komutu yaz:
```bash
python --version
```
Çıktı şu şekilde olmalı:
```
Python 3.x.x
```

🎉 Python çalışıyor! Şimdi ilk programımızı yazalım!

---

## 👩‍💻 1.5 Python ile İlk Program

Bir dosya aç ve şu kodu yaz:
```python
print("Hello, Python!")
```
**Çalıştır:**
```bash
python dosya_adı.py
```
📌 Çıktı:
```
Hello, Python!
```
İlk programını çalıştırdın! 

---

## 🏗️ 1.6 Python'un Temel Yapısı

- **Python, yorumlanabilir (interpreted) bir dildir.** Yani derleme yapmadan çalıştırabilirsin.
- **Girinti (indentation) çok önemlidir!** `{}` yerine girinti kullanır:

```python
if True:
    print("Girintiye dikkat et!")
```

**Hatalı:**
```python
if True:
print("Bu hata verir!")  # ❌
```

💡 **PEP 8** standardını takip etmek yazdığın kodu daha anlaşılır hale getirir.

---

## ⚖️ 1.7 Python’un Avantajları & Dezavantajları

### ✅ Avantajlar
✔ Kolay öğrenilir ve okunur 
✔ Dinamik tür yapısı sayesinde esnektir 
✔ Kapsamlı kütüphane desteği 
✔ Büyük ve aktif bir topluluğa sahiptir 
✔ Platform bağımsızdır 

### ❌ Dezavantajlar
❌ C++ ve Java gibi dillere göre daha yavaş 
❌ Mobil uygulama geliştirme için pek uygun değil 
❌ Gömülü sistemlerde (embedded) pek tercih edilmiyor 

---

## 🔥 1.8 Python'un Popüler Framework ve Kütüphaneleri

- **📊 Veri Bilimi:** `pandas`, `numpy`, `matplotlib`
- **🤖 Makine Öğrenmesi:** `scikit-learn`, `tensorflow`
- **🌐 Web Geliştirme:** `Django`, `Flask`
- **🔄 API İletişimi:** `requests`, `httpx`
- **🔍 Web Scraping:** `BeautifulSoup`, `Scrapy`

Python öğrenirken bu kütüphaneleri keşfetmek çok işine yarayacak!

---

## 🌍 1.9 Python Topluluğu ve Kaynaklar

Python öğrenirken şu platformları takip edebilirsin:

📌 **[Python.org](https://www.python.org/)** → Resmi Python dökümantasyonu  
📌 **Stack Overflow** → Python ile ilgili sorularını sorabileceğin bir forum  
📌 **GitHub** → Açık kaynak projelere katkı sağla!  
📌 **Reddit - r/learnpython** → Python hakkında harika içerikler bulunuyor!

Unutma ki her programlama dili gibi Python öğrenmek bir yolculuktur ve bu yolculukta ne kadar pratik yaparsan o kadar hızlı ilerlersin!
