# Syngenta Türkiye - Amacımız & Omurgamız

> SharePoint sitesinin (`Our Purpose & Backbone`) Türkçe statik versiyonu. GitHub Pages üzerinde yayınlanmak üzere hazırlandı.

## 📂 Dosya yapısı

```
syngenta-amac-omurga/
├── index.html                       Ana sayfa (5 panelli hero grid)
├── omurgamiz.html                   Omurgamız
├── amacimiz.html                    Amacımız
├── hedefimiz-ve-stratejimiz.html    Hedefimiz ve Stratejimiz
├── davranislarimiz.html             Davranışlarımız (4 davranış)
├── hikayemiz.html                   Hikayemiz (8 hikaye accordion)
├── styles.css                       Ortak stil dosyası
└── README.md                        Bu dosya
```

## 🚀 GitHub Pages'e Yayınlama

### 1. Repo oluştur
```bash
cd syngenta-amac-omurga
git init
git add .
git commit -m "Initial: Amacımız & Omurgamız Türkçe versiyon"
```

### 2. GitHub'da yeni repo aç
- `syngenta-amac-omurga` adıyla
- Public veya Private (Pages için Pro hesap gerekir Private'da)

### 3. Push et
```bash
git remote add origin https://github.com/koselerkubra-bot/syngenta-amac-omurga.git
git branch -M main
git push -u origin main
```

### 4. Pages aktif et
- Repo → **Settings** → **Pages**
- **Source**: Deploy from a branch
- **Branch**: `main` / `/ (root)`
- **Save**

Birkaç dakika sonra şu adreste yayında olacak:
**https://koselerkubra-bot.github.io/syngenta-amac-omurga/**

## ⚠️ DEPLOY ÖNCESİ YAPILACAKLAR

### 1. Tagline finalist swap
Tagline placeholder olarak kullanılmış. Viva Engage oylama sonucuna göre değiştirilecek alanlar:

| Dosya | Konum | Mevcut placeholder |
|---|---|---|
| `index.html` | `.tagline-overlay` içinde | "Çiftçiler için çığır açan çözümler, her tarlada™" |
| `amacimiz.html` | `.tagline-wordmark` içinde | aynı metin |
| `hikayemiz.html` | İçerik metinleri | aynı metin (3 yerde geçiyor) |

**Tek seferde değiştirmek için** `find & replace`:
- Bul: `Çiftçiler için çığır açan çözümler, her tarlada`
- Değiştir: [Final Türkçe tagline]

HTML dosyalarında `TAGLINE FİNALİSTİ:` yorum satırlarıyla işaretlendi.

### 2. Marka materyalleri linklerini güncelle
Sayfalardaki `<a href="#" class="asset-btn">...` linkleri SharePoint kaynaklarına işaret etmiyor (placeholder `#`). Gerçek SharePoint linkleriyle güncelle. Sayfalar:
- `amacimiz.html` - Trinity marka materyalleri (3 link)
- `omurgamiz.html` - Omurga materyalleri (3 link)
- 8 hikayedeki "Devamını oku" butonları

### 3. Görseller
Şu anda CSS gradient placeholder'lar kullanılıyor. Gerçek Syngenta görselleri için:
- `assets/` klasörü oluştur
- Görselleri buraya yükle
- CSS'de `.hero-*` class'larındaki `background:` özelliklerini gerçek görsel URL'leriyle değiştir

Örnek:
```css
.hero-purpose {
  background: url('assets/purpose-hero.jpg') center/cover, linear-gradient(...);
}
```

### 4. Video embed'ler
`video-placeholder` div'leri var. Gerçek video embed için (Stream / YouTube / Vimeo):
```html
<iframe src="STREAM_URL" width="100%" height="320" frameborder="0" allowfullscreen></iframe>
```

## 🎨 Brand Renkleri

`styles.css` içinde tanımlı (`:root`):
- Magenta: `#C8017E`
- Magenta deep: `#A8016B`
- Green: `#95D600`
- Dark: `#1A1A1A`

## 🌐 Çeviri Notları

Kullanılan ana çeviriler:
| EN | TR |
|---|---|
| Our Purpose | Amacımız |
| Our Backbone | Omurgamız |
| Our Ambition | Hedefimiz |
| Our Strategy | Stratejimiz |
| Our Behaviors | Davranışlarımız |
| Our Story | Hikayemiz |
| Collaborative | İşbirlikçi |
| Curious | Meraklı |
| Courageous | Cesur |
| Accountable | Hesap Verebilir |
| Breakthrough Stories | Çığır Açan Hikayelerimiz |
| Microskills | Mikro Becerilerimiz |

## 📱 Responsive

3 breakpoint var:
- `> 980px`: tam desktop layout
- `≤ 980px`: tablet/küçük desktop (kolon sayıları azalır)
- `≤ 600px`: mobile (tek kolon)

## 📝 Lokal test

```bash
cd syngenta-amac-omurga
python3 -m http.server 8000
# Tarayıcıda: http://localhost:8000
```

---

**Hazırlayan:** Kubra Koseler için Claude
**Versiyon:** 1.0 (Türkçe statik mirror)
**Son güncelleme:** Haziran 2026
