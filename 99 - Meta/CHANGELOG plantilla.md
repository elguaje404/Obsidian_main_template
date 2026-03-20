# CHANGELOG plantilla

## 2026-03-20

### Git portable

- `obsidian-git` queda configurado con ruta relativa estable a `.obsidian/git_portable/cmd/git.exe`.
- Se documenta que el mensaje `Can't find a valid git repository` es esperado si la boveda aun no tiene `.git/`.
- Se anade en `99 - Meta/Git portable en esta boveda.md` un bloque de inicializacion minima (`git init`, `add`, `commit`) usando el binario portable.
- Se documenta una revision conservadora de optimizacion del bundle portable: no recortar manualmente `mingw64/` y `usr/` para evitar roturas.

## 2026-03-19

### Coherencia general

- Se desactivo `Obsidian Sync` en la plantilla base.
- Se configuraron las notas diarias para crear archivos en `06 - Daily/` con formato `YYYY-MM-DD`.
- Se limpio el `workspace` inicial para evitar pestanas duplicadas.

### Visual y tema

- Se redujo el solapamiento entre `Minimal` y snippets CSS.
- `Fonts.css` queda centrado en fuentes y deja el tamano al tema y a su plugin.
- Se elimino una regla redundante de decoracion de enlaces en `CyanVoxel's General Tweaks.css`.
- `Minimal Theme Settings` ya no fuerza subrayado de enlaces.
- Los temas `Minecraft` y `Runescape` pasan a usar fuentes locales cargadas con `@font-face`.
- `Daily Note Themes` se ordena para usar `JetBrainsMonoCustom` como familia local coherente.
- Se documenta que en esta boveda las fuentes tematicas fueron mas fiables al referenciarlas por nombre real de familia desde los snippets, en vez de depender de aliases intermedios.
- El tema `osrs` reserva `RuneScape-Quill-8.ttf` para enfasis/italica.
- Se confirma que `minecraft` no fue fiable con fuentes locales y pasa a usar `Pixelify Sans` cargada remotamente desde Google Fonts y consumida directamente desde el snippet del tema.
- `osrs` pasa a usar `IM Fell English` cargada remotamente desde Google Fonts.
- Se anaden clases utilitarias `font-minecraft` y `font-osrs` para aplicar solo la tipografia de cada estilo sin activar el tema visual completo.

### Excalidraw

- La carpeta base pasa a `99 - Meta/Excalidraw/`.
- La carpeta de scripts pasa a `99 - Meta/Excalidraw/Scripts/`.
- La carpeta de fuentes CJK pasa a `99 - Meta/Excalidraw/CJK Fonts/`.
- La ruta de plantilla por defecto se deja vacia hasta definir una plantilla real.

### Documentacion

- Se anadieron notas de auditoria y referencia central para la plantilla.
- Se actualizo la guia de estilos para reflejar ajustes reales de la plantilla.
- Se amplio `.gitignore.notes-repo.example` como base para una boveda real sincronizada con Git.

### Plantilla diaria

- Se configuro el core plugin `Templates` con carpeta `99 - Meta/Templates/`.
- Se anadio una plantilla diaria base en `99 - Meta/Templates/Plantilla Daily.md`.
- `Daily Notes` ahora usa esa plantilla al crear notas nuevas.
