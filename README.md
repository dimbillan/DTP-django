
# 📚 Unattendance Tracking System (DTP - Django)

Üniversite öğrencileri için **devamsızlık takibi**, **ders yönetimi**, **duyuru sistemi** ve daha fazlasını sağlayan modüler ve ölçeklenebilir bir Django projesi.

## 🚀 Özellikler

- **Kullanıcı Yönetimi:** Kayıt, giriş, profil düzenleme (üniversite, fakülte, bölüm seçimiyle)
- **Akademik Yapı:** Üniversite → Fakülte → Bölüm hiyerarşisi
- **Ders Yönetimi:** Öğrenci ders istekleri, kayıt, katalog görüntüleme
- **Devamsızlık Takibi:** Kayıt oluşturma, belge yükleme, istatistiksel analiz
- **Duyurular:** Hedefli bildirimler ve ek dosyalarla destekli içerik
- **Modüler Mimari:** 6 ayrı Django app'iyle ayrılmış temiz yapı

## 🏗️ Proje Yapısı

```
unattendance_tracker/
├── apps/
│   ├── accounts/          # Kullanıcı yönetimi
│   ├── academic/          # Akademik yapı
│   ├── courses/           # Ders işlemleri
│   ├── unattendances/     # Devamsızlık modülü
│   ├── announcements/     # Duyurular
│   └── core/              # Ortak bileşenler (base view, mixin, template)
├── config/                # Ayarlar ve URL yönlendirme
├── static/ & media/       # Statik ve medya dosyaları
├── templates/             # Genel şablonlar
├── .env                   # Ortam değişkenleri
└── requirements.txt
```

## ⚙️ Kurulum

### 1. Ortamı Hazırla

```bash
git clone https://github.com/dimbillan/DTP-django.git
cd DTP-django
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 2. Ayarları Yap

`.env` dosyasını oluştur:

```env
DEBUG=True
SECRET_KEY=senin_secret_keyin
ALLOWED_HOSTS=127.0.0.1,localhost
DATABASE_URL=sqlite:///db.sqlite3
```

### 3. Veritabanını Kur

```bash
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser
```

### 4. Çalıştır

```bash
python manage.py runserver
```

## 🧩 Kullanılan Teknolojiler

- Django (multi-app architecture)
- PostgreSQL (opsiyonel)
- Bootstrap tabanlı frontend
- Django Templates
- Signal, Manager, Mixin gibi advanced pattern'lar

## 📁 Geliştirici Notları

- Tüm app’ler `apps/` klasörü altında yer alır.
- `config/settings/` altında `base`, `development`, `production`, `testing` ayrı ayrı tutulur.
- Ortak kodlar `core/` app'ine yazılır.
- `INSTALLED_APPS` içinde sıralama korunmalıdır.

## 📌 Yol Haritası (TODO)

- [ ] API endpoint’ler (DRF entegrasyonu)
- [ ] Testler (unit & integration)
- [ ] Dockerfile ve docker-compose desteği
- [ ] CI/CD entegrasyonu

## 🤝 Katkı Sağlamak

PR’lar, issue’lar, öneriler baş tacı. Forkla, geliştir, gönder. 👊

---

**Lisans:** MIT  
**Yapanlar:** @dimbillan ve ekip
