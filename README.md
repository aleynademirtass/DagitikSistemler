
# 🚀 Dağıtık Sistemler İçin Spring Boot + Nginx + PostgreSQL + Redis

Bu proje, **yük dengeleme**, **önbellekleme** ve **dağıtık yapı** özellikleriyle ölçeklenebilir bir **Spring Boot** uygulaması oluşturmak için geliştirilmiştir. **Docker Compose** kullanarak, aşağıdaki servisleri tek bir komutla ayağa kaldırabilirsiniz:  

- **Nginx** → Yük dengeleyici olarak çalışır.  
- **Spring Boot (2 replika)** → Backend servisimizdir.  
- **PostgreSQL** → Veritabanı olarak kullanılır.  
- **Redis** → Önbellekleme mekanizmasıdır.  

---

## 📌 Proje İçeriği  

**1️⃣ Nginx (nginx.conf)**  
- **Gelen HTTP isteklerini Spring Boot uygulamasına yönlendirir.**  
- **Yük dengelemesi yaparak birden fazla backend servisi yönetir.**  
- **Özel hata sayfaları tanımlıdır.**  

**2️⃣ Spring Boot (app)**  
- **PostgreSQL veritabanı ile bağlantılıdır.**  
- **Redis önbellekleme mekanizmasını kullanır.**  
- **İki replikasyonlu olarak çalışır.**  

**3️⃣ PostgreSQL (db)**  
- **Spring Boot uygulamasının veritabanı olarak kullanılır.**  
- **Docker volume ile kalıcı veri saklama özelliğine sahiptir.**  

**4️⃣ Redis (redis_cache)**  
- **Spring Boot tarafından cacheleme için kullanılır.**  
- **Uygulama performansını artırır.**  

---

## 🛠️ Kurulum ve Çalıştırma  

Projenin çalıştırılması için **Docker ve Docker Compose** yüklü olmalıdır.  

1️⃣ *Docker ve Docker Compose’un yüklü olduğundan emin olun:*  
  
   docker -v
   docker-compose -v
2️⃣ *Projeyi klonlayın:*
git clone https://github.com/kullaniciadi/proje-adi.git
cd proje-adi
3️⃣ *Docker Compose ile servisleri başlatın:*
docker-compose up -d --build
4️⃣ *Çalışan servisleri kontrol edin:*
docker ps

5️⃣ *Tarayıcıdan erişin:*
http://localhost/

🔥 Nasıl Çalışıyor?
Nginx, gelen HTTP isteklerini Spring Boot backend servisine yönlendirir.
Spring Boot uygulaması, PostgreSQL ile çalışır ve Redis’i önbellekleme için kullanır.
Spring Boot uygulaması 2 replikaya sahip olduğu için yük dengeleme işlemi yapılır.
Tüm bileşenler Docker Compose ile container içinde yönetilir.

