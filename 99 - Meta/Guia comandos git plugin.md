# ✅ **COMANDOS FUNDAMENTALES**
---
## **🔼 Git: Push**

Sube tus commits locales a GitHub.

→ Solo sube **lo que ya está commiteado**.

---

## **🔽 Git: Pull**

Descarga cambios de GitHub a tu bóveda local.

---

## **🔁 Git: Fetch**

Pregunta a GitHub si hay cambios, pero **no los trae a tu carpeta**.

---

## **📝 Git: Commit**

Crea un commit con los cambios que tienes en staging.

→ Es como “guardar una foto” del estado de tu bóveda.

---

## **📝 Git: Commit all changes**

Hace:

1. `git add .`
2. `git commit -m "mensaje"`

Es decir, **mete todos los cambios y los commitea**.

Es el comando más usado en Obsidian.

---

# ⚙️ **COMANDOS DE CONFIGURACIÓN**
---
## **Git: Edit remotes**

Sirve para cambiar o añadir conexiones con GitHub, como:

- `origin`
- usuario/URL del repo

En tu caso, lo usaste para poner:

https://github.com/elguaje404/Obsidian_main_template.git

---

## **Git: Remove remote**

Elimina un remoto configurado (como `origin`).

---

## **Git: Initialize a new repo**

Crea un repositorio nuevo dentro de la bóveda actual.  
Equivale a:

git init

→ Fue lo primero que hiciste, por eso apareció `.git`.

---

## **Git: Clone an existing remote repo**

En vez de crear un repo vacío, **descarga uno desde GitHub**.

Si fueras a usar una bóveda ya existente subida, esta sería la opción correcta.

---

# 🌿 **COMANDOS DE RAMAS**
---
## **Git: Switch branch**

Cambia entre ramas existentes.

---

## **Git: Create new branch**

Crea una rama nueva (ej.: `main`, `develop`, etc).

---

## **Git: Delete branch**

Borra una rama local.

---

## **Git: Switch to remote branch**

Cambia a una rama que está en GitHub, no en local.

Esto fue lo que te provocó el problema de:

> “detached HEAD at origin/main”

porque te movió a una rama remota sin crear una local.

---

## **Git: Set upstream branch**

Conecta una rama local con una rama remota  
(para que `push` y `pull` sepan dónde actuar).

Ejemplo:

git push -u origin main

---

# 🗑️ **COMANDOS DE PELIGRO**
---
## **Git: CAUTION: Delete repository**

Borra la carpeta `.git` entera → pierdes historial pero no archivos.

---

## **Git: CAUTION: Discard all changes**

Tira TODOS los cambios no commiteados.

---

# 🔍 **OTROS COMANDOS ÚTILES**
---
## **Git: Open history view**

Abre una ventana con el historial de commits (muy útil).

---

## **Git: List changed files**

Te muestra qué archivos cambiaron.

---

## **Git: Edit .gitignore**

Abre el archivo donde decides qué NO quieres subir a GitHub.

---

## **Git: Commit-and-sync**

Hace:

1. `add`
2. `commit`
3. `push`
4. `pull`  
    (todo automático)

Muy útil si usas Obsidian en varios dispositivos.

---