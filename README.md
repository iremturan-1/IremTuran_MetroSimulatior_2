Bu proje, İstanbul metrolarında en kısa ve en hızlı rotaları bulmak için geliştirilmiş bir rota planlama uygulamasıdır. Kullanıcıların başlangıç ve varış noktalarını seçerek:

En az aktarmalı rotayı (BFS algoritması ile)

En kısa süreli rotayı (A* algoritması ile)

bulmalarını sağlar. Gerçek İstanbul metro hatları ve istasyonları temel alınarak oluşturulmuştur.

2. Kullanılan Teknolojiler ve Kütüphaneler
Python Kütüphaneleri:
collections:

defaultdict: Sözlük yapısına varsayılan değer atama özelliği ekler

deque: Çift uçlu kuyruk yapısı, BFS algoritmasında kullanıldı

heapq: Öncelik kuyruğu (priority queue) yapısı, A* algoritmasında kullanıldı

typing: Python tip ipuçları (type hints) için kullanıldı

Veri Yapıları:
Graf yapısı (istasyonlar düğüm, bağlantılar kenar olarak)

Komşuluk listesi (adjacency list) ile metro ağı temsili

3. Algoritmaların Çalışma Mantığı
BFS (Breadth-First Search) Algoritması
Nasıl Çalışır?

Başlangıç düğümünden başlar, tüm komşuları keşfeder

Sonra komşuların komşularını keşfetmeye devam eder

Seviye seviye (katman katman) ilerler

Hedefe ulaşınca durur

Neden Kullandık?

En az aktarmalı rotayı garantiler

Ağırlıksız graf (weighted graph) için uygundur

Basit ve etkili bir algoritmadır

A* (A-Star) Algoritması
Nasıl Çalışır?

Her düğüm için maliyet fonksiyonu (f(n) = g(n) + h(n)) hesaplar

g(n): Başlangıçtan o düğüme olan gerçek maliyet

h(n): Düğümden hedefe tahmini maliyet (heuristic)

En düşük maliyetli düğümleri öncelikle işler

Hedefe ulaşınca durur

Neden Kullandık?

En kısa süreli rotayı bulmak için ideal

Gerçek dünya problemlerinde etkilidir

Dijkstra'dan daha verimli çalışır (heuristic sayesinde)

4. Örnek Kullanım ve Test Sonuçları
Senaryo 1: Kadıköy'den Taksim'e
Copy
En az aktarmalı rota: 
Kadıköy (M4) -> Ayrılık Çeşmesi (M4) -> Ayrılık Çeşmesi (Marmaray) -> Yenikapı (Marmaray) -> Yenikapı (M2) -> Vezneciler (M2) -> Taksim (M2)

En hızlı rota (24 dakika): 
Kadıköy (M4) -> Ayrılık Çeşmesi (M4) -> Ayrılık Çeşmesi (Marmaray) -> Yenikapı (Marmaray) -> Yenikapı (M2) -> Vezneciler (M2) -> Taksim (M2)
Senaryo 2: Atatürk Havalimanı'ndan Kadıköy'e
Copy
En az aktarmalı rota: 
Atatürk Havalimanı (M1A) -> Ulubatlı (M1A) -> Emniyet (M1A) -> Aksaray (M1A) -> Yenikapı (M1A) -> Yenikapı (Marmaray) -> Ayrılık Çeşmesi (Marmaray) -> Ayrılık Çeşmesi (M4) -> Kadıköy (M4)

En hızlı rota (29 dakika): 
Atatürk Havalimanı (M1A) -> Ulubatlı (M1A) -> Emniyet (M1A) -> Aksaray (M1A) -> Yenikapı (M1A) -> Yenikapı (Marmaray) -> Ayrılık Çeşmesi (Marmaray) -> Ayrılık Çeşmesi (M4) -> Kadıköy (M4)
5. Projeyi Geliştirme Fikirleri
Gerçek Zamanlı Veri Entegrasyonu:

İETT'nin gerçek zamanlı metro verilerini çekerek güncel bilgilerle çalışma

GUI Arayüzü:

PyQt veya Tkinter ile kullanıcı dostu bir arayüz ekleme

İnteraktif metro haritası oluşturma

Ek Özellikler:

Engelli erişim bilgileri

Yoğunluk verilerine göre rota önerileri

Tarihi/sanatsal istasyonları vurgulama

Mobil Uygulama:

Kivy veya Flutter ile mobil uygulama geliştirme

Veritabanı Entegrasyonu:

İstasyon bilgilerini SQLite veya MongoDB'de saklama

Çoklu Ulaşım Modları:

Metro, tramvay, otobüs, vapur entegrasyonu

Yürüme sürelerini hesaba katma
