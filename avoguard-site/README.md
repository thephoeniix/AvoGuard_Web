# AvoGuard — Sitio web (ExpoIng 2026 · Grupo XRCX)

Página única con el demo de percepción en vivo, el pipeline de cálculo y toda la
información del proyecto. Es **HTML estático puro**: no necesita servidor ni build.

## Estructura
```
index.html            ← la página (autocontenida; la imagen va embebida)
.nojekyll             ← evita que GitHub Pages procese el sitio con Jekyll
assets/
  AvoGuard-ExpoIng.pdf   ← presentación (botón de descarga)
  AvoGuard-Poster.html   ← póster científico (botón de descarga)
```

## Antes de publicar
1. Abre `index.html` y busca esta línea (cerca del final, en `<script>`):
   ```js
   var REPO = "https://github.com/usuario/avoguard";
   ```
   Cámbiala por la URL real de tu repositorio. Eso actualiza los 3 botones de "GitHub".

## Publicar con GitHub Pages (gratis, sin login para los jueces)
1. Copia `index.html`, `.nojekyll` y la carpeta `assets/` a la **raíz** de tu repo.
2. Sube los cambios:
   ```bash
   git add index.html .nojekyll assets/
   git commit -m "Sitio AvoGuard"
   git push
   ```
3. En GitHub: **Settings → Pages**.
4. En *Build and deployment → Source*, elige **Deploy from a branch**.
5. Branch: **main**, carpeta: **/(root)** → **Save**.
6. Espera ~1 minuto. Tu URL pública será:
   ```
   https://<tu-usuario>.github.io/<nombre-del-repo>/
   ```
7. Comparte ese enlace con los jueces. No necesitan cuenta ni permisos.

> Nota: en cuentas gratuitas, GitHub Pages requiere que el repo sea **público**.
> Si tienes GitHub Education / Pro, también funciona con repo privado.

## Alternativas (sin tocar el repo)
- **Netlify Drop**: arrastra la carpeta a https://app.netlify.com/drop → URL al instante.
- **Vercel**: `vercel` en la carpeta, o conecta el repo en vercel.com.

## Notas técnicas
- El demo corre 100% en el navegador (Canvas). La foto que sube un juez **no se
  envía a ningún lado**, se procesa localmente.
- El pipeline está embebido como SVG vectorial (se ve nítido a cualquier tamaño).
