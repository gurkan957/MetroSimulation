# 🚇 Sürücüsüz Metro Simülasyonu

Bu proje, Python kullanılarak geliştirilen bir sürücüsüz metro simülasyonudur. A* ve BFS algoritmaları kullanılarak, belirlenen metro durakları arasındaki en kısa ve en az aktarmalı rotalar hesaplanır. Ankara ve İstanbul'dan bazı metro durakları önceden tanımlıdır.

---

## 🛠 Kullanılan Teknolojiler ve Kütüphaneler

Bu proje, Python'un standart kütüphaneleri ile geliştirilmiştir.

- Python 3.x*: Projenin ana programlama dili.
- heapq: A* algoritması için öncelikli kuyruk (priority queue) yapısını sağlamak amacıyla kullanılmıştır.
- collections.deque: BFS algoritmasında kullanılan çift uçlu kuyruk veri yapısını sağlar.
- math: A* algoritmasında iki nokta arasındaki Öklid mesafesini hesaplamak için kullanılmıştır.

---

## 🔍 Algoritmaların Çalışma Mantığı

### 📌 BFS (Breadth-First Search)
BFS, graf üzerindeki tüm yolları genişlik öncelikli olarak tarayan bir algoritmadır.

- Başlangıç noktasından itibaren her komşu durak ziyaret edilir.
- FIFO (First In, First Out) mantığı ile çalışarak öncelikle en yakın düğümleri inceler.
- Avantajı: En az durak değiştirerek hedefe ulaşan yolu garantiler.
- Dezavantajı: A*'ye göre daha yavaş çalışabilir, çünkü maliyetleri hesaba katmaz.

### 🌟 A* (A Star) Algoritması
A* algoritması, en iyi yolu bulmak için sezgisel (heuristic) bir yaklaşımla çalışır.

- Her durak için bir maliyet fonksiyonu hesaplar: f(n) = g(n) + h(n)
  - g(n): Başlangıç noktasından o durağa kadar olan gerçek maliyet.
  - h(n): Heuristik tahmin (genellikle Öklid mesafesi veya Manhattan mesafesi kullanılır).
- En düşük f(n) değerine sahip düğümler öncelikli olarak ziyaret edilir.
- *Avantajı*: Daha kısa sürede en iyi sonucu bulur.
- *Dezavantajı*: BFS'ye kıyasla biraz daha karmaşıktır ve ekstra hesaplama gerektirir.

---

## 🚀 Neden Bu Algoritmalar Kullanıldı?

- *BFS*: En az aktarma ile gidilebilecek en kısa yolu bulmak için kullanıldı.
- *A**: Duraklar arası mesafeyi hesaba katarak zaman açısından en verimli güzergahı belirlemek için kullanıldı.

---

## 📊 Test Sonuçları

### 🏙 İstanbul Metro Test Senaryoları

#### 1️⃣ Haliç -> Levent

- En az aktarmalı rota: Haliç -> Taksim -> Levent
- En hızlı rota (16 dakika): Haliç -> Taksim -> Levent

#### 2️⃣ Yenikapı -> Söğütlüçeşme

- En az aktarmalı rota: Yenikapı -> Merter -> Zincirlikuyu -> Altunizade -> Söğütlüçeşme
- En hızlı rota (76 dakika): Yenikapı -> Merter -> Zincirlikuyu -> Altunizade -> Söğütlüçeşme

#### 3️⃣ Merter -> Altunizade

- En az aktarmalı rota: Merter -> Zincirlikuyu -> Altunizade
- En hızlı rota (40 dakika): Merter -> Zincirlikuyu -> Altunizade

### 🏙 Ankara Metro Test Senaryoları

#### 4️⃣ AŞTİ -> OSB

- En az aktarmalı rota: AŞTİ -> Kızılay -> Ulus -> Demetevler -> OSB
- En hızlı rota (25 dakika): AŞTİ -> Kızılay -> Ulus -> Demetevler -> OSB

#### 5️⃣ Demetevler -> Keçiören

- En az aktarmalı rota: Demetevler -> Gar -> Keçiören
- En hızlı rota (14 dakika): Demetevler -> Gar -> Keçiören

#### 6️⃣ Keçiören -> AŞTİ

- En az aktarmalı rota: Keçiören -> Gar -> Sıhhiye -> Kızılay -> AŞTİ
- En hızlı rota (19 dakika): Keçiören -> Gar -> Sıhhiye -> Kızılay -> AŞTİ

---

## 💡 Projeyi Geliştirme Fikirleri

- Daha fazla şehir ekleme: Şu an sadece Ankara ve İstanbul durakları tanımlı, diğer şehirlerin metro sistemleri de eklenebilir.
- Harita entegrasyonu: Durakların harita üzerinde görselleştirilmesi için bir arayüz geliştirilebilir.
- Gerçek zamanlı trafik durumu: Metro yoğunluğu veya sefer sıklığını dikkate alan bir sistem entegre edilebilir.
- Veritabanı bağlantısı: Durak bilgileri ve mesafeler için bir SQL veya NoSQL veritabanı entegrasyonu yapılabilir.

📌 Bu projeyi geliştirmek isterseniz, pull request gönderebilir veya issue açabilirsiniz! 🚀
