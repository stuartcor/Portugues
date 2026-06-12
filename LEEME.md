# Revisão PT — PWA offline

App de repaso de portugués instalable en el teléfono que funciona sin conexión.

## Contenido
- `index.html` — toda la app (autocontenida, sin dependencias)
- `sw.js` — service worker (caché offline)
- `manifest.webmanifest` — manifiesto PWA
- `icon-192.png`, `icon-512.png` — íconos

## Importante
Los service workers solo funcionan sobre **HTTPS** (o localhost). Abrir el
`index.html` directo desde el sistema de archivos (file://) muestra la app
pero **no** la hace instalable ni offline. Necesitas hospedarla — toma 2 minutos:

## Opción A — GitHub Pages (recomendada)
1. Crea un repo (puede ser privado con Pages habilitado, o público), p. ej. `revisao-pt`.
2. Sube estos 5 archivos a la raíz del repo.
3. Settings → Pages → Source: `Deploy from a branch` → branch `main`, carpeta `/ (root)`.
4. En 1–2 min tendrás `https://<tu-usuario>.github.io/revisao-pt/`.

## Opción B — Netlify Drop
1. Entra a https://app.netlify.com/drop
2. Arrastra la carpeta con los 5 archivos. Listo, te da una URL HTTPS.

## Instalar en el teléfono
- **Android (Chrome):** abre la URL → menú ⋮ → "Agregar a pantalla de inicio" /
  "Instalar app". La primera visita ya deja todo en caché; después funciona sin internet.
- **iOS (Safari):** abre la URL → botón Compartir → "Agregar a pantalla de inicio".

## Probar offline
Abre la app una vez con internet, activa modo avión y vuelve a abrirla desde el ícono.

## Actualizar la app
Si cambias `index.html`, sube el cambio y edita en `sw.js` la línea
`const CACHE = "revisao-pt-v1"` → `"revisao-pt-v2"` para invalidar el caché viejo.
