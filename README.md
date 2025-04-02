#  Registro Universitario

Este es un proyecto **CRUD** desarrollado en **Spring Boot**, que permite gestionar estudiantes, docentes y materias en una universidad. Se implementan operaciones básicas de **Crear, Leer, Actualizar y Eliminar** sobre los estudiantes utilizando **Java 21**, **Spring Boot**, **JPA** y **H2 Database**.

---

##  Funcionalidades Principales

Este sistema ofrece las siguientes funcionalidades:

-  **CRUD de Estudiantes**: Permite registrar, consultar, modificar y eliminar estudiantes.
-  **Gestor de Materias**: Consulta las materias disponibles en la universidad.
-  **Gestor de Docentes**: Manejo de profesores registrados en la institución.
-  **Uso de DTOs (Data Transfer Objects)** para mejorar la transferencia de datos.
-  **Patrones de diseño** como Service y Repository para una mejor organización del código.
-  **Persistencia con JPA y H2 Database**, permitiendo almacenar y recuperar información de manera eficiente.
-  **Pruebas de los endpoints** con herramientas como **Postman** y **cURL**.

---

##  Tecnologías Utilizadas

El proyecto está construido con las siguientes tecnologías:

-  **Java 21**: Lenguaje de programación principal.
-  **Spring Boot**: Framework para aplicaciones Java de alta productividad.
-  **Spring Data JPA**: Para la gestión de la persistencia de datos.
-  **Spring Web**: Para la creación de una API REST.
-  **H2 Database**: Base de datos en memoria utilizada para pruebas y desarrollo.
-  **Lombok**: Para reducir el código repetitivo en las clases Java.
-  **Maven**: Herramienta de gestión de dependencias y construcción del proyecto.

---

##  Estructura del Proyecto

El código está organizado de la siguiente manera:

```
registroUniversitario/
  src/
    main/
      java/
        com/
          example/
            universidad/
              controller/
                EstudianteController.java
              dto/
                DocenteDTO.java
                EstudianteDTO.java
                MateriaDTO.java
              model/
                Docente.java
                Estudiante.java
                Materia.java
                Persona.java
              repository/
                EstudianteRepository.java
              service/
                impl/
                  EstudianteServiceImpl.java
                IEstudianteService.java
      resources/
        application.properties
```

###  Explicación de los paquetes

- **controller/**: Contiene los controladores REST que manejan las solicitudes HTTP.
- **dto/**: Contiene los objetos de transferencia de datos (DTO) para manejar la información de manera estructurada.
- **model/**: Define las entidades del sistema (Estudiante, Docente, Materia, etc.).
- **repository/**: Interfaz para la interacción con la base de datos mediante JPA.
- **service/**: Contiene la lógica de negocio, separada en interfaces y sus implementaciones.
- **resources/**: Contiene la configuración del sistema, como `application.properties`.

---

##  Instalación y Ejecución

Para ejecutar el proyecto en tu entorno local, sigue estos pasos:

1. **Clonar el repositorio**:
   ```sh
   git clone https://github.com/tu_usuario/registroUniversitario.git
   cd registroUniversitario
   ```

2. **Compilar y ejecutar** el proyecto con Maven:
   ```sh
   mvn spring-boot:run
   ```

3. **Acceder a la API**:
   - La aplicación estará disponible en: `http://localhost:8080/api/estudiantes`

---

##  Endpoints Principales

###  Estudiantes

| Método | Endpoint | Descripción |
|--------|---------|-------------|
| **GET** | `/api/estudiantes` | Obtiene la lista de todos los estudiantes. |
| **GET** | `/api/estudiantes/{id}` | Obtiene los detalles de un estudiante específico. |
| **POST** | `/api/estudiantes` | Registra un nuevo estudiante en la base de datos. |
| **PUT** | `/api/estudiantes/{id}` | Actualiza la información de un estudiante. |
| **DELETE** | `/api/estudiantes/{id}` | Elimina un estudiante del sistema. |

Ejemplo de solicitud **GET** para obtener todos los estudiantes:
```http
GET /api/estudiantes
```

Ejemplo de solicitud **POST** para registrar un nuevo estudiante:
```json
{
  "nombre": "Juan",
  "apellido": "Pérez",
  "email": "juan@example.com",
  "numeroInscripcion": "S001"
}
```

---

##  Pruebas y Validación

Las pruebas se realizaron utilizando **Postman** y **cURL**.

###  Ejemplo de pruebas con cURL

 **Crear un estudiante**
```sh
curl -X POST "http://localhost:8080/api/estudiantes" \
     -H "Content-Type: application/json" \
     -d '{"nombre": "Juan", "apellido": "Pérez", "email": "juan@example.com", "numeroInscripcion": "S001"}'
```

 **Actualizar un estudiante**
```sh
curl -X PUT "http://localhost:8080/api/estudiantes/1" \
     -H "Content-Type: application/json" \
     -d '{"nombre": "Juan", "apellido": "Pérez", "email": "juan.perez@example.com", "numeroInscripcion": "S002"}'
```

 **Eliminar un estudiante**
```sh
curl -X DELETE "http://localhost:8080/api/estudiantes/1"
```

---

## Conclusión

Este proyecto proporciona una base sólida para la gestión de estudiantes en una universidad utilizando **Spring Boot**. Es fácil de extender para incluir más funcionalidades como autenticación, validaciones avanzadas y conexiones con bases de datos más robustas como **PostgreSQL** o **MySQL**.




