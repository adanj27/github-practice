# README: Guía práctica en GitFlow

## ¿Qué es GitFlow?

GitFlow es un modelo de ramificación para proyectos gestionados con Git que propone un flujo de trabajo estricto, estructurado, consistente y compatible con proyectos basadados en metodologías ágiles como el nuestro. 

### Ramas Principales:

**Main:** Representa la rama principal del proyecto y contiene el código en producción.

**Develop:** Es la rama base para la integración de nuevas características. Se considera una versión en desarrollo.


### Ramas de Funcionalidad:

**Feature:** Cada nueva característica se desarrolla en una rama separada de `feature`. Estas ramas se crean desde `develop` y se fusionan de nuevo en `develop` cuando la funcionalidad está completa.


### Ramas de Publicación:

**Release:** Cuando se está preparando una nueva versión para lanzamiento, se crea una rama `release` desde `develop`. Se pueden realizar correcciones de errores en esta rama y, una vez lista, se fusiona en `main` y `develop`, además de etiquetar la versión.


### Ramas de Corrección de Errores:

**Hotfix:** Se utilizan para corregir problemas críticos en producción. Se crean a partir de `main`, se aplican los cambios necesarios y luego se fusionan tanto en `main` como en `develop`.

> [!TIP]
> Más información en: https://www.atlassian.com/es/git/tutorials/comparing-workflows/gitflow-workflow


## ¿En qué consiste este repositorio?

Este repositorio es un ejercicio colaborativo que intenta simular un ambiente de trabajo real con GitFlow. En ese sentido, contiene las dos ramas principales: `main` y `dev`, y es labor de cada uno crear las otras ramas en lo que consideren necesario para practicar. El objetivo final es generar un pull request que cumpla con las condiciones y que será revisado para su aprobación.

## Pasos iniciales

### 1. Crear un Fork del repositorio original

### 2. Clonar su repositorio remoto en su máquina local 

```bash
git clone https://github.com/SU-NOMBRE-DE-USUARIO/github-practice.git
```

## Flujo de trabajo

### 1. Actualización de su repositorio local
La primera obligación antes de generar cualquier código es asegurarse de que cada rama de su repositorio local (main y dev) está actualizada con respecto al repositorio original.

La primera opción es hacerlo desde Github a través de Sync Fork, el cual mostrará el botón Update Branch cuando haya una actualización.

La segunda opción es a través de la línea de comandos:

```bash
# Agregar fuente de actualización (solo la primera vez)
git remote add upstream git@github.com:adanj27/github-practice.git
```
```bash
# Traer los últimos cambios del repositorio original
git fetch upstream
```
```bash
# Fusionar los últimos cambios de main en remoto con su rama main en local
git merge upstream/main
```
```bash
# Cambiar a la rama `dev`
git checkout dev
```
```bash
# Fusionar los últimos cambios de dev en remoto con su rama dev en local
git merge upstream/dev

```
### 2. Inicialización de GitFlow
```bash
git flow init
```
> [!TIP]
> Los comandos basados en GitFlow forman parte de una extensión que se instala automáticamente con las últimas versiones de Git y agilizan la labor a modo de atajos

### 3. Creación de una rama de trabajo

Para nuevas funcionalidades:

```bash
git flow feature start nombre_de_tu_rama
```
Para nuevas versiones:
```bash
git flow release start X.X.X
```
Para correción de errores:
```bash
git flow hotfix start nombre_de_tu_rama
```
### 4. Generación del commit
Una vez los cambios han sido realizados, generar el commit utilizando el formato de `Conventional Commits`. Si está utilzando Visual Studio Code, puede valerse de la extensión [VSCode Conventional Commits](https://marketplace.visualstudio.com/items?itemName=vivaxy.vscode-conventional-commits).

> [!TIP]
> Conventional Commits es una manera de estandarizar la escritura de los commits para todos los desarrolladores de un proyecto. Más información: https://www.conventionalcommits.org/en/v1.0.0/

### 5. Actualización de su repositorio remoto
```bash
git push origin nombre_de_tu_rama
```

### 6. Creación de un Pull Request
- Ir a la página de su repositorio remoto en GitHub.
- Seleccione la pestaña `Pull Requests`.
- Haga clic en `New Pull Request`.
- Asegúrese de que la rama base sea `dev` y la rama comparada sea la suya.
- Complete la descripción y los detalles del Pull Request.
- Solicite la revisión de otros colaboradores.

### 7. Finalización de la rama de trabajo
Solo una vez que el cambio ha sido aprobado, utilice este comando para traer lo realizado en su rama de trabajo a su rama `dev` (o `dev` y `main` si se trata de un `release` o un `hotfix`) y eliminarla. Al igual que en el repositorio original, al final solo debe haber una rama `main` y una `dev`. La rama de trabajo cumplió su objetivo y debe ser eliminada.

```bash
# Para ramas de funcionalidad
git flow feature finish feature_branch
```
```bash
# Para ramas de versionado
git flow release finish 'X.X.X'
```
```bash
# Para ramas de correción
git flow hotfix finish hotfix_branch
```