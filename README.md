# Backend para Sistema de Consorcio

Este proyecto es el backend para un sistema de consorcio, implementado en Go y utilizando el framework Gin para el servidor HTTP, con PostgreSQL como sistema de gestión de base de datos.

## Características

- **Login**: Autenticación de usuarios.
- **CRUD Proveedores**: Administración de proveedores.
- **CRUD Empleados**: Administración de empleados.
- **CRUD Propietarios**: Administración de propietarios.

## Tecnologías Utilizadas

- **[Go](https://golang.org/)**: Lenguaje de programación.
- **[Gin](https://github.com/gin-gonic/gin)**: Framework web.
- **[PostgreSQL](https://www.postgresql.org/)**: Sistema de gestión de base de datos.
- **[Docker](https://www.docker.com/)**: Plataforma de contenedores.
- **[golang-migrate](https://github.com/golang-migrate/migrate)**: Herramienta para migraciones de base de datos.

## Instalación

### Requisitos Previos

- Docker y Docker Compose
- Go (para desarrollo sin Docker)

### Con Docker

1. Clona el repositorio y navega al directorio del proyecto:
   
```bash
git clone <URL-del-repositorio>
cd <nombre-del-repositorio>
```
2. Levanta los servicios utilizando Docker Compose:

docker-compose up --build
Este comando construirá la imagen de tu aplicación y levantará todos los servicios necesarios, incluido PostgreSQL.

Instalación Local (sin Docker)
Asegúrate de tener Go instalado en tu máquina. Consulta la documentación oficial para la instalación.

Instala las dependencias del proyecto:

```bash
go mod tidy
```

Ejecuta el servidor:
```bash
go run main.go
```

## Correr Migraciones
Para mantener tu base de datos sincronizada y aplicar las migraciones necesarias, estamos utilizando golang-migrate. Asegúrate de tenerlo instalado y luego ejecuta:

```bash
migrate -path /migrations -database "postgresql://user:password@localhost:5432/mydb?sslmode=disable" up
```
Ajusta el comando con tus credenciales y la ubicación de tus archivos de migración.

## Framework: Gin
Este proyecto utiliza Gin, un framework web de alto rendimiento para Go que facilita la creación de APIs RESTful de manera rápida y sencilla.
