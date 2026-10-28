# Portfolio — Kacper Filas

Czysty HTML + CSS, bez frameworka i bez builda. Pliki: `index.html`, `style.css`, `gallery/`.

## Podgląd lokalnie

Wystarczy dwuklik w `index.html`. Albo serwer (port 8000 zajmuje ComfyUI, więc inny):

```bash
python -m http.server 8765 --bind 127.0.0.1
```

i wejdź na http://127.0.0.1:8765

## Dodawanie i podmiana prac

Każdy projekt to jeden blok `<article class="work">` w sekcji `#prace` w `index.html` (wzór i opis są w komentarzu nad siatką).

1. Pliki wrzuć do `gallery/nazwa-projektu/`. Screeny jako JPG/PNG, animacje najlepiej jako krótkie MP4 (lżejsze od GIF-ów); GIF też zadziała jako `<img>`.
2. Skopiuj `<article class="work">`, zmień okładkę (`<img>` w `<button>`), tytuł, tagi i numer.
3. W `<template>` wstaw zawartość okna projektu: `<img src="...">` albo `<video src="....mp4" poster="....jpg" autoplay muted loop playsinline>`.
4. Rozmiar kafelka to klasa: `s-4x2`, `s-3x2`, `s-2x2` albo `s-2x1` (siatka ma 6 kolumn, puste miejsca same się zapełniają).

Zawartość `<template>` ładuje się dopiero po kliknięciu, więc dużo wideo nie spowalnia strony głównej.

## Publikacja na GitHub Pages

Wariant A: adres `https://kacperfilas.github.io` (polecany)

1. Na GitHubie: New repository, nazwa dokładnie `KacperFilas.github.io`, Public, bez README.
2. W tym folderze:

```bash
git init -b main
git add index.html style.css gallery README.md
git commit -m "Portfolio"
git remote add origin https://github.com/KacperFilas/KacperFilas.github.io.git
git push -u origin main
```

3. Repo → Settings → Pages → Source: "Deploy from a branch", Branch: `main` / `/ (root)` → Save.
4. Po 1–2 minutach strona działa pod `https://kacperfilas.github.io`.

Wariant B: osobne repo, np. `portfolio`. Te same kroki, adres to `https://kacperfilas.github.io/portfolio/`. Ścieżki w HTML są względne, więc działa bez zmian.

Aktualizacja później: `git add -A && git commit -m "Nowe prace" && git push`.
