# 🚀 Git y GitHub - Bootcamp Completo para Principiantes

## Tabla de Contenidos

1. [Introducción](#introducción)
2. [Conceptos Básicos](#conceptos-básicos)
3. [Instalación y Configuración](#instalación-y-configuración)
4. [Primeros Pasos](#primeros-pasos)
5. [Comandos Fundamentales](#comandos-fundamentales)
6. [Flujo de Trabajo Local](#flujo-de-trabajo-local)
7. [Trabajando con Repositorios Remotos](#trabajando-con-repositorios-remotos)
8. [Ramas y Branching](#ramas-y-branching)
9. [Colaboración y Pull Requests](#colaboración-y-pull-requests)
10. [Resolución de Conflictos](#resolución-de-conflictos)
11. [Ejercicios Prácticos](#ejercicios-prácticos)
12. [Buenas Prácticas](#buenas-prácticas)
13. [Recursos Adicionales](#recursos-adicionales)

---

## Introducción

### ¿Qué es Git?

Git es un **sistema de control de versiones distribuido** que permite:
- Rastrear cambios en tus archivos
- Colaborar con otros desarrolladores
- Mantener un historial completo de tu proyecto
- Volver a versiones anteriores si es necesario

### ¿Qué es GitHub?

GitHub es una plataforma que:
- Aloja repositorios Git en la nube
- Facilita la colaboración entre equipos
- Proporciona herramientas de gestión de proyectos
- Permite compartir y descubrir código

### ¿Por qué aprender Git y GitHub?

✅ Es el estándar de la industria
✅ Fundamental para cualquier desarrollo de software
✅ Esencial para el trabajo en equipo
✅ Mejora tu flujo de trabajo personal

---

## Conceptos Básicos

### Terminología Esencial

| Término | Descripción |
|---------|------------|
| **Repositorio (Repo)** | Carpeta que contiene tu proyecto y todo su historial |
| **Commit** | Snapshot (foto) de tu código en un momento específico |
| **Branch** | Rama de desarrollo independiente |
| **Master/Main** | Rama principal del proyecto |
| **Remote** | Repositorio alojado en la nube (GitHub) |
| **Pull** | Traer cambios del repositorio remoto |
| **Push** | Enviar cambios al repositorio remoto |
| **Merge** | Fusionar cambios de una rama a otra |
| **Clone** | Descargar un repositorio completo |
| **Fork** | Copiar un repositorio de otro usuario |
| **Pull Request (PR)** | Propuesta de cambios para ser revisada |

### Flujo Básico de Git

```
Cambios en archivos → Stage → Commit → Push → GitHub
                      (add)           (local)  (remoto)
```

---

## Instalación y Configuración

### Para Windows

1. Descarga Git desde: https://git-scm.com/download/win
2. Ejecuta el instalador
3. Sigue las instrucciones (acepta las opciones por defecto)

### Para macOS

```bash
# Usando Homebrew
brew install git

# O usando el instalador oficial
# Descarga desde https://git-scm.com/download/mac
```

### Para Linux

```bash
# Ubuntu/Debian
sudo apt-get update
sudo apt-get install git

# Fedora
sudo dnf install git

# Arch
sudo pacman -S git
```

### Verificar la Instalación

```bash
git --version
# Deberías ver algo como: git version 2.40.0
```

### Configuración Inicial

```bash
# Configura tu nombre (se verá en los commits)
git config --global user.name "Tu Nombre"

# Configura tu email (debe ser el mismo de GitHub)
git config --global user.email "tu@email.com"

# Verifica la configuración
git config --global --list
```

---

## Primeros Pasos

### Crear tu Primera Cuenta en GitHub

1. Ve a https://github.com
2. Haz clic en "Sign up"
3. Completa el registro con:
   - Email
   - Contraseña
   - Nombre de usuario (username)
4. Verifica tu email

### Crear tu Primer Repositorio en GitHub

1. Inicia sesión en GitHub
2. Haz clic en el icono `+` en la esquina superior derecha
3. Selecciona "New repository"
4. Completa:
   - **Repository name**: `mi-primer-repo`
   - **Description**: Opcional pero recomendado
   - **Public/Private**: Elige Public para aprender
   - **Initialize with README**: Marca esta opción
5. Haz clic en "Create repository"

---

## Comandos Fundamentales

### 1. Inicializar un Repositorio

```bash
# En la carpeta de tu proyecto
git init

# Esto crea una carpeta oculta .git
# que contiene todo el historial de tu proyecto
```

**¿Cuándo usarlo?** Cuando comienzes un proyecto nuevo desde cero.

---

### 2. Clonar un Repositorio Existente

```bash
# Descargar un repositorio completo
git clone https://github.com/usuario/nombre-repo.git

# Descargar en una carpeta específica
git clone https://github.com/usuario/nombre-repo.git mi-carpeta
```

**¿Cuándo usarlo?** Cuando quieras trabajar con un proyecto existente.

---

### 3. Ver el Estado del Repositorio

```bash
git status

# Output ejemplo:
# On branch main
# Changes not staged for commit:
#   modified:   archivo.txt
# Untracked files:
#   nuevo-archivo.js
```

**¿Cuándo usarlo?** Siempre que quieras ver qué cambios tienes.

---

### 4. Agregar Archivos (Stage)

```bash
# Agregar un archivo específico
git add archivo.txt

# Agregar todos los cambios
git add .

# Agregar todos los cambios de un tipo de archivo
git add *.js

# Ver qué se va a agregar
git diff --staged
```

**¿Cuándo usarlo?** Antes de hacer un commit, prepara qué cambios incluir.

---

### 5. Hacer un Commit

```bash
# Commit con mensaje
git commit -m "Descripción clara del cambio"

# Ejemplo bien escrito:
git commit -m "Agregar función de autenticación al login"

# Commit de un archivo específico
git commit archivo.txt -m "Actualizar documentación"

# Ver cambios antes de commitear
git diff
```

**¿Cuándo usarlo?** Después de agregar archivos, para grabar los cambios.

---

### 6. Ver el Historial de Commits

```bash
# Ver todos los commits
git log

# Ver últimos 5 commits
git log -5

# Ver en una línea (más compacto)
git log --oneline

# Ver cambios específicos de un autor
git log --author="nombre"

# Ver commits de los últimos 2 días
git log --since="2 days ago"
```

**¿Cuándo usarlo?** Para entender qué cambios se han hecho.

---

### 7. Ver Diferencias

```bash
# Ver cambios no preparados
git diff

# Ver cambios preparados
git diff --staged

# Ver cambios entre commits
git diff commit1 commit2

# Ver cambios en un archivo específico
git diff archivo.txt
```

**¿Cuándo usarlo?** Para revisar exactamente qué cambió.

---

## Flujo de Trabajo Local

### El Ciclo Básico: Modificar → Stage → Commit

**Paso 1: Hacer cambios**
```bash
# Edita tus archivos
# (usando tu editor favorito)
```

**Paso 2: Verificar cambios**
```bash
git status
git diff
```

**Paso 3: Preparar cambios**
```bash
git add .
```

**Paso 4: Confirmar cambios**
```bash
git commit -m "Descripción clara del cambio"
```

**Paso 5: Verificar**
```bash
git log --oneline
```

### Deshacer Cambios

```bash
# Descartar cambios en un archivo (sin preparar)
git restore archivo.txt

# O la forma antigua
git checkout -- archivo.txt

# Descartar cambios preparados
git restore --staged archivo.txt

# Deshacer el último commit (mantener cambios)
git reset --soft HEAD~1

# Deshacer el último commit (perder cambios)
git reset --hard HEAD~1

# Volver a una versión anterior
git revert hash-del-commit
```

---

## Trabajando con Repositorios Remotos

### Conectar con GitHub

```bash
# Ver repositorios remotos configurados
git remote -v

# Agregar un repositorio remoto
git remote add origin https://github.com/tu-usuario/tu-repo.git

# Cambiar URL del remoto
git remote set-url origin https://github.com/nuevo-url.git
```

### Enviar Cambios a GitHub

```bash
# Enviar commits a GitHub
git push origin main

# Primera vez (crea rama en GitHub)
git push -u origin main

# Forzar push (¡usar con cuidado!)
git push --force
```

### Descargar Cambios de GitHub

```bash
# Descargar cambios
git pull origin main

# Equivalente a:
# git fetch origin
# git merge origin/main
```

### Sincronizar Local con Remoto

```bash
# Descargar cambios sin fusionar
git fetch origin

# Mira qué cambios hay
git status

# Luego fusiona manualmente si quieres
git merge origin/main
```

---

## Ramas y Branching

### ¿Por qué usar ramas?

- Trabajar en features sin afectar el código principal
- Colaborar sin conflictos
- Mantener main/master estable

### Crear y Cambiar Ramas

```bash
# Ver todas las ramas locales
git branch

# Ver todas las ramas (local + remoto)
git branch -a

# Crear una rama nueva
git branch nombre-rama

# Cambiar a una rama
git checkout nombre-rama

# O la forma moderna
git switch nombre-rama

# Crear y cambiar en un comando
git checkout -b nombre-rama

# O
git switch -c nombre-rama
```

### Nombrar Ramas Correctamente

```bash
# ❌ Malo
git checkout -b feature
git checkout -b bug

# ✅ Bueno
git checkout -b feature/login-form
git checkout -b bug/header-alignment
git checkout -b docs/readme-update
git checkout -b refactor/database-connection
```

### Fusionar Ramas

```bash
# Cambiar a la rama donde quieres fusionar
git checkout main

# Fusionar otra rama
git merge feature/login-form

# Ver ramas ya fusionadas
git branch --merged

# Ver ramas no fusionadas
git branch --no-merged

# Eliminar una rama
git branch -d nombre-rama

# Forzar eliminación
git branch -D nombre-rama
```

---

## Colaboración y Pull Requests

### Flujo típico de colaboración

1. Creas una rama para tu feature
2. Haces commit de tus cambios
3. Empujas la rama a GitHub
4. Abres un Pull Request (PR)
5. Otros revisan tu code
6. Haces ajustes si es necesario
7. Se fusiona a main

### Crear un Pull Request

**Paso 1: Trabajar en tu rama**
```bash
git checkout -b feature/nueva-funcionalidad
# ... hacer cambios ...
git add .
git commit -m "Implementar nueva funcionalidad"
git push -u origin feature/nueva-funcionalidad
```

**Paso 2: En GitHub:**
1. Ve a tu repositorio
2. Haz clic en "Compare & pull request"
3. Llena el formulario del PR:
   - Título claro
   - Descripción detallada
   - Reference issues si aplica
4. Haz clic en "Create Pull Request"

### Hacer cambios en un PR

```bash
# Simplemente haz más cambios en tu rama
git add .
git commit -m "Ajustar feedback del revisor"
git push origin feature/nueva-funcionalidad

# Los cambios se agregan automáticamente al PR
```

### Revisar Pull Requests

```bash
# Ver PRs en tu repositorio (desde GitHub)
# 1. Ve a la pestaña "Pull Requests"
# 2. Selecciona el PR
# 3. Revisa los cambios en "Files changed"
# 4. Deja comentarios

# Para probar localmente:
git fetch origin
git checkout origin/feature-branch
```

---

## Resolución de Conflictos

### ¿Cuándo ocurren conflictos?

Cuando dos personas editan la misma línea en archivos diferentes o la misma rama.

### Resolver un Conflicto

**Paso 1: Intentar merge**
```bash
git merge feature/otra-rama
# CONFLICT (content merge): ¡Conflicto!
```

**Paso 2: Ver conflictos**
```bash
git status

# O
cat archivo-con-conflicto.txt
```

**El archivo mostrará:**
```
<<<<<<< HEAD
Tu versión (main)
=======
Versión de la otra rama
>>>>>>> feature/otra-rama
```

**Paso 3: Resolver manualmente**

Edita el archivo y elige cuál versión mantener:

```javascript
// ✅ Opción 1: Cada cambio por separado
function miFunction() {
  // cambios de main
  // cambios de otra rama
}

// ✅ Opción 2: Solo uno
function miFunction() {
  // cambios de otra rama (mejor implementación)
}
```

**Paso 4: Completar el merge**
```bash
git add archivo-resuelto.txt
git commit -m "Resolver conflicto en merge"
git push
```

### Usando herramientas para Conflictos

```bash
# Usar VS Code para resolver
git config --global core.editor "code"

# O herramientas especializadas
# gitk, meld, kdiff3, etc.

# Abortar un merge si lo necesitas
git merge --abort
```

---

## Ejercicios Prácticos

### Ejercicio 1: Configuración Inicial

**Objetivo:** Configurar Git y crear tu primer repositorio

```bash
# 1. Verifica que Git está instalado
git --version

# 2. Configura tu identidad
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"

# 3. Verifica la configuración
git config --global --list

# 4. Crea una carpeta para el proyecto
mkdir mi-primer-proyecto
cd mi-primer-proyecto

# 5. Inicializa un repositorio
git init

# 6. Verifica que se creó
ls -la
# Deberías ver la carpeta ".git"
```

**Verificación:** ¿Puedes ver la carpeta `.git`?

---

### Ejercicio 2: Primer Commit

**Objetivo:** Crear archivos y hacer tu primer commit

```bash
# 1. Crea un archivo
echo "# Mi Primer Proyecto" > README.md

# 2. Ver estado
git status

# 3. Preparar cambios
git add README.md

# 4. Verificar que está preparado
git status

# 5. Hacer commit
git commit -m "Agregar README inicial"

# 6. Ver el historial
git log
```

**Desafío:** Crea dos archivos más (index.html y style.css) en un solo commit.

---

### Ejercicio 3: Cambios y Diferencias

**Objetivo:** Practicar git diff y cambios

```bash
# 1. Modifica el README.md
echo "## Descripción del Proyecto" >> README.md

# 2. Ver cambios sin preparar
git diff

# 3. Preparar cambios
git add README.md

# 4. Ver cambios preparados
git diff --staged

# 5. Hacer commit
git commit -m "Agregar sección de descripción"

# 6. Ver historial con cambios
git log -p

# 7. Ver en una línea
git log --oneline
```

**Verificación:** ¿Puedes ver las diferencias entre commits?

---

### Ejercicio 4: Crear y Cambiar Ramas

**Objetivo:** Entender el concepto de branching

```bash
# 1. Ver rama actual
git branch

# 2. Crear una rama nueva
git branch feature/formulario

# 3. Cambiar a la rama
git switch feature/formulario

# 4. Criar tus cambios en esta rama
echo "<form></form>" > formulario.html
git add formulario.html
git commit -m "Crear formulario HTML"

# 5. Ver ramas
git branch

# 6. Cambiar a main
git switch main

# 7. Nota que el archivo no está aquí
ls

# 8. Cambiar de vuelta
git switch feature/formulario

# 9. El archivo aparece de nuevo
ls
```

**Desafío:** Crea 3 ramas diferentes y cambia entre ellas.

---

### Ejercicio 5: Fusionar Ramas

**Objetivo:** Practicar merges simples

```bash
# 1. Asegúrate de estar en main
git switch main

# 2. Crea una rama de feature
git checkout -b feature/estilos

# 3. Haz cambios
echo "body { margin: 0; }" > estilos.css
git add estilos.css
git commit -m "Agregar estilos básicos"

# 4. Vuelve a main
git switch main

# 5. Fusiona la rama
git merge feature/estilos

# 6. Verifica que los archivos están en main
ls

# 7. Ver historial
git log --oneline

# 8. Elimina la rama
git branch -d feature/estilos
```

**Verificación:** ¿Los cambios están ahora en main?

---

### Ejercicio 6: Crear Repositorio en GitHub

**Objetivo:** Conectar tu proyecto local con GitHub

```bash
# 1. Crea un repositorio en GitHub (username/mi-primer-proyecto)

# 2. En tu terminal local
git remote add origin https://github.com/tu-usuario/mi-primer-proyecto.git

# 3. Verifica la conexión
git remote -v

# 4. Cambia el nombre de la rama (si es necesario)
git branch -M main

# 5. Envía tus cambios
git push -u origin main

# 6. Verifica en GitHub
# Ve a https://github.com/tu-usuario/mi-primer-proyecto
```

**Verificación:** ¿Puedes ver tus commits en GitHub?

---

### Ejercicio 7: Push y Pull

**Objetivo:** Practicar sincronización con GitHub

```bash
# 1. Haz un cambio local
echo "## Instalación" >> README.md
git add README.md
git commit -m "Agregar sección instalación"

# 2. Envía a GitHub
git push origin main

# 3. Verifica en GitHub que está actualizado

# 4. Haz un cambio directamente en GitHub:
#    - Ve a README.md
#    - Haz clic en el icono de editar
#    - Agregar una línea
#    - Commit the change

# 5. Descarga los cambios
git pull origin main

# 6. Verifica el cambio localmente
cat README.md
```

**Desafío:** Crea un .gitignore en GitHub, descárgalo, edítalo localmente y vuelve a subirlo.

---

### Ejercicio 8: Resolver Conflictos

**Objetivo:** Practicar resolución de conflictos

```bash
# 1. Crea dos ramas
git checkout -b rama-a
echo "Versión A" > archivo.txt
git add archivo.txt
git commit -m "Crear archivo versión A"

# 2. Vuelve a main
git checkout main

# 3. Crea otra rama
git checkout -b rama-b
echo "Versión B" > archivo.txt
git add archivo.txt
git commit -m "Crear archivo versión B"

# 4. Vuelve a main
git checkout main

# 5. Fusiona la primera rama (sin conflicto)
git merge rama-a

# 6. Intenta fusionar la segunda (¡conflicto!)
git merge rama-b

# 7. Ver conflicto
cat archivo.txt

# 8. Resuelve el conflicto (edita el archivo)
# Mantén la versión que prefieras

# 9. Completa el merge
git add archivo.txt
git commit -m "Resolver conflicto entre rama-a y rama-b"

# 10. Ver resultado
git log --oneline --graph --all
```

**Desafío:** Crea un conflicto más complejo con múltiples líneas.

---

### Ejercicio 9: Historial y Búsqueda

**Objetivo:** Dominar git log y búsquedas

```bash
# 1. Ver historial completo
git log

# 2. Ver en una línea
git log --oneline

# 3. Ver últimos 3 commits
git log -3

# 4. Ver historial gráfico
git log --graph --oneline --all

# 5. Buscar por mensaje
git log --grep="Agregar"

# 6. Buscar por autor
git log --author="Tu Nombre"

# 7. Ver cambios de una fecha
git log --since="2024-01-01"

# 8. Ver commits de un archivo específico
git log -- README.md

# 9. Ver quién cambió cada línea
git blame archivo.txt
```

**Desafío:** Encuentra el commit que introdujo un cambio específico.

---

### Ejercicio 10: Pull Request Completo

**Objetivo:** Hacer un PR real con revisión

```bash
# 1. Crea una rama para una feature
git checkout -b feature/descripcion-mejorada

# 2. Haz cambios
echo "## Descripción Detallada" >> README.md
git add README.md
git commit -m "Mejorar descripción del proyecto"

# 3. Envía a GitHub
git push -u origin feature/descripcion-mejorada

# 4. En GitHub:
#    - Haz clic en "Compare & pull request"
#    - Llena la descripción
#    - Crea el PR

# 5. Revisa los cambios en la pestaña "Files changed"

# 6. Haz clic en "Merge pull request"

# 7. Elimina la rama remota

# 8. Localmente:
git checkout main
git pull origin main
git branch -d feature/descripcion-mejorada
```

**Desafío:** Pide que alguien más revise y comente tu PR.

---

## Buenas Prácticas

### 1. Mensajes de Commit Claros

```bash
# ❌ Malo
git commit -m "fix bug"
git commit -m "update stuff"
git commit -m "."

# ✅ Bueno
git commit -m "Arreglar validación de email en formulario"
git commit -m "Actualizar dependencias de seguridad"
git commit -m "Refactorizar función calcularTotal para mejor legibilidad"
```

**Formato recomendado:**
```
<tipo>(<scope>): <descripción breve>

<descripción detallada si es necesario>

<referencias a issues>
```

**Tipos comunes:**
- `feat`: Nueva funcionalidad
- `fix`: Corrección de bug
- `docs`: Cambios en documentación
- `style`: Cambios de formato (espacios, comas, etc.)
- `refactor`: Reestructuración sin cambiar funcionalidad
- `perf`: Mejoras de rendimiento
- `test`: Agregar o actualizar tests

---

### 2. Commits Atómicos

Cada commit debe representar **un cambio lógico completo**.

```bash
# ❌ Malo: Todo en un commit
git add .
git commit -m "Actualizar login, agregar validación, arreglar bug, actualizar docs"

# ✅ Bueno: Commits separados
git add autenticacion.js
git commit -m "Implementar validación de email"

git add formulario.js
git commit -m "Agregar validación de contraseña fuerte"

git add bug-resolver.js
git commit -m "Arreglar error en reset de formulario"

git add README.md
git commit -m "Documentar nuevas funciones de validación"
```

---

### 3. Usar .gitignore

```bash
# Crear archivo .gitignore
cat > .gitignore << EOF
# Dependencias
node_modules/
venv/

# Variables de entorno
.env
.env.local

# Archivos del editor
.vscode/
.idea/
*.swp

# Logs
*.log
logs/

# Compilados
dist/
build/
*.pyc
EOF

git add .gitignore
git commit -m "Agregar gitignore"
```

---

### 4. Mantener Main Estable

```bash
# ❌ Nunca:
# - Trabajar directamente en main
# - Hacer push de código incompleto a main
# - Romper tests en main

# ✅ Siempre:
git checkout -b feature/nombre
# ...trabajo...
# ...tests pasan...
# ...pull request y revisión...
git merge a main
```

---

### 5. Rebase vs Merge

**Merge:**
```bash
# Crea un commit de fusión
# Historial más claro pero con merge commits
git merge feature/rama
```

**Rebase (para ramas locales):**
```bash
# Reescribe historial
# Historial más limpio pero usa con cuidado
git rebase main
```

**Regla de oro:** Nunca hagas rebase en ramas compartidas.

---

### 6. Revisar Antes de Hacer Push

```bash
# Siempre verifica antes de empujar
git log --oneline main..origin/main  # Ver cambios que harías pull
git diff main origin/main             # Ver diferencias

# Luego sí
git push
```

---

### 7. Sincronizarse Frecuentemente

```bash
# No esperes días para sincronizar
# Hazlo regularmente
git fetch origin
git pull origin main

# Esto evita conflictos grandes
```

---

## Recursos Adicionales

### Documentación Oficial

- [Git Official Documentation](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com)
- [Pro Git Book (Gratis)](https://git-scm.com/book)

### Visuales y Tutoriales

- [Learn Git Branching](https://learngitbranching.js.org/) - Juego interactivo
- [Git Visualization](https://git-school.github.io/visualizing-git/) - Simulador visual
- [GitHub Learning Lab](https://github.com/skills) - Tutoriales interactivos

### Herramientas Útiles

- **GitHub Desktop**: Interfaz gráfica (https://desktop.github.com/)
- **GitKraken**: Cliente Git avanzado
- **VS Code**: Editor con integración Git incorporada
- **Tower**: Cliente Git para Mac/Windows

### Comandos de Emergencia

```bash
# Ver qué cambios tienes sin guardar
git stash list
git stash  # Guardar cambios temporalmente
git stash pop  # Recuperar cambios

# Ver todo lo que pasó (incluso deletados)
git reflog

# Recuperar un commit deletado
git checkout hash-del-commit

# Ver cambios antes de commitear
git diff
git diff --staged

# Revertir a la versión anterior
git revert hash

# Ver quién cambió cada línea
git blame archivo.txt
```

---

## Checklist Final

Antes de considerar que has completado este bootcamp:

- [ ] Git está instalado y configurado
- [ ] Entiendes los conceptos básicos (commit, branch, merge)
- [ ] Has creado un repositorio en GitHub
- [ ] Has hecho push y pull exitosamente
- [ ] Completaste todos los 10 ejercicios
- [ ] Has resuelto un conflicto manualmente
- [ ] Entiendes cómo escribir buenos mensajes de commit
- [ ] Sabes cuándo usar ramas
- [ ] Comprendes el flujo de Pull Request
- [ ] Puedes ayudar a otros con Git

---

## Próximos Pasos

1. **Contribuye a Open Source**: Busca proyectos en GitHub y haz tu primer PR
2. **Aprende Más Comandos Avanzados**: `cherry-pick`, `squash`, `rebase interactivo`
3. **Automatización**: GitHub Actions para CI/CD
4. **Colaboración Real**: Trabaja en equipo y aprende de otros desarrolladores

---

## Preguntas Frecuentes (FAQ)

### P: Acidentalmente hice commit a la rama equivocada, ¿qué hago?

```bash
# No entremos en pánico
git log --oneline  # Ver el commit
git revert hash    # O vuelve a main
git checkout -b rama-correcta
git cherry-pick hash  # Trae el commit a la rama correcta
```

### P: Hice push de algo que no debería, ¿cómo lo arreglo?

```bash
# Si solo tú tienes cambios:
git reset HEAD~1        # Deshacer commit
git push --force-with-lease

# Si otros ya vieron el cambio:
git revert hash
git push
```

### P: ¿Cómo elimino un archivo del historial?

```bash
# Para archivos grandes o sensibles:
git rm --cached archivo.txt
echo "archivo.txt" >> .gitignore
git add .gitignore
git commit -m "Remover archivo sensible"

# Para eliminar completamente del historial (peligroso):
# Usa: git filter-branch (requiere cuidado)
```

### P: ¿Debo hacer commit de dependencias (node_modules)?

```bash
# ❌ NO
# Usa .gitignore
echo "node_modules/" >> .gitignore

# En su lugar, usa package.json
npm install  # Instala desde package.json

# ✅ Sí:
git commit package.json
git commit package-lock.json (si existe)
```

---

## ¡Felicidades!

Has completado el Bootcamp de Git y GitHub. Ahora eres capaz de:

✅ Inicializar y clonar repositorios
✅ Hacer commits con mensajes claros
✅ Crear y fusionar ramas
✅ Colaborar usando Pull Requests
✅ Resolver conflictos
✅ Mantener un historial limpio

**Recuerda:** La práctica hace al maestro. Sigue usando Git en tus proyectos y cada día te sentirás más cómodo.

¡Bienvenido a la comunidad de desarrolladores! 🎉

---

**Última actualización:** Marzo 2026
**Versión:** 1.0
**Autor:** GitHub Bootcamp Tutorial
