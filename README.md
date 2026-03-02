# ReponNuevo

Repositorio para seguir el curso de GitHub en Platzi y no olvidar los comandos importantes para un buen trabajo y buenas prácticas.

---

## Comandos importantes de Git

### Configuración inicial
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
git config --global core.editor "code --wait"   # Usar VS Code como editor
```

### Iniciar un repositorio
```bash
git init                  # Inicializar repositorio local
git clone <url>           # Clonar repositorio remoto
```

### Estado y seguimiento
```bash
git status                # Ver estado del repositorio
git log                   # Ver historial de commits
git log --oneline --graph # Ver historial compacto con grafo de ramas
git diff                  # Ver cambios no preparados
git diff --staged         # Ver cambios preparados (en staging)
```

### Guardar cambios
```bash
git add <archivo>         # Agregar archivo al área de staging
git add .                 # Agregar todos los cambios al staging
git commit -m "mensaje"   # Confirmar cambios con mensaje
git commit -am "mensaje"  # Agregar y confirmar archivos rastreados en un solo paso
```

### Ramas (Branches)
```bash
git branch                      # Listar ramas locales
git branch <nombre>             # Crear nueva rama
git checkout <nombre>           # Cambiar de rama
git checkout -b <nombre>        # Crear y cambiar a nueva rama
git switch -c <nombre>          # Crear y cambiar a nueva rama (forma moderna)
git merge <rama>                # Fusionar rama en la rama actual
git branch -d <nombre>          # Eliminar rama (seguro)
git branch -D <nombre>          # Eliminar rama (forzado)
```

### Repositorio remoto
```bash
git remote -v                       # Ver repositorios remotos configurados
git remote add origin <url>         # Agregar repositorio remoto
git push origin <rama>              # Enviar cambios al remoto
git push -u origin <rama>           # Enviar y establecer rama de seguimiento
git pull origin <rama>              # Traer y fusionar cambios del remoto
git fetch origin                    # Traer cambios del remoto sin fusionar
```

### Deshacer cambios
```bash
git restore <archivo>             # Descartar cambios en el área de trabajo
git restore --staged <archivo>    # Quitar archivo del staging
git revert <commit>               # Revertir un commit (crea nuevo commit)
git reset --soft HEAD~1           # Deshacer último commit, mantener cambios en staging
git reset --mixed HEAD~1          # Deshacer último commit, mantener cambios sin staging
git reset --hard HEAD~1           # Deshacer último commit y descartar cambios (¡cuidado!)
```

### Stash (almacenamiento temporal)
```bash
git stash                         # Guardar cambios temporalmente
git stash list                    # Listar stashes guardados
git stash pop                     # Aplicar y eliminar el último stash
git stash apply stash@{n}         # Aplicar un stash específico sin eliminarlo
git stash drop stash@{n}          # Eliminar un stash específico
```

### Etiquetas (Tags)
```bash
git tag                           # Listar etiquetas
git tag <nombre>                  # Crear etiqueta ligera
git tag -a <nombre> -m "mensaje"  # Crear etiqueta anotada
git push origin <nombre-tag>      # Publicar etiqueta en el remoto
git push origin --tags            # Publicar todas las etiquetas
```

---

## Buenas prácticas

- **Commits atómicos**: cada commit debe representar un único cambio lógico.
- **Mensajes descriptivos**: usar mensajes claros en imperativo, p. ej. `Agrega validación de formulario`.
- **Ramas por funcionalidad**: crear una rama por cada nueva característica o corrección (`feature/`, `fix/`, `hotfix/`).
- **Pull Requests**: revisar el código antes de fusionar ramas principales.
- **`.gitignore`**: excluir archivos que no deben rastrearse (dependencias, variables de entorno, archivos del sistema).
- **No hacer `push --force` en ramas compartidas**: puede sobreescribir el trabajo de otros.
- **Sincronizar frecuentemente**: hacer `git pull` antes de empezar a trabajar para evitar conflictos.

---

## Recursos

- [Documentación oficial de Git](https://git-scm.com/doc)
- [Platzi - Curso profesional de Git y GitHub](https://platzi.com/cursos/git-github/)
- [GitHub Docs](https://docs.github.com)
