# Ai Merkezi — Marketim yasal siteleri

Statik gizlilik politikası ve kullanım koşulları. Marka: **Ai Merkezi** · Ürün: **Marketim** (`app.xewn.marketim`).

Hedef URL’ler:

| Sayfa | URL |
|-------|-----|
| Ana | https://aimerkezi.site/ |
| Gizlilik | https://aimerkezi.site/gizlilik |
| Kullanım koşulları | https://aimerkezi.site/kullanim-kosullari |

`www.aimerkezi.site` de bağlanırsa aynı path’ler geçerlidir.

---

## RevenueCat’e yapıştırılacak URL’ler

Vercel’de domain’i `aimerkezi.site` yaptıktan sonra RevenueCat (Privacy / Terms) alanlarına **birebir** şunları girin:

```
Privacy → https://aimerkezi.site/gizlilik
Terms   → https://aimerkezi.site/kullanim-kosullari
```

Domain henüz yokken geçici test için `*.vercel.app` kullanabilirsiniz; RC’ye mümkünse kalıcı domain URL’lerini yazın.

---

## Yerel önizleme

PowerShell:

```powershell
cd aimerkezi-legal
npx --yes serve .
```

Tarayıcıda `http://localhost:3000` (veya `serve`’in yazdığı port).

---

## Vercel’e deploy

### A) Vercel CLI

```powershell
cd aimerkezi-legal
npx --yes vercel
```

Production için:

```powershell
npx --yes vercel --prod
```

Çıktıdaki `*.vercel.app` adresi domain bağlanana kadar çalışır.

### B) GitHub + Vercel Dashboard

1. Bu klasörü bir Git deposuna koyun (veya mevcut monorepo’da yalnızca `aimerkezi-legal/` kökünü Root Directory yapın).
2. [vercel.com](https://vercel.com) → **Add New Project** → depoyu seçin.
3. **Framework Preset:** Other / static.
4. **Root Directory:** `aimerkezi-legal` (monorepo ise).
5. Build komutu gerekmez; Output Directory boş bırakılabilir (statik HTML kökten servis edilir).
6. Deploy.

Projeyi Ai Merkezi / Marketim ile ilişkilendirmek için Vercel proje adını örneğin `aimerkezi-legal` veya `marketim-legal` yapabilirsiniz.

---

## Custom domain: aimerkezi.site

1. Vercel proje → **Settings** → **Domains** → `aimerkezi.site` ekleyin (isterseniz `www.aimerkezi.site` da ekleyin; apex’e yönlendirin veya tersi).
2. DNS sağlayıcınızda Vercel’in gösterdiği kayıtları ekleyin:
   - Apex için genelde **A** / **ALIAS** (Vercel IP’leri),
   - veya `www` için **CNAME** → `cname.vercel-dns.com`.
3. SSL otomatik tamamlanana kadar bekleyin.
4. Doğrulama:
   - https://aimerkezi.site/gizlilik
   - https://aimerkezi.site/kullanim-kosullari
5. RevenueCat Privacy / Terms URL’lerini yukarıdaki değerlerle güncelleyin.

Path’ler klasör yapısından gelir (`gizlilik/index.html`, `kullanim-kosullari/index.html`). Ayrı rewrite gerekmez; `vercel.json` yalnızca `cleanUrls` / `trailingSlash` ayarlar.

---

## İletişim e-postasını değiştirme

Sayfalarda varsayılan: `destek@aimerkezi.site`. Değiştirmek için `index.html`, `gizlilik/index.html` ve `kullanim-kosullari/index.html` içindeki adresleri güncelleyip yeniden deploy edin.

---

## Not

Metinler hukuki danışmanlık değildir; Google Play için makul başlangıç belgeleridir.
