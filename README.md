# README plantilla

Esta nota centraliza la documentacion operativa de la plantilla para poder auditarla rapido.

Dentro de la carpeta "99 - Meta" hay mas documentación y guias de cosas que incluye esta plantilla:

- **Changelog**: incluye información de cambios que se fueron haciendo (algo tecnico, puedes ignorarlo si no te importa como funciona por dentro) 
- **Git portable**: incluye información de como esta configurado git para usar una versión portable, puedes ignorarlo si no te importa como funciona por dentro o no te da problemas
- **Guia CSSclasses**: explica todas las clases css que puedes usar en las notas que crees (inpiración y plantillas de [CyanVoxel](https://www.youtube.com/watch?v=rAkerV8rlow&t=352s))
- **Guia propiedades**: explica algunas propiedades que ya hay creadas que puedes usar para organizar tus notas y combinarlas con los maps of content creados en /Templates (inspirados en el metodo Bullet Journal)
- **Guia VIM**: Pequeña guia para motivarte a usar Vim, es un gran editor de tecto activado por defecto en esta plantilla ;) (puedes desactivar Vim en ajustes de la boveda)
- **Trucos obsidian**: Pequeños tips para darle formato a tus notas :D
- **Vimtutor**: Documento original de vimtutor para practicar con el editor de Vim

## Objetivo

- Mantener una plantilla completa de Obsidian.
- Documentar que forma parte del nucleo de la plantilla y que es accesorio.
- Dejar trazabilidad de cambios para revisar despues con facilidad.

## Estado de la plantilla

- Es una plantilla base, no una boveda de trabajo real.
- La estructura principal usa carpetas numeradas para `PARA`, `ZETTEL`, `Daily(bullet journal)` y `Meta`.
- `Git portable` se mantiene dentro de `.obsidian` como decision explicita de distribucion para Windows.
- La organizacion busca combinar una base de `PARA` con notas permanentes tipo `zettel` y un flujo de captura/revision inspirado en `bullet journal`.

## Configuraciones especiales

- Tema activo: `Minimal`.
- Notas diarias:
  - carpeta: `06 - Daily/`
  - formato: `YYYY-MM-DD`
  - plantilla: `99 - Meta/Templates/Plantilla Daily.md`
- Plantillas MOC y de revision temporal:
  - mensual: `99 - Meta/Templates/Plantilla Monthly.md`
  - future log: `99 - Meta/Templates/Plantilla Future log.md`
  - sirven como puntos de organizacion para revisar objetivos, proyectos activos, tareas migradas y enlaces a notas relacionadas
- Excalidraw:
  - carpeta base: `99 - Meta/Excalidraw/`
  - carpeta de scripts: `99 - Meta/Excalidraw/Scripts/`
  - carpeta de fuentes CJK: `99 - Meta/Excalidraw/CJK Fonts/`
  - plantilla por defecto: no configurada
- Obsidian Sync:
  - desactivado en la plantilla base

## Plugins activos

### Nucleo de la plantilla

- `obsidian-minimal-settings`
- `obsidian-style-settings`
- `obsidian-icon-folder`
- `calendar`
- `obsidian-excalidraw-plugin`
- `obsidian-git`

### Complementos de productividad

- `editing-toolbar`
- `obsidian-text-format`
- `settings-search`
- `url-into-selection`
- `vim-toggle`
- `image-converter`

### Complementos de navegacion o presentacion

- `notebook-navigator`
- `obsidian-advanced-slides`

## Snippets activos

### Globales

- `Fonts`
- `CyanVoxel's General Tweaks`
- `Colored Sidebar Items`

### Tematicos por nota

- `Daily Note Themes`
- `Japanese Font Support`
- `Minecraft`
- `Notebook Backgrounds`
- `Runescape`

## Notas de auditoria

- No se desactivan plugins por defecto solo por ser opcionales.
- Se intenta evitar contradicciones entre tema, plugins y snippets.
- Las decisiones especiales se documentan en `99 - Meta/`.
- Las plantillas de `Monthly` y `Future log` estan pensadas para funcionar como MOCs ligeros: no sustituyen a `PARA` ni al archivo zettelkasten, sino que los conectan desde revisiones periodicas.

## Tradeoffs conocidos

- `vim-toggle` puede parecer redundante porque `vimMode` ya viene activado por defecto, pero se conserva para poder alternarlo rapidamente desde comando o ribbon.
- `calendar` y `notebook-navigator` tienen cierto solapamiento funcional, pero ambos se mantienen porque la plantilla prioriza mostrar posibilidades completas.
- `obsidian-git` queda preparado para uso manual con `git portable`; no esta configurado como sistema de backup automatico.
- `obsidian-text-format` contiene caracteres Unicode en su configuracion y conviene leer ese archivo en UTF-8 si se inspecciona fuera de Obsidian.
- `obsidian-advanced-slides` es un complemento de escritorio; se mantiene instalado como parte del enfoque de plantilla completa.
- `image-converter` amplia bastante el flujo con imagenes, pero ahora mismo queda configurado de forma conservadora:
  - preset principal a `WEBP (75, no resizing)`
  - nombres originales o `NoteName-Timestamp`
  - sin forzar conversion global ni redimensionado por defecto

## Hallazgo sobre fuentes personalizadas

- En esta instalacion de Obsidian, varias fuentes tematicas locales (`ttf`/`woff2`) no fueron fiables para el tema `minecraft`, incluso cuando la clase CSS y los selectores si se aplicaban correctamente.
- La variante que si funciono de forma consistente fue cargar la fuente remotamente desde Google Fonts en `Fonts.css` y consumirla directamente por nombre en `Minecraft.css`.
- Como criterio operativo para esta boveda, si una fuente tematica falla en local pero funciona remota, conviene priorizar la fuente remota documentada antes que seguir envolviendola en aliases o conversiones.
- El tema `minecraft` queda usando `Pixelify Sans` cargada desde Google Fonts.
- El tema `osrs` queda usando `IM Fell English` cargada desde Google Fonts.
- `RuneScape-Quill-8.ttf` queda reservado como fuente de enfasis/italica dentro del tema `osrs`.
- Existen clases de utilidad para aplicar solo la tipografia sin el resto del tema:
  - `font-minecraft`
  - `font-osrs`

## Documentacion relacionada

- `99 - Meta/CHANGELOG plantilla.md`
- `99 - Meta/Git portable en esta boveda.md`
- `99 - Meta/Guia CSSClasses y estilos de la boveda.md`
- `.gitignore.notes-repo.example`

## Gitignore de ejemplo

- `.gitignore.notes-repo.example` esta pensado para una boveda real conectada a un repositorio de notas.
- Ignora el estado local de Obsidian, basura del sistema operativo y `git_portable`.
- Mantiene versionables las notas y la configuracion compartible de la boveda.
- Incluye bloques opcionales comentados para excluir datos locales de plugins o adjuntos pesados si hiciera falta.

## Decision sobre plantillas

- La plantilla diaria base usa el core plugin `Templates`.
- No depende de `Templater`.
- Si en el futuro se quieren clases CSS por dia de la semana, enlaces automaticos a ayer/manana, prompts o logica condicional, entonces si tendria sentido evaluar `Templater`.

## Plantillas MOC

- `Plantilla Monthly.md` funciona como MOC temporal del mes.
- Su papel es agrupar objetivos, proyectos activos, eventos y notas del periodo para revisar trabajo y contexto sin perder el enlace con `PARA` ni con notas permanentes.
- `Plantilla Future log.md` funciona como vista de horizonte mas largo.
- Su papel es mantener proyectos planeados, tareas migradas sin fecha y una vision anual para bajar despues ese contenido a mensuales, proyectos o notas mas atomicas.
- En conjunto, estas plantillas refuerzan una capa de navegacion y revision, no una jerarquia nueva: el archivo real sigue viviendo en sus carpetas y notas correspondientes.

## Plugin de imagenes

- `image-converter` se ha añadido como complemento de productividad para trabajar mejor con adjuntos visuales dentro de la boveda.
- Encaja bien con una plantilla completa porque cubre varios casos comunes sin depender de herramientas externas:
  - conversion a `WEBP`
  - compresion ligera
  - renombrado consistente
  - resize no destructivo
  - anotacion y marcado
- La configuracion actual es prudente y reusable:
  - no obliga a convertir siempre
  - mantiene por defecto la carpeta definida por Obsidian
  - permite usar nombres originales o basados en la nota
  - deja preparado un preset `WebP 75` para usarlo cuando interese
