# LUUM — Estado del proyecto

## Qué es
App generativa de estrategias creativas. PWA publicada en GitHub Pages: santiagoparada.github.io/luum
Todo el app vive en un solo archivo: index.html
Licencia propia TRRNGR (no CC). © TRRNGR — parada.santi@gmail.com

## Stack
- HTML/CSS/JS puro, sin frameworks
- PWA con manifest.json y sw.js
- GitHub Pages (branch main, raíz del repo santiagoparada/luum)
- Fuente: DM Sans (Google Fonts)

## Contenido
- 90 frases detonadoras (ES/EN)
- 64 proposiciones de acción (ES/EN)
- 15 colores pop
- +170.000 combinaciones posibles
- Fuentes conceptuales: Kosuth, Sennett, McLuhan, Baudrillard, NIDO (matriz pedagógica)
- Referencia estructural: Oblique Strategies (Brian Eno)

## Funcionalidades implementadas
- Generador aleatorio con animación (tap / click / swipe / teclado)
- Cambio de idioma ES/EN
- Overlay de instrucciones (bilingüe)
- Overlay de términos y condiciones (bilingüe, licencia propia TRRNGR)
- Acceso completamente gratuito, sin límites ni bloqueos
- Sin localStorage — no se guarda ningún dato en el dispositivo

## Modelo de negocio
- Acceso gratuito para todos los usuarios
- Licencia comercial: uso comercial o adaptaciones requieren acuerdo con TRRNGR
- Franquicia ligera: tarifa de entrada + porcentaje sobre ingresos derivados (a convenir)
- Contacto: parada.santi@gmail.com

## Android / TWA — Estado actual (2026-05-21)

### Datos de la app
- **Título:** LUUM — Slow Fields
- **Package name:** io.github.santiagoparada.luum
- **PWA URL:** https://santiagoparada.github.io/luum/
- **Repo fuente:** ~/projects/LUUM
- **Proyecto Android (Bubblewrap):** ~/twa-luum
- **Keystore:** ~/twa-luum/android.keystore (alias: `android`)

### Fase actual
Proyecto Android generado con Bubblewrap (`bubblewrap init` completado). **Primer build pendiente.**

### Próximos pasos
1. Ejecutar `bubblewrap build` en ~/twa-luum y obtener el APK firmado
2. Extraer el SHA-256 fingerprint del keystore:
   ```bash
   keytool -list -v -keystore ~/twa-luum/android.keystore -alias android
   ```
3. Crear `/.well-known/assetlinks.json` en el repo fuente con el fingerprint obtenido
4. Verificar el Digital Asset Link en https://digitalassetlinks.googleapis.com/v1/statements:list?source.web.site=https://santiagoparada.github.io&relation=delegate_permission/common.handle_all_urls
5. Probar el TWA en dispositivo/emulador antes de subir
6. Preparar ficha de Google Play (descripción, capturas, íconos)
7. Crear cuenta de desarrollador en Google Play Console ($25 USD, pago único) y publicar en acceso anticipado

## Notas de desarrollo
- Commits clave:
  - `eb536b1` — frases NIDO
  - `550f965` — instrucciones bilingüe
  - `6b0111f` — layout barra inferior
  - `5dd5ff0` — eliminar paywall, LUUM gratuita
  - `96745bc` — limpiar términos (sin referencias a pagos)
