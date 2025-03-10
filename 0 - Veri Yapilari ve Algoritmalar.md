# 🧠 Veri Yapıları ve Algoritmalar

Merhaba, geleceğin algoritma ustası! Eğer bu satırları okuyorsan, **"Veri Yapıları ve Algoritmalar"** konusuna hoş geldin! Bu bölüm, programlamanın en kritik yapı taşlarından biridir. "Ben sadece kod yazmak istiyorum, bunlarla uğraşmasam olur mu?" diye düşünüyorsan... Maalesef hayır! Çünkü iyi bir programcı olmak istiyorsan **veriyi verimli bir şekilde saklamayı** ve **problemleri en hızlı yoldan çözmeyi** bilmelisin!

Bu rehberde, veri yapıları ve algoritmaları en temel seviyeden başlayarak detaylı bir şekilde öğreneceğiz. Konular **hem teorik hem de pratik kod örnekleriyle** desteklenecek. Yani, **Python bilmiyor olsan bile** buradaki açıklamalar sayesinde her şeyi rahatça anlayabileceksin!

---

## 📌 3.1 Giriş: Veri Yapıları ve Algoritmaların Önemi

Önce şu soruyu soralım: **Veri yapıları ve algoritmalar neden bu kadar önemli?**

- **Verileri düzenli ve verimli bir şekilde saklamak için** kullanılır.
- **Kodlarımızın performansını artırır!** Daha az bellek kullanarak daha hızlı çalışan uygulamalar geliştirebiliriz.
- **Google, Facebook, Amazon gibi dev şirketlerin altyapısı bunlara dayanır.** En iyi yazılımcılar, veriyi en iyi şekilde işleyebilenlerdir.
- **İyi bir algoritma, kötü bir algoritmadan 1000 kat hızlı olabilir!** (Gerçek bir örnek: Google’ın arama motoru)
- **Mülakatlarda en çok sorulan konular arasındadır!** Eğer yazılım sektöründe çalışmak istiyorsan, kesinlikle öğrenmelisin.

### 🏎️ Algoritma Analizi ve Karmaşıklık Teorisi

Bir algoritmanın iyi veya kötü olduğunu nasıl anlarız? İşte burada **algoritma analizi** devreye giriyor. Bir algoritmanın ne kadar hızlı çalıştığını belirlemek için iki ana ölçüt vardır:

1. **Zaman Karmaşıklığı (Time Complexity)**: Algoritmanın çalıştırılması ne kadar sürer?
2. **Uzay Karmaşıklığı (Space Complexity)**: Algoritma ne kadar bellek kullanır?

Örneğin, iki farklı kod parçası aynı işi yapabilir ama biri 1 saniyede çalışırken diğeri 10 dakikada çalışabilir! İşte bu yüzden **algoritmaların verimliliğini ölçmek önemlidir.**

### ⏳ Big O Notasyonu

Big O Notasyonu, bir algoritmanın **veri büyüdükçe nasıl performans gösterdiğini** ölçen bir sistemdir. Örneklerle daha iyi anlayalım:

- **O(1) - Sabit zaman** → Veri büyüse bile işlem süresi değişmez. En hızlı algoritmadır. 
- **O(log n) - Logaritmik zaman** → Veri arttıkça işlem süresi çok az artar. Çok verimli bir yöntemdir. 
- **O(n) - Doğrusal zaman** → Veri büyüdükçe işlem süresi de aynı oranda artar. Ortalama bir durumdur. 
- **O(n²) - Karesel zaman** → Veri arttıkça işlem süresi **katlanarak artar.** Büyük veri setlerinde büyük bir sorun olabilir. 
- **O(2^n) - Üstel zaman** → Veriler arttıkça işlem süresi **patlayarak artar.** Kötü bir algoritmadır, mümkünse kaçınılmalıdır! 

Bir algoritmanın performansını anlamak için **döngülerin ve iç içe işlemlerin** etkisini göz önünde bulundurmalıyız.

---

## 📜 3.2 Listeler

Python'da **listeler (lists)**, **verileri sıralı şekilde saklayan ve değiştirebileceğimiz (mutable) veri yapılarıdır.**

### 🔹 Liste Tanımlama ve Temel İşlemler

Python’da liste tanımlamak çok kolaydır:

```python
meyveler = ["Elma", "Armut", "Muz", "Çilek"]
print(meyveler)  # ['Elma', 'Armut', 'Muz', 'Çilek']
```

Liste elemanlarına erişmek için:

```python
print(meyveler[0])  # Elma
print(meyveler[-1]) # Çilek (Son eleman)
```

Listelere eleman eklemek ve çıkarmak:

```python
meyveler.append("Karpuz")   # Listeye ekleme
meyveler.remove("Armut")   # Elemanı silme
print(meyveler)  # ['Elma', 'Muz', 'Çilek', 'Karpuz']
```

### 📜 Liste Metotları ve Fonksiyonları

- `append()` → Eleman ekler.
- `remove()` → Belirtilen elemanı siler.
- `pop()` → Son elemanı çıkarır ve döndürür.
- `insert(i, x)` → Belirtilen **i** konumuna **x** ekler.
- `sort()` → Listeyi sıralar.
- `reverse()` → Listeyi ters çevirir.

```python
sayilar = [5, 2, 9, 1]
sayilar.sort()
print(sayilar)  # [1, 2, 5, 9]
```

---

### 🔗 Bağlı Listeler (Linked Lists)

Bağlı Listeler, dizilerden farklı olarak **dinamik bellek yönetimi** sağlar. Bellekte parçalı şekilde saklandığı için **boyutları değiştirilebilir** ve **ekleme-silme işlemleri daha hızlı yapılabilir.**

### 📌 Tek Yönlü Bağlı Liste (Singly Linked List)

### 📌 Tek Yönlü Bağlı Liste Nedir?

Tek yönlü bağlı liste, her düğümün sadece **bir sonraki düğümü gösterdiği** bir veri yapısıdır. Python’daki listelere benzese de, bellekte farklı bir şekilde tutulur. Listeler diziler gibi bitişik alanlarda saklanmaz, her düğüm (node) kendi verisini ve bir sonraki düğümün referansını içerir.

### 🔹 Tek Yönlü Bağlı Listenin Avantajları
- **Dinamik boyut**: Boyutu önceden belirlemeye gerek yoktur, gerektiğinde büyüyebilir veya küçülebilir.
- **Hızlı ekleme & silme**: Başta veya ortada eleman ekleme/silme işlemleri, dizilere kıyasla daha verimlidir.
- **Daha az bellek harcama**: Büyük veri kümeleri için daha az bellek parçalanmasına sebep olur.

### 🔹 Tek Yönlü Bağlı Listenin Dezavantajları
- **Dizi gibi rastgele erişim yoktur**: Bir elemanı bulmak için en baştan itibaren taramak gerekir.
- **Daha fazla bellek kullanabilir**: Her düğüm, verinin yanında bir de referans bilgisi tutar.

### 🔹 Tek Yönlü Bağlı Liste Örneği (Kodlu Açıklama)

Şimdi Python ile bir bağlı liste oluşturalım:

```python
# Düğüm (Node) yapısını tanımlıyoruz.
class Dugum:
    def __init__(self, veri):
        self.veri = veri  # Düğümde saklanan veri
        self.sonraki = None  # Bir sonraki düğümü gösteren referans

# Bağlı listeyi tanımlıyoruz.
class BagliListe:
    def __init__(self):
        self.bas = None  # Bağlı listenin ilk düğümünü temsil eden referans

    # Başa eleman ekleme fonksiyonu
    def ekle(self, veri):
        yeni_dugum = Dugum(veri)  # Yeni düğüm oluştur
        yeni_dugum.sonraki = self.bas  # Yeni düğümün sonraki referansını mevcut başa bağla
        self.bas = yeni_dugum  # Yeni düğümü baş düğüm yap

    # Bağlı listeyi ekrana yazdıran fonksiyon
    def yazdir(self):
        temp = self.bas  # Geçici bir değişkenle baştan itibaren düğümleri gez
        while temp:  # Düğümler bitene kadar devam et
            print(temp.veri, end=" -> ")  # Düğüm verisini ekrana yazdır
            temp = temp.sonraki  # Bir sonraki düğüme geç
        print("None")  # Listenin sonunu göster

# Bağlı listeyi oluşturalım
liste = BagliListe()
liste.ekle(3)
liste.ekle(2)
liste.ekle(1)
liste.yazdir()  # Çıktı: 1 -> 2 -> 3 -> None
```

📌 **Kod Açıklamaları:**
- `Dugum` sınıfı, her düğümün veri ve bir sonraki düğüme referans tutmasını sağlar.
- `BagliListe` sınıfı, bir bağlı liste oluşturmak için kullanılır.
- `ekle()` fonksiyonu, bağlı listenin **başına** yeni bir düğüm ekler.
- `yazdir()` fonksiyonu, tüm düğümleri sırasıyla yazdırır.
- `liste.ekle(3)`, `liste.ekle(2)`, `liste.ekle(1)` komutlarıyla 1, 2 ve 3 sırasıyla başa eklenir.
- Son olarak **"1 -> 2 -> 3 -> None"** çıktısını alırız.


### 📌 Çift Yönlü Bağlı Liste (Doubly Linked List)

```python
class Dugum:
    def __init__(self, veri):
        self.veri = veri
        self.onceki = None
        self.sonraki = None
```

### 📌 Dairesel Bağlı Liste (Circular Linked List)

Son düğümün, **ilk düğüme bağlı olduğu** özel bir bağlı listedir. Oyun motorlarında ve döngüsel işlemlerde kullanılır!

---

### 🎯 Sonuç

- **Listeler** çok yönlü ve kullanışlıdır.
- **Bağlı listeler**, büyük verilerle çalışırken daha esnektir.
- **Algoritma analizi** sayesinde yazdığımız kodun ne kadar verimli olduğunu anlayabiliriz.
- **Big O Notasyonu** ile kodlarımızın hızını ölçebiliriz!

---

## 3.3 Yığınlar (Stacks)

#### 📌 Yığın (Stack) Nedir?
Yığın (Stack), **son giren ilk çıkar (LIFO - Last In First Out)** prensibiyle çalışan bir veri yapısıdır. Yani, bir yığını bir kutu gibi düşünebiliriz: **En son eklenen eleman, ilk çıkar.**  
Örneğin, üst üste kitap koyduğumuzu düşünelim. En son koyduğumuz kitabı, önce kaldırırız.

#### 📌 Yığın Kullanım Alanları
- **Fonksiyon Çağrı Yığını**: Python veya diğer dillerde fonksiyon çağrıları yığın mantığıyla çalışır.
- **Geri Alma (Undo) Mekanizması**: Metin editörleri, Photoshop gibi programlar yapılan değişiklikleri geri almak için yığın kullanır.
- **İleri-Geri Butonları**: Web tarayıcılarında ileri-geri gezinme işlemleri bir yığınla yönetilir.
- **İfade Çözümleme**: Parantez dengeleme, derleyicilerde derleme işlemleri.

#### 📌 Yığın Operasyonları

1. **Push (Ekleme)**: Yığına yeni bir eleman ekler.
2. **Pop (Çıkarma)**: Yığının en üstündeki elemanı çıkarır.
3. **Peek (Üst Elemanı Görüntüleme)**: Yığının en üstündeki elemanı getirir ama silmez.
4. **isEmpty (Boş mu?)**: Yığının boş olup olmadığını kontrol eder.

#### 🔹 Python ile Yığın Uygulaması
```python
class Yigin:
    def __init__(self):
        self.elemanlar = []  # Yığını temsil eden liste

    def push(self, veri):
        """Yığına eleman ekler"""
        self.elemanlar.append(veri)

    def pop(self):
        """Yığının en üstündeki elemanı çıkarır"""
        if not self.isEmpty():
            return self.elemanlar.pop()
        return "Yığın boş!"

    def peek(self):
        """Yığının en üstündeki elemanı görüntüler"""
        if not self.isEmpty():
            return self.elemanlar[-1]
        return "Yığın boş!"

    def isEmpty(self):
        """Yığının boş olup olmadığını kontrol eder"""
        return len(self.elemanlar) == 0

# Yığın kullanımı
yigin = Yigin()
yigin.push(5)
yigin.push(10)
yigin.push(15)

print(yigin.peek())  # Çıktı: 15
print(yigin.pop())   # Çıktı: 15
print(yigin.pop())   # Çıktı: 10
print(yigin.isEmpty())  # Çıktı: False
```
---

## 3.4 Kuyruklar (Queues)

#### 📌 Kuyruk (Queue) Nedir?
Kuyruklar, **ilk giren ilk çıkar (FIFO - First In First Out)** prensibiyle çalışan veri yapılarıdır.  
Gerçek hayatta bir ATM kuyruğu gibi düşünebiliriz: **İlk gelen müşteri ilk hizmet alır.**

#### 📌 Kuyruk Kullanım Alanları
- **İşlem Sıralama**: Yazıcı sırası gibi işlemlerin sırayla yapılmasını sağlar.
- **Veri Akışı Yönetimi**: Ağ paketlerinin iletilmesi.
- **CPU Zaman Paylaşımı**: İşletim sistemlerinde süreçlerin sırayla çalıştırılması.

#### 📌 Kuyruk Operasyonları

1. **Enqueue (Ekleme)**: Kuyruğa eleman ekler.
2. **Dequeue (Çıkarma)**: Kuyruğun başındaki elemanı çıkarır.
3. **isEmpty (Boş mu?)**: Kuyruğun boş olup olmadığını kontrol eder.
4. **Front (İlk Eleman)**: Kuyruğun başındaki elemanı görüntüler.

#### 🔹 Python ile Kuyruk Uygulaması
```python
from collections import deque

class Kuyruk:
    def __init__(self):
        self.elemanlar = deque()  # Kuyruk için deque kullanıyoruz

    def enqueue(self, veri):
        """Kuyruğa eleman ekler"""
        self.elemanlar.append(veri)

    def dequeue(self):
        """Kuyruğun başındaki elemanı çıkarır"""
        if not self.isEmpty():
            return self.elemanlar.popleft()
        return "Kuyruk boş!"

    def front(self):
        """Kuyruğun başındaki elemanı görüntüler"""
        if not self.isEmpty():
            return self.elemanlar[0]
        return "Kuyruk boş!"

    def isEmpty(self):
        """Kuyruğun boş olup olmadığını kontrol eder"""
        return len(self.elemanlar) == 0

# Kuyruk kullanımı
kuyruk = Kuyruk()
kuyruk.enqueue(1)
kuyruk.enqueue(2)
kuyruk.enqueue(3)

print(kuyruk.front())  # Çıktı: 1
print(kuyruk.dequeue())  # Çıktı: 1
print(kuyruk.dequeue())  # Çıktı: 2
print(kuyruk.isEmpty())  # Çıktı: False
```
---

## 3.5 Sıralama Algoritmaları
**Sıralama algoritmaları, verileri belirli bir düzene sokmak için kullanılır.** En yaygın sıralama algoritmalarına bakalım:

#### 📌 1. Seçmeli Sıralama (Selection Sort)
Her turda en küçük eleman bulunur ve başa yerleştirilir.
```python
def selection_sort(liste):
    n = len(liste)
    for i in range(n):
        min_index = i
        for j in range(i + 1, n):
            if liste[j] < liste[min_index]:
                min_index = j
        liste[i], liste[min_index] = liste[min_index], liste[i]

# Örnek
veri = [29, 10, 14, 37, 13]
selection_sort(veri)
print(veri)  # Çıktı: [10, 13, 14, 29, 37]
```

#### 📌 2. Kabarcık Sıralama (Bubble Sort)
Yan yana olan elemanları karşılaştırarak sıralar.
```python
def bubble_sort(liste):
    n = len(liste)
    for i in range(n):
        for j in range(n - i - 1):
            if liste[j] > liste[j + 1]:
                liste[j], liste[j + 1] = liste[j + 1], liste[j]

# Örnek
veri = [64, 25, 12, 22, 11]
bubble_sort(veri)
print(veri)  # Çıktı: [11, 12, 22, 25, 64]
```

---

## 3.6 Arama Algoritmaları
Arama algoritmaları, veri içinden istenen bir elemanı bulmak için kullanılır.

#### 📌 1. Doğrusal Arama (Linear Search)
Her eleman tek tek kontrol edilir.
```python
def linear_search(liste, hedef):
    for i in range(len(liste)):
        if liste[i] == hedef:
            return i
    return -1

veri = [3, 8, 4, 2, 9]
print(linear_search(veri, 4))  # Çıktı: 2
```

#### 📌 2. İkili Arama (Binary Search)
**Sadece sıralı listelerde** çalışır ve ortadan bölerek arama yapar.
```python
def binary_search(liste, hedef):
    bas, son = 0, len(liste) - 1
    while bas <= son:
        orta = (bas + son) // 2
        if liste[orta] == hedef:
            return orta
        elif liste[orta] < hedef:
            bas = orta + 1
        else:
            son = orta - 1
    return -1

veri = [2, 4, 7, 10, 15]
print(binary_search(veri, 10))  # Çıktı: 3
```
---

## 3.7 Ağaçlar (Trees) 🌳  

### 📌 Ağaç (Tree) Nedir?
Ağaçlar, veri yapıları arasında bir **hiyerarşi** kurarak bilgiyi düzenlemenin harika bir yolunu sunar. Düşünün ki, ağaçlar birer aile soy ağacı gibidir; bir kök (root) ve onun altında bulunan birçok çocuğu (child) vardır.  
Her ağaç, aşağıdaki temel bileşenlerden oluşur:
- **Kök (Root)**: Bu, ağacın en tepe noktasıdır; ağaç buradan başlar.
- **Düğüm (Node)**: İçinde veri tutan ve diğer düğümlerle bağlantılı elemandır. Düğümün ne kadar özelliği olursa olsun, tüm düğümler bir araya gelerek ağacı oluşturur.
- **Alt Ağaç (Subtree)**: Bir düğüm ve onun altındaki düğümlerden oluşan yapı; yani, ağaç içinde ağaç! 
- **Yaprak (Leaf)**: Alt düğümü olmayan düğümdür. Yapraklar, ağacın dışındaki veri noktalarıdır.
- **Derinlik (Depth)**: Kökten bir düğüme olan mesafeyi ifade eder. Yani, "kimin kiminle daha derin ilişkisi var?" sorusu için bir ölçüm!
- **Yükseklik (Height)**: Kökten en derindeki yaprağa olan mesafedir. Kısacası, ağacın "ne kadar uzun" olduğunu gösterir.

En yaygın ağaç türü, **İkili Ağaçlar (Binary Trees)**'dır; bu ağaçlar, sağda ve solda en fazla iki çocuğa sahiptir. Haydi biraz daha derinleşelim!  

---

### 🌲 **İkili Ağaçlar (Binary Trees)**
İkili ağaçlar, her düğümün en fazla iki alt düğümü olabileceği bir yapı sunar. Burada soldaki alt düğüm, sağdakinden **küçük** ya da **önce gelir**. Yani solda bir "şirin" varsa sağda bir "büyükanne" bulabilirsiniz. Kod örneğimiz şöyle: 

```python
class Node:
    def __init__(self, veri):
        self.veri = veri  # Düğümde saklanan veri
        self.sol = None  # Sol alt düğüm
        self.sag = None  # Sağ alt düğüm

class IkiliAgac:
    def __init__(self):
        self.kok = None  # Başlangıçta ağaç boş

    def ekle(self, veri):
        """Ağaca yeni düğüm ekler"""
        if self.kok is None:
            self.kok = Node(veri)  # İlk düğüm kök olur
        else:
            self._ekle(self.kok, veri)

    def _ekle(self, mevcut, veri):
        """Yardımcı fonksiyon: Rekürsif ekleme yapar"""
        if veri < mevcut.veri:
            if mevcut.sol is None:
                mevcut.sol = Node(veri)
            else:
                self._ekle(mevcut.sol, veri)
        else:
            if mevcut.sag is None:
                mevcut.sag = Node(veri)
            else:
                self._ekle(mevcut.sag, veri)

    def inorder(self, mevcut=None):
        """Ağacı sıralı şekilde yazdırır (küçükten büyüğe)"""
        if mevcut is None:
            mevcut = self.kok
        if mevcut:
            self.inorder(mevcut.sol)
            print(mevcut.veri, end=" ")
            self.inorder(mevcut.sag)

# Ağaç kullanımı
agac = IkiliAgac()
agac.ekle(10)
agac.ekle(5)
agac.ekle(15)
agac.ekle(2)
agac.ekle(7)

agac.inorder()  # Çıktı: 2 5 7 10 15
```

Burada gördüğünüz gibi, her yeni veri ağaca ekleniyor ve ağaç, verileri düzenli bir şekilde tutmak için kendine bir yol buluyor! 

---

### 🔍 **İkili Arama Ağaçları (BST - Binary Search Trees)**
BST, ikili ağaçların süper düzenli bir türüdür! Bu yapıda:
- **Sol çocuk düğümler küçüktür.**
- **Sağ çocuk düğümler büyüktür.**
Yani, sanki veriler burada küçükten büyüğe sıralanmış gibi!

Bu özel yapı, arama, ekleme ve silme işlemlerini O(log n) zaman karmaşıklığı ile yapmanıza olanak tanır. Yani, 1 milyon elemanın içinde arama yaparken sadece en fazla 20 adım atmanız gerekir! Gerçekten etkileyici, değil mi?

---

### 🏗️ **Dengeli Ağaçlar**
Dengeli ağaçlar, düğümlerin eşit dağılımını sağlamak için tasarlanmış özel ağaçlardır. Bu ağaçlar, işlemlerin daha hızlı gerçekleşmesine olanak tanır. İki popüler türü vardır:
1. **AVL Ağaçları**: Her düğümün sol ve sağ alt ağaçlarının yüksekliği en fazla 1 fark eder. Yani, ağaçlarımız düzgün bir şekilde "dengelenmiş" durumda!
2. **Kırmızı-Siyah Ağaçlar**: Özel renklendirme kurallarıyla dengede kalan ağaçlardır. Böylece, hangi yapının daha dikkat çekici olduğuna karar vermek sizin elinizde!

Dengeli ağaçlar, veri tabanları ve dosya sistemlerinde yaygın bir şekilde kullanılır; her şeyin düzenli ve ulaşılabilir olması için!  

---

### 🌳 **N-ary Ağaçlar**  
İkili ağaçlardan farklı olarak, **her düğümün 2’den fazla çocuğu** olabilir. Düşünün ki, her düğüm bir baba, anne ve birkaç çocuğa sahip! Bu tür ağaçlar genellikle:
- **Dosya sistemleri** (Her klasör birçok alt klasör içerebilir)
- **Oyun ağaçları** (Satranç, Go gibi oyunlarda hamle hesaplamak için kullanılır)

Yani, her düğümün birçok yolu olduğu ve karmaşanın oldukça fazla olabileceği bir ortam yaratıyor.  

---

### 🔤 **Trie (Prefix Tree)**
Trie, kelime veya ön ekleri saklamak için kullanılan özel bir ağaç türüdür. Düşünsenize, bir sözlükte **"cat", "car", "care"** kelimeleri şöyle saklanır:

```
    c
   / \
  a   r
 /     \
t       e
 \       \
  r       e
```

Burada, kelimelerin ortak kök noktalarından yola çıkarak saklandığını görebiliriz. Trie, **arama motorlarında otomatik tamamlama** gibi işlemlerde kullanılır. Yani, bir kelime aradığınızda, çok daha hızlı sonuç almanızı sağlar!  

---

## 3.8 Graf Yapıları (Graphs) 🔗

### 📌 **Graf Nedir?**
Graf, **düğümler (nodes) ve kenarlardan (edges) oluşan** bir veri yapısıdır. Bu yapılar, gerçek hayatta sosyal ağlar, yol haritaları gibi birçok alanda karşımıza çıkar. Örneğin, **Facebook arkadaş listesi** veya **Google Haritalar** gibi durumlarda bu yapılar sıkça kullanılır! 

---

### 📍 **Graf Temsilleri**
Grafı bilgisayarda saklamanın iki temel yöntemi vardır:
1. **Komşuluk Matrisi (Adjacency Matrix)**: NxN boyutunda bir matris kullanarak düğümler arasındaki bağlantıları gösterir. Düşünün ki, bir oyun alanında her oyuncunun birbirine olan bağlantısını gösteren bir tablo!
2. **Komşuluk Listesi (Adjacency List)**: Her düğüm için bağlantılar bir listede saklanır. Böylece, hangi düğümün hangi düğümlere bağlı olduğunu kolayca görebilirsiniz.

Bu temsiller, graf yapısının nasıl çalıştığını anlamanızı sağlar.  

---

### 🔎 **Graf Algoritmaları**
Graf yapıları üzerinde çalışırken kullanılan birkaç önemli algoritma vardır:
- **DFS (Derinlik Öncelikli Arama)**: Önce derine git, sonra geri dön! Bir ağaçta gezinmenin bir yolu. Eğer çiçekleri çok seviyorsanız, DFS tam size göre! 🔍  
- **BFS (Genişlik Öncelikli Arama)**: Önce genişle, sonra derine in! Her seferinde tüm komşuları ziyaret ederek ilerliyor; kısaca, toplu gezme yöntemi!

---

### 🚀 **En Kısa Yol Algoritmaları**
Graf yapıları içinde en kısa yolu bulmak için kullanılan iki popüler algoritma vardır:
- **Dijkstra**: Ağırlıklı grafikte en kısa yolu bulur. Düşünsenize, yolculuk yaparken en kısa rotayı bulmaya çalışıyorsunuz!
- **Bellman-Ford**: Negatif ağırlıkları da destekler. Yani, bazı yolların olumsuz etkileri olduğunu göz önünde bulundurur.

Bunlar, yolları analiz etmek için harika araçlardır!  

---

### 🏗 **En Az Maliyetli Ağaç Algoritmaları**
Bir ağaç oluştururken en az maliyetle bunu başarmak için kullanılan algoritmalar:
- **Kruskal Algoritması**: En küçük kenarları ekleyerek bir ağaç oluşturur. Yani, maliyetleri azaltmak için en uygun yolları bulmaya çalışıyor!
- **Prim Algoritması**: Bir düğümden başlayarak büyüyen bir ağaç oluşturur. Kendi kendine büyüyen bir ağaç hayal edin; başlangıç noktası çok önemli!

---

## 3.9 Hashing ve Hash Tablolar 🗃️

### 📌 **Hashing Nedir?**
Hashing, **verileri belirli bir hash fonksiyonu ile** sayılara dönüştürme işlemidir. Düşünün ki, "Merhaba" kelimesi `129847` gibi bir sayıya dönüşebilir. Bu sayede veriler daha hızlı ve etkili bir şekilde saklanabilir!

---

### 📍 **Çarpışma Çözme Teknikleri**
Bazen, **iki farklı veri aynı hash değerini alabilir**. Bu çarpışmayı önlemek için birkaç yöntem kullanılır:
1. **Ayrık Zincirleme (Separate Chaining)**: Aynı hash’e düşen elemanları bir liste içinde saklarız. Yani, çarpışan verileri yan yana getiriyoruz!
2. **Açık Adresleme (Open Addressing)**: Boş bir hücre bulunana kadar başka yerlere bakarız. Yani, "burada değil, başka bir yerde!" yöntemi.

Bu teknikler, hashing sistemlerini daha etkili hale getirir!  

---

### 🎯 **Hash Tabloların Kullanım Alanları**
Hash tablolar, birçok farklı alanda kullanılır:
- **Veri tabanları** (Anahtar-değer saklama) - Verilerinizi düzenli bir şekilde saklayarak hızlı erişim sağlar.
- **Parola saklama** (MD5, SHA-256 gibi hashing algoritmaları) - Kullanıcı parolalarını güvende tutmanın harika bir yoludur!
- **İndeksleme** (Arama motorları) - İnternetin karmaşık yapısında verileri hızlı bir şekilde bulmanın anahtarıdır!

---

## 3.10 Dinamik Programlama ve Böl ve Fethet (Divide and Conquer) 🔍

### 📌 Dinamik Programlama Temelleri
Dinamik programlama, karmaşık problemleri daha küçük parçalara bölüp, bu parçaların çözümlerini kullanarak tüm problemin çözümünü bulma yöntemidir. Yani, sanki dev bir bulmacayı çözüp, ardından bu bulmacanın her parçasını birleştiriyoruz!

#### 🔑 Ortak Alt Problemler
Dinamik programlamanın en önemli özelliklerinden biri, bazı alt problemlerin tekrar tekrar çözülmesidir. Düşünün ki, bir film izlerken aynı sahneyi defalarca izlemek zorunda kalıyorsunuz. Bunun yerine, bu sahneyi bir kez izleyip sonra kaydetseydiniz, zaman kazanırdınız!

#### 📊 Bellek Tabloları (Memoization) ve Tablo Tablosu (Tabulation)
- **Bellek Tabloları (Memoization)**: Rekürsif çözümlerde daha önce hesaplanmış sonuçları saklayarak tekrar hesaplamaktan kaçınmamıza yardımcı olur. Yani, bir konuda çalıştıktan sonra, o bilgiyi bir köşeye not alırız!
- **Tablo Tablosu (Tabulation)**: Alt problemleri sistematik bir şekilde hesaplayarak tablo şeklinde saklamak anlamına gelir. Burada, tüm sonuçları bir tabloya yerleştiriyoruz; böylece, her şeyi daha düzenli bir şekilde görebiliyoruz!

Dinamik programlama, Fibonacci dizisi, en uzun ortak alt dizi gibi pek çok klasik problemde kullanılır.

---

### 📌 Böl ve Fethet Stratejisi
Böl ve fethet, bir problemi daha küçük parçalara ayırarak her bir parçayı bağımsız bir şekilde çözme stratejisidir. Düşünsenize, büyük bir pizzayı dilim dilim kesmek gibi! 

#### 🔎 Karşılaştırmalı Analiz
Böl ve fethet yöntemleri, genellikle hızlı sıralama (quicksort) ve birleştirme sıralaması (mergesort) gibi algoritmalarda kullanılır. Bu yöntemlerde, her parça kendi içinde sıralanır ve daha sonra birleştirilerek sonuç elde edilir.  
Böl ve fethet, dinamik programlamadan farklı olarak, her alt problemi ayrı ayrı çözüp sonuçları birleştirir, yani hiç kimse birbirine karışmaz! 

---

## 3.11 Algoritma Tasarım Teknikleri 🎯

### 📌 Greedy Algoritmalar
Greedy algoritmalar, her adımda en iyi veya en avantajlı görünen seçeneği tercih eder. Bu yöntemle, kısa vadeli çözümler üretilirken, genel çözüm daha iyi hale getirilmeye çalışılır. Düşünün ki, bir dağa tırmanırken her zaman en dik yoldan gitmeye çalışıyorsunuz! 

#### ⚖️ Örnek Problemler
- **Knapsack Problemi**: Sınırlı bir kapasiteye sahip bir çantaya en yüksek değerdeki nesneleri yerleştirme problemi. Burada, her nesnenin ağırlığına ve değerine göre seçim yaparak en iyi kombinasyonu bulmaya çalışırız.
- **Coin Change Problemi**: Belirli bir miktarı vermek için en az sayıda bozuk para kullanma problemi. Yani, cebinizdeki paraları en verimli şekilde kullanarak hedefe ulaşmaya çalışıyorsunuz.

---

### 📌 Backtracking
Backtracking, olası tüm çözümleri denemek ve yanlış olanları geri çekmek anlamına gelir. Düşünün ki, bir labirentte ilerliyor ve yanlış yola saparsanız, geri dönüp doğru yolu bulmaya çalışıyorsunuz!

#### 🧩 Örnek Problemler
- **N-Queens Problemi**: N adet satranç tahtasına N adet kraliçe yerleştirme problemi. Amaç, kraliçelerin birbirini tehdit etmeden tahtaya yerleştirilmesini sağlamaktır.
- **Sudoku**: Boş kutulara doğru sayıları yerleştirerek tüm tabloyu doldurma problemi. Yani, bir bulmacayı çözmeye çalışıyorsunuz ve adım adım ilerliyorsunuz!

---

## 3.12 İleri Veri Yapıları

### 📌 B-ağacı ve B+-ağacı
- **B-ağacı**: Denge sağlamak için tasarlanmış bir ağaç yapısıdır. Her düğümde belirli sayıda anahtar ve çocuk düğüm bulundurur, bu da verilerin hızlı bir şekilde aranmasına olanak tanır. Veritabanlarında sıkça kullanılır.
- **B+-ağacı**: B-ağacının bir çeşidi olup, yalnızca yaprak düğümlerde veri saklar. Yani, tüm anahtarlar yaprak düğümlerde bulunur, bu da arama işlemlerini hızlandırır.

### 📌 Fibonacci Yığınları (Fibonacci Heaps)
Fibonacci yığınları, özellikle minimum değere sahip öğeleri hızlı bir şekilde bulma ve birleştirme işlemleri için kullanılan bir yığın yapısıdır. Bu yapılar, karmaşık algoritmalarda, örneğin Dijkstra ve Prim algoritmalarında performansı artırmak için kullanılır.

### 📌 Union-Find Veri Yapıları
Union-Find, bağlantılı bileşenleri izlemek için kullanılan bir veri yapısıdır. Özellikle graf teorisi ve küme birleştirme problemlerinde kullanılır. Her iki önemli işlevi vardır:
- **Union**: İki kümenin birleştirilmesi.
- **Find**: Bir öğenin hangi kümenin içinde olduğunu bulma.

### 📌 Segment Ağaçları (Segment Trees)
Segment ağaçları, bir dizi üzerinde aralık sorguları ve güncellemeleri gerçekleştirmek için kullanılan bir veri yapısıdır. Örneğin, belirli bir aralıktaki toplam veya maksimum değeri hızlı bir şekilde bulmak için kullanılır. Kısacası, dizi üzerinde çalışırken hızlı sonuçlar almanızı sağlar!

### 📌 Suffix Ağaçları ve Suffix Dizileri
Suffix ağaçları, bir dizi veya metin içinde alt dizeleri hızlı bir şekilde aramak için kullanılır. Metin işleme uygulamalarında oldukça faydalıdır. Suffix dizileri ise, metnin tüm suffixlerini bir arada tutan bir yapıdır. Örneğin, bir metin içindeki tüm kelimeleri hızlı bir şekilde bulmak için harika bir yöntemdir!