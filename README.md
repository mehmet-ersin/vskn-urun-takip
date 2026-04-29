# İskenderun Limanı VSKN - Ürün Takip Sistemi

## 🎯 Amaç
Veteriner Sınır Kontrol Noktası'nda işlenen uygunsuzluk kayıtlarını (Excel'den okunan) sorgulamak için web uygulaması.

## 📂 Proje Yapısı
```
yeni proje/
├── server.py              # Flask backend (API)
├── public/
│   ├── index.html          # Frontend (güncellenmiş, logo entegre)
│   └── logo1.png           # Logo resmi
├── veriler/
│   ├── UYGUNSUZLUK VE GERİ DÖNEN ÜRÜN TAKİP2.xlsx
│   └── serbest dolaşım uygunsuzluk.xlsx
├── package.json
└── README.md               # Bu dosya
```

## 🚀 Çalıştırma
```bash
cd "/home/mehmet-ersin/Belgeler/yeni proje"
python3 server.py
```
Sunucu: http://127.0.0.1:5000 (ve ağdan http://192.168.0.69:5000)

## ✅ Yapılanlar
- [x] server.py — 1762 kayıt yüklü, API endpoint'leri: `/api/sorgula`, `/api/kayitlar`
- [x] index.html — mevcut API'ye tam uyumlu, tablo görünümü, sıralama, istatistik kartları
- [x] Logo entegrasyonu — `logo1.png` header'da gösteriliyor
- [x] Excel dosyaları mevcut ve okunuyor
- [x] Çift içerik sorunu temizlendi (index.html ve server.py tek versiyon)

## 📌 Yapılacaklar / Potansiyel Geliştirmeler
- GTIP/barkod sorgulama eklenebilir
- Firma bilgisi sorgulama eklenebilir
- Tarih filtresi eklenebilir
- Sayfalama (şu an 200 kayıt limiti var, sayfalama yapılabilir)
- PDF/Excel rapor çıktısı eklenebilir
