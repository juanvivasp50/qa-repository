# Casos de Prueba de API — reqres.in

---

## API-001 — Listar usuarios de la página 2

**Método:** GET  
**Endpoint:** `https://reqres.in/api/users?page=2`  
**Datos enviados:** N/A

**Resultado esperado**

Código de estado 200 OK. La respuesta contiene:
- `page` con valor 2
- `per_page` con valor 6
- El array `data` con 6 usuarios
- `total` (12) y `total_pages` (2) coherentes con `per_page` (6)

**Resultado actual**

Código de estado 200 OK. La respuesta contiene:
- `page` con valor 2
- `per_page` con valor 6
- El array `data` con 6 usuarios
- `total` (12) y `total_pages` (2) coherentes con `per_page` (6)

**Estado:** Pass

## API-002 — Crear usuario nuevo con POST

**Método:** POST  
**Endpoint:** `https://reqres.in/api/users`

**Datos enviados:**
```json
{
  "name": "Athar",
  "job": "Team Leader"
}
```

**Resultado esperado**

Código de estado 201 Created. La respuesta contiene:
- `name` con el valor enviado
- `job` con el valor enviado
- Un campo `id` generado por el servidor
- Un campo `createdAt` con la fecha de creación

**Resultado actual**

Código de estado 201 Created.
```json
{
  "name": "Athar",
  "job": "Team Leader",
  "id": "997",
  "createdAt": "2026-08-12T15:00:40.747Z"
}
```

**Estado:** Pass

## API-003 — Modificar usuarios con PUT

**Método:** PUT
**Endpoint:** `https://reqres.in/api/users/2`

**Datos enviados:**
```json
{
  "name": "Yahya",
  "job": "QA Engineer"
}
```

**Resultado esperado**

Código de estado 200 OK. La respuesta contiene:
- `name` con el valor enviado
- `job` con el valor enviado
- Un campo `updatedAt` con la fecha de actualización

**Resultado actual**

Código de estado 200 OK.
```json
{
  "name": "Yahya",
  "job": "QA Engineer",
  "updatedAt": "2026-08-12T15:06:59.953Z"
}
```

**Estado:** Pass

## API-004 — Eliminar base de usuarios con DELETE

**Método:** DELETE
**Endpoint:** `https://reqres.in/api/users/2`

**Datos enviados:**
N/A

**Resultado esperado**

Código de estado 204 No Content. Se elimina completamente la base de datos de los usuarios de la página 2, no muestra nada en pantalla. 

**Resultado actual**

Código de estado 204 No Content. Se elimina completamente la base de datos de los usuarios de la página 2, no muestra nada en pantalla. 

**Estado:** Pass
