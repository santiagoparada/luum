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
- Paywall: 10 mensajes gratis → bloqueo → $7 USD de por vida
- localStorage: `luum_mensajes` (contador) / `luum_premium` (acceso)
- Bypass developer: `?dev=true` en la URL activa luum_premium automáticamente

## Modelo de negocio
- Usuario final: 10 mensajes gratis, luego $7 USD pago único de por vida
- Licencia comercial: uso comercial o adaptaciones requieren acuerdo con TRRNGR
- Franquicia ligera: tarifa de entrada + porcentaje sobre ingresos derivados (a convenir)
- Contacto: parada.santi@gmail.com

## Próxima tarea: Google Play + RevenueCat

### 1. Preparar la PWA para TWA
- Verificar que manifest.json tenga todos los campos requeridos por TWA
- Agregar Digital Asset Links en `/.well-known/assetlinks.json`
- Asociar el dominio santiagoparada.github.io con el package name Android

### 2. Generar el APK con Bubblewrap
```bash
npm i -g @bubblewrap/cli
bubblewrap init --manifest https://santiagoparada.github.io/luum/manifest.json
bubblewrap build
```

### 3. Google Play Console
- Crear cuenta de desarrollador ($25 USD, pago único)
- Subir APK, completar ficha, publicar en acceso anticipado

### 4. RevenueCat
- Crear proyecto en revenuecat.com, conectar con Google Play
- Definir producto: pago único $7 USD (tipo one_time / lifetime)
- Integrar SDK en la app

### 5. Reemplazar paywall temporal
- El botón DESBLOQUEAR actualmente muestra `alert('Próximamente / Coming soon')`
- Con RevenueCat: llamar a `RC.purchase()` → al completar → `luum_premium = 'true'`

## Notas de desarrollo
- Reset paywall en consola del navegador:
  ```js
  localStorage.removeItem('luum_premium')
  localStorage.removeItem('luum_mensajes')
  ```
- Bypass dev: abrir `santiagoparada.github.io/luum?dev=true` (persiste en localStorage)
- Commits clave:
  - `eb536b1` — frases NIDO
  - `550f965` — instrucciones bilingüe
  - `0e591ee` — paywall + términos
  - `6b0111f` — layout barra inferior
