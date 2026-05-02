# 🔍 DataScope — Buscador Excel Multi-Hoja

Una herramienta web ligera y sin dependencias de servidor para **buscar, filtrar y explorar archivos Excel** con múltiples hojas directamente desde el navegador.

![HTML](https://img.shields.io/badge/HTML-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![SheetJS](https://img.shields.io/badge/SheetJS-0.18.5-green?style=flat)
![Sin servidor](https://img.shields.io/badge/backend-ninguno-blue?style=flat)

---

## ✨ Características

- **Carga de archivos Excel** — Compatibilidad con `.xlsx` y `.xls`, arrastrar y soltar o seleccionar desde el explorador
- **Soporte multi-hoja** — Cada hoja se trata como una categoría independiente (ideal para datos organizados por año)
- **Búsqueda en tiempo real** — Filtra simultáneamente en todas las columnas con múltiples términos separados por espacios
- **Filtros por hoja** — Tabs con colores únicos para activar/desactivar hojas específicas
- **Filtros por columna** — Selecciona en qué columnas buscar con un solo clic
- **Vista tabla y tarjetas** — Alterna entre vista tabular y tarjetas visuales
- **Ordenamiento por columna** — Clic en el encabezado para ordenar ascendente/descendente
- **Paginación** — Navega por resultados de 50 en 50 con controles inteligentes
- **Resaltado de coincidencias** — Los términos buscados se destacan en los resultados
- **Copiar resultados** — Exporta los resultados filtrados al portapapeles en formato TSV (compatible con Excel/Sheets)
- **100% cliente** — Todo funciona en el navegador, sin enviar datos a ningún servidor

---

## 🚀 Uso

No requiere instalación ni servidor. Solo abre el archivo HTML en cualquier navegador moderno.

```bash
# Opción 1 — Abre directo
open index.html

# Opción 2 — Sirve localmente (opcional)
npx serve .
# o
python -m http.server 8080
```

### Flujo de uso

1. Arrastra tu archivo `.xlsx` / `.xls` al área de carga, o haz clic en **Seleccionar archivo**
2. DataScope analiza todas las hojas y muestra un resumen (hojas, registros, columnas)
3. Usa los **tabs de hoja** para filtrar por año u hoja específica
4. Escribe en la barra de búsqueda — los resultados aparecen instantáneamente
5. Ajusta los **filtros de columna** para acotar la búsqueda
6. Alterna entre vista **Tabla** o **Tarjetas** según prefieras
7. Haz clic en **Copiar resultados** para exportar al portapapeles

---

## 📁 Estructura del proyecto

```
datascope/
└── index.html    # Aplicación completa (HTML + CSS + JS en un solo archivo)
```

La aplicación es un archivo HTML autocontenido — no hay dependencias locales que instalar.

---

## 🛠️ Dependencias externas (CDN)

| Librería | Versión | Uso |
|----------|---------|-----|
| [SheetJS (xlsx)](https://sheetjs.com/) | 0.18.5 | Parseo de archivos Excel |
| [Syne](https://fonts.google.com/specimen/Syne) | — | Tipografía de títulos |
| [DM Sans](https://fonts.google.com/specimen/DM+Sans) | — | Tipografía de cuerpo |

Ambas fuentes se cargan desde Google Fonts. SheetJS se carga desde `cdnjs.cloudflare.com`.

---

## 🖥️ Compatibilidad

| Navegador | Soporte |
|-----------|---------|
| Chrome / Edge (moderno) | ✅ Completo |
| Firefox | ✅ Completo |
| Safari | ✅ Completo |
| IE 11 | ❌ No soportado |

Requiere soporte para `FileReader API`, `Clipboard API` y `CSS Variables`.

---

## 📊 Formato de archivo esperado

DataScope funciona con cualquier archivo Excel donde:

- Cada **hoja** representa una categoría (ej. un año: `2022`, `2023`, `2024`)
- La **primera fila** de cada hoja contiene los encabezados de columna
- Las filas siguientes contienen los datos

No hay restricción sobre el número de columnas o el tipo de datos — todo se trata como texto para la búsqueda.

---

## ⚙️ Personalización

Todos los colores, fuentes y tamaños están definidos como **CSS variables** al inicio del archivo:

```css
:root {
  --bg: #0a0a0f;
  --accent: #6c63ff;
  --accent2: #ff6b9d;
  --accent3: #00d4aa;
  /* ... */
}
```

Los colores de los tabs por hoja se asignan cíclicamente desde el array `COLORS` en el script:

```javascript
const COLORS = ['#6c63ff','#ff6b9d','#00d4aa','#ffa45c','#4fc3f7','#ce93d8','#80cbc4','#ffab91'];
```

---

## 📄 Licencia

MIT — libre para uso personal y comercial.
