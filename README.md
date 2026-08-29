#  Sistema de Inventario — NovaTech Solutions
 
Proyecto integrador desarrollado como parte de la actividad **"Misión Git Flow"**, cuyo objetivo es demostrar dominio de **Git**, **GitHub**, **Git Flow**, gestión de **releases** y resolución de **conflictos**, simulando el rol de un equipo profesional de desarrollo de software.
 
---
 
##  Descripción del proyecto
 
NovaTech Solutions necesita un sistema de inventario para administrar productos. La aplicación permite gestionar el ciclo completo de un producto: creación, listado, edición y eliminación.
 
### Modelo de datos — Producto
 
| Campo     | Descripción                  |
|-----------|-------------------------------|
| ID        | Identificador único           |
| Nombre    | Nombre del producto           |
| Precio    | Precio unitario                |
| Categoría | Categoría del producto        |
| Stock     | Cantidad disponible           |
 
---
 
##  Estrategia de ramas (Git Flow)
 
Este proyecto sigue el modelo **Git Flow**, con las siguientes ramas obligatorias:
 
- **`main`** → Código en producción (estable, listo para desplegar).
- **`develop`** → Rama de integración de todas las funcionalidades.
- **`feature/*`** → Ramas para desarrollar funcionalidades individuales.
- **`release/1.0.0`** → Rama de preparación de la versión estable.
- **`hotfix/1.0.1`** → Rama para corrección urgente en producción.
```
feature/* → develop → release/1.0.0 → main → hotfix/1.0.1
```
 
**Flujo:** Desarrollo → Integración → Preparación → Producción → Corrección urgente
 
---
 
## ⚙️ Fase 1 — Configuración inicial del repositorio
 
```bash
git init
git config user.name "Nombre Estudiante"
git config user.email "correo@ejemplo.com"
 
git add .
git commit -m "chore: estructura inicial del proyecto"
git remote add origin URL_DEL_REPOSITORIO
git push -u origin main
```
 
---
 
## 🔧 Fase 2 — Inicialización de Git Flow
 
```bash
git flow init
```
 
Configuración utilizada:
 
```
Production releases: main
develop: develop
```
 
---
 
##  Fase 3 — Desarrollo por funcionalidades (features)
 
| Feature            | Descripción                     |
|---------------------|----------------------------------|
| `crear-producto`    | Alta de nuevos productos        |
| `listar-productos`  | Listado de productos existentes |
| `editar-producto`   | Edición de productos            |
| `eliminar-producto` | Eliminación de productos        |
 
Ejemplo de flujo para cada feature:
 
```bash
git flow feature start crear-producto
git add .
git commit -m "feat: agregar creación de productos"
git flow feature finish crear-producto
```
 
*(Se repite el mismo patrón para `listar-productos`, `editar-producto` y `eliminar-producto`.)*
 
---
 
##  Fase 4 — Release 1.0.0
 
```bash
git flow release start 1.0.0
git add .
git commit -m "docs: actualizar documentación de la versión 1.0.0"
git flow release finish 1.0.0
 
git push origin main
git push origin develop
git push origin --tags
```
 
---
 
##  Fase 5 — Hotfix 1.0.1
 
**Escenario:** después de publicar la versión 1.0.0, se detectó un error crítico en el cálculo del precio. Se corrigió sin detener el flujo de desarrollo normal.
 
```bash
git flow hotfix start 1.0.1
git add .
git commit -m "fix: corregir cálculo del precio"
git flow hotfix finish 1.0.1
 
git push origin main
git push origin develop
git push origin --tags
```
 
---
 
##  Fase 6 — Resolución de conflictos
 
Dos integrantes del equipo modificaron deliberadamente la misma sección del `README.md`, generando un conflicto al integrar los cambios. El conflicto fue analizado, resuelto manualmente y documentado.
 
```bash
git status
git add .
git commit -m "fix: resolver conflicto de integración"
```
 
**Proceso:** Conflicto → Analizar → Decidir → Resolver → `git add` → `commit`
 
---
 
##  Defensa técnica
 
Preguntas que el equipo debe estar preparado para responder:
 
1. ¿Por qué no se debe desarrollar directamente sobre `main`?
2. ¿Qué diferencia existe entre `main` y `develop`?
3. ¿Cuándo se utiliza una `feature`?
4. ¿Cuándo se utiliza `release`?
5. ¿Cuándo se utiliza `hotfix`?
6. ¿Qué es un conflicto de Git y por qué ocurre?
7. ¿Qué diferencia existe entre `merge` y `rebase`?
8. ¿Qué función cumple un tag como `v1.0.0`?
---
 
##  Evidencias entregadas
 
- [x] URL del repositorio de GitHub
- [x] Captura de las ramas `main` y `develop`
- [x] Captura de las ramas `feature`
- [x] Captura del release `v1.0.0`
- [x] Captura del hotfix `v1.0.1`
- [x] Historial de commits con mensajes claros
- [x] Evidencia del conflicto resuelto
- [x] README.md completo
- [x] Demostración funcional del sistema
- [x] Defensa técnica (5 minutos)
---
 
##  Equipo
 
| Nombre | Rol |
|--------|-----|
| Juan   | estudiante |
 
---
 
##  Regla de oro
 
> "No gana el equipo que escribe más código; gana el equipo que demuestra que sabe controlar profesionalmente el ciclo de vida del código."
 
