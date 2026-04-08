# Gestión de Personas – CRUD con Spring Data REST, Caché y Frontend

## Descripción

Este proyecto consiste en completar la aplicación desarrollada en clase utilizando Spring Boot y Spring Data REST. La aplicación implementa un CRUD completo de personas, un mecanismo de caché en el backend y una interfaz web desarrollada con ayuda de IA.

Además, se resolvió el problema de CORS que ocurre cuando el frontend intenta consumir la API desde otro origen durante el desarrollo.

---

# Objetivos

* Implementar un CRUD completo para la entidad `Person`.
* Exponer los datos mediante una API REST.
* Agregar caché para optimizar consultas.
* Generar un frontend que consuma la API.
* Resolver el error de CORS entre frontend y backend.

---

# Tecnologías Utilizadas

## Backend

* Java
* Spring Boot
* Spring Data REST
* Spring Cache
* ConcurrentMapCacheManager
* JPA / Hibernate

## Frontend

* HTML
* JavaScript
* Tailwind CSS
* Font Awesome

---

# Modelo de Datos

La aplicación trabaja con una entidad llamada `Person`.

Cada persona tiene:

* id
* firstName
* lastName

---

# CRUD Implementado

Se implementaron las operaciones completas del CRUD:

| Operación                    | Método HTTP | Endpoint     |
| ---------------------------- | ----------- | ------------ |
| Crear persona                | POST        | /people      |
| Consultar todas las personas | GET         | /people      |
| Consultar una persona        | GET         | /people/{id} |
| Actualizar persona           | PUT         | /people/{id} |
| Eliminar persona             | DELETE      | /people/{id} |

---

# Implementación de Caché

Para optimizar el rendimiento del backend se utilizó Spring Cache.

En la clase principal se habilitó el uso de caché y se definió el administrador de caché. Además, en el repositorio se aplicaron anotaciones que permiten guardar temporalmente los resultados de las consultas. Cuando se crea, actualiza o elimina una persona, la caché se limpia automáticamente. De esta forma, la siguiente consulta vuelve a traer los datos actualizados.

---

# Problema de CORS

Cuando el frontend intentó consumir la API desde otro origen, el navegador bloqueó la petición mostrando un error de CORS. Para resolverlo se creó la clase `CorsConfig`. Con esta configuración el backend permite peticiones desde cualquier origen durante el desarrollo.

---

# Frontend Generado con IA

Se utilizó Gemini para generar una interfaz web moderna para la gestión de personas.

La interfaz permite:

* Ver la lista de personas.
* Crear nuevas personas.
* Editar personas existentes.
* Eliminar personas.
* Mostrar la cantidad total de registros.

La comunicación con la API se realiza usando `fetch`.

La URL utilizada por el frontend es:

```javascript
const apiUrl = 'http://localhost:9090/people';
```

---

# Funcionamiento del Frontend

## Crear persona

Cuando el usuario llena el formulario y presiona “Guardar”, se envía una petición POST.

## Editar persona

Si se selecciona editar, se carga la información en el formulario y luego se envía una petición PUT.

## Eliminar persona

Al presionar el botón de eliminar se envía una petición DELETE.

## Listar personas

La función `loadPeople()` realiza una petición GET y actualiza la tabla.

---

# Cómo Ejecutar el Proyecto

## 1. Ejecutar el backend

Abrir el proyecto en IntelliJ IDEA y ejecutar:

```text
AccessingDataRestApplication
```

El backend quedará disponible en:

```text
http://localhost:9090
```

---

# Conclusiones

* Se logró implementar un CRUD completo utilizando Spring Data REST.
* La caché mejora el rendimiento al evitar consultas repetidas.
* El problema de CORS fue resuelto mediante configuración en el backend.
* La IA permitió generar rápidamente una interfaz funcional y moderna.
* La integración entre frontend y backend quedó completamente operativa.
