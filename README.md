# Kibor — kibor.uz

Minimal landing sayt (single-file). Mockup dizayn tizimi asosida: Manrope, #FF8A3D→#C94A08.

## Fayllar
- `index.html` — deploy qilinadigan yakuniy fayl (rasmlar base64 ichida, ~1.9MB)
- `index.template.html` — manba (rasm o'rniga `{{IMG_*}}` placeholder)
- `images/` — asl rasmlar
- `preview-*.png` — skrinshotlar (repo'ga kirmaydi)

## Qayta yig'ish
Template o'zgarganda:
```bash
python3 - <<'PY'
import base64
def b64(p): return 'data:image/jpeg;base64,' + base64.b64encode(open(p,'rb').read()).decode()
tpl = open('index.template.html', encoding='utf-8').read()
for k, f in {'{{IMG_HERO}}':'images/kibor-hero.jpg','{{IMG_PALTO}}':'images/kibor-product-palto.jpg','{{IMG_KOYLAK}}':'images/kibor-product-koylak.jpg','{{IMG_TRENCH}}':'images/kibor-product-trench.jpg'}.items():
    tpl = tpl.replace(k, b64(f))
open('index.html','w',encoding='utf-8').write(tpl)
PY
```

## Holat
Barcha funksiyalar "Tez orada" rejimida — hech narsa ishlayotgandek ko'rsatilmaydi.
TODO: Telegram bot havolasi, real kontent, RU tarjima, sotuvchi forma backend'i.
