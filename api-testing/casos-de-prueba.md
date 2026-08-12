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
