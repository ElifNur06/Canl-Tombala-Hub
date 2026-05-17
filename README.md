# 🎲 Canlı Tombala Hub (Live Bingo Hub)

![Python](https://img.shields.io/badge/Python-3.13-blue?style=for-the-badge&logo=python)
![Flask](https://img.shields.io/badge/Flask-3.0-black?style=for-the-badge&logo=flask)
![Socket.IO](https://img.shields.io/badge/Socket.IO-RealTime-black?style=for-the-badge&logo=socket.io)
![SQLite](https://img.shields.io/badge/SQLite-Database-003B57?style=for-the-badge&logo=sqlite)

Modern web teknolojileri ile geliştirilmiş, **gerçek zamanlı**, **ölçeklenebilir** ve **kriptografik olarak adil (Provably Fair)** yeni nesil çok oyunculu tombala platformu.

Monolitik mimariden olay güdümlü (event-driven) ve bağımsız iş parçacığı tabanlı (threading) bir altyapıya evrilen bu proje; Python 3.13 standartlarında dış kütüphane kilitlenmelerini (Eventlet, Celery, Redis vb.) sıfıra indirerek kusursuz bir performans sunar.

---

## ✨ Öne Çıkan Özellikler

* **🛡️ Sunucu Taraflı Hile Koruması (Anti-Cheat):** İstemci tarafındaki (DOM) manipülasyonlara karşı tam koruma. Tüm kart işaretlemeleri ve kazanım iddiaları doğrudan veritabanı şeması üzerinden sunucuda doğrulanır.
* **🔐 Provably Fair (Adil Oyun):** Her oyun odasında `game_hash` ve `game_salt` algoritmaları (SHA-256) kullanılarak çekilen sayıların %100 rastgele ve manipüle edilemez olduğu matematiksel olarak garanti altına alınır.
* **⚡ Asenkron Thread Mimarisi:** Oyun döngüleri, ana web sunucusunu kilitlemeyen yerel `threading.Thread` arka plan işçileri (daemon) tarafından saniyesi saniyesine yönetilir.
* **🎫 Dinamik Çoklu Bilet & Oto-İşaretleme (Auto-Daub):** Oyuncular aynı anda diledikleri kadar bilet satın alabilir. İsteğe bağlı açılıp kapanabilen "Oto-İşaretleme" modu ile kazanan numaralar kartlarda anında kırmızıya boyanır.
* **💬 Gerçek Zamanlı Sosyal Lobi:** WebSockets (`Socket.IO`) aracılığıyla gecikmesiz (latency-free) canlı sohbet ve sistem durum bildirimleri.

---
## Görseller
<img width="1154" height="649" alt="image" src="https://github.com/user-attachments/assets/7f0e2b9b-685d-4f41-8d16-91298aba8f11" />
<img width="1157" height="649" alt="image" src="https://github.com/user-attachments/assets/e38f1259-5ec9-4df6-9767-ff99cc3586c9" />
<img width="1154" height="646" alt="image" src="https://github.com/user-attachments/assets/7d71ae15-087f-4c92-bf16-c0530221e607" />
<img width="1158" height="647" alt="image" src="https://github.com/user-attachments/assets/c590e5e3-41d3-4907-a856-a730f99e5d78" />
<img width="1157" height="646" alt="image" src="https://github.com/user-attachments/assets/a898feb2-67ba-4eea-b4bd-87d4be7a9d27" />


## 🛠️ Kullanılan Teknolojiler

**Backend:**
* Python 3.13
* Flask (Web Framework)
* Flask-SocketIO (WebSocket & Event Driven İletişim)
* SQLAlchemy (ORM) & SQLite (Veritabanı)
* Flask-CORS

**Frontend:**
* HTML5 & CSS3 (Glassmorphism & Siber Neon Dark Teması)
* Vanilla JavaScript (ES6+)
* Socket.IO Client API

---
## 🎮 Nasıl Oynanır?
Lobiye girdikten sonra sağ alttaki [ADMIN] Yeni Oyun Başlat butonuna basarak ilk odayı oluşturun (Oda ilk 10 saniye bilet alımları için bekleme modunda kalır).
+1 Kart Al butonuna tıklayarak siber-neon tasarımlı biletlerinizi ekrana dizin.
Arka plandaki Thread 4 saniyede bir yeni numara çekecek ve numaralar ekranınızdaki genel tabelada belirecektir.
İster manuel olarak biletinizdeki numaralara tıklayarak heyecanı yaşayın, isterseniz Oto-İşaretleme modunu açarak arkanıza yaslanın!


## 📁 Proje Klasör Yapısı
canli-tombala-hub/
│
├── backend/
│   ├── app.py                  # Ana sunucu ve API yönlendirmeleri
│   ├── models.py               # SQLAlchemy Veritabanı şemaları (Game, Player)
│   ├── socket_manager.py       # WebSocket olayları (join, send_message)
│   ├── game_engine.py          # Tombala kart matrisi ve kazanım mantığı algoritmaları
│   ├── requirements.txt        # Proje bağımlılıkları
│   └── tombala_database.db     # Otomatik oluşturulan SQLite veritabanı
│
└── frontend/
    ├── index.html              # Neon arayüz
    ├── style.css               # Glassmorphism ve animasyon stilleri
    └── app.js                  # DOM etkileşimleri ve Socket.IO istemcisi

Geliştirici: Elif Nur Ayhan | © 2026 Canlı Tombala Hub
