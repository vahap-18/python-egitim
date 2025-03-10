## 14. Python ile Web Geliştirme 🌟

### 14.1 Web Geliştirmeye Giriş 🌐

Web geliştirme, internet üzerinde çalışan sitelerin veya uygulamaların tasarlanması, oluşturulması ve sürdürülmesi sürecini kapsar. Bu süreçte, kullanıcıların gördüğü ön yüz (frontend) ve arka planda çalışan iş mantığı (backend) birlikte çalışır. Web geliştirme, modern yazılım geliştirme dünyasının en önemli alanlarından biridir ve birçok farklı teknolojiyi içerir. Bu bölümde, web geliştirmenin temel kavramlarını, mimarisini ve iletişim protokollerini inceleyeceğiz.


#### **Web Geliştirmenin Temel Kavramları**
Web geliştirme sürecinde iki temel katman bulunur: **frontend** ve **backend**. Bu katmanlar, birbirini tamamlayan parçalardır ve birlikte çalışarak bir web sitesinin veya uygulamasının işlevselliğini sağlar.

1. **Frontend (Ön Yüz)**:
   Frontend, kullanıcıların doğrudan etkileşime girdiği kısımdır. Örneğin, bir e-ticaret sitesinde gördüğünüz butonlar, resimler, yazılar gibi öğeler frontend'in sorumluluğundadır. HTML, CSS ve JavaScript gibi teknolojilerle oluşturulan bu bölüm, kullanıcının gördüğü her şeyi içerir. Frontend, kullanıcı deneyimini (UX/UI) şekillendiren ana unsurdur.

2. **Backend (Arka Yüz)**:
   Backend, kullanıcıların görmesine gerek olmayan ancak siteyi işlevsel kılan kodları içerir. Örneğin, bir blog yazısı yazdığınızda bu yazı bir veritabanında saklanır ve gerektiğinde kullanıcıya sunulur. Backend genellikle veritabanı yönetimi, kullanıcı kimlik doğrulaması ve sunucu işlemleri gibi görevleri üstlenir. Backend, bir web uygulamasının "beyni" olarak düşünülebilir.

Bu iki katman arasındaki etkileşim, web sitelerinin çalışmasını mümkün kılar. Örneğin, bir kullanıcı bir form doldurduğunda, frontend bu veriyi backend'e gönderir. Backend ise bu veriyi işler, veritabanına kaydeder ve gerekli yanıtı frontend'e geri gönderir.


#### **İstemci-Sunucu Mimarisi**
Web uygulamaları, **istemci-sunucu mimarisine** dayanır. Bu mimari, kullanıcıların tarayıcıları (istemci) ile web sunucuları arasında iletişim kurmasını sağlar.

- **İstemci (Client)**:
  İstemci, kullanıcıların kullandığı tarayıcılar (örneğin Chrome, Firefox) veya mobil uygulamalardır. İstemci, sunucudan aldığı verileri işleyerek kullanıcıya görsel olarak sunar.

- **Sunucu (Server)**:
  Sunucu, internet sitelerinin dosyalarını ve verilerini depolayan bilgisayar sistemleridir. Bir kullanıcı bir siteyi ziyaret ettiğinde, sunucu istenen içeriği tarayıcıya gönderir.

Örneğin, bir blog sitesinde yazdığınız bir yorum, sunucuda saklanır. Başka bir kullanıcı o sayfayı açtığında, sunucu bu yorumu ona gönderir. Bu iletişim, web sitelerinin çalışmasını mümkün kılar.


#### **HTTP/HTTPS Protokolleri**
Web tarayıcıları ile sunucular arasında iletişim kurmak için kullanılan temel protokol **HTTP (HyperText Transfer Protocol)**'dir. HTTP, tarayıcının sunucuya "bu sayfayı bana getir" talebini iletmek için kullandığı bir iletişim dilidir. Sunucu da bu talebi alır ve sayfanın içeriğini tarayıcıya gönderir.

Ancak HTTP'nin bir dezavantajı vardır: güvenli değildir. Eğer bir saldırgan bu iletişimi izlerse, sizin gönderdiğiniz veriler (örneğin şifreler veya kişisel bilgiler) tehlikeye girebilir. İşte bu yüzden **HTTPS (HTTP Secure)** geliştirilmiştir. HTTPS, iletişimde şifreleme kullanarak verilerinizi korur.

- **HTTP**: Temel iletişim protokolüdür, ancak güvenli değildir.
- **HTTPS**: Şifreleme ile güçlendirilmiş, güvenli iletişim sağlar.

Günümüzde neredeyse tüm web siteleri HTTPS kullanmaktadır. Özellikle e-ticaret siteleri, bankacılık uygulamaları ve kişisel bilgilerin girildiği platformlar için HTTPS kullanımı zorunludur.


#### **Web Teknolojilerinin Evrimi**
Web teknolojileri, son 30 yılda inanılmaz bir evrim geçirmiştir. İlk olarak, statik HTML sayfalarından oluşan basit web siteleri vardı. Ancak zamanla, daha dinamik ve etkileşimli siteler oluşturmak için CSS, JavaScript ve backend teknolojileri geliştirilmiştir.

- **HTML**: Web sayfalarının yapı taşlarını oluşturur.
- **CSS**: Sayfaların görünümünü ve stilini belirler.
- **JavaScript**: Kullanıcıların sayfayla etkileşimini sağlar.
- **Backend Teknolojileri**: Veritabanı yönetimi, kullanıcı kimlik doğrulaması ve diğer arka plan işlemleri için kullanılır.

Günümüzde, web geliştirme için yüzlerce araç ve çerçeve (framework) mevcuttur. Örneğin, React ve Angular gibi frontend çerçeveleri, Django ve Flask gibi backend çerçeveleri, geliştiricilere büyük kolaylıklar sağlar.


#### **Gerçek Dünya Örnekleri**
Web geliştirme kavramlarını daha iyi anlamak için gerçek dünya örneklerine bakabiliriz. Örneğin:

1. **E-Ticaret Sitesi**:
   Bir e-ticaret sitesinde, frontend ürün listelerini, sepeti ve ödeme formlarını içerir. Backend ise ürün stoklarını, kullanıcı bilgilerini ve ödeme işlemlerini yönetir.

2. **Sosyal Medya Platformu**:
   Sosyal medya platformlarında, frontend gönderileri, yorumları ve beğenileri gösterir. Backend ise bu verileri depolar, kullanıcıları doğrular ve güvenlik sağlar.


---


### 14.2 HTML, CSS ve JavaScript Temelleri 🛠️

Web geliştirme dünyasında, **HTML**, **CSS** ve **JavaScript**, frontend'in temel taşlarını oluşturur. Bu üç teknoloji, birlikte çalışarak kullanıcıların gördüğü web sayfalarını oluşturur ve etkileşimli hale getirir. Bu bölümde, bu teknolojilerin temel kavramlarını, işlevlerini ve nasıl kullanıldıklarını inceleyeceğiz.


#### **HTML (HyperText Markup Language)**
HTML (HyperText Markup Language), web sayfalarının yapı taşlarını oluşturan bir işaretleme dilidir. HTML, bir web sayfasının hangi öğelerden oluşacağını (örneğin başlıklar, paragraflar, resimler) ve bu öğelerin nasıl düzenleneceğini tanımlar.

- **HTML'nin Temel Yapısı**:
  Bir HTML dosyası, belirli bir yapıya sahiptir. İşte en basit HTML dokümanı:

  ```html
  <!DOCTYPE html>
  <html>
  <head>
      <title>Sayfa Başlığı</title>
  </head>
  <body>
      <h1>Başlık</h1>
      <p>Bu bir paragraftır.</p>
  </body>
  </html>
  ```

  - `<!DOCTYPE html>`: HTML5 belgesi olduğunu belirtir.
  - `<html>`: HTML dokümanının başlangıcını ve bitişini tanımlar.
  - `<head>`: Sayfanın meta bilgilerini (başlık, karakter seti vb.) içerir.
  - `<body>`: Kullanıcıların gördüğü içeriği içerir.

- **HTML Etiketleri ve Elementleri**:
  HTML, içerikleri tanımlamak için etiketler (tags) kullanır. Her etiket, belirli bir amaca hizmet eder. İşte en sık kullanılan etiketler ve açıklamaları:

  1. **Başlık Etiketleri (`<h1>` - `<h6>`)**:
     ```html
     <h1>En Büyük Başlık</h1>
     <h2>Alt Başlık</h2>
     ```
     Başlık etiketleri, metnin önem derecesini belirtir. Arama motorları da bu etiketleri SEO açısından değerlendirir.

  2. **Paragraf Etiketi (`<p>`)**:
     ```html
     <p>Bu bir paragraftır.</p>
     ```

  3. **Bağlantı Etiketi (`<a>`)**:
     ```html
     <a href="https://www.example.com">Buraya tıklayın!</a>
     ```
     Bu kod, "Buraya tıklayın!" yazısına tıklandığında `example.com` adresine yönlendirme yapar.

  4. **Resim Etiketi (`<img>`)**:
     ```html
     <img src="resim.jpg" alt="Açıklama Metni">
     ```
     Resim eklemek için kullanılır. `alt` özelliği, resim yüklenmezse veya görsel görmeyen kullanıcılar için açıklama sağlar.

  5. **Liste Etiketleri (`<ul>`, `<ol>`, `<li>`)**:
     ```html
     <ul>
         <li>Öğe 1</li>
         <li>Öğe 2</li>
     </ul>
     <ol>
         <li>Öğe A</li>
         <li>Öğe B</li>
     </ol>
     ```


#### **CSS (Cascading Style Sheets)**
CSS (Cascading Style Sheets), web sitelerine stil vermek için kullanılır. HTML'deki metinleri, resimleri ve diğer öğeleri nasıl görüneceğini belirleriz. CSS olmadan, bir web sitesi sadece düz metinlerden oluşan bir yapıda kalır.

- **CSS'nin Temel Yapısı**:
  CSS, HTML öğelerine stil uygulamak için seçiciler (selectors) kullanır. İşte temel bir CSS örneği:

  ```css
  body {
      background-color: lightblue;
  }
  h1 {
      color: navy;
      text-align: center;
  }
  p {
      font-family: Arial, sans-serif;
  }
  ```

  Bu kod, sayfanın arka planını açık mavi yapar, başlıkları mavi ve ortalanmış olarak ayarlar ve paragrafları Arial yazı tipinde gösterir.

- **Seçiciler ve Özellikler**:
  CSS'de stil tanımlamak için farklı türde seçiciler kullanılır:
  1. **Element Seçici**:
     ```css
     h1 {
         color: red;
     }
     ```
  2. **ID Seçici**:
     ```css
     #header {
         background-color: blue;
     }
     ```
  3. **Class Seçici**:
     ```css
     .button {
         padding: 10px;
     }
     ```

- **Box Model ve Yerleşim (Layout)**:
  Her HTML öğesi aslında bir "kutu" olarak düşünülebilir. Bu kutunun içinde **içerik**, etrafında ise **kenar boşlukları (margin)**, **dolgu (padding)** ve **kenarlık (border)** bulunur. Buna **Box Model** denir.

  ```css
  div {
      width: 200px;
      padding: 10px;
      border: 2px solid black;
      margin: 20px;
  }
  ```

  Yerleşim (layout) ise, öğelerin sayfada nasıl konumlandırılacağını belirler. Modern CSS araçları olan **Flexbox** ve **Grid**, karmaşık düzenler oluşturmak için idealdir.


#### **JavaScript**
JavaScript, web sitelerine interaktivite katmak için kullanılan bir programlama dilidir. HTML ve CSS ile oluşturduğunuz statik bir siteyi, JavaScript ile dinamik hale getirebilirsiniz. Örneğin, bir butona tıklandığında bir mesaj göstermek veya bir formu doğrulamak istiyorsanız, JavaScript'i kullanırsınız.

- **JavaScript'in Temel Kavramları**:
  JavaScript'te verileri saklamak için değişkenler kullanılır. Değişkenler, `let`, `const` veya `var` anahtar kelimeleriyle tanımlanır.

  ```javascript
  let age = 25;
  const name = "Ahmet";
  var isActive = true;
  ```

- **DOM Manipülasyonu**:
  JavaScript ile HTML dokümanını değiştirebilirsiniz. Buna **DOM Manipülasyonu** denir:

  ```javascript
  document.getElementById("header").innerHTML = "Yeni Başlık";
  ```

- **Event Handling**:
  Kullanıcı etkileşimlerini yakalamak için event listener'lar kullanılır:

  ```javascript
  button.addEventListener("click", function() {
      alert("Butona tıklandı!");
  });
  ```


#### **Gerçek Dünya Örnekleri**
Bu teknolojileri bir araya getirerek gerçek dünya projeleri geliştirebiliriz. Örneğin:

1. **Kişisel Blog Sitesi**:
   - HTML: Yazılar, başlıklar ve resimler için kullanılır.
   - CSS: Yazı tipleri, renkler ve düzen için kullanılır.
   - JavaScript: Yorum gönderme veya beğenme butonları için kullanılır.

2. **E-Ticaret Sitesi**:
   - HTML: Ürün listeleri ve detay sayfaları için kullanılır.
   - CSS: Ürün kartlarının düzeni ve stil için kullanılır.
   - JavaScript: Sepete ekleme veya ödeme işlemleri için kullanılır.

---


### 14.3 Python ile Backend Geliştirme 🚀

Backend geliştirme, web sitelerinin veya uygulamaların arka planda çalışan kısmını ifade eder. Bu bölümde, Python'un backend geliştirme dünyasındaki rolünü, avantajlarını ve temel kavramlarını inceleyeceğiz. Ayrıca, Python ile basit bir sunucu oluşturmayı ve RESTful API'ler geliştirmeyi öğreneceğiz.


#### **Python'un Web Geliştirme İçin Avantajları**
Python, backend geliştirme için son derece popüler bir dildir. İşte Python'un bu alandaki en büyük avantajları:

1. **Okunabilirlik ve Kolaylık**:
   Python, basit ve anlaşılır bir sözdizimine sahiptir. Bu, kod yazmayı ve anlamayı kolaylaştırır. Özellikle yeni başlayanlar için idealdir.

2. **Zengin Kütüphane Desteği**:
   Python, web geliştirme için birçok hazır kütüphane ve framework sunar. Örneğin, Flask ve Django gibi güçlü araçlar, hızlı bir şekilde web uygulamaları geliştirmenizi sağlar.

3. **Topluluk Desteği**:
   Python, dünya çapında geniş bir topluluğa sahiptir. Bu, sorun yaşarken yardım alabileceğiniz anlamına gelir. Ayrıca, birçok açık kaynak proje Python ile yazılmıştır.


#### **Temel Backend Kavramları**
Backend geliştirme, kullanıcıların görmesine gerek olmayan ancak siteyi işlevsel kılan kodları içerir. İşte backend geliştirme sürecinde sıkça karşılaşılan temel kavramlar:

1. **Sunucu Tarafı Programlama**:
   Backend, sunucu tarafında çalışan kodları içerir. Bu kodlar, veritabanı sorguları, kullanıcı kimlik doğrulaması ve API'ler gibi görevleri yerine getirir.

2. **API'ler ve Web Servisleri**:
   API (Application Programming Interface), iki yazılım arasında iletişim kurmak için kullanılan bir arayüzdür. Örneğin, bir hava durumu uygulaması yapmak istiyorsanız, bir hava durumu API'si kullanabilirsiniz.

3. **Veritabanı Yönetimi**:
   Backend, genellikle veritabanlarıyla sıkı bir şekilde bağlantılıdır. Veritabanları, uygulamanın verilerini depolamak ve yönetmek için kullanılır. SQL ve NoSQL veritabanları, bu süreçte yaygın olarak kullanılır.


#### **Python ile Basit Bir Sunucu Oluşturmak**
Python ile basit bir sunucu oluşturmak için birkaç farklı yöntem bulunur. İşte en yaygın iki yöntem:

1. **`http.server` Modülü ile Basit Sunucu**:
   Python, `http.server` modülü ile hızlı bir şekilde basit bir HTTP sunucusu oluşturmanıza olanak tanır. Bu, özellikle küçük projeler veya test amaçlı kullanım için idealdir.

    ```python
    # Gerekli modülleri içe aktarır: HTTPServer ve BaseHTTPRequestHandler sınıflarını kullanarak sunucu oluşturur.
    from http.server import HTTPServer, BaseHTTPRequestHandler

    # Özel bir istek işleyici sınıfı tanımlanır. Bu sınıf, gelen HTTP isteklerini işler.
    class SimpleHTTPRequestHandler(BaseHTTPRequestHandler):
        # GET isteklerini işlemek için bir yöntem tanımlanır.
        def do_GET(self):
            # İstemciye HTTP 200 (OK) yanıt kodunu gönderir.
            self.send_response(200)
            
            # Yanıtın başlık kısmını sonlandırır.
            self.end_headers()
            
            # İstemciye bir yanıt mesajı gönderir. Mesaj bayt formatında olmalıdır.
            self.wfile.write(b"Merhaba, Python Sunucusu!")

    # HTTPServer sınıfı kullanılarak bir sunucu oluşturulur.
    # Sunucu localhost adresinde (127.0.0.1) ve 8000 numaralı portta çalışır.
    server = HTTPServer(("localhost", 8000), SimpleHTTPRequestHandler)

    # Kullanıcıya sunucunun çalıştığını bildiren bir mesaj yazdırılır.
    print("Sunucu 8000 portunda çalışıyor...")

    # Sunucuyu sürekli olarak çalışır durumda tutar. İstekleri almaya devam eder.
    server.serve_forever()
    ```

   Bu kod, `localhost:8000` adresinde çalışan basit bir sunucu oluşturur. Tarayıcıdan bu adrese eriştiğinizde "Merhaba, Python Sunucusu!" mesajını görürsünüz.

2. **Flask ile İlk Adımlar**:
   Flask, Python ile web uygulamaları geliştirmek için kullanılan minimalist bir micro-framework'tür. Flask ile basit bir web uygulaması şu şekilde oluşturulabilir:

   ```python
    # Flask framework'ünü içe aktarır.
    from flask import Flask

    # Flask uygulaması oluşturulur.
    app = Flask(__name__)

    # '/' URL yoluna gelen GET isteklerini işleyen bir rota tanımlanır.
    @app.route("/")
    def home():
        # İstemciye "Merhaba, Flask!" mesajını yanıt olarak döndürür.
        return "Merhaba, Flask!"

    # Dosya doğrudan çalıştırıldığında Flask uygulamasını başlatır.
    if __name__ == "__main__":
        # Uygulamayı geliştirme modunda çalıştırır.
        app.run(debug=True)
   ```

   Bu kod, Flask kullanarak basit bir web uygulaması oluşturur. `@app.route("/")` dekoratörü, ana sayfaya erişildiğinde çalışacak fonksiyonu belirtir.


#### **RESTful API'ler ve Web Servisleri**
RESTful API'ler, modern web uygulamalarının temelini oluşturur. REST (Representational State Transfer), HTTP protokolünü kullanarak veri alışverişi yapar. RESTful API'ler, genellikle JSON formatında veri döndürür.

- **Temel Kavramlar**:
  - **Kaynaklar (Resources)**: Verilerin temsil edildiği nesnelerdir. Örneğin, bir blog sitesinde her bir makale bir kaynaktır.
  - **HTTP Metodları**: GET, POST, PUT, DELETE gibi metotlar, kaynaklar üzerinde işlem yapmak için kullanılır.
  - **Endpoint'ler**: API'nin belirli bir URL'sidir. Örneğin, `/api/users` endpoint'i kullanıcıları temsil eder.

- **Örnek Bir REST API**:
  Flask ile basit bir REST API şu şekilde oluşturulabilir:

  ```python
    # Gerekli modülleri içe aktarır: Flask, jsonify (JSON dönüşümü için) ve request (istek verilerine erişim için).
    from flask import Flask, jsonify, request

    # Flask uygulaması oluşturulur.
    app = Flask(__name__)

    # Kullanıcı verilerini tutan bir liste tanımlanır.
    users = [
        {"id": 1, "name": "Ahmet"},
        {"id": 2, "name": "Mehmet"}
    ]

    # "/api/users" URL yoluna GET isteği geldiğinde çalışır.
    # Tüm kullanıcıları JSON formatında döndürür.
    @app.route("/api/users", methods=["GET"])
    def get_users():
        return jsonify(users)

    # "/api/users" URL yoluna POST isteği geldiğinde çalışır.
    # Yeni bir kullanıcı ekler ve oluşturulan kullanıcıyı JSON formatında döndürür.
    @app.route("/api/users", methods=["POST"])
    def add_user():
        # Yeni kullanıcı bilgisi oluşturulur. ID otomatik olarak hesaplanır, isim istekten alınır.
        new_user = {"id": len(users) + 1, "name": request.json["name"]}
        # Yeni kullanıcı listeye eklenir.
        users.append(new_user)
        # Oluşturulan kullanıcıyı JSON formatında döndürür ve HTTP 201 (Created) durum kodu ile yanıt verir.
        return jsonify(new_user), 201

    # Dosya doğrudan çalıştırıldığında Flask uygulamasını başlatır.
    if __name__ == "__main__":
        # Uygulamayı geliştirme modunda çalıştırır.
        app.run(debug=True)
  ```

  Bu kod, basit bir REST API oluşturur. `/api/users` endpoint'i, tüm kullanıcıları listeler ve yeni kullanıcı eklemek için kullanılır.


#### **Gerçek Dünya Örnekleri**
Python ile backend geliştirme, birçok gerçek dünya uygulamasında kullanılır. İşte bazı örnekler:

1. **E-Ticaret Platformu**:
   - Ürün listelerini, sepeti ve ödeme işlemlerini yönetmek için Flask veya Django kullanılabilir.
   - Veritabanı olarak PostgreSQL veya MongoDB kullanılabilir.

2. **Sosyal Medya Uygulaması**:
   - Kullanıcı profilleri, gönderiler ve yorumlar için API'ler oluşturmak için Django REST Framework kullanılabilir.
   - Kimlik doğrulama için JWT (JSON Web Token) kullanılabilir.

---


### 14.4 Flask Framework 🔥

Flask, Python ile web uygulamaları geliştirmek için kullanılan minimalist bir micro-framework'tür. Flask, özellikle küçük ölçekli projeler veya hızlı prototip oluşturmak için idealdir. Bu bölümde, Flask'ın temel kavramlarını, routing ve view fonksiyonlarını, şablonları, form işlemlerini ve veritabanı entegrasyonunu inceleyeceğiz.


#### **Flask'a Giriş**
Flask, basit ve esnek bir yapıya sahiptir. Bu, geliştiricilere tam kontrol sağlar ve gereksiz karmaşıklıktan kaçınır. Flask'u kullanmaya başlamak için önce kurulum yapmanız gerekir:

```bash
pip install flask
```

Kurulum tamamlandıktan sonra, ilk Flask uygulamanızı şu şekilde oluşturabilirsiniz:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Merhaba, Flask!"

if __name__ == "__main__":
    app.run(debug=True)
```

Bu kod, Flask kullanarak basit bir web uygulaması oluşturur. `@app.route("/")` dekoratörü, ana sayfaya erişildiğinde çalışacak fonksiyonu belirtir.


#### **Routing ve View Fonksiyonları**
Routing, bir URL'in belirli bir fonksiyonla eşleştirilmesi işlemidir. Flask'ta bu işlem, `@app.route()` dekoratörü ile yapılır.

- **Dinamik URL'ler**:
  Flask, dinamik URL'ler oluşturmanıza olanak tanır. Örneğin, bir kullanıcı profil sayfası oluşturmak için:

  ```python
    # "/user/<username>" URL yoluna gelen GET isteklerini işler.
    # '<username>' dinamik bir değişkendir ve URL'den alınan değeri temsil eder.
    @app.route("/user/<username>")
    def show_user_profile(username):
        # URL'den alınan kullanıcı adını bir metin içinde kullanarak istemciye yanıt döndürür.
        return f"Kullanıcı Adı: {username}"
  ```

  Bu kod, `/user/Ahmet` gibi bir URL'ye erişildiğinde "Kullanıcı Adı: Ahmet" mesajını döndürür.

- **HTTP Metodları**:
  Flask, GET, POST, PUT, DELETE gibi HTTP metodlarını destekler. Örneğin, bir form göndermek için:

  ```python
  @app.route("/login", methods=["GET", "POST"])
  def login():
      if request.method == "POST":
          return "Giriş Yapıldı!"
      else:
          return "Giriş Sayfası"
  ```


#### **Şablonlar (Templates)**
Flask, HTML şablonlarını oluşturmak için Jinja2 adlı bir motor kullanır. Şablonlar, dinamik içerikleri HTML sayfalarına eklemenizi sağlar.

- **Basit Bir Şablon**:
  `templates` klasörü içinde bir HTML dosyası oluşturun (`index.html`):

  ```html
  <!DOCTYPE html>
  <html>
  <head>
      <title>Flask Şablon Örneği</title>
  </head>
  <body>
      <h1>Merhaba, {{ name }}!</h1>
  </body>
  </html>
  ```

  Flask'da bu şablonu şu şekilde render edebilirsiniz:

  ```python
  from flask import render_template

    # "/" URL yoluna gelen GET isteklerini işler.
    # Kullanıcı ana sayfaya eriştiğinde 'home' fonksiyonu çalışır.
    @app.route("/")
    def home():
        # 'index.html' şablonunu render eder ve 'name' değişkenine "Ahmet" değerini gönderir.
        # 'render_template', HTML dosyalarını dinamik olarak oluşturmak için kullanılır.
        return render_template("index.html", name="Ahmet")
  ```

- **Template Inheritance (Kalıtım)**:
  Jinja2, şablon kalıtımı özelliğini destekler. Ortak bir layout oluşturup, diğer şablonlarda bu layout'u genişletebilirsiniz.

  ```html
    <!-- base.html -->
    <!-- HTML belgesinin temel yapısını tanımlar. Bu şablon, diğer şablonlar tarafından genişletilir (inheritance). -->
    <!DOCTYPE html>
    <html>
    <head>
        <!-- "title" bloğu tanımlanır. 
            Diğer şablonlar bu bloğu doldurabilir. Eğer doldurulmazsa boş kalır. -->
        <title>{% block title %}{% endblock %}</title>
    </head>
    <body>
        <!-- "content" bloğu tanımlanır. 
            Diğer şablonlar bu bloğu doldurarak sayfanın ana içeriğini belirler. -->
        {% block content %}{% endblock %}
    </body>
    </html>
  ```

  ```html
    <!-- index.html -->
    <!-- "base.html" şablonunu genişletir (inheritance). 
        Bu sayede "base.html" içindeki yapıyı kullanabilir ve üzerine yeni içerikler ekleyebiliriz. -->
    {% extends "base.html" %}

    <!-- "title" bloğunu tanımlar. 
        "base.html" içinde bir "title" bloğu varsa, buradaki içerik onu değiştirir. -->
    {% block title %}Anasayfa{% endblock %}

    <!-- "content" bloğunu tanımlar. 
        "base.html" içinde bir "content" bloğu varsa, buradaki içerik o bölüme yerleştirilir. -->
    {% block content %}
        <h1>Hoş Geldiniz!</h1>
    {% endblock %}
  ```


#### **Form İşlemleri**
Flask'ta form işlemleri için WTForms adlı bir kütüphane kullanılabilir. WTForms, form doğrulama ve hata yönetimi için güçlü bir araçtır.

- **Basit Bir Form**:
  ```python
    # Gerekli modülleri içe aktarır:
    # Flask, render_template (HTML şablonlarını render etmek için), request (istek verilerine erişim için).
    # WTForms, Form sınıfı ve StringField (form alanları için), validators (doğrulama kuralları için).
    from flask import Flask, render_template, request
    from wtforms import Form, StringField, validators

    # Flask uygulaması oluşturulur.
    app = Flask(__name__)

    # LoginForm adlı bir form sınıfı tanımlanır.
    # Bu sınıf, kullanıcı giriş formunu temsil eder.
    class LoginForm(Form):
        # Kullanıcı adı alanı, minimum 4 maksimum 25 karakter uzunluğunda olmalıdır.
        username = StringField("Kullanıcı Adı", [validators.Length(min=4, max=25)])
        # Şifre alanı, minimum 6 karakter uzunluğunda olmalıdır.
        password = StringField("Şifre", [validators.Length(min=6)])

    # "/login" URL yoluna GET veya POST isteği geldiğinde çalışır.
    @app.route("/login", methods=["GET", "POST"])
    def login():
        # Form nesnesi oluşturulur ve istek verileri ile doldurulur.
        form = LoginForm(request.form)
        
        # Eğer istek yöntemi POST ise ve form doğrulaması başarılıysa:
        if request.method == "POST" and form.validate():
            # Kullanıcıyı karşılama mesajı döndürülür. 'form.username.data' ile kullanıcı adı alınır.
            return f"Hoş Geldin, {form.username.data}!"
        
        # Eğer GET isteği geldiyse veya form doğrulaması başarısızsa,
        # 'login.html' şablonu render edilir ve form nesnesi şablona gönderilir.
        return render_template("login.html", form=form)
  ```

  `login.html` şablonunda formu şu şekilde gösterebilirsiniz:

  ```html
    <!-- Form, POST yöntemiyle veri gönderir. -->
    <form method="POST">
        <!-- Gizli alanlar (örneğin CSRF koruma) eklenir. -->
        {{ form.hidden_tag() }}
        
        <!-- Kullanıcı adı etiketi ve input alanı. -->
        <p>{{ form.username.label }}: {{ form.username }}</p>
        
        <!-- Şifre etiketi ve input alanı. -->
        <p>{{ form.password.label }}: {{ form.password }}</p>
        
        <!-- Gönder butonu, form verilerini sunucuya gönderir. -->
        <button type="submit">Giriş Yap</button>
    </form>
  ```


#### **Veritabanı Entegrasyonu**
Flask'ta veritabanı işlemleri için SQLAlchemy adlı bir ORM (Object-Relational Mapping) aracı kullanılabilir. SQLAlchemy, veritabanı sorgularını Python koduyla yazmanızı sağlar.

- **Basit Bir Veritabanı Modeli**:
  ```python
    from flask import Flask
    from flask_sqlalchemy import SQLAlchemy

    # Flask uygulaması oluşturulur.
    app = Flask(__name__)

    # Veritabanı ayarları yapılır. SQLite kullanılır ve veritabanı dosyası 'site.db' olarak kaydedilir.
    app.config["SQLALCHEMY_DATABASE_URI"] = "sqlite:///site.db"

    # SQLAlchemy ile veritabanı bağlantısı kurulur.
    db = SQLAlchemy(app)

    # User adlı bir veritabanı modeli tanımlanır.
    class User(db.Model):
        # Kullanıcı ID'si, birincil anahtar olarak atanır.
        id = db.Column(db.Integer, primary_key=True)
        # Kullanıcı adı, benzersiz olmalı ve boş bırakılamaz.
        username = db.Column(db.String(20), unique=True, nullable=False)
        # E-posta adresi, benzersiz olmalı ve boş bırakılamaz.
        email = db.Column(db.String(120), unique=True, nullable=False)

    # Ana sayfada tüm kullanıcıların kullanıcı adlarını listeler.
    @app.route("/")
    def home():
        # Veritabanından tüm kullanıcılar çekilir.
        users = User.query.all()
        # Kullanıcı adlarını bir liste olarak döndürür.
        return f"Kullanıcılar: {[user.username for user in users]}"
  ```


#### **RESTful API'ler**
Flask ile RESTful API'ler oluşturmak için Flask-RESTful adlı bir uzantı kullanılabilir.

- **Basit Bir API**:
  ```python
  from flask import Flask
  from flask_restful import Api, Resource

  app = Flask(__name__)
  api = Api(app)

  class HelloWorld(Resource):
      def get(self):
          return {"message": "Merhaba, Dünya!"}

  api.add_resource(HelloWorld, "/")

  if __name__ == "__main__":
      app.run(debug=True)
  ```

---


### 14.5 Django Framework ⚡

Django, Python ile yazılmış tam teşekküllü bir web framework'üdür. Özellikle büyük ölçekli projeler için idealdir ve birçok hazır özellik içerir (örneğin, admin paneli, ORM, kimlik doğrulama). Bu bölümde, Django'nun temel kavramlarını, proje yapısını, modelleri, view'ları, şablonları ve API oluşturma süreçlerini inceleyeceğiz.


#### **Django'ya Giriş**
Django, "batteries included" (piller dahil) felsefesiyle tanınır. Yani, geliştiricilere hızlı bir şekilde uygulama geliştirmeleri için gerekli olan birçok araç ve özellik hazır olarak sunulur. Django'yu kullanmaya başlamak için önce kurulum yapmanız gerekir:

```bash
pip install django
```

Kurulum tamamlandıktan sonra, ilk Django projesini şu şekilde oluşturabilirsiniz:

```bash
# Django projesi oluşturur. "myproject" adında bir proje klasörü oluşturulur.
django-admin startproject myproject

# Oluşturulan "myproject" klasörüne geçiş yapar.
cd myproject

# Django geliştirme sunucusunu başlatır. Varsayılan olarak http://127.0.0.1:8000/ adresinde çalışır.
python manage.py runserver
```

Bu komutlar, size hazır bir Django projesi oluşturur ve geliştirme sunucusunu başlatır. Tarayıcıda `http://127.0.0.1:8000/` adresine giderek "The install worked successfully!" mesajını görebilirsiniz.


#### **Proje Yapısı ve Uygulama Yönetimi**
Django projeleri, birden fazla **app (uygulama)** içerir. Her app, belirli bir işlevi yerine getirir. Örneğin, bir blog sitesinde `posts` adlı bir app blog gönderilerini, `users` adlı bir app ise kullanıcıları yönetebilir.

- **Yeni Bir App Oluşturmak**:
  ```bash
  python manage.py startapp posts
  ```

  Bu komut, `posts` adlı yeni bir app oluşturur. Oluşturulan app'i projeye dahil etmek için `settings.py` dosyasındaki `INSTALLED_APPS` listesine eklemeniz gerekir:

  ```python
    INSTALLED_APPS = [
        # Diğer app'ler...
        'posts',  # 'posts' adlı uygulamayı projeye dahil eder. Bu, Django'da bir uygulamanın aktif hale getirilmesini sağlar.
    ]
  ```


#### **Modeller ve Veritabanı Yönetimi**
Django, veritabanı işlemlerini kolaylaştırmak için güçlü bir ORM (Object-Relational Mapping) sistemi sağlar. ORM, veritabanı sorgularını Python koduyla yazmanızı sağlar.

- **Basit Bir Model**:
  `models.py` dosyasında bir model tanımlayabilirsiniz:

  ```python
    from django.db import models

    # Post adında bir model sınıfı tanımlanır. Bu sınıf, veritabanında bir tabloya karşılık gelir.
    class Post(models.Model):
        # title alanı, maksimum 100 karakter uzunluğunda bir metin alanıdır.
        title = models.CharField(max_length=100)
        
        # content alanı, uzun metinler için kullanılır. Sınırsız uzunlukta olabilir.
        content = models.TextField()
        
        # created_at alanı, tarih ve saat bilgisini saklar. 
        # auto_now_add=True ile kayıt oluşturulduğunda otomatik olarak şu anki zamanı ekler.
        created_at = models.DateTimeField(auto_now_add=True)

        # __str__ metodu, modelin herhangi bir nesnesi çağrıldığında gösterilecek değeri belirler.
        def __str__(self):
            return self.title  # Başlığı döndürerek modelin daha okunabilir bir temsilini sağlar.
  ```

  Bu model, `Post` adlı bir tablo oluşturur. `title`, `content` ve `created_at` alanları, veritabanındaki sütunlara karşılık gelir.

- **Migration İşlemleri**:
  Modelleri oluşturduktan sonra, veritabanına uygulamak için migration işlemleri yapılır:

  ```bash
    # 'makemigrations' komutu, modellerde yapılan değişiklikleri (örneğin yeni bir model veya alan eklemek) 
    # algılar ve bu değişiklikleri bir geçiş (migration) dosyası olarak kaydeder.
    python manage.py makemigrations

    # 'migrate' komutu, 'makemigrations' ile oluşturulan geçiş dosyalarını uygular 
    # ve veritabanında gerekli tabloları veya değişiklikleri oluşturur.
    python manage.py migrate
  ```


#### **Views ve URL Yönlendirme**
Django'da, bir URL'in belirli bir fonksiyonla eşleştirilmesi işlemi **view** ve **URL yönlendirme** ile yapılır.

- **Function-Based Views**:
  Basit bir view şu şekilde oluşturulabilir:

  ```python
  from django.http import HttpResponse

  def home(request):
      return HttpResponse("Merhaba, Django!")
  ```

- **Class-Based Views**:
  Daha karmaşık senaryolar için class-based views kullanılabilir:

  ```python
    from django.views.generic import ListView
    from .models import Post

    # PostListView adında bir sınıf oluşturur. Bu sınıf, ListView'i genişleterek özelleştirir.
    class PostListView(ListView):
        model = Post  # Kullanılacak modeli belirtir. Bu durumda 'Post' modeli kullanılır.
        template_name = "post_list.html"  # Hangi şablonun kullanılacağını belirtir.
        context_object_name = "posts"  # Şablona geçirilecek veri kümesinin ismini belirtir (örneğin: posts).
  ```

- **URL Yönlendirme**:
  `urls.py` dosyasında URL'ler tanımlanır:

  ```python
  from django.urls import path
  from . import views

  urlpatterns = [
      path("", views.home, name="home"),
      path("posts/", views.PostListView.as_view(), name="post-list"),
  ]
  ```


#### **Şablonlar ve Static Dosyalar**
Django, HTML şablonlarını oluşturmak için kendi şablon motorunu kullanır. Ayrıca, CSS, JavaScript ve resim gibi static dosyaları yönetmek için özel bir yapı sağlar.

- **Basit Bir Şablon**:
  `templates` klasörü içinde bir HTML dosyası oluşturun (`post_list.html`):

  ```html
  <!DOCTYPE html>
  <html>
  <head>
      <title>Blog</title>
  </head>
  <body>
      <h1>Gönderiler</h1>
      <ul>
          {% for post in posts %}
              <li>{{ post.title }}</li>
          {% endfor %}
      </ul>
  </body>
  </html>
  ```

- **Static Dosyalar**:
  CSS veya JavaScript dosyalarını `static` klasörüne ekleyin ve şablonda şu şekilde kullanın:

  ```html
  <link rel="stylesheet" href="{% static 'css/style.css' %}">
  ```


#### **Admin Paneli**
Django, hazır bir admin paneli sağlar. Admin panelini kullanmak için önce bir superuser oluşturmanız gerekir:

```bash
python manage.py createsuperuser
```

Ardından, `admin.py` dosyasında modelleri kaydedin:

```python
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```

Artık `/admin` adresinden giriş yaparak modelleri yönetebilirsiniz.


#### **Kimlik Doğrulama ve Yetkilendirme**
Django, kullanıcı kimlik doğrulama ve yetkilendirme için hazır bir sistem sunar.

- **Login ve Logout**:
  ```python
  from django.contrib.auth import authenticate, login, logout

  def user_login(request):
      if request.method == "POST":
          username = request.POST["username"]
          password = request.POST["password"]
          user = authenticate(request, username=username, password=password)
          if user is not None:
              login(request, user)
              return HttpResponse("Giriş Başarılı!")
      return render(request, "login.html")
  ```


#### **Django REST Framework (DRF)**
Django ile RESTful API'ler oluşturmak için Django REST Framework (DRF) adlı bir uzantı kullanılabilir.

- **Basit Bir API**:
  ```python
    # 'serializers', verileri JSON veya diğer formatlara dönüştürmek için kullanılır.
    # 'viewsets', CRUD işlemlerini otomatik olarak yöneten yapıları sağlar.
    from rest_framework import serializers, viewsets
    from .models import Post

    # PostSerializer adında bir seriализator tanımlar. 
    # Bu seriализator, Post modelinin verilerini serileştirmek için kullanılır.
    class PostSerializer(serializers.ModelSerializer):
        class Meta:
            model = Post  # Serileştirilecek modeli belirtir.
            fields = "__all__"  # Modeldeki tüm alanları dahil eder.

    # PostViewSet adında bir ViewSet tanımlar. 
    # Bu ViewSet, Post modeli için CRUD işlemleri sağlar.
    class PostViewSet(viewsets.ModelViewSet):
        queryset = Post.objects.all()  # Tüm Post nesnelerini getiren sorguyu tanımlar.
        serializer_class = PostSerializer  # Kullanılacak seriализator sınıfını belirtir.
  ```

---


### 14.6 RESTful Servisler ve Web Servisleri 🌐

RESTful servisler, modern web uygulamalarının temelini oluşturur. REST (Representational State Transfer), HTTP protokolünü kullanarak veri alışverişi yapar. Bu bölümde, RESTful API'lerin temel kavramlarını, tasarım ilkelerini, güvenlik önlemlerini ve nasıl oluşturulacağını inceleyeceğiz.


#### **REST API Kavramları**
REST, web servislerinin tasarlanması için bir mimari stil olarak tanımlanır. RESTful API'ler, genellikle JSON formatında veri döndürür ve HTTP metotlarını (GET, POST, PUT, DELETE) kullanır.

- **Kaynaklar (Resources)**:
  Kaynaklar, API'nin temsil ettiği nesnelerdir. Örneğin, bir blog sitesinde her bir makale bir kaynaktır. Kaynaklar genellikle URL'lerle temsil edilir:

  ```
  GET /api/posts       -> Tüm gönderileri listele
  GET /api/posts/1     -> ID'si 1 olan gönderiyi getir
  POST /api/posts      -> Yeni bir gönderi oluştur
  PUT /api/posts/1     -> ID'si 1 olan gönderiyi güncelle
  DELETE /api/posts/1  -> ID'si 1 olan gönderiyi sil
  ```

- **HTTP Metodları**:
  - **GET**: Veri almak için kullanılır.
  - **POST**: Yeni bir kaynak oluşturmak için kullanılır.
  - **PUT**: Mevcut bir kaynağı güncellemek için kullanılır.
  - **DELETE**: Bir kaynağı silmek için kullanılır.

- **Durum Kodları**:
  RESTful API'ler, HTTP durum kodlarını kullanarak istemciye yanıt verir:
  - `200 OK`: İstek başarılı.
  - `201 Created`: Kaynak başarıyla oluşturuldu.
  - `400 Bad Request`: İstemci hatası.
  - `404 Not Found`: Kaynak bulunamadı.
  - `500 Internal Server Error`: Sunucu hatası.

---

#### **API Dokümantasyonu**
Bir API'nin kullanılabilir olması için iyi bir dokümantasyon gereklidir. API dokümantasyonu, endpoint'lerin ne işe yaradığını, girdi çıktı formatlarını ve örnek kullanım senaryolarını açıklar.

- **Swagger**:
  Swagger, API dokümantasyonu oluşturmak için kullanılan popüler bir araçtır. Swagger UI ile interaktif bir dokümantasyon arayüzü oluşturabilirsiniz.

- **Postman**:
  Postman, API'leri test etmek için kullanılan bir araçtır. API'nizi geliştirirken veya paylaşırken Postman ile testler yapabilirsiniz.


#### **Güvenlik ve Kimlik Doğrulama**
RESTful API'ler, özellikle hassas veriler içerdiğinde güvenliği sağlamak için özel önlemler almalıdır.

- **Token-Based Authentication**:
  Token tabanlı kimlik doğrulama, kullanıcıların giriş yaptıktan sonra bir token almasını sağlar. Bu token, sonraki isteklerde kimlik doğrulama için kullanılır.

- **JWT (JSON Web Token)**:
  JWT, modern API'lerde sıkça kullanılan bir kimlik doğrulama yöntemidir. JWT, kullanıcı bilgilerini içeren bir token oluşturur ve bu token şifrelenerek gönderilir.

  ```python
    from flask import Flask, jsonify, request
    import jwt

    # Flask uygulaması oluşturulur.
    app = Flask(__name__)

    # JWT işlemlerinde kullanılacak gizli anahtar tanımlanır.
    SECRET_KEY = "mysecretkey"

    # "/login" URL yoluna POST isteği geldiğinde çalışır.
    @app.route("/login", methods=["POST"])
    def login():
        # İstekten kullanıcı adı ve şifre alınır.
        username = request.json.get("username")
        password = request.json.get("password")
        
        # Kullanıcı adı ve şifre kontrol edilir.
        if username == "admin" and password == "password":
            # Doğrulama başarılıysa, bir JWT token oluşturulur.
            token = jwt.encode({"username": username}, SECRET_KEY, algorithm="HS256")
            return jsonify({"token": token})  # Token istemciye gönderilir.
        
        # Kullanıcı adı veya şifre yanlışsa hata döner.
        return jsonify({"error": "Invalid credentials"}), 401

    # "/protected" URL yoluna GET isteği geldiğinde çalışır.
    @app.route("/protected", methods=["GET"])
    def protected():
        # İstek başlıklarından "Authorization" alanındaki token alınır.
        token = request.headers.get("Authorization")
        
        # Eğer token yoksa hata döner.
        if not token:
            return jsonify({"error": "Token is missing"}), 401
        
        try:
            # Token çözümlenir ve içeriği alınır.
            data = jwt.decode(token, SECRET_KEY, algorithms=["HS256"])
            # Token geçerliyse hoş geldin mesajı döner.
            return jsonify({"message": f"Welcome, {data['username']}!"})
        except:
            # Token geçersizse hata döner.
            return jsonify({"error": "Invalid token"}), 401
  ```


#### **Örnek Bir REST API**
Flask veya Django ile basit bir REST API oluşturabiliriz. İşte Flask ile bir örnek:

```python
from flask import Flask, jsonify, request

    app = Flask(__name__)
    # Kitapları temsil eden bir liste. Her kitap bir sözlük olarak tanımlanır.
    books = [
        {"id": 1, "title": "Savaş ve Barış", "author": "Tolstoy"},
        {"id": 2, "title": "1984", "author": "George Orwell"}
    ]

    # "/api/books" URL yoluna GET isteği geldiğinde çalışır.
    # Tüm kitapları JSON formatında döndürür.
    @app.route("/api/books", methods=["GET"])
    def get_books():
        return jsonify(books)

    # "/api/books/<int:id>" URL yoluna GET isteği geldiğinde çalışır.
    # Belirli bir ID'ye sahip kitabı bulur ve JSON formatında döndürür.
    @app.route("/api/books/<int:id>", methods=["GET"])
    def get_book(id):
        # ID'si eşleşen kitabı bulur. Eğer bulunamazsa None döner.
        book = next((book for book in books if book["id"] == id), None)
        if book:
            return jsonify(book)  # Kitabı JSON formatında döndürür.
        return jsonify({"error": "Book not found"}), 404  # Kitap bulunamazsa hata döner.

    # "/api/books" URL yoluna POST isteği geldiğinde çalışır.
    # Yeni bir kitap ekler ve oluşturulan kitabı JSON formatında döndürür.
    @app.route("/api/books", methods=["POST"])
    def add_book():
        new_book = request.json  # İstekten gelen JSON verisini alır.
        new_book["id"] = len(books) + 1  # Yeni kitaba bir sonraki ID atanır.
        books.append(new_book)  # Kitap listesine eklenir.
        return jsonify(new_book), 201  # Oluşturulan kitabı ve HTTP 201 (Created) durum kodunu döndürür.

    # Dosya doğrudan çalıştırıldığında Flask uygulamasını başlatır.
    if __name__ == "__main__":
        app.run(debug=True)  # Uygulamayı geliştirme modunda çalıştırır.
```

Bu kod, basit bir REST API oluşturur. `/api/books` endpoint'i, tüm kitapları listeler ve yeni bir kitap eklemek için kullanılır.


#### **Gerçek Dünya Örnekleri**
RESTful API'ler, birçok gerçek dünya uygulamasında kullanılır. İşte bazı örnekler:

1. **Hava Durumu API'si**:
   - Kullanıcıların belirli bir şehrin hava durumunu sorgulamasına olanak tanır.
   - Örnek endpoint: `/api/weather?city=Istanbul`

2. **E-Ticaret API'si**:
   - Ürün listelerini, sepeti ve ödeme işlemlerini yönetir.
   - Örnek endpoint: `/api/products`

3. **Sosyal Medya API'si**:
   - Kullanıcı profilleri, gönderiler ve yorumlar için API'ler oluşturur.
   - Örnek endpoint: `/api/users/<id>/posts`

---


### 14.7 Veritabanı Yönetimi ve Entegrasyonu 🗄️

Veritabanları, web uygulamalarının temel taşlarından biridir. Veritabanları, uygulamanın verilerini depolamak ve yönetmek için kullanılır. Bu bölümde, SQL ve NoSQL veritabanlarını, ORM (Object-Relational Mapping) kavramını, veritabanı ilişkilerini ve Python ile nasıl entegre edileceğini inceleyeceğiz.


#### **SQL ve NoSQL Veritabanları**
Web geliştirme dünyasında iki ana tür veritabanı kullanılır: **SQL** ve **NoSQL**.

1. **SQL Veritabanları**:
   - İlişkisel veri modellerini kullanır.
   - Örnekler: PostgreSQL, MySQL, SQLite.
   - Veriler tablolar halinde saklanır ve sorgular SQL diliyle yapılır.

   ```python
   # SQLite ile basit bir veritabanı bağlantısı
   import sqlite3

   # Veritabanı bağlantısı oluştur
   connection = sqlite3.connect("example.db")  # example.db adlı bir veritabanı oluşturur veya bağlanır
   cursor = connection.cursor()

   # Tablo oluştur
   cursor.execute("""
       CREATE TABLE IF NOT EXISTS users (
           id INTEGER PRIMARY KEY,
           name TEXT NOT NULL,
           email TEXT NOT NULL
       )
   """)  # users adlı bir tablo oluşturur (eğer yoksa)

   # Veri ekle
   cursor.execute("INSERT INTO users (name, email) VALUES (?, ?)", ("Ahmet", "ahmet@example.com"))
   connection.commit()  # Değişiklikleri kaydeder

   # Veri çek
   cursor.execute("SELECT * FROM users")
   rows = cursor.fetchall()  # Tüm kullanıcıları çeker
   for row in rows:
       print(row)

   connection.close()  # Bağlantıyı kapatır
   ```

2. **NoSQL Veritabanları**:
   - İlişkisel olmayan veri modellerini kullanır.
   - Örnekler: MongoDB, Redis.
   - Veriler genellikle JSON formatında saklanır.

   ```python
   # MongoDB ile basit bir veritabanı bağlantısı
   from pymongo import MongoClient

   # MongoDB bağlantısı oluştur
   client = MongoClient("mongodb://localhost:27017/")  # MongoDB sunucusuna bağlanır
   db = client["mydatabase"]  # mydatabase adlı bir veritabanı oluşturur veya bağlanır
   collection = db["users"]  # users adlı bir koleksiyon oluşturur veya bağlanır

   # Veri ekle
   user_data = {"name": "Mehmet", "email": "mehmet@example.com"}
   collection.insert_one(user_data)  # Koleksiyona bir kullanıcı ekler

   # Veri çek
   users = collection.find()  # Tüm kullanıcıları çeker
   for user in users:
       print(user)
   ```


#### **ORM (Object-Relational Mapping)**
ORM, veritabanı işlemlerini Python koduyla yapmanızı sağlar. SQLAlchemy ve Django ORM, Python'da en yaygın kullanılan ORM araçlarıdır.

1. **SQLAlchemy ile ORM Kullanımı**:
   ```python
   from sqlalchemy import create_engine, Column, Integer, String
   from sqlalchemy.ext.declarative import declarative_base
   from sqlalchemy.orm import sessionmaker

   # Veritabanı bağlantısı oluştur
   engine = create_engine("sqlite:///example.db")  # SQLite veritabanı bağlantısı
   Base = declarative_base()  # ORM için temel sınıf

   # Model tanımla
   class User(Base):
       __tablename__ = "users"  # Tablo adı
       id = Column(Integer, primary_key=True)  # ID sütunu
       name = Column(String, nullable=False)  # İsim sütunu
       email = Column(String, nullable=False)  # E-posta sütunu

   # Tabloyu oluştur
   Base.metadata.create_all(engine)  # users tablosunu oluşturur

   # Session oluştur
   Session = sessionmaker(bind=engine)
   session = Session()

   # Veri ekle
   new_user = User(name="Fatma", email="fatma@example.com")
   session.add(new_user)  # Yeni bir kullanıcı ekler
   session.commit()  # Değişiklikleri kaydeder

   # Veri çek
   users = session.query(User).all()  # Tüm kullanıcıları çeker
   for user in users:
       print(user.name, user.email)
   ```

2. **Django ORM ile CRUD İşlemleri**:
   ```python
   from django.db import models

   # Model tanımla
   class Product(models.Model):
       name = models.CharField(max_length=100)  # Ürün adı
       price = models.DecimalField(max_digits=10, decimal_places=2)  # Ürün fiyatı

       def __str__(self):
           return self.name

   # Veri ekle
   product = Product(name="Laptop", price=5000)
   product.save()  # Ürünü kaydeder

   # Veri çek
   products = Product.objects.all()  # Tüm ürünleri çeker
   for p in products:
       print(p.name, p.price)
   ```


#### **Veritabanı İlişkileri**
İlişkisel veritabanlarında, tablolar arasında ilişkiler kurulabilir. En yaygın ilişki türleri:

1. **One-to-One (Bire Bir)**:
   ```python
   class Profile(models.Model):
       user = models.OneToOneField(User, on_delete=models.CASCADE)  # Her kullanıcı için bir profil
       bio = models.TextField()
   ```

2. **One-to-Many (Bire Çok)**:
   ```python
   class Category(models.Model):
       name = models.CharField(max_length=100)

   class Article(models.Model):
       title = models.CharField(max_length=100)
       category = models.ForeignKey(Category, on_delete=models.CASCADE)  # Bir kategoriye ait birçok makale
   ```

3. **Many-to-Many (Çoktan Çoğa)**:
   ```python
   class Tag(models.Model):
       name = models.CharField(max_length=50)

   class Post(models.Model):
       title = models.CharField(max_length=100)
       tags = models.ManyToManyField(Tag)  # Bir gönderi birçok etikete sahip olabilir
   ```


#### **Gerçek Dünya Örnekleri**
Veritabanı yönetimi, birçok gerçek dünya uygulamasında kullanılır. İşte bazı örnekler:

1. **E-Ticaret Platformu**:
   - Ürün listelerini, sepeti ve siparişleri yönetmek için SQL veritabanları kullanılabilir.
   - Örnek model: `Product`, `Order`, `Customer`.

2. **Sosyal Medya Uygulaması**:
   - Kullanıcı profilleri, gönderiler ve yorumlar için ilişkisel veritabanları kullanılabilir.
   - Örnek ilişki: `User` → `Post` → `Comment`.

---


### 14.8 Deployment ve Sunucu Yönetimi 🚀

Deployment (dağıtım), geliştirilen web uygulamasının üretim ortamına taşınması ve kullanıcılar tarafından erişilebilir hale getirilmesi sürecidir. Bu bölümde, deployment temellerini, sunucu seçeneklerini, WSGI/ASGI protokollerini ve CI/CD süreçlerini inceleyeceğiz.


#### **Deployment Temelleri**
Deployment sürecinde, geliştirme ortamından farklı olarak bazı ayarlar yapılır. Örneğin, debug modu kapatılır, güvenlik önlemleri alınır ve performans optimizasyonları yapılır.

1. **Debug Modunu Kapatma**:
   ```python
   # settings.py (Django için)
   DEBUG = False  # Debug modunu kapatır
   ALLOWED_HOSTS = ["example.com"]  # İzin verilen domainleri belirtir
   ```

   - Debug modu, geliştirme sırasında hata ayıklamak için kullanılır. Ancak üretim ortamında bu mod açık bırakılırsa güvenlik riski oluşturur.

2. **Statik Dosyaları Topla**:
   ```bash
   python manage.py collectstatic
   ```
   - Django gibi framework'lerde statik dosyalar (CSS, JavaScript, resimler) toplanır ve sunucuya yüklenir.


#### **Sunucu Seçenekleri**
Web uygulamalarını dağıtmak için birçok sunucu seçeneği bulunur. İşte en yaygın olanlar:

1. **Heroku**:
   Heroku, basit ve hızlı bir deployment süreci sunar. Uygulamanızı GitHub veya CLI üzerinden kolayca yayınlayabilirsiniz.

   ```bash
   # Heroku CLI ile deployment
   heroku create myapp  # Yeni bir Heroku uygulaması oluşturur
   git push heroku main  # Kodu Heroku'ya gönderir
   heroku open  # Uygulamayı tarayıcıda açar
   ```

   - `heroku create` komutu, Heroku üzerinde yeni bir uygulama oluşturur. `git push heroku main` ise kodunuzu Heroku'ya yükler.

2. **AWS (Amazon Web Services)**:
   AWS, geniş bir altyapı hizmetleri yelpazesi sunar. EC2, S3 ve RDS gibi hizmetler, uygulamanızı tamamen özelleştirerek barındırmanıza olanak tanır.

   ```bash
   # AWS EC2'de bir sunucu başlatma
   aws ec2 run-instances --image-id ami-0abcdef1234567890 --instance-type t2.micro
   ```
   - Bu komut, AWS üzerinde bir EC2 örneği (sunucu) başlatır. `--image-id` parametresi, kullanılacak işletim sistemini belirtir.

3. **DigitalOcean**:
   DigitalOcean, basit ve uygun fiyatlı bir bulut hizmetidir. Droplet adı verilen sanal makineler oluşturarak uygulamanızı barındırabilirsiniz.

   ```bash
   # DigitalOcean'da bir droplet oluşturma
   doctl compute droplet create my-droplet --region nyc1 --size s-1vcpu-1gb --image ubuntu-20-04
   ```
   - `doctl` aracı, DigitalOcean API'sini kullanarak bir droplet (sanal makine) oluşturur.


#### **WSGI ve ASGI**
Python web uygulamaları, WSGI (Web Server Gateway Interface) veya ASGI (Asynchronous Server Gateway Interface) protokolleriyle çalışır. Bu protokoller, uygulamanızı web sunucusuyla iletişim kurmasını sağlar.

1. **Gunicorn ile WSGI Deployment**:
   ```bash
   pip install gunicorn  # Gunicorn'u yükle
   gunicorn myproject.wsgi:application --bind 0.0.0.0:8000
   ```
   - `gunicorn`, Python uygulamalarını çalıştırmak için kullanılan bir WSGI sunucusudur. `myproject.wsgi:application` ifadesi, Django'nun WSGI yapılandırmasını belirtir.

2. **uWSGI ile Deployment**:
   ```bash
   uwsgi --http :8000 --wsgi-file myproject/wsgi.py
   ```
   - `uWSGI`, başka bir popüler WSGI sunucusudur. `--wsgi-file` parametresi, WSGI yapılandırma dosyasını belirtir.


#### **Nginx ve Apache ile Reverse Proxy**
Nginx veya Apache, uygulamanızı internete açmak için reverse proxy olarak kullanılabilir. Bu, uygulamanızın güvenliğini artırır ve performansını optimize eder.

1. **Nginx Konfigürasyonu**:
   ```nginx
   server {
       listen 80;
       server_name example.com;

       location / {
           proxy_pass http://127.0.0.1:8000;  # Gunicorn veya uWSGI'ye yönlendirir
           proxy_set_header Host $host;
           proxy_set_header X-Real-IP $remote_addr;
       }
   }
   ```
   - Bu yapılandırma, Nginx'in istekleri `127.0.0.1:8000` adresinde çalışan Gunicorn sunucusuna yönlendirmesini sağlar.

2. **Apache Konfigürasyonu**:
   ```apache
   <VirtualHost *:80>
       ServerName example.com

       ProxyPreserveHost On
       ProxyPass / http://127.0.0.1:8000/
       ProxyPassReverse / http://127.0.0.1:8000/
   </VirtualHost>
   ```
   - Bu yapılandırma, Apache'nin istekleri `127.0.0.1:8000` adresinde çalışan uygulamaya yönlendirmesini sağlar.


#### **CI/CD ve Otomasyon**
CI/CD (Continuous Integration/Continuous Deployment), uygulamanızın sürekli olarak test edilmesini ve dağıtılmasını sağlar.

1. **GitHub Actions ile CI/CD**:
   ```yaml
   name: CI/CD Pipeline

   on:
     push:
       branches:
         - main  # Ana dalda değişiklik olduğunda tetiklenir

   jobs:
     build:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout code
           uses: actions/checkout@v2  # Kodu indirir

         - name: Install dependencies
           run: pip install -r requirements.txt  # Bağımlılıkları kurar

         - name: Run tests
           run: pytest  # Testleri çalıştırır

         - name: Deploy to Heroku
           run: |
             git push https://heroku:$HEROKU_API_KEY@git.heroku.com/myapp.git main
           env:
             HEROKU_API_KEY: ${{ secrets.HEROKU_API_KEY }}  # Heroku API anahtarını kullanır
   ```
   - Bu YAML dosyası, GitHub Actions ile bir CI/CD pipeline tanımlar. Kod değişikliklerinde otomatik olarak test edilir ve dağıtılır.

2. **Docker ile Containerization**:
   ```dockerfile
   # Dockerfile
   FROM python:3.9-slim  # Python 3.9 tabanlı bir imaj kullanır

   WORKDIR /app  # Çalışma dizinini belirler
   COPY . /app  # Proje dosyalarını kopyalar
   RUN pip install -r requirements.txt  # Bağımlılıkları kurar

   CMD ["gunicorn", "myproject.wsgi:application", "--bind", "0.0.0.0:8000"]
   ```
   - Bu Dockerfile, uygulamanızı bir container içine paketler. `CMD` komutu, container başlatıldığında çalışacak komutu belirtir.

---


### 14.9 Proje Geliştirme ve Pratik Örnekler 🛠️

Bu bölümde, daha önce öğrendiğimiz HTML, CSS, JavaScript, Flask/Django, veritabanı yönetimi ve deployment süreçlerini bir araya getireceğiz. Bir blog sitesi projesi üzerinden ilerleyeceğiz. Bu proje, kullanıcıların blog gönderilerini oluşturmasını, okumasını ve yorum yapmasını sağlayacak.


#### **Proje Fikirleri ve Planlama**
Bir proje geliştirmeden önce, projenin amacını ve işlevselliğini netleştirmek önemlidir. İşte bu projenin temel özellikleri:

1. **Kullanıcılar**:
   - Kullanıcılar kayıt olabilir ve giriş yapabilir.
   - Giriş yapan kullanıcılar yeni gönderiler oluşturabilir.

2. **Gönderiler**:
   - Her gönderi bir başlık, içerik ve yazar bilgisi içerir.
   - Gönderiler listelenir ve detay sayfasında görüntülenebilir.

3. **Yorumlar**:
   - Kullanıcılar gönderilere yorum yapabilir.

4. **Admin Paneli**:
   - Yöneticiler, gönderileri ve yorumları yönetebilir.


#### **Tamamlanmış Bir Proje Örneği: Blog Sitesi**

1. **Proje Yapısı**:
   Django kullanarak bir blog sitesi oluşturacağız. Proje yapısı şu şekilde olacaktır:
   ```
   myblog/
   ├── manage.py
   ├── myblog/
   │   ├── settings.py
   │   ├── urls.py
   │   └── wsgi.py
   ├── posts/
   │   ├── models.py
   │   ├── views.py
   │   ├── urls.py
   │   └── templates/
   │       └── posts/
   │           ├── post_list.html
   │           └── post_detail.html
   └── users/
       ├── models.py
       ├── views.py
       └── templates/
           └── users/
               ├── login.html
               └── register.html
   ```

2. **Modeller (Models)**:
   ```python
   # posts/models.py
   from django.db import models
   from django.contrib.auth.models import User

   class Post(models.Model):
       title = models.CharField(max_length=200)  # Gönderi başlığı
       content = models.TextField()  # Gönderi içeriği
       author = models.ForeignKey(User, on_delete=models.CASCADE)  # Yazar
       created_at = models.DateTimeField(auto_now_add=True)  # Oluşturulma tarihi

       def __str__(self):
           return self.title  # Admin panelinde gönderi başlığını gösterir

   class Comment(models.Model):
       post = models.ForeignKey(Post, on_delete=models.CASCADE)  # Hangi gönderiye ait
       user = models.ForeignKey(User, on_delete=models.CASCADE)  # Yorum yapan kullanıcı
       text = models.TextField()  # Yorum metni
       created_at = models.DateTimeField(auto_now_add=True)  # Oluşturulma tarihi

       def __str__(self):
           return f"{self.user.username} - {self.text[:20]}"  # İlk 20 karakteri gösterir
   ```

   - `Post` modeli, blog gönderilerini temsil eder. `Comment` modeli ise gönderilere yapılan yorumları temsil eder.

3. **Görünümler (Views)**:
   ```python
   # posts/views.py
   from django.shortcuts import render, get_object_or_404
   from .models import Post, Comment
   from .forms import CommentForm

   def post_list(request):
       posts = Post.objects.all()  # Tüm gönderileri alır
       return render(request, "posts/post_list.html", {"posts": posts})  # Şablona gönderir

   def post_detail(request, pk):
       post = get_object_or_404(Post, pk=pk)  # Belirli bir gönderiyi alır
       if request.method == "POST":
           form = CommentForm(request.POST)  # Yorum formunu alır
           if form.is_valid():
               comment = form.save(commit=False)
               comment.post = post
               comment.user = request.user
               comment.save()  # Yorumu kaydeder
       else:
           form = CommentForm()
       return render(request, "posts/post_detail.html", {"post": post, "form": form})
   ```

   - `post_list`, tüm gönderileri listeler. `post_detail`, belirli bir gönderiyi ve yorumlarını gösterir.

4. **Şablonlar (Templates)**:
   ```html
   <!-- posts/templates/posts/post_list.html -->
   <h1>Gönderiler</h1>
   <ul>
       {% for post in posts %}
           <li>
               <a href="{% url 'post_detail' post.pk %}">{{ post.title }}</a>
               <p>{{ post.content|truncatewords:20 }}</p>  <!-- İçeriği kısaltır -->
           </li>
       {% endfor %}
   </ul>
   ```

   - Bu şablon, gönderi listesini gösterir. Her gönderi için bir bağlantı oluşturur.

5. **Formlar (Forms)**:
   ```python
   # posts/forms.py
   from django import forms
   from .models import Comment

   class CommentForm(forms.ModelForm):
       class Meta:
           model = Comment
           fields = ["text"]  # Yorum metnini içerir
   ```

   - `CommentForm`, yorum eklemek için kullanılan bir formdur.

6. **URL Yönlendirme**:
   ```python
   # posts/urls.py
   from django.urls import path
   from . import views

   urlpatterns = [
       path("", views.post_list, name="post_list"),  # Ana sayfa
       path("post/<int:pk>/", views.post_detail, name="post_detail"),  # Gönderi detayı
   ]
   ```

   - URL'ler, view fonksiyonlarına yönlendirir.

7. **Deployment**:
   Projeyi Heroku'ya dağıtmak için aşağıdaki adımları izleyin:
   ```bash
   # requirements.txt dosyası oluştur
   pip freeze > requirements.txt

   # Procfile oluştur
   echo "web: gunicorn myblog.wsgi" > Procfile

   # Git repository oluştur
   git init
   git add .
   git commit -m "Initial commit"

   # Heroku CLI ile deployment
   heroku create myblogapp
   git push heroku main
   heroku open
   ```
   - Bu adımlar, projenizi Heroku'ya dağıtır.


#### **Hata Ayıklama ve Performans Optimizasyonu**
1. **Debugging Tools**:
   Django'nun `DEBUG` modu ve `print()` ifadeleri, hata ayıklamada yardımcı olur.

2. **Query Optimizasyonu**:
   Veritabanı sorgularını optimize etmek için `select_related` ve `prefetch_related` kullanılır.

   ```python
   posts = Post.objects.select_related("author").all()
   ```
   - Bu kod, ilişkili yazar verilerini tek bir sorguda çeker.
