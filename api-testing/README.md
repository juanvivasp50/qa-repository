# Proyecto 2 - API Testing

Proyecto de testing manual sobre API de demostración, cubriendo los 4 métodos de HTTP (GET, POST, PUT y DELETE) para poder obtener la base de datos de usuarios, crear usuarios, modificar y eliminar utilizando Postman. 

---

## Aplicación bajo prueba

**reqres.in** API REST pública y gratuita en línea que sirve como un entorno de prueba para desarrolladores, permitiendo simular solicitudes HTTP (como GET, POST, PUT, DELETE) sin necesidad de configurar un servidor o un backend.

---

## Alcance

Se probaron las siguientes áreas:

| Requisito | Área |
|---|---|
| API-001 | GET - Lista de usuarios (page, per_page, total, total_pages, array data) |
| API-002 | POST - Creación de usuarios (datos enviados(name y job), id y createdAt) |
| API-003 | PUT - Modificar usuarios (datos enviados,(name y job) updatedAt) |
| API-004| DELETE - Eliminar usuarios |

**Fuera de alcance:** 

Autenticación y permisos, Rendimiento y Seguridad.

---

## Resultados

**4 casos de prueba** ejecutados (API-001 a API-004).

### Hallazgos destacados

**API-004 — El DELETE informa éxito pero no elimina el recurso**

La petición DELETE devuelve 204 No Content, código que indica eliminación correcta. Sin embargo, al consultar el mismo endpoint con GET, el usuario sigue existiendo y responde 200 OK con todos sus datos.

En un sistema real esto supone un riesgo grave: si un usuario ejerce su derecho de supresión y el sistema confirma el borrado sin ejecutarlo, la empresa está incumpliendo normativa de protección de datos además de engañar al usuario.

El hallazgo solo aparece si se verifica el estado real del recurso después de la operación, en lugar de confiar en el código de respuesta.

**POST sin validación de datos de entrada**

El endpoint de creación acepta cualquier contenido en los campos `name` y `job`: valores numéricos, símbolos o campos vacíos. Todos devuelven 201 Created.

En un sistema real, la ausencia de validación degrada la calidad de los datos: registros sin nombre imposibles de contactar, usuarios indistinguibles entre sí y problemas en cualquier proceso que dependa de esos campos.

---

## Estructura del repositorio

```
api-testing/
├── API-Testing.postman_collection.json    Colección de Postman con las 4 peticiones
├── casos-de-prueba.md                     Casos API-001 a API-004 documentados
└── README.md                              Este documento
```

**API Testing.postman_collection.json** — Colección exportada de Postman con las peticiones GET, POST, PUT y DELETE listas para ejecutar.
- **casos-de-prueba.md** — Cada caso documentado con ID, método, endpoint, datos enviados, resultado esperado, resultado actual y estado.

---

## Técnicas aplicadas

- Verificación de códigos de estado HTTP según el método utilizado
- Validación de la estructura y contenido de las respuestas JSON
- Comprobación de consistencia interna de los datos devueltos
- Verificación del estado real del recurso tras una operación, en lugar de confiar únicamente en el código de respuesta
- Pruebas con datos de entrada no válidos

---

## Entorno de pruebas

Postman · reqres.in · API key de acceso gratuito
