# LUUM — Slow Fields

LUUM — Slow Fields is a contemplative mobile web app built around slow atmospheres, minimal interaction, and generative states of attention.

Dispositivo generativo de estrategias para la práctica artística.

---

## Qué es

LUUM cruza tres tablas de forma aleatoria en cada tiro:

- **90 frases detonadoras** — preguntas y proposiciones conceptuales
- **64 proposiciones artísticas** — acciones concretas para ejecutar
- **15 colores pop** — un fondo distinto cada vez

La lógica es la del I Ching: las mismas variables producen combinaciones infinitas. Con el contenido actual hay más de **170.000 combinaciones posibles**.

---

## Cómo usar

Abrir el link en cualquier navegador. Tocar o hacer clic para lanzar una nueva combinación. Deslizar hacia arriba o hacia abajo también funciona.

El botón **ES / EN** en la esquina inferior derecha cambia el idioma.

Para instalar como app en el teléfono: **Compartir → Agregar a pantalla de inicio**.

LUUM es completamente gratuita. Sin pagos, sin suscripciones.

---

## Estructura del proyecto

```
luum/
├── index.html      — app completa (HTML + CSS + JS en un solo archivo)
├── manifest.json   — configuración PWA
├── sw.js           — service worker para funcionamiento offline
└── icons/          — íconos en todos los tamaños requeridos
```

---

## Cómo agregar contenido

Abrir `index.html` y buscar las dos secciones marcadas:

```
/* ─── TABLA 1 · frases detonadoras ─── */
```
```
/* ─── TABLA 2 · proposiciones artísticas ─── */
```

Agregar nuevas frases o proposiciones dentro del array correspondiente, respetando el formato: `"Texto nuevo.",`

Cada vez que se actualiza el contenido, cambiar la versión del cache en `sw.js`:
```
const CACHE = 'luum-v2';  →  const CACHE = 'luum-v3';
```

---

## Referencias

El contenido surge del cruce entre:

- Joseph Kosuth — *Art after Philosophy* (1969)
- Richard Sennett — *El artesano* (2008)
- Marshall McLuhan / Edmund Carpenter — *Auditory Space*
- Jean Baudrillard — *La vida secreta de los objetos*
- Brian Eno / Peter Schmidt — *Oblique Strategies* (referente estructural)

---

## Despliegue

El proyecto corre como sitio estático. Cualquier plataforma que sirva HTML funciona.

Actualmente desplegado en **GitHub Pages**: https://santiagoparada.github.io/luum/

---

## Android / TWA

| Campo | Valor |
|---|---|
| Título | LUUM — Slow Fields |
| Package name | io.github.santiagoparada.luum |
| PWA URL | https://santiagoparada.github.io/luum/ |
| Herramienta | Bubblewrap CLI |
| Proyecto Android | ~/twa-luum |
| Keystore | ~/twa-luum/android.keystore (alias: `android`) |

**Estado (2026-05-21):** Proyecto Bubblewrap generado. Primer build pendiente.

Próximos pasos:
1. `bubblewrap build` → obtener APK firmado
2. Extraer SHA-256 fingerprint del keystore con `keytool`
3. Publicar `/.well-known/assetlinks.json` en este repo con el fingerprint
4. Probar TWA en dispositivo
5. Subir a Google Play Console

---

© TRRNGR 2026
