# Proyecto de Ciencia de Datos

Este repositorio contiene el libro, diapositivas, códigos, datos e imágenes del curso Proyecto de Ciencia de Datos. 

El libro está hecho en Quarto, pensado para ser exportado principalmente a HTML, en donde mantiene sus elementos interactivos. Puedes exportarlo a PDF también si así lo deseas, pero habrá algunos elementos que no se renderearán y algunos márgenes que no se respetarán.

Al momento de escribir esto, el libro está suficientemente completo, con algunos errores en el capítulo de agentes, por lo que ese código no se ejecuta al renderear. Además, las slides son podrían estar levemente desactualizadas después de algunos ajustes manuales en el libro. Está pendiente ejecutar un proceso de homologación automática.

Si quieres renderear tú mismo, puedes setear tu ambiente virtual con uv

```bash
uv sync
```

y usar 

```bash
quarto render --to html
```

para renderear a HTML. El rendereo a PDF requiere instalar tinytex o algúna otra herramienta que permita renderear de .tex a .pdf.

El resto del README fue generado con IA. Para dudas de Quarto, revisar [documentación oficial de Quarto](https://quarto.org/docs/guide/): 

## 🎨 Temas

- **Libro**: Tema oscuro personalizado (darkly + custom.scss)
- **Slides HTML**: Tema oscuro con custom-slides.scss
- **Slides PDF**: Tema Madrid de Beamero render chapters/01-introduccion-slides.qmd

Para slides en PDF (Beamer):

```bash
quarto render chapters/01-introduccion-slides.qmd --to beamer
```

### Vista Previa en Vivo

Para trabajar con vista previa en tiempo real:

```bash
quarto preview
```

## 📝 Crear Nuevo Capítulo

Cada tema tiene dos archivos:

1. **Capítulo del libro** (`XX-tema.qmd`):
   ```yaml
   ---
   title: "Título del Tema"
   ---
   
   ## Sección 1
   Contenido del capítulo...
   ```

2. **Slides** (`XX-tema-slides.qmd`):
   ```yaml
   ---
   title: "Título del Tema"
   format:
     revealjs:
       theme: [default, ../custom-slides.scss]
     beamer:
       theme: Madrid
       aspectratio: 169
   ---
   
   # Sección 1 {background-color="#1a1a1a"}
   
   ## Slide 1
   Contenido...
   

Luego agregar el capítulo a `_quarto.yml`:

```yaml
book:
  chapters:
    - chapters/XX-tema.qmd
```

## Características

### Libro HTML
- ✅ Tema oscuro personalizado
- ✅ Navegación lateral (sidebar)
- ✅ Búsqueda integrada
- ✅ Code folding y copy
- ✅ Numeración de secciones
- ✅ Enlaces externos en nueva ventana

### Libro PDF
- ✅ Formato libro profesional
- ✅ Tabla de contenidos
- ✅ Numeración de capítulos
- ✅ Referencias bibliográficas
- ✅ Idioma español

### Slides RevealJS
- ✅ Tema oscuro
- ✅ Pizarra interactiva (chalkboard)
- ✅ Navegación con teclado
- ✅ Vista de presentador
- ✅ Código resaltado
- ✅ Exportable a PDF

### Slides Beamer
- ✅ Tema profesional
- ✅ Fondo oscuro
- ✅ Formato PDF nativo
- ✅ Compatible con LaTeX

## Agregar Nuevo Capítulo

1. Crear archivos en `chapters/`:
   - `XX-nombre-tema.qmd` (versión libro)
   - `XX-nombre-tema-slides.qmd` (versión slides)

2. Agregar referencia en `_quarto.yml`:

```yaml
chapters:
  - chapters/XX-nombre-tema.qmd
```

3. Renderizar:

```bash
quarto render
```

## Elementos Especiales

### Callouts

```markdown
::: {.callout-note}
Nota importante
:::

::: {.callout-tip}
Consejo útil
:::

::: {.callout-warning}
Advertencia
:::
```

### Columnas (solo slides)

```markdown
:::: {.columns}
::: {.column width="50%"}
Contenido izquierda
:::
::: {.column width="50%"}
Contenido derecha
:::
::::
```

### Listas Incrementales (slides)

```markdown
::: {.incremental}
- Item 1
- Item 2
- Item 3
:::
```

### Tabs

```markdown
::: {.panel-tabset}
### Tab 1
Contenido 1

### Tab 2
Contenido 2
:::
```

## 📦 Requisitos

- **Quarto** (v1.4+)
- **Para PDF**: LaTeX (TinyTeX recomendado)
  ```bash
  quarto install tinytex
  ```

## 🔧 Formato de Salida

### Libro
- **HTML**: `_book/index.html` (con navegación, búsqueda, tema oscuro)
- **PDF**: `_book/Proyecto-de-Ciencia-de-Datos.pdf` (libro completo)

### Slides
- **HTML**: Interactivas con RevealJS, pizarra, navegación
- **PDF**: Formato Beamer profesional para impresión

Al momento de escribir esto, las slides no reflejan 100% el contenido del libro, ya que las iteraciones para corregir detalles fueron hechas solo en el libro. En el futuro, esos cambias los actualizaré a las slides, cuando tengamos una versión más estable.

## 📚 Contenido Planificado

### Parte I: Fundamentos
- Introducción al curso
- Metodologías ágiles (Scrum, Kanban)

### Parte II: Gestión de Proyectos
- Gestión de proyectos de datos
- Trabajo en equipo y comunicación

### Parte III: Herramientas Técnicas
- Git y GitHub
- Cloud computing
- Linux y línea de comandos

### Parte IV: Desarrollo y Entregas
- Documentación técnica
- Presentaciones efectivas
- Reproducibilidad

## 🤝 Contribuir

Para agregar nuevo contenido:

1. Crear archivo `.qmd` en `chapters/`
2. Agregar entrada en `_quarto.yml`
3. Renderizar para verificar
4. Commit y push

## 📄 Licencia

Material del curso MDS7201 - Universidad de Chile
