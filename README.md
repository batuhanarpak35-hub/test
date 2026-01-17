# MOORTINY House - Full-Stack Tiny House Website

Türkiye'nin tiny house uzmanı MOORTINY için geliştirilen production-ready, full-stack web uygulaması.

## Özellikler

### Public Website
- Ana sayfa (hero, featured models, benefits, CTA)
- Modeller sayfası (grid layout, filtreleme)
- Model detay sayfaları (galeri, teknik özellikler)
- Blog (SEO odaklı içerik)
- Teklif formu (il/ilçe seçimi)
- İletişim sayfası

### Admin Panel
- Dashboard (istatistikler, son teklifler)
- Model yönetimi (CRUD işlemleri)
- Blog yönetimi (CRUD işlemleri)
- Teklif yönetimi (liste, durum takibi)
- Supabase Auth ile güvenli giriş

### Teknik Özellikler
- Next.js 15 App Router
- TypeScript
- Tailwind CSS v4
- Supabase (PostgreSQL + Auth)
- Server Components (SEO için SSR)
- Row Level Security (RLS)
- Responsive tasarım
- SEO optimize edilmiş
- Dinamik sitemap ve robots.txt

## Kurulum

### 1. Proje Dosyalarını İndirin
Bu projeyi v0.dev üzerinden bilgisayarınıza indirin.

### 2. Bağımlılıkları Yükleyin
```bash
npm install
```

### 3. Supabase Bağlantısı
Proje zaten Supabase ile bağlantılı durumda. Environment variables otomatik olarak tanımlı:
- `NEXT_PUBLIC_SUPABASE_URL`
- `NEXT_PUBLIC_SUPABASE_ANON_KEY`

### 4. Veritabanı
Veritabanı tabloları ve örnek veriler zaten oluşturuldu:
- `users` - Admin kullanıcılar
- `tiny_house_models` - Tiny house modelleri
- `model_images` - Model görselleri
- `blog_posts` - Blog yazıları
- `quotes` - Teklif talepleri
- `site_settings` - Site ayarları

### 5. Admin Girişi
**Admin Bilgileri:**
- E-posta: `admin@moortiny.com`
- Şifre: `Admin123!`

Admin paneline giriş için: `/admin/giris`

### 6. Geliştirme Sunucusunu Başlatın
```bash
npm run dev
```

Uygulama `http://localhost:3000` adresinde çalışacaktır.

## Deployment (Vercel)

### 1. GitHub'a Push
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin YOUR_GITHUB_REPO
git push -u origin main
```

### 2. Vercel'e Deploy
1. Vercel dashboard'a gidin
2. "New Project" tıklayın
3. GitHub repo'nuzu seçin
4. Deploy edin

Environment variables otomatik olarak Supabase entegrasyonu sayesinde tanımlıdır.

## Proje Yapısı

```
moortiny-house/
├── app/
│   ├── (public)/          # Public sayfalar (Header + Footer ile)
│   │   ├── page.tsx       # Ana sayfa
│   │   ├── modeller/      # Modeller
│   │   ├── blog/          # Blog
│   │   ├── teklif/        # Teklif formu
│   │   └── iletisim/      # İletişim
│   ├── admin/             # Admin panel (Auth korumalı)
│   │   ├── giris/         # Login
│   │   ├── page.tsx       # Dashboard
│   │   ├── modeller/      # Model yönetimi
│   │   ├── blog/          # Blog yönetimi
│   │   ├── teklifler/     # Teklif yönetimi
│   │   └── ayarlar/       # Ayarlar
│   ├── sitemap.ts         # Dinamik sitemap
│   └── robots.ts          # robots.txt
├── components/
│   ├── layout/            # Header, Footer, AdminNav
│   └── forms/             # Form bileşenleri
├── lib/
│   ├── supabase/          # Supabase client/server
│   ├── types.ts           # TypeScript tipleri
│   └── utils.ts           # Yardımcı fonksiyonlar
├── scripts/
│   ├── 01-create-database-schema.sql
│   └── 02-seed-data.sql
└── proxy.ts               # Middleware (auth koruma)
```

## SEO Özellikleri

- Server-side rendering (SSR)
- Dinamik meta tags
- Open Graph tags
- Twitter Cards
- Structured data (LocalBusiness)
- Dinamik XML sitemap
- robots.txt
- Türkçe SEO-friendly URL'ler
- Alt text'ler
- Semantic HTML

## Güvenlik

- Supabase Auth (JWT tokens)
- Row Level Security (RLS)
- HTTP-only cookies
- Middleware ile route koruması
- bcrypt şifre hashleme
- CSRF koruması

## Özelleştirme

### Renk Paleti
`app/globals.css` dosyasında design tokens'ları düzenleyin:
- `--primary`: Ana renk (kahverengi/amber)
- `--secondary`: İkincil renk (yeşil)
- `--accent`: Vurgu rengi

### İletişim Bilgileri
`components/layout/footer.tsx` dosyasını düzenleyin.

### Logo
Header'daki "MOORTINY" tekstini logo görseli ile değiştirin.

## Destek

Sorularınız için: info@moortiny.com

## Lisans

© 2026 MOORTINY House. Tüm hakları saklıdır.
