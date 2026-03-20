# Git portable en esta boveda

Esta plantilla deja Git portable dentro de la propia boveda para que el plugin `obsidian-git` no dependa de una instalacion global en Windows.

## Estado de la plantilla

- La ruta configurada para Git es relativa:
  - `.obsidian/git_portable/cmd/git.exe`
- El plugin `obsidian-git` sigue instalado y configurado para usar esa ruta.
- La plantilla no incluye ningun repositorio Git inicializado.
- La carpeta `.git/` se elimino para que esta snapshot quede limpia antes de publicarse.

## Cambios aplicados (2026-03-20)

- Se dejo `obsidian-git` apuntando a:
  - `.obsidian/git_portable/cmd/git.exe`
- Se probo un wrapper `.cmd`, pero se descarto por error `spawn EINVAL` en `obsidian-git`.
- El estado final estable vuelve a usar `git.exe` directo.
- El aviso `Can't find a valid git repository` es esperado mientras la boveda no tenga `.git/`.

## Inicializar repo (cuando quieras empezar a versionar)

En Windows, desde la raiz de la boveda:

```powershell
.\.obsidian\git_portable\cmd\git.exe init
.\.obsidian\git_portable\cmd\git.exe add .
.\.obsidian\git_portable\cmd\git.exe commit -m "init vault"
```

Despues de eso, `obsidian-git` ya no deberia mostrar el mensaje de "valid git repository".

## Que se versiona en el repo de la plantilla

En el repo de esta plantilla si tiene sentido guardar:

- `.obsidian/git_portable/`
- snippets, fuentes, plugins y configuracion de la boveda
- notas de documentacion dentro de `99 - Meta/`

La idea es que el repo publique una instalacion completa y reproducible.

## Que conviene hacer al crear una boveda de uso real

Cuando crees una boveda para trabajar con tus notas, lo recomendable es:

1. Copiar o clonar esta plantilla.
2. Crear un repositorio nuevo para tus notas.
3. Elegir una estrategia de `.gitignore` segun tu objetivo:
   - Si quieres portabilidad real entre equipos sin Git instalado: **no ignores** `.obsidian/git_portable/`.
   - Si quieres repos mas ligeros y aceptas depender de Git instalado en cada equipo: puedes ignorar `.obsidian/git_portable/`.
   - En ambos casos conviene ignorar `workspace.json` y `.trash/`.


## Limites de esta solucion

- Esta portabilidad esta pensada sobre todo para Windows.
- En macOS o Linux no funcionara ese `git.exe`.
- Si en una boveda de notas decides ignorar `.obsidian/git_portable/`, el binario seguira existiendo solo en tu copia local, no en el repo.

## Optimizacion conservadora del Git portable

Revision actual del bundle:

- Tamano aproximado: `379.69 MB`
- Archivos: `9293`
- Directorios mas pesados:
  - `mingw64` (~`201.9 MB`)
  - `usr` (~`175.49 MB`)

Recomendacion para evitar problemas:

- No recortar manualmente `mingw64/` ni `usr/` (alto riesgo de romper `git`, `ssh`, `curl` o TLS).
- Mantener `gitPath` en `cmd/git.exe` (es lo mas compatible con `obsidian-git`).
- Si quieres reducir peso de forma segura, hacerlo en una iteracion aparte migrando a un paquete mas pequeño (por ejemplo MinGit) y probando `pull/push` en limpio antes de adoptarlo.

## Diagnostico rapido si en otro equipo aparece "Cannot run git command"

1. Comprobar que existe esta ruta dentro de la boveda:
   - `.obsidian/git_portable/cmd/git.exe`
2. Comprobar que en `obsidian-git` el `gitPath` sigue siendo:
   - `.obsidian/git_portable/cmd/git.exe`
3. Si el archivo no existe en ese equipo, revisar tu `.gitignore` del repo de notas:
   - no debe ignorar `.obsidian/git_portable/` si quieres portabilidad real entre equipos.

## Resumen corto

- La plantilla queda limpia y sin vinculo a ningun repo anterior.
- Git portable sigue disponible dentro de `.obsidian`.
- El repo de la plantilla puede conservar ese binario como parte de la snapshot.
- Si quieres que funcione en cualquier equipo sin instalar Git, el repo de notas debe versionar `.obsidian/git_portable/`.
