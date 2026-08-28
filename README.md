# Lector RSVP

Lector de lectura rápida (RSVP) 100% local para PDF y EPUB — sin servidor, sin subir tus archivos a ningún lado. Corre entero en el navegador.

**[🇪🇸 Español](#-español) · [🇬🇧 English](#-english)**

---

## 🇪🇸 Español

Un lector de velocidad tipo RSVP (*Rapid Serial Visual Presentation*) que muestra una palabra a la vez, con controles de reproducción inspirados en un reproductor de video: velocidad ajustable, barra de progreso arrastrable y paradas guardadas con notas.

### ✨ Características

- **100% local y privado** — el PDF o EPUB se procesa por completo en tu navegador; nunca se sube a ningún servidor.
- **Control de velocidad tipo YouTube** — acelera o desacelera (100–900 palabras por minuto) mientras lees, con pausas automáticas más largas en signos de puntuación.
- **Barra de progreso arrastrable** — salta a cualquier punto del documento como en un reproductor de video, con marcas visuales donde tienes paradas guardadas.
- **Paradas con notas** — marca cualquier posición (ej. "palabra 1555") con una etiqueta y una descripción (ej. *"parte donde el autor explica…"*) para volver después. Se guarda automáticamente tu última posición como "lectura actual".
- **Vista dividida — documento real**:
  - En **PDF**: se muestra la página real renderizada, con un recuadro amarillo sobre la posición exacta de la palabra actual.
  - En **EPUB**: se muestra el capítulo real con su estructura (títulos, párrafos), con la palabra actual resaltada dentro del flujo de texto.
  - El auto-scroll solo ocurre mientras reproduces, así que puedes pausar y revisar una figura, tabla o dato con calma sin perder tu resaltado.
- **Biblioteca persistente** — cada documento que abres se guarda completo en el navegador (IndexedDB), junto con tu posición, velocidad y paradas. Cierra la pestaña, vuelve cuando quieras, y retómalo con un clic desde "Tu biblioteca".
- **Atajos de teclado** — `espacio` reproducir/pausar, `←/→` palabra por palabra, `↑/↓` velocidad, `B` marcar parada, `M` cambiar de vista.

### 🚀 Uso

No requiere instalación ni build:

1. Descarga `index.html` (o clona el repositorio).
2. Ábrelo directamente en tu navegador (doble clic), o publícalo con GitHub Pages.
3. Arrastra un PDF o EPUB, o haz clic para seleccionarlo.

> La primera vez necesitas conexión a internet para cargar `pdf.js` y `JSZip` desde un CDN. Después de eso, la lectura funciona sin conexión (mientras no cierres la pestaña en frío).

### ⚠️ Limitaciones conocidas

- Los EPUB con DRM no se pueden abrir (la extracción de texto no funciona sobre contenido cifrado).
- En PDF, el resaltado de posición sobre la página es una aproximación basada en el ancho reportado por `pdf.js` para cada fragmento de texto — funciona bien en la gran mayoría de documentos, pero puede desalinearse levemente en diseños con tipografías muy irregulares.
- La biblioteca vive en el almacenamiento local de ese navegador y equipo; no se sincroniza entre dispositivos.
- PDFs a varias columnas pueden extraerse en un orden de lectura distinto al visual, dependiendo de cómo esté generado el archivo.

### 💡 Ideas para el futuro

Contribuciones bienvenidas. Algunas ideas abiertas:

- Soporte directo para `.txt` / `.md`.
- Extracción de imágenes embebidas en EPUB.
- Tamaño de fuente y tema (claro/oscuro) configurables.
- Exportar/importar biblioteca y paradas como JSON (respaldo o migrar de navegador).
- Modo "chunking" (mostrar 2–3 palabras a la vez).
- Manejo de PDFs a varias columnas.
- Empaquetado como PWA con caché offline completo desde el primer uso.

### 🛠️ Stack

Un único archivo HTML con JavaScript vanilla. Sin frameworks, sin build. Usa:
- [PDF.js](https://mozilla.github.io/pdf.js/) para leer y renderizar PDF.
- [JSZip](https://stuk.github.io/jszip/) para leer el contenedor EPUB.
- `IndexedDB` del navegador para la biblioteca persistente.

### 📄 Licencia

[MIT](./LICENSE) — úsalo, modifícalo, compártelo.

---

## 🇬🇧 English

A speed-reading tool (RSVP — *Rapid Serial Visual Presentation*) that flashes one word at a time, with video-player-style controls: adjustable speed, a draggable progress bar, and saved bookmarks with notes.

### ✨ Features

- **100% local and private** — your PDF or EPUB is processed entirely in your browser; it never gets uploaded anywhere.
- **YouTube-style speed control** — speed up or slow down (100–900 words per minute) on the fly, with longer automatic pauses on punctuation.
- **Draggable progress bar** — scrub to any point in the document like a video player, with tick marks for your saved bookmarks.
- **Bookmarks with notes** — mark any position (e.g. "word 1555") with a label and a description (e.g. *"where the author explains…"*) to come back to later. Your last position is auto-saved as "current reading".
- **Split view — the real document**:
  - For **PDF**: renders the actual page image, with a yellow box over the exact position of the current word.
  - For **EPUB**: renders the real chapter with its structure (headings, paragraphs), with the current word highlighted in that flow.
  - Auto-scroll only happens while playing, so you can pause to check a figure, table, or data point without losing your highlight.
- **Persistent library** — every document you open is saved in full in your browser (IndexedDB), along with your position, speed, and bookmarks. Close the tab, come back anytime, and resume with one click from "Your library".
- **Keyboard shortcuts** — `space` play/pause, `←/→` step word by word, `↑/↓` speed, `B` add bookmark, `M` toggle view.

### 🚀 Usage

No install, no build step:

1. Download `index.html` (or clone this repo).
2. Open it directly in your browser (double-click), or host it with GitHub Pages.
3. Drag a PDF or EPUB in, or click to pick a file.

> The first load needs an internet connection to fetch `pdf.js` and `JSZip` from a CDN. After that, reading works offline (as long as you don't cold-reload the tab).

### ⚠️ Known limitations

- DRM-protected EPUBs can't be opened — text extraction doesn't work on encrypted content.
- The PDF position highlight is an approximation based on the width `pdf.js` reports for each text fragment — it works well for the vast majority of documents, but can drift slightly on layouts with very irregular typography.
- The library lives in that browser/device's local storage; it doesn't sync across devices.
- Multi-column PDFs may extract in a different reading order than the visual layout, depending on how the file was generated.

### 💡 Ideas for the future

Contributions welcome. Some open ideas:

- Direct `.txt` / `.md` support.
- Extracting embedded images from EPUB.
- Configurable font size and light/dark theme.
- Export/import library and bookmarks as JSON (backup or move browsers).
- "Chunking" mode (show 2–3 words at a time).
- Multi-column PDF handling.
- Package as a PWA with full offline caching from the first load.

### 🛠️ Stack

A single HTML file with vanilla JavaScript. No frameworks, no build step. Uses:
- [PDF.js](https://mozilla.github.io/pdf.js/) to read and render PDFs.
- [JSZip](https://stuk.github.io/jszip/) to read the EPUB container.
- The browser's `IndexedDB` for the persistent library.

### 📄 License

[MIT](./LICENSE) — use it, modify it, share it.
