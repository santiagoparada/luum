# LUUM

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

Actualmente desplegado en **GitHub Pages**.

---

© TRRNGR 2026
