# Portfolio — Kacper Filas

Czysty HTML + CSS, bez frameworka i bez builda. Pliki: `index.html`, `style.css`, `gallery/`.

## Podgląd lokalnie

Wystarczy dwuklik w `index.html`. Albo serwer (port 8000 zajmuje ComfyUI, więc inny):

```bash
python -m http.server 8765 --bind 127.0.0.1
```

i wejdź na http://127.0.0.1:8765

## Dodawanie i podmiana prac

1. Wrzuć plik (JPG, PNG, GIF) do `gallery/`. Najlepiej 16:9, do ~2 MB (duże GIF-y spowalniają stronę).
2. W `index.html`, w sekcji `#galeria`, skopiuj blok `<figure>` i zmień `src` oraz `alt`.
3. Nowy projekt: nowy `<h3>` + `<p class="note">` + `<div class="gallery">` (wzór jest w komentarzu w HTML).

`gallery/placeholder.svg` to zaślepka na czas, zanim będzie screen.

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
