---
cssclasses:
---

Esta nota sirve como referencia rápida de:

- cambios visuales globales activos en la bóveda
- `cssclasses` disponibles para notas concretas
- combinaciones recomendadas

## Vista rapida

| Area | Estado actual |
| --- | --- |
| Fuente de interfaz | `Junicode` |
| Fuente de texto | `JetBrains Mono` |
| Fuente de codigo | `JetBrains Mono` |
| Snippets activos | `Fonts`, `CyanVoxel's General Tweaks`, `Colored Sidebar Items`, `Daily Note Themes`, `Japanese Font Support`, `Minecraft`, `Notebook Backgrounds`, `Runescape` |

## Cambios globales activos

Estos cambios afectan a toda la boveda salvo que una nota use una clase tematica que los sobreescriba:

- La interfaz de Obsidian usa `Junicode`.
- El texto normal de las notas usa `JetBrains Mono`.
- El texto de codigo, inline code y bloques de codigo usa `JetBrains Mono`.
- Los enlaces no muestran subrayado por defecto.
- Las imagenes tienen bordes redondeados.
- Los callouts tienen esquinas redondeadas.
- Los checkboxes tienen un borde algo mas grueso.
- La sidebar colorea carpetas segun prefijos numericos como `00`, `01`, `02`, `03`, etc.

## Ajustes de plantilla

- Las notas diarias de la plantilla se crean en `06 - Daily/`.
- El formato por defecto de daily note es `YYYY-MM-DD`.
- Obsidian Sync no queda activado en la plantilla base.

## Como usar cssclasses

En cualquier nota puedes declarar una o varias clases en el frontmatter:

```yaml
---
cssclasses:
  - center-images
  - page-manila
  - pen-blue
---
```

Tambien puedes escribir una sola clase:

```yaml
---
cssclasses: minecraft
---
```

## Catalogo de clases

### Utilidades generales

| Clase | Efecto |
| --- | --- |
| `center-images` | Centra las imagenes de la nota |
| `image-borders` | Anade un borde suave a las imagenes |
| `center-titles` | Centra todos los encabezados |
| `no-embed-border` | Quita el borde lateral de embeds |

Ejemplo:

```yaml
---
cssclasses:
  - center-images
  - center-titles
---
```

### Soporte japones

| Clase | Efecto |
| --- | --- |
| `japanese` | Usa una fuente mas adecuada para texto japones en la nota |

Ejemplo:

```yaml
---
cssclasses: japanese
---
```

### Daily Note Themes

Clase base:

- `daily`

Clases de dia:

- `sunday` o `Sunday`
- `monday` o `Monday`
- `tuesday` o `Tuesday`
- `wednesday` o `Wednesday`
- `thursday` o `Thursday`
- `friday` o `Friday`
- `saturday` o `Saturday`

Efectos:

- cambia fondo, colores de texto, enlaces y checkboxes
- rediseña encabezados `h1`, `h2`, `h3` y `h4`
- centra las imagenes de la nota

Ejemplo:

```yaml
---
cssclasses:
  - daily
  - friday
---
```

### Minecraft

| Clase | Efecto |
| --- | --- |
| `minecraft` | Aplica una estetica inspirada en Minecraft a la nota |
| `font-minecraft` | Aplica solo la tipografia estilo Minecraft sin el resto del tema |

Efectos:

- paleta de color verde y oscura
- fuente tematica para el texto de la nota
- ajustes de encabezados, iconos, metadata y detalles visuales

Ejemplo:

```yaml
---
cssclasses: minecraft
---
```

Solo tipografia:

```yaml
---
cssclasses: font-minecraft
---
```

### RuneScape

| Clase | Efecto |
| --- | --- |
| `osrs` | Aplica una estetica inspirada en Old School RuneScape |
| `font-osrs` | Aplica solo la tipografia estilo RuneScape sin el resto del tema |

Efectos:

- paleta marron y naranja
- fuente `IM Fell English` para la nota
- cursiva/enfasis con `RuneScape Quill 8`
- ajustes de encabezados, enlaces e iconos

Ejemplo:

```yaml
---
cssclasses: osrs
---
```

Solo tipografia:

```yaml
---
cssclasses: font-osrs
---
```

### Notebook Backgrounds

Clases de pagina:

| Clase | Efecto |
| --- | --- |
| `page-white` | Papel blanco |
| `page-manila` | Papel manila |
| `page-blueprint` | Papel blueprint |

Clases de tinta:

| Clase | Efecto |
| --- | --- |
| `pen-white` | Tinta blanca |
| `pen-blue` | Tinta azul |
| `pen-red` | Tinta roja |
| `pen-green` | Tinta verde |
| `pen-black` | Tinta negra |
| `pen-gray` | Tinta gris |
| `pen-purple` | Tinta morada |

Clases extra:

| Clase | Efecto |
| --- | --- |
| `page-grid` | Anade cuadricula al fondo |
| `recolor-images` | Recolorea imagenes segun el color de tinta |

Efectos generales:

- cambia fondo, color de texto, enlaces y bordes
- cambia el estilo de bloques de codigo dentro de notas con `page-*`
- modifica el aspecto de elementos interactivos como tags, checkboxes y callouts

Ejemplos:

```yaml
---
cssclasses:
  - page-manila
  - pen-black
---
```

```yaml
---
cssclasses:
  - page-blueprint
  - pen-white
  - page-grid
---
```

## Combinaciones recomendadas

| Objetivo | Clases |
| --- | --- |
| Diario tematico | `daily` + un dia de la semana |
| Nota estilo cuaderno clasico | `page-manila` + `pen-black` |
| Nota clara con tinta azul | `page-white` + `pen-blue` |
| Plano tecnico | `page-blueprint` + `pen-white` + `page-grid` |
| Nota estilo Minecraft | `minecraft` |
| Nota estilo RuneScape | `osrs` |
| Solo fuente Minecraft | `font-minecraft` |
| Solo fuente RuneScape | `font-osrs` |
| Complemento visual | `center-images` o `center-titles` |

## Reglas practicas

- `minecraft`, `osrs`, `daily` y `page-*` son clases tematicas fuertes.
- `font-minecraft` y `font-osrs` son clases ligeras: cambian tipografia, no el tema completo.
- Lo normal es usar solo una familia tematica fuerte por nota.
- `center-images`, `image-borders`, `center-titles` y `no-embed-border` si son buenas clases de apoyo.
- Si mezclas varias clases tematicas fuertes, el resultado dependera de que variables toque cada snippet.

## Plantillas utiles

### Diario

```yaml
---
cssclasses:
  - daily
  - monday
---
```

### Nota tipo cuaderno

```yaml
---
cssclasses:
  - page-manila
  - pen-black
  - center-images
---
```

### Nota experimental

```yaml
---
cssclasses:
  - page-blueprint
  - pen-white
  - page-grid
  - recolor-images
---
```
