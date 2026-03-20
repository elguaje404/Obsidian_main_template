# Guia Vim

Esta nota no sustituye a `Vimtutor`. Sirve como guia de consulta rapida para usar `Vim mode` dentro de Obsidian sin tener que reaprenderlo desde cero cada vez.

## Idea base

- `Normal mode`: moverte, borrar, copiar, cambiar, buscar.
- `Insert mode`: escribir texto.
- `Visual mode`: seleccionar texto.
- `Command mode`: ejecutar comandos con `:`.
- Regla practica: si te pierdes, pulsa `Esc`.

## Supervivencia minima

Estos son los comandos que merece la pena automatizar primero:

```text
Esc      volver a modo normal
i        insertar antes del cursor
a        insertar despues del cursor
o        nueva linea debajo
O        nueva linea encima
x        borrar caracter
u        deshacer
Ctrl-r   rehacer
:w       guardar
:q       salir
:wq      guardar y salir
```

## Movimiento

### Basico

```text
h j k l  izquierda abajo arriba derecha
0        inicio de linea
$        final de linea
gg       inicio de nota
G        final de nota
```

### Por palabras y bloques

```text
w        siguiente palabra
b        palabra anterior
e        final de palabra
(        frase o bloque anterior
)        frase o bloque siguiente
{        parrafo anterior
}        parrafo siguiente
```

### Saltos utiles en Markdown

```text
/texto   buscar hacia delante
?texto   buscar hacia atras
n        siguiente coincidencia
N        coincidencia anterior
%        pareja de (), [], {}
```

## Editar sin entrar en Insert todo el rato

### Borrado

```text
x        borrar caracter
dw       borrar palabra
d$       borrar hasta final de linea
dd       borrar linea
2dd      borrar 2 lineas
diw      borrar palabra actual
```

### Cambio

```text
cw       cambiar palabra
ciw      cambiar palabra actual completa
c$       cambiar hasta final de linea
cc       cambiar linea entera
r        reemplazar un caracter
R        reemplazar escribiendo encima
```

### Copiar y pegar

```text
yy       copiar linea
2yy      copiar 2 lineas
p        pegar debajo o despues
P        pegar encima o antes
```

## Visual mode

```text
v        seleccion por caracteres
V        seleccion por lineas
Ctrl-v   seleccion en bloque
```

Patron util:

```text
v + movimiento + d
v + movimiento + y
v + movimiento + c
```

Ejemplos:

```text
viw      seleccionar palabra actual
Vjj      seleccionar esta linea y dos mas
```

## La logica de Vim

La mayoria de comandos siguen este patron:

```text
[numero] + accion + objeto
```

Ejemplos:

```text
2dd      borrar dos lineas
daw      borrar una palabra con espacios
ciw      cambiar palabra actual
y$       copiar hasta final de linea
```

Acciones frecuentes:

- `d`: borrar
- `c`: cambiar
- `y`: copiar
- `v`: seleccionar

Objetos frecuentes:

- `w`: palabra
- `iw`: palabra actual
- `aw`: palabra con espacio
- `$`: hasta final de linea
- `0`: hasta inicio de linea
- `}`: parrafo siguiente

## Busqueda y sustitucion

```text
/texto           buscar
n                siguiente resultado
N                resultado anterior
:%s/viejo/nuevo/g
:%s/viejo/nuevo/gc
```

Uso recomendado:

- `:%s/foo/bar/g` para cambiar todo de una vez
- `:%s/foo/bar/gc` si quieres confirmar uno por uno

## Comandos que mas ayudan en notas

### Listas

```text
o        crear item debajo
O        crear item encima
dd       borrar item actual
yy p     duplicar item
>>       indentar linea
<<       desindentar linea
```

### Reordenar bloques

```text
ddp      bajar una linea
ddkP     subir una linea
vip      seleccionar parrafo
```

### Tareas

Patron simple:

- moverte con `j` y `k`
- editar con `ciw`, `A`, `I`, `o`
- duplicar con `yy` + `p`
- borrar con `dd`

## Atajos muy utiles para Markdown

```text
A        ir al final de linea e insertar
I        ir al inicio de linea e insertar
fX       saltar hasta caracter X en la linea
tX       saltar hasta antes de X
;        repetir ultimo f/t
,        repetir en sentido contrario
```

Ejemplos:

```text
f]       ir hasta ]
f:       ir hasta :
A        anadir al final de un item
I-       convertir linea en lista rapidamente
```

## Flujo recomendado para Obsidian

Si estas empezando, usa solo este subconjunto durante unos dias:

```text
Esc
j k
w b
0 $
i a o
dd yy p
u Ctrl-r
/ n N
```

Cuando eso salga natural, añade:

```text
ciw
diw
A
I
gg
G
:%s/.../.../gc
```

## Trucos para memorizar

- Piensa en `Vim` como idioma, no como lista de atajos.
- Aprende por patrones: `d`, `c`, `y` sobre `w`, `iw`, `$`, `}`.
- Repite siempre el mismo flujo en notas reales.
- Si dudas entre varios comandos, usa el mas simple que recuerdes.
- Si te bloqueas, `Esc`, reposiciona y vuelve a empezar.

## Mini chuleta

```text
Moverse:      h j k l | w b e | 0 $ | gg G
Insertar:     i a o O | A I
Borrar:       x | dw | dd | diw
Cambiar:      cw | ciw | cc | c$
Copiar:       yy | p | P
Seleccionar:  v | V | Ctrl-v
Buscar:       / ? n N
Deshacer:     u | Ctrl-r
Guardar:      :w
```

## Para practicar en esta boveda

Ejercicios cortos:

1. Duplicar una tarea con `yy` y `p`.
2. Cambiar una palabra con `ciw`.
3. Moverte al final de una nota con `G` y volver arriba con `gg`.
4. Buscar una etiqueta o propiedad con `/`.
5. Reordenar dos lineas con `ddp`.

## Relacion con otras notas

- [Vimtutor](/D:/Obsidian_Main_template/99%20-%20Meta/Vimtutor.md)
- [trucos en obsidian](/D:/Obsidian_Main_template/99%20-%20Meta/trucos%20en%20obsidian.md)
- [Guia propiedades](/D:/Obsidian_Main_template/99%20-%20Meta/Guia%20propiedades.md)
