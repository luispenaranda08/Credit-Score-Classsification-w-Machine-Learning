# Guía de Git: Push y Pull desde la Terminal de VS Code

Esta guía te ayudará a realizar operaciones de `push` y `pull` usando la terminal integrada de Visual Studio Code.

## 📋 Prerequisitos

Antes de comenzar, asegúrate de tener:
- Visual Studio Code instalado
- Git instalado en tu sistema
- Un repositorio Git configurado
- Credenciales de GitHub configuradas

## 🔧 Abrir la Terminal en VS Code

1. **Método 1**: Presiona `` Ctrl + ` `` (tecla de acento grave)
2. **Método 2**: Ve a `Terminal` → `New Terminal` en el menú superior
3. **Método 3**: Presiona `Ctrl + Shift + P` y escribe "Terminal: Create New Terminal"

## 📤 Git Push - Subir Cambios al Repositorio Remoto

### Flujo Básico Completo

```bash
# 1. Verifica el estado de tus archivos
git status

# 2. Agrega los archivos modificados al staging area
git add .                    # Agrega todos los archivos
# O específicamente:
git add archivo.py          # Agrega un archivo específico
git add *.py                # Agrega todos los archivos .py

# 3. Crea un commit con un mensaje descriptivo
git commit -m "Descripción de los cambios realizados"

# 4. Sube los cambios al repositorio remoto
git push origin main        # Para la rama main
# O
git push origin nombre-rama # Para otra rama específica
```

### Ejemplo Práctico

```bash
# Supongamos que modificaste el archivo eda.ipynb
git status                                    # Ver qué archivos cambiaron
git add eda.ipynb                            # Agregar el archivo
git commit -m "Actualizar análisis exploratorio de datos"
git push origin main                         # Subir a GitHub
```

### Primer Push de una Rama Nueva

Si es la primera vez que subes una rama nueva:

```bash
git push -u origin nombre-rama
```

El flag `-u` establece la rama remota como upstream, así en futuros push solo necesitas escribir `git push`.

## 📥 Git Pull - Descargar Cambios del Repositorio Remoto

### Comando Básico

```bash
# Descargar y fusionar cambios de la rama actual
git pull origin main        # Para la rama main
# O
git pull origin nombre-rama # Para otra rama específica
```

### Flujo Recomendado Antes de Trabajar

```bash
# 1. Verifica en qué rama estás
git branch

# 2. Asegúrate de estar en la rama correcta
git checkout main           # O la rama que necesites

# 3. Descarga los últimos cambios
git pull origin main

# 4. Ahora puedes comenzar a trabajar con la versión más reciente
```

### Pull con Rebase (Alternativa)

Para mantener un historial más limpio:

```bash
git pull --rebase origin main
```

## 🔄 Flujo de Trabajo Completo Recomendado

### Comenzando el Día de Trabajo

```bash
# 1. Actualiza tu repositorio local
git pull origin main

# 2. Crea una nueva rama para tu trabajo (opcional pero recomendado)
git checkout -b feature/nueva-funcionalidad

# 3. Realiza tus cambios en los archivos...

# 4. Verifica qué cambios hiciste
git status
git diff                    # Ver cambios específicos

# 5. Agrega y commitea tus cambios
git add .
git commit -m "Implementar nueva funcionalidad X"

# 6. Sube tu rama al repositorio remoto
git push -u origin feature/nueva-funcionalidad
```

### Trabajando en una Rama Existente

```bash
# 1. Cambia a tu rama
git checkout mi-rama

# 2. Actualiza con los últimos cambios
git pull origin mi-rama

# 3. Realiza cambios...

# 4. Guarda los cambios
git add .
git commit -m "Mensaje descriptivo"

# 5. Sube los cambios
git push origin mi-rama
```

## ⚠️ Problemas Comunes y Soluciones

### 1. Error: "Updates were rejected"

**Problema**: Alguien más subió cambios antes que tú.

**Solución**:
```bash
# Primero descarga los cambios remotos
git pull origin main

# Resuelve conflictos si los hay (edita los archivos marcados)

# Luego intenta push de nuevo
git push origin main
```

### 2. Conflictos de Fusión (Merge Conflicts)

**Cuando ejecutas `git pull` y hay conflictos**:

```bash
# Git te mostrará los archivos en conflicto
# Edita cada archivo y busca las marcas:
# <<<<<<< HEAD
# Tu código
# =======
# Código del repositorio remoto
# >>>>>>> 

# Después de resolver los conflictos:
git add archivo-resuelto.py
git commit -m "Resolver conflictos de fusión"
git push origin main
```

### 3. Olvidaste Hacer Pull Antes de Trabajar

```bash
# Guarda tus cambios temporalmente
git stash

# Descarga los cambios remotos
git pull origin main

# Recupera tus cambios guardados
git stash pop

# Resuelve conflictos si los hay, luego:
git add .
git commit -m "Tus cambios"
git push origin main
```

### 4. Rechazar el último commit (antes de hacer push)

```bash
# Deshacer el último commit pero mantener los cambios
git reset --soft HEAD~1

# O deshacer el commit y los cambios
git reset --hard HEAD~1
```

## 📝 Comandos Útiles Adicionales

```bash
# Ver el historial de commits
git log --oneline

# Ver qué archivos cambiaron
git status

# Ver diferencias específicas
git diff archivo.py

# Ver ramas locales y remotas
git branch -a

# Cambiar entre ramas
git checkout nombre-rama

# Crear y cambiar a nueva rama
git checkout -b nueva-rama

# Ver la configuración actual
git config --list

# Ver el repositorio remoto configurado
git remote -v
```

## 🔑 Configuración de Credenciales

### Configurar nombre y email (solo una vez)

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

### Guardar credenciales para no ingresarlas cada vez

```bash
# En Windows
git config --global credential.helper wincred

# En Mac
git config --global credential.helper osxkeychain

# En Linux
git config --global credential.helper store
```

## 🎯 Mejores Prácticas

1. **Hacer Pull frecuentemente**: Antes de comenzar a trabajar cada día
2. **Commits pequeños y frecuentes**: Es mejor hacer varios commits pequeños que uno grande
3. **Mensajes de commit descriptivos**: Explica QUÉ y POR QUÉ hiciste el cambio
4. **Revisar antes de commitear**: Usa `git status` y `git diff` antes de hacer commit
5. **Trabajar en ramas**: Para funcionalidades nuevas, crea ramas separadas
6. **No hacer commit de archivos sensibles**: Usa `.gitignore` para excluir archivos

## 📚 Recursos Adicionales

- [Documentación oficial de Git](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

## 🆘 ¿Necesitas Ayuda?

Si encuentras problemas:
1. Lee el mensaje de error cuidadosamente
2. Usa `git status` para entender el estado actual
3. Busca el error en Google o Stack Overflow
4. Consulta con tu equipo o mentor

---

**Nota**: Esta guía está diseñada específicamente para usar con la terminal integrada de VS Code, pero los comandos funcionan en cualquier terminal.
