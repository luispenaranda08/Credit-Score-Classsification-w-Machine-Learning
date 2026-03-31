# Git Quick Reference - Referencia Rápida de Git

## 🚀 Comandos Esenciales / Essential Commands

### Push (Subir cambios)
```bash
git add .                           # Agregar todos los archivos
git commit -m "mensaje"             # Crear commit
git push origin main                # Subir a GitHub
```

### Pull (Descargar cambios)
```bash
git pull origin main                # Descargar y fusionar cambios
```

### Flujo Completo / Complete Workflow
```bash
git status                          # Ver estado
git add .                           # Agregar cambios
git commit -m "mensaje"             # Confirmar cambios
git push origin main                # Subir a repositorio remoto
```

## 🔄 Comandos Diarios / Daily Commands

```bash
git status                          # Estado actual
git pull origin main                # Actualizar antes de trabajar
git add archivo.py                  # Agregar archivo específico
git commit -m "mensaje"             # Commit con mensaje
git push origin rama                # Push a una rama
git log --oneline                   # Ver historial
```

## ⚠️ Soluciones Rápidas / Quick Fixes

### Olvidaste hacer pull / Forgot to pull
```bash
git stash                           # Guardar cambios temporalmente
git pull origin main                # Actualizar
git stash pop                       # Recuperar cambios
```

### Deshacer último commit / Undo last commit
```bash
git reset --soft HEAD~1             # Mantener cambios
```

### Ver diferencias / See differences
```bash
git diff                            # Ver cambios no agregados
git diff --staged                   # Ver cambios agregados
```

## 🌿 Ramas / Branches

```bash
git branch                          # Ver ramas locales
git checkout -b nueva-rama          # Crear y cambiar a rama
git checkout main                   # Cambiar a main
git merge otra-rama                 # Fusionar rama
```

## 🔧 Configuración Inicial / Initial Setup

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "email@ejemplo.com"
```

---

Para más detalles, consulta [GIT_TUTORIAL.md](./GIT_TUTORIAL.md)
