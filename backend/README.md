# Kampüs Etkinlikleri - Backend (Sprint 8)

Bu proje, Express.js ve MongoDB/Mongoose kullanılarak geliştirilmiş, kalıcı veri saklama yeteneğine sahip bir REST API backend servisidir. Üniversite kampüs etkinliklerinin yönetilmesi ve listelenmesi amacıyla hazırlanmıştır.

## Öğrenci Bilgileri
* **Ad Soyad:** Deniz Karanfil
* **Öğrenci Numarası:** 2416501047

---

## Kurulum ve Çalıştırma

Projeyi yerel ortamınızda veya Atlas bağlantısıyla çalıştırmak için sırasıyla şu adımları izleyin:

1. Bağımlılıkları yükleyin:
   ```bash
   npm install
   ```

2. Ortam değişkenlerini (`.env`) ayarlayın (`.env.example` dosyasını baz alarak `.env` oluşturun):
   ```env
   PORT=3000
   MONGODB_URI=mongodb://127.0.0.1:27017/kampus
   ```
   *(MongoDB Atlas kullanıyorsanız Atlas connection string'inizi `MONGODB_URI` değerine yazın)*

3. Veritabanını örnek verilerle doldurun (Seed):
   ```bash
   npm run seed
   ```

4. Geliştirme modunda sunucuyu başlatın:
   ```bash
   npm run dev
   ```

---

## API Uç Noktaları ve Durum Kodları

| Metot | Endpoint | Açıklama | Başarı Kodu | Hata Kodu |
| :--- | :--- | :--- | :--- | :--- |
| **GET** | `/health` | Sistem sağlık kontrolü, zaman ve öğrenci numarasını döner | `200 OK` | - |
| **GET** | `/events` | Veritabanındaki tüm etkinlikleri tarihe göre sıralı listeler | `200 OK` | - |
| **GET** | `/events/:id` | `_id` değerine göre tek bir etkinliğin detayını getirir | `200 OK` | `404 Not Found` |
| **POST** | `/events` | Schema doğrulamasıyla sisteme yeni bir etkinlik ekler | `201 Created` | `400 Bad Request` |

---

## Test İstekleri (Postman)
Tüm test istekleri `backend/requests/kampus-api.json` dosyası altında yer almaktadır. Postman'a **Import** ederek tüm testleri tek tıkla gerçekleştirebilirsiniz.
