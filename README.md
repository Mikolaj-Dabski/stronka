# Dabski FPV

Strona-portfolio operatora dronów **FPV i DJI** — Mikołaj Dąbski.

Statyczna strona (jeden plik `index.html` + folder `assets/`). Bez frameworków i buildu — wystarczy hosting plików statycznych.

## Struktura

```
dabski-fpv/
├── index.html            # cała strona (HTML + CSS + JS w jednym pliku)
├── assets/
│   ├── hero.mp4          # wideo w tle sekcji hero
│   ├── sea.webp          # poster morza (ładuje się zanim wystartuje wideo)
│   └── logos/            # loga firm do siatki „Zaufali mi” (3×2)
└── README.md
```

## Sekcje

1. **Hero** — wideo w tle + napis „DABSKI FPV”. Poster morza pokazuje się natychmiast, wideo pojawia się płynnie gdy się załaduje (również na mobile).
2. **Intro** — krótki opis + 3 kafle (Loty FPV / Kadry DJI / Montaż).
3. **Zaufali mi** — siatka 3×2 z logami firm.
4. **Showreel** — dwa filmy z YouTube. Ładują się dopiero po kliknięciu (lekka „fasada” = szybki start strony).
5. **Kontakt** — mail, Instagram, LinkedIn.

## Podgląd lokalny

```bash
# w folderze projektu
py -m http.server 8099
# następnie otwórz http://localhost:8099
```

## Wdrożenie — GitHub + Cloudflare Pages

1. Wrzuć repozytorium na GitHub (patrz komendy niżej).
2. Wejdź na **dash.cloudflare.com → Workers & Pages → Create → Pages → Connect to Git**.
3. Wybierz to repozytorium.
4. Ustawienia budowania:
   - **Framework preset:** `None`
   - **Build command:** *(puste)*
   - **Build output directory:** `/`
5. **Save and Deploy**. Gotowe — każdy `git push` automatycznie aktualizuje stronę.

### Wysłanie na GitHub

```bash
git remote add origin https://github.com/<twoja-nazwa>/dabski-fpv.git
git branch -M main
git push -u origin main
```

## Wymiana filmów showreel

W `index.html` znajdź `data-yt="..."` i podmień ID filmu z YouTube:

```html
<div class="reel" data-yt="TU_ID_FILMU">
```

ID to część adresu po `youtu.be/` lub `watch?v=`.
