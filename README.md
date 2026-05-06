# İskenderun Limanı VSKN - Ürün Takip Sistemi

## 🎯 Amaç
Veteriner Sınır Kontrol Noktası'nda işlenen uygunsuzluk kayıtlarını (Excel'den okunan) sorgulamak için web uygulaması.

## 🌐 Canlı
**https://vskn-urun-takipp.onrender.com**

## 📂 Proje Yapısı
```
yeni proje/
├── server.py              # Flask backend (API)
├── public/
│   ├── index.html         # Frontend (arayüz, logo, bayrak)
│   ├── logo1.png          # VSKN Logosu
│   └── bayrak-ve-ataturk.png
├── veriler/
│   └── UYGUNSUZLUK VE GERİ DÖNEN ÜRÜN TAKİP.xlsx  # 1853 kayıt
├── requirements.txt       # Flask, openpyxl, gunicorn, flask-cors
├── UYGUNSUZLUK VE GERİ DÖNEN ÜRÜN TAKİP(1).xlsx  # Ana kaynak Excel
└── README.md
```

## 🚀 Yerelde Çalıştırma
```bash
cd "/home/mehmet-ersin/Belgeler/yeni proje"
python3 server.py
```
Sunucu: http://127.0.0.1:5000

## 📊 Veri
- **1853 kayıt** (4 sayfa)
- Kategoriler: **İthalat**, **İhracattan Geri Dönen Ürün**, **Transit**, **Gemi Kumanyası**

## 🔧 Önemli Değişiklikler (Mayıs 2026)
- [x] Yeni Excel eklendi (1853 kayıt, eski Exceller silindi)
- [x] "Serbest Dolaşım" → **"İthalat"** olarak değiştirildi
- [x] RED/UYGUN karar etiketleri **sadece İhracattan Geri Dönen**'de gösteriliyor
- [x] Render uyumluluğu (PORT env, debug kapalı, gunicorn)
- [x] GitHub: https://github.com/mehmet-ersin/vskn-urun-takip

## 🔄 Güncelleme (GitHub → Render)
```bash
git add -A
git commit -m "yapılan değişiklik"
git push origin main
```
Render Dashboard → Manual Deploy → Deploy latest commit

## 📌 Potansiyel Geliştirmeler
- GTIP/barkod sorgulama
- Firma bilgisi sorgulama
- Tarih filtresi
- Sayfalama (şu an 200 kayıt limiti)
- PDF/Excel rapor çıktısı

## 📜 API
| Endpoint | Method | Açıklama |
|----------|--------|----------|
| `/api/sorgula` | POST | Ürün adı ve ülkeye göre sorgulama |
| `/api/kayitlar` | GET | İlk 100 kaydı getirir |
| `/api/son-guncelleme` | GET | Toplam kayıt ve son güncelleme tarihi |
