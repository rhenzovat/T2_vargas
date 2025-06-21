# Blockbuster Fake

Blockbuster Fake es una aplicación web desarrollada con Spring Boot, Thymeleaf y MySQL, que permite gestionar el alquiler de películas en línea. Ideal como proyecto educativo para comprender el desarrollo full-stack con Java.

## Características

- Gestión completa de clientes, películas y alquileres.
- Registro de nuevos alquileres y actualización de estado (Activo, Devuelto, Retrasado).
- Persistencia con Spring Data JPA y Hibernate.
- Interfaz moderna y responsiva con Thymeleaf, HTML5, CSS3 y FontAwesome.
- Uso de combos (dropdowns) para relaciones foráneas (cliente, película).
- Validaciones de campos y mensajes de error/success con @Valid y Bootstrap.

## Requisitos

- Java 17 o superior
- Maven 3.8+
- MySQL Server

## Instalación

1. Clona el repositorio:
   ```sh
   git clone https://github.com/tu-usuario/tu-repo.git
   cd tu-repo
   ```

2. Configura la base de datos MySQL:
   - Crea una base de datos llamada `BD_T2_VARGAS`.
   - Ajusta el usuario y contraseña en [`src/main/resources/application.properties`](src/main/resources/application.properties) si es necesario.

3. Compila y ejecuta la aplicación:
   ```sh
   ./mvnw spring-boot:run
   ```

4. Accede a la aplicación en [http://localhost:8080](http://localhost:8080)

## Tecnologías Utilizadas

| Tecnología      | Uso                            |
| --------------- | ------------------------------ |
| Spring Boot     | Backend y configuración        |
| Thymeleaf       | Motor de plantillas HTML       |
| Spring Data JPA | Persistencia con Hibernate     |
| MySQL           | Base de datos relacional       |
| Bootstrap 5     | Diseño responsivo (formulario) |
| Lombok          | Getters/Setters automáticos    |


## Entidades JPA

-Cliente: nombre y email obligatorios (@NotBlank).
-Pelicula: título obligatorio, stock entero.
-Alquiler: incluye fecha, cliente, total, y estado como enum.
-DetalleAlquiler: clave compuesta por alquiler y pelicula.

## Vistas Thymeleaf

-clientes.html: Lista y formulario de clientes.
-peliculas.html: Lista y formulario de películas.
-alquileres.html: Formulario con combos para seleccionar cliente y películas.
-detalles.html: Visualización del detalle de alquileres.
-Manejo de mensajes de validación y confirmación.

## Validaciones

-Campos obligatorios validados con @NotBlank y @NotNull.
-El campo fecha no es serializable (@JsonIgnore si se expone a API).
-El estado se representa como un enum.

## Estructura del Proyecto

```
src/
 └── main/
     ├── java/
     │    └── com.cibertec.blockbusterfake/
     │         ├── model/            # Entidades JPA
     │         ├── repository/       # Repositorios Spring Data
     │         ├── service/          # Servicios @Service
     │         ├── controller/       # Controladores @Controller
     │         └── BlockbusterFakeApplication.java
     └── resources/
          ├── templates/             # HTML Thymeleaf
          ├── static/                # CSS/JS/Img
          └── application.properties

```

## Configuración

La configuración principal se encuentra en [`src/main/resources/application.properties`](src/main/resources/application.properties).

## Licencia

Este proyecto es de uso educativo para la asignatura de Desarrollo Web en Cibertec. Puedes modificarlo libremente para uso personal o académico.

## AUTOR
RENZO VARGAS TENORIO
