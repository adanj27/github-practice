# README: Proyecto Colaborativo

Este repositorio es un proyecto colaborativo con dos ramas principales: `main` y `dev`. Aquí tienes un paso a paso detallado para contribuir al proyecto.

## Clonar el Repositorio

```bash
git clone https://github.com/adanj27/github-practice.git
```

## Cambiarse a la rama `dev`

```bash
git checkout dev
```

## Crear y nombrar una rama usando gitflow
- Ejm:

```bash
git flow feature start nombre_de_tu_rama
```

## Trabajar en tu rama
- Realiza tus cambios y realiza commits siguiendo el formato de `Conventional Commits`.

### Subir tu Rama

```bash
git push origin nombre_de_tu_rama
```

## Crear un Pull Request

- Ve a la página del repositorio en GitHub.
- Selecciona la pestaña `Pull Requests`.
- Haz clic en `New Pull Request`.
- Asegúrate de que la rama base sea `dev` y la rama comparada sea la tuya.
- Completa la descripción y los detalles del Pull Request.
- Solicita la revisión de otros colaboradores.

## Esperar Aprobación

Espera a que otros revisen y aprueben tu Pull Request. Realiza ajustes según sea necesario.

## Hacer el Merge

Una vez aprobado, realiza el merge de tu rama a `dev`.

- Haz clic en el botón `Merge Pull Request`.
- Selecciona `Confirm Merge`.
- Tu código ahora está en la rama `dev`.