# Docker-Compose-Projesi

 Docker Compose ile Çok Katmanlı Uygulama
Bu proje, üç farklı bileşenden oluşan bir sistemin Docker Compose kullanılarak ayağa kaldırılmasını sağlar:

PostgreSQL veritabanı

Spring Boot tabanlı bir backend uygulaması

React.js ile geliştirilmiş bir frontend arayüzü

Tüm servisler birbiriyle izole ama iletişim halinde olacak şekilde yapılandırılmıştır.

📁 Proje Yapısı
bash
Kopyala
Düzenle
.
├── backend/
│   └── Dockerfile
├── frontend/
│   └── Dockerfile
├── docker-compose.yml
🔧 Kullanılan Servisler
1. 🛠 backend
Teknoloji: Spring Boot

Port: 8080:8080

Bağlantı: PostgreSQL veritabanına bağlanır.

Bağımlılık: db servisine depends_on özelliği ile bağlıdır.

2. 🎨 frontend
Teknoloji: React.js

Port: 3000:3000

Bağlantı: Arka uç servis olan backend ile HTTP üzerinden iletişim kurar.

3. 🗄️ db
Teknoloji: PostgreSQL

Görünen Port: 5432:5432

Kullanıcı: postgres

Şifre: root

Veritabanı adı: rent_a_car

🚀 Uygulamayı Başlatma
Tüm servisleri başlatmak için terminalden şu komutu çalıştırın:

bash
Kopyala
Düzenle
docker-compose up --build
Ardından aşağıdaki adreslerden servislere erişebilirsiniz:

Frontend: http://localhost:3000

Backend: http://localhost:8080

PostgreSQL: localhost:5432 (Dışarıdan bağlantı için)

🧹 Temizlik
Tüm konteynerleri durdurmak ve ağları kaldırmak için:

bash
Kopyala
Düzenle
docker-compose down
⚠️ Notlar
PostgreSQL verileri için bir volume tanımlanmadığı için konteyner silinirse veriler kaybolur.

Geliştirme sırasında restart: always özelliği kullanılmamalıdır.

React uygulaması için .env dosyasına backend adresini eklemeyi unutmayın.

