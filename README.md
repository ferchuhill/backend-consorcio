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


## Posibles Datos:
1. Login
Para el sistema de Login, se necesitan datos que permitan la autenticación de los usuarios. Esto generalmente incluye:

Username o Email: Para identificar de manera única al usuario.
Contraseña: Debe ser almacenada de manera segura, preferentemente usando hash y sal para protegerla en caso de una violación de datos.
Roles o Permisos: Para controlar el acceso a diferentes partes del sistema según el rol del usuario (por ejemplo, administrador, propietario, empleado).

2. CRUD Proveedores
Para los proveedores que trabajan con el consorcio, los datos a gestionar pueden incluir:

ID del Proveedor: Identificador único para cada proveedor.
Nombre de la Empresa: El nombre oficial de la empresa proveedora.
CIF/NIF: Número de identificación fiscal de la empresa.
Dirección: Dirección postal de la empresa.
Teléfono de Contacto: Número(s) de teléfono para comunicarse con la empresa.
Email de Contacto: Dirección de correo electrónico para comunicarse con la empresa.
Servicios Ofrecidos: Descripción de los servicios que ofrece el proveedor.
Datos Bancarios: Para realizar pagos a los proveedores.


3. CRUD Empleados
Para los empleados del consorcio, los datos necesarios pueden incluir:

ID del Empleado: Identificador único para cada empleado.
Nombre Completo: El nombre y apellidos del empleado.
DNI: Número de identificación personal.
Unidad Funcional: Numero de identificacion funcional
Dirección: Dirección postal del empleado.
Teléfono de Contacto: Número de teléfono del empleado.
Email: Dirección de correo electrónico del empleado.
Cargo: Posición o rol dentro del consorcio.
Salario: Información sobre la compensación económica.
Fecha de Inicio: Cuando comenzó a trabajar en el consorcio.\


4. CRUD Propietarios
Para los propietarios de unidades dentro del consorcio, se requiere gestionar datos como:

ID del Propietario: Identificador único para cada propietario.
Nombre Completo: El nombre y apellidos del propietario.
DNI/NIF: Número de identificación personal.
Dirección del Apartamento/Unidad: Incluyendo el número de apartamento o unidad.
Teléfono de Contacto: Número de teléfono del propietario.
Email: Dirección de correo electrónico del propietario.
Datos Bancarios: Para gestionar pagos de cuotas o recibir pagos/reembolsos.
Consideraciones de Seguridad
Las contraseñas deben almacenarse de manera segura, utilizando técnicas de hash y sal.
Los datos bancarios y números de identificación personal (DNI/NIF, CIF) son datos sensibles y deben ser tratados de acuerdo con las normativas de protección de datos aplicables (como GDPR en Europa).
Implementar medidas de seguridad en la aplicación para proteger los datos de accesos no autorizados, incluyendo el uso de HTTPS, tokens de autenticación, y políticas de CORS adecuadas.
